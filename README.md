#Thali

Thali project.
#### Building this project for iOS
The instructions below are based on ~/Code being your root folder. Adjust as needed.
##### Install latest Node.JS
Follow the instructions at [https://nodejs.org/](https://nodejs.org/)
##### Install Cordova
```
~> sudo npm install -g cordova
```
##### Clone JXcore
```
~Code> git clone https://github.com/jxcore/jxcore.git
```
or
```
git clone git@github.com:jxcore/jxcore.git
```
 
##### Build JXcore for iOS
```
~/Code cd jxcore
~/Code/jxcore ./build_scripts/ios_compile.sh
```

##### Install latest Node.JS
https://nodejs.org/

Install Cordova
sudo npm install -g cordova

Create Cordova project
cordova create Thali org.thaliproject.thali Thali

In Cordova project root, clone jxcore-cordova
~/Code/Thali: git clone git@github.com:jxcore/jxcore-cordova.git

Place output from JXcore build
cp -a ~/Code/jxcore/out_ios/ios/bin ~/Code/Thali/jxcore-cordova/io.jxcore.node

Add jxcore-cordova plugin and iOS platform
cordova platform remove ios
cordova plugin remove io.jxcore.node
cordova plugin add jxcore-cordova/io.jxcore.node/
cordova platform add ios

Build the Cordova project
~/Code/Thali: cordova build


License
-------
MIT

Feedback
--------
If you have any questions, suggestions, or contributions to Thali, please [email thali-talk@thaliproject.org](mailto:thali-talk@thaliproject.org).