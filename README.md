# google-datastore-clojure-docker-image

This is a quick little demo of getting [gcloud](http://googlecloudplatform.github.io/gcloud-java/0.2.6/index.html) working in Clojure. 

The issue is that Clojure makes heavy use of reflection. The gcloud library makes heavy use of the builder pattern. Although the builder pattern serves some purpose in Java, in a highly reflective language like Clojure it can cause problems due to a [bug in Java](http://bugs.java.com/bugdatabase/view_bug.do?bug_id=4283544) that has existed for 15+ years. I wouldn't hold my breath that it is going to be fixed anytime soon. :)

The work around is to build the objects you need in java, compile them using javac, and then import them into Clojure. Super super lame, but there it is.

Additional Refs:
http://stackoverflow.com/questions/38059977/cant-call-public-method-of-non-public-class-public-google-gcloud-library
