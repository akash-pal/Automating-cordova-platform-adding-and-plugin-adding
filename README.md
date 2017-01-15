# Automating-cordova-platform-adding-and-plugin-adding
Automating the process of adding a Cordova platform and plugins

<b><u>Standard process of creating a cordova project and adding plugins:</u></b>
1. cordova create SampleApp com.example.sampleapp SampleApp
2. cd SampleApp
3. cordova platfrom add android
4. cordova platfrom add ios
5. cordova plugin add cordova-plugin-camera
6. cordova plugin add cordova-plugin-device
<!--Add other plugins-->
7. cordova run android
8. cordova run ios

<b><u>The Problem</u></b>
Mainatining and managaing all the plugins is a cumberson process.
When the plugins are added a specific version of the plugin is added.
If the plugins have to be modified or the project has to be updated then it becomes very difficult.

<b><u>The Solution</u></b>
All the plugins and platforms are mentioned in a file - package.json

<i>The key "platforms" has an array of platforms as value</i>

    "platforms": [
        "android",
        "ios"  
      ]

The above snippet will add the latest cordova android platform version.

The version of platform can also be specificed as below:

    "platforms": [
        "android@4.1.1",
        "ios"  
      ]
The above snippet will add cordova android platform version 4.1.1

<i>The key "plugins" has an array of plugins as value</i>

    "plugins": [
       "http://github.com/don/cordova-filechooser.git",
       "cordova-plugin-camera",
       "cordova-plugin-device",
       "cordova-plugin-dialogs",
       "cordova-plugin-fcm",
       "cordova-plugin-file",
       "cordova-plugin-file-transfer",
       "cordova-plugin-image-picker",
       "cordova-plugin-inappbrowser",
       "cordova-plugin-network-information",
       "cordova-plugin-spinner-dialog",
       "cordova-plugin-splashscreen"
      ]
      
 The above snippet adds the latest version of each respective plugin.
 
 A specific version of a plugin can be added as specified below:
     
     "plugins": [
         "cordova-plugin-camera@2.3.0",
     ]
    
 <b> Automating the process <b>
 
 1. Platform automation
 
  The platform installation script platforms.js under tasks directory adds each platform
 
  For running the platform script, type: 
 
  node tasks/platfroms.js (This command will add all the platforms mentioned)
  node tasks/platfroms.js remove (This command will remove all the platforms mentioned)

 2. Plugin automation
 
  The plugin installation script plugins.js under tasks directory adds each plugin
 
  For running the plugin script, type: 
 
  node tasks/plugins.js (This command will add all the plugins mentioned)
  node tasks/plugins.js remove (This command will remove all the plugins mentioned)
  
  Note: Place the package.json and tasks folder under the root directory
        This will be same for both ionic and cordova based hybrid projects.  
  

