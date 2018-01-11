# MAGENTO2 GULPFILE #

Based on Bitbull's Simple Gulpfile for Magento2 (https://github.com/bitbull-team/magento2-gulpfile).

Usage
-----

1. Place the gulpfile.js and the package.json in the root of your project.

2. Install the required modules:

        npm install /  yarn install  


3. Create a configuration file **dev/tools/gulp/themes.js** with the following contents.

        module.exports = {
        <Theme>: {
          "src": [
            "vendor/<Vendor>/<Theme-name>",
            "vendor/<Vendor>/<Module-name>"
            ],
          "dest": "pub/static/frontend/<Vendor>/<Theme-name>",
          "locale": [locale,locale],
          "lang": "less",
          "area": "frontend",
          "vendor": <Vendor>,
          "name": <Theme-name>,
          "files": [
            "css/styles-m",
            "css/styles-l"
           ]
         }
        };
        


src:  Array of theme and modules you want to compile in format "vendor/<Vendor>/<Module-name>"

dest: Path in pub/static of your theme

area: area, one of (frontend|adminhtml|doc),

name: theme name in format theme-name,

locale: array of language to compile,

files: Files to compile


Commands
--------
 
1. **Task watch**. Watches for less changes in vendor modules/themes and compile them in pub/static..       
        
        gulp watch --Theme-name
        
2. **Task clean**. Clean old assets and run deployments commands.    
        
        gulp clean --Theme-name

2. **Task clean cache**. Clean cache.   
        
        gulp clean-cache --Theme-name

Licence
-------
[OSL - Open Software Licence 3.0](http://opensource.org/licenses/osl-3.0.php)

Changelog
--------

- 3.1.0 Compile in different locales
- 3.0.0 Added build and clean tasks
- 2.0.0 Added sourcemaps
- 1.0.0 First release
