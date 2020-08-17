
# DevOps Project Android CI CD Deploy build to S3 Bucket.

##### Below are the Steps for creating this project .

##### Installation of Android SDK on Ubuntu 

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

18. 


```
