### YAS3FS Console

This is web console to easy monitor the nodes of a YAS3FS cluster, i.e. nodes that are listening to the same SNS topic.

YAS3FS (Yet Another S3-backed File System) is a [Filesystem in Userspace (FUSE)](http://fuse.sourceforge.net)
interface to [Amazon S3](http://aws.amazon.com/s3/).
It was inspired by [s3fs](http://code.google.com/p/s3fs/) but rewritten from scratch to implement
a distributed cache synchronized by [Amazon SNS](http://aws.amazon.com/sns/) notifications.

**If you use YAS3FS please share your experience on the [wiki](https://github.com/danilop/yas3fs/wiki), thanks!**

For more informations please look at the [YAS3FS](https://github.com/danilop/yas3fs) project.

* AWS credentials can be passed using AWS\_ACCESS\_KEY\_ID and AWS\_SECRET\_ACCESS\_KEY environment variables.
* The AWS_DEFAULT_REGION environment variable must point to a valid AWS region (e.g. eu-west-1)
* In an [EC2](http://aws.amazon.com/ec2/) instance a [IAM](http://aws.amazon.com/iam/) role can be used to give access to SNS/SQS resources.

The web console is based on [Node.js](http://nodejs.org), you can run it with:

    git clone git://github.com/danilop/yas3fs.git
    cd yas3fs/yas3fs-console
    npm install
    node server.js

It is using port 3000 by default (e.g. "http://localhost:3000"), but you can change it using the PORT environment variable, e.g.:

    export PORT=8080
    node yas3fs-console/server.js

Here’s a sample screenshot of the web interface:

![YAS3FS Console screenshot](http://blog.danilopoccia.net/wp-content/uploads/sites/2/2013/06/yas3fs-console.png)

The list of nodes and the attributes are updated dynamically depending on the configuration parameters.

In the future I’d like to add management capabilities as well into the console, such as “cache reset on a node”, or alarms, such as “disk cache is running out of space”.

Happy File Sharing!


