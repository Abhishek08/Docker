
# DevOps Project Android CI CD Deploy build to S3 Bucket.

##### Below are the Steps for creating this project .

##### Installation of Android SDK on Ubuntu 18.04 and setup the configration 

```sh

1. sudo apt-get update

2. sudo apt install openjdk-8-jdk

3. sudo apt install android-sdk

4. sudo mkdir /usr/lib/android-sdk/cmdline-tools

5. cd /usr/lib/android-sdk/cmdline-tools

6. sudo  wget https://dl.google.com/android/repository/commandlinetools-linux-6609375_latest.zip

7. sudo unzip commandlinetools-linux-6609375_latest.zip 

8. sudo rm commandlinetools-linux-6609375_latest.zip  

9. rm commandlinetools-linux-6609375_latest.zip 

10. export ANDROID_HOME=/usr/lib/android-sdk/

11. export PATH=$PATH:$ANDROID_HOME/cmdline-tools/tools/bin

12. export PATH=$PATH:$ANDROID_HOME/platform-tools

13. sdkmanager --version

14. sdkmanager --list

15. sudo chmod 777 $ANDROID_HOME -R

16. yes | sdkmanager --licenses

17.  yes | sdkmanager "platform-tools" "platforms;android-29"

```

##### Install Jenkins on Same Server 

```sh 

1. wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -

2. sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'

3. sudo apt update

4. sudo apt install jenkins

5. sudo systemctl start jenkins 

6. Get the password sudo cat /var/lib/jenkins/secrets/initialAdminPassword

7. Install Suggested Plugins 


```


##### SetUp Java and Android Path 

```sh

1. Goto Manage Jenkins ->  Global Tool Configration 

2. Setup Java Path in Env, 

JAVA Default Location = /usr/lib/jvm/java-8-openjdk-amd64/

3. Click Save and Apply and Back button 

4. Click on Configration - in Env. Set the Android_SDK path  

ANDROID_HOME = /usr/lib/android-sdk/



```

##### Create S3 Bucket on Amazon and Create IM roles 

```sh
1. Goto AWS and Search S3 

2. Create new S3 bucket,

3. Search IM on AWS search 

4. In IM page click on the roles 

5. Create new Role and Select AWS Service and EC2 and Next.

6. Attach permissions policies- Select the AmazonS3FullAccess and Click Next. 

7. Add tags (optional) -  Provide the key and value

8. Review - Provide the role name and click on create role


```

##### Attach Role to EC2 

```sh

1. Goto Ec2 and Click on Running instance 

2. Select the Instance where Jenkins are installed and click Action (button) -> Instance Setting - > Attach and Replace IM roles.

3. Attach/Replace IAM Role - Select the Roles that you created from DropDown and click on Apply.


```

##### Install S3 publisher plugin on Jenkins 


```sh

1. Goto the Jenkins click on Manage Jenkins - > Manage Plugins 

1. Click on Available tab and Search S3 publisher plugin and Install without Restart.

2. After installtion Complete Click on Jenkins Icon from Left corner - > Manage Jenkins -> Configure System -> Amazon S3 profiles(at the bootom ) 

3. Fill the information Profile name- Provide any name here and Click on Use IAM Role	 Checkbox after Click on Apply and Save. 


```
