The following are instructions for installing Apache Maven and Java 8 on an Amazon EC2 instance. These are required for the Amazon Neptune Signature Version 4 authentication samples.

Steps To Install Apache Maven and Java 8 on your EC2 instance
Connect to your Amazon EC2 instance with an SSH client.

Install Apache Maven on your EC2 instance. First, enter the following to add a repository with a Maven package.

sudo wget https://repos.fedorapeople.org/repos/dchen/apache-maven/epel-apache-maven.repo -O /etc/yum.repos.d/epel-apache-maven.repo

Enter the following to set the version number for the packages.

sudo sed -i s/\$releasever/6/g /etc/yum.repos.d/epel-apache-maven.repo

Then you can use yum to install Maven.

sudo yum install -y apache-maven

The Gremlin libraries require Java 8. Enter the following to install Java 8 on your EC2 instance.

sudo yum install java-1.8.0-devel

Enter the following to set Java 8 as the default runtime on your EC2 instance.

sudo /usr/sbin/alternatives --config java

When prompted, enter the number for Java 8.
Enter the following to set Java 8 as the default compiler on your EC2 instance.

sudo /usr/sbin/alternatives --config javac

When prompted, enter the number for Java 8.
Verify your maven version mvn -v
Project Preparation
Create the .m2 directory in the home directory of your current user mkdir ~/.m2

Create the Settings file inside of the ~/.m2 directory cd ~/.m2/ mv demo/settings.xml ~/.m2/
