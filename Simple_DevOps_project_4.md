
# DevOps Project Android CI CD Deploy build to App Center

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


##### SetUp Java and Android Path 

```sh

1. Goto Manage Jenkins ->  Global Tool Configration 

2. Setup Java Path in Env, 

JAVA Default Location = /usr/lib/jvm/java-8-openjdk-amd64/

3. Click Save and Apply and Back button 

4. Click on Configration - in Env. Set the Android_SDK path  

ANDROID_HOME = /usr/lib/android-sdk/


```


##### Setup Path in Jenkins


```sh


JAVA Default Location = /usr/lib/jvm/java-8-openjdk-amd64/

3. Click Save and Apply and Back button 

4. Click on Configration - in Env. Set the Android_SDK path  

ANDROID_HOME = /usr/lib/android-sdk/


```

##### SetUp AppCenter Account 

```sh

1. Create the account in AppCenter 

2. Copy the API Key from -> Account Setting  -> User API token -> Click on New API -> Provide the name and Allow all the access and copy the token

3. Goto Dashboard -> Click on Add New - >

                    1. Click on Add New App
                    2. Provide the App Name.
                    3. Release Type 
                    5. OS type 
                    6. Platform 
4. After Creating App 
          1. Click on Distribution 
          2. Click on Group 
          3. Create the New Group

5. Copy the User name from ->  Account Setting 

```

##### Post Build setting to App Center 

```sh

1. Provide the API token 
2. Provide the App Name 
3. Provide the APK path 
4. Provide the Group Name 
```
