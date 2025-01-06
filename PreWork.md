1. Virtual Box, set up RAM, Storage, NAT network (Redhat Linux, Redhat x86(CentOS base on Redhat Linux))
2. Download CentOS 9 iso file: https://www.centos.org/download/
   choose the right iso file, base on the system architecture
3. Run virtual machine, Install CentOS
4. JDK package install:

Step 1: Update the system

Before start, it's always good practice to update your system:
```
sudo yum update -y
```
Step 2: Install OpenJDK 17

To install OpenJDK 17, you can use the yum package manager:
```
sudo yum install java-17-openjdk-devel -y
```
This will install OpenJDK 17 and the development tools (such as compilers and debuggers).

Step 3: Verify the Installation

After installation, you can verify the version of JDK installed using the following command:
```
java -version
```
You should see output similar to this:
```
openjdk version "17.0.x" 2021-09-14
OpenJDK Runtime Environment (build 17.0.x+xx)
OpenJDK 64-Bit Server VM (build 17.0.x+xx, mixed mode, sharing)
```
You can also verify the javac (Java compiler) version:
```
javac -version
```
Step 4: Set JAVA_HOME (optional but recommended)

To set the JAVA_HOME environment variable globally, you can add it to your profile file (/etc/profile or ~/.bash_profile).

Find the location of the JDK installation:
```
sudo update-alternatives --config java
```
This command will show you the installation paths for different versions of Java. Select the path for JDK 17.

Set JAVA_HOME:
```
sudo vi /etc/profile
```
Add the following line at the end of the file (replace <jdk_path> with the actual path, e.g., /usr/lib/jvm/java-17-openjdk):
```
export JAVA_HOME=/usr/lib/jvm/java-17-openjdk
export PATH=$JAVA_HOME/bin:$PATH
```
Reload the profile file:
```
source /etc/profile
```
You can verify that JAVA_HOME is set correctly by running:
```
echo $JAVA_HOME
```
It should display the path you set, for example:
```
/usr/lib/jvm/java-17-openjdk
```
