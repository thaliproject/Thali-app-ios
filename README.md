#Thali

Thali project.

#### Creating this project from scratch
The instructions below should help you create this project from scratch. They are based 
on ~/Code being your root folder, so adjust things as needed. I'm including them here to
document the process for others. 

##### Prerequisites
* Xcode 6, or later
* Python 2.6 or 2.7
* GCC 4.2, or later
* GNU make 3.81, or later
* 'which' python module (sudo easy_install tools/which-1.1.0-py2.7.egg)  
* Coffee 

##### Install setuptools
Make sure you have [setuptools](https://pypi.python.org/pypi/setuptools) installed. The 
instructions on the site neglect to sudo the python, so the correct command line is:
```
~> curl https://bootstrap.pypa.io/ez_setup.py -o - | sudo python
~> sudo easy_install tools/which-1.1.0-py2.7.egg
```

##### Install latest Node.JS
Follow the instructions at [https://nodejs.org/](https://nodejs.org/). When you're done, you should see:
```
~>   node -v
v0.12.2
~>   npm -v
2.7.4
```
(Or later versions.)

##### Install Cordova
```
~> sudo npm install -g cordova
```

##### Clone JXcore
```
~/Code> git clone git@github.com:jxcore/jxcore.git
```
 
##### Build JXcore for iOS
This will take a very, very long time and is why coffee is a prerequisite. 
```
~/Code cd jxcore
~/Code/jxcore ./build_scripts/ios_compile.sh
```

##### Create your Cordova project
```
~/Code> cordova create Thali org.thaliproject.thali Thali
```

##### In Cordova project root, clone jxcore-cordova
```
~/Code> cd Thali
~/Code/Thali> git clone git@github.com:jxcore/jxcore-cordova.git
```

##### Place output from JXcore build into jxcore-cordova
```
~/Code/Thali> cp -a ~/Code/jxcore/out_ios/ios/bin ~/Code/Thali/jxcore-cordova/io.jxcore.node
```

##### Add jxcore-cordova plugin and iOS platform
```
~/Code/Thali> cordova plugin add jxcore-cordova/io.jxcore.node/
~/Code/Thali> cordova platform add ios
```
You can remove / re-add jxcore-cordova plugin and iOS platform using:
```
~/Code/Thali> cordova platform remove ios
~/Code/Thali> cordova plugin remove io.jxcore.node
~/Code/Thali> cordova plugin add jxcore-cordova/io.jxcore.node/
~/Code/Thali> cordova platform add ios
```

##### Build the Cordova project
```
~/Code/Thali: cordova build
```


License
-------
MIT

Feedback
--------
If you have any questions, suggestions, or contributions to Thali, please [email thali-talk@thaliproject.org](mailto:thali-talk@thaliproject.org).