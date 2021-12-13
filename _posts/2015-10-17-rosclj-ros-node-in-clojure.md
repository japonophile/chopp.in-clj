---
layout: post
title: "rosclj - ROS node in Clojure"
date: "2015-10-17"
type: post
published: true
status: publish
---

Playing with robots, and learning **[ROS](http://www.ros.org/)** (robot operating system), I was happy to find out about **[rosclj](http://wiki.ros.org/rosclj)**, Clojure bindings for ROS.  I would be able to control robots from the REPL; how nice!

However, I quickly discovered that the only thing remaining from rosclj is its documentation: the code (originally in a SVN repo of Berkeley) has disappeared.  But never mind.  Clojure can do Java interoperop, right?  So I gave it a shot, and it turned out pretty well, so I thought I'd publish my findings because there is not much up-to-date information out there.

I started by familiarising myself with **[rosjava](http://wiki.ros.org/rosjava?distro=indigo)** and create a pub-sub sample project following the [nice tutorial here](http://wiki.ros.org/rosjava_build_tools/Tutorials/indigo/WritingPublisherSubscriber%28Java%29).  But don't worry, you don't really need to fiddle out with catkin to get Clojure talk to a ROS node.  This is actually simpler.

 

**Your first ROS node in Clojure**

Here are the steps:

1\. Create a lein project (I called mine roscljtest), and add rosjava repository and dependencies to your project.clj.  Here is mine:

```clojure
(defproject roscljtest "0.1.0-SNAPSHOT"
  :description "FIXME: write description"
  :url "http://example.com/FIXME"
  :license {:name "Eclipse Public License"
            :url "http://www.eclipse.org/legal/epl-v10.html"}
  :dependencies [[org.clojure/clojure "1.7.0"]
                 [org.ros.rosjava_core/rosjava "0.2.1"]
                 [org.ros.rosjava_messages/geometry_msgs "1.11.7"]]
  :repositories [["rosjava" "https://raw.githubusercontent.com/rosjava/rosjava_mvn_repo/master"]]
  :aot :all)
```

2\. Write a ROS node in Clojure.  I simply translated the Listener from the rosjava tutorial to clojure:

```clojure
(ns roscljtest.core
  (:import [org.apache.commons.logging Log]
           [org.ros.message MessageListener]
           [org.ros.namespace GraphName]
           [org.ros.node AbstractNodeMain ConnectedNode NodeMain]
           [org.ros.node.topic Subscriber]))

(gen-class
  :name "roscljtest.core.CljListener"
  :extends org.ros.node.AbstractNodeMain
  :prefix "clist-")

(defn clist-getDefaultNodeName [this]
  (GraphName/of "rosjava/listener"))

(defn clist-onStart [this connectedNode]
  (let [log (.getLog connectedNode)]
    (doto (.newSubscriber connectedNode "chatter" std_msgs.String/_TYPE)
      (.addMessageListener
        (proxy [MessageListener] []
          (onNewMessage [msg]
            (.info log (str "I heard: \"" (.getData msg) "\""))))))))
```

3\. Build the Clojure code, and create a uberjar, which will be useful to avoid messing up with the classpath:

```bash
> lein uberjar
```

If everything goes well, the following jar file should be generated, and (notice the :aot :all in our project.clj) contain all .class files: roscljtest-0.1.0-SNAPSHOT-standalone.jar

4\. Start ROS core and the Talker from the Java tutorial (don't start the Listener, since we will start the one we just wrote in Clojure)

```bash
> roscore &
> cd src/rosjava_catkin_package_a/my_pub_sub_tutorial
> cd build/install/my_pub_sub_tutorial/bin
> ./my_pub_sub_tutorial com.github.rosjava.rosjava_catkin_package_a.my_pub_sub_tutorial.Talker &
```

5\. Finally, start the Clojure node, as follows:

```bash
> java -cp target/roscljtest-0.1.0-SNAPSHOT-standalone.jar org.ros.RosRun roscljtest.core.CljListener
```

Once the connection is established, you should see the following output flow, at a rate of about 1 message per second:

```
Oct 17, 2015 8:28:18 PM org.ros.internal.node.RosoutLogger info
INFO: I heard: "Hello world! 26"
Oct 17, 2015 8:28:19 PM org.ros.internal.node.RosoutLogger info
INFO: I heard: "Hello world! 27"
```

**Next Steps**

OK, this is great.  And the thing I like the most, is that we don't even need our project to be "catkinized": we can just use Leiningen as usual (provided we specify the correct repo in our project.clj).

I was actually even able to run the CljListener on a separate machine (provided I set `ROS_MASTER_URI` and `ROS_IP` correctly on both machines): I did not even have to install ROS on the machine running the CljListener!

Next step will be to make this a little more idiomatic Clojure, because extending Java classes and overriding methods is no fun.  And I want to be able to run commands from the REPL, which I haven't tried yet.

But all in all, this looks very promising.
