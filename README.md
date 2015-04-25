# JAST Stack

**PLEASE NOTE:** the project structure has changed. Read below and only upgrade old projects with great caution.

JAST is a boilerplate with a  mash of tools for rapid Alloy development. Let's be opinionated then. The stack includes:

 * [Alloy](http://projects.appcelerator.com/alloy/docs/Alloy-bootstrap/index.html) -
   Appcelerator's own MVC Framework
 * [Babel](https://babeljs.io/) - to give us some ES6 support.
 * [Jade](http://jade-lang.com/) - the [best](http://www.yydigital.com/blog/2013/7/10/A_Case_For_Jade_With_Alloy) template
   engine for alloy views
 * [STSS](https://github.com/RonaldTreur/STSS) - Sassy TSS, or Sassy Titanium Style Sheets.
 * [TiShadow](http://tishadow.yydigital.com/) - the fastest __Open Source__ toolset
   for titanium development.

And these libraries:
 * [nano](https://github.com/dbankier/nano) - for simple data-binding.
 * [XHR](https://github.com/raulriera/XHR) - a new XHR wrapper.

And these widgets:
 * [nl.fokkezb.loading](https://github.com/FokkeZB/nl.fokkezb.loading) - simple loading widget
 * yy.alert - yet another alert widget.



~~See the following (outdated) [demo](http://www.youtube.com/watch?v=c1u92zT-oA4) - it uses LTSS instead of STSS but you'll get the idea.~~

If you would like coffee with that see [grunt-titanium-tishadow](https://github.com/xissy/grunt-titanium-tishadow).

# Prerequisites

 * [Get started](http://tishadow.yydigital.com/getting%20started) with TiShadow

# Let's Go

## Configuration

The configuration is in `.devices.json`. However, you should copy this file to `devices.YOURUSERNAME.json` (get your username by running `whoami` in your terminal). That way you can have a configuration file which is unique to your computer and doesn't creates conflicts when working with version control systems.

You **must** modify the `devices.YOURUSERNAME.json` values to suit your environment. The `ti info` command can help to get the correct ios simulator device id.

Feel free to add multiple platforms as:

```
{
  "iphone5": ["-p","ios","-T", "simulator", "--device-id","11146D86-F1A5-468C-9D0E-8231FF0F6B72"],
  "iphone6": ["-p","ios","-T", "simulator", "--device-id","1DF27F5C-3960-4901-A000-DCFCFBDC96BE"],
  "ipad2": ["-p","ios","-T", "simulator", "--device-id","0437C66A-24A2-4654-84EF-6A94ED12C908"],
  "android": ["-p","android", "-T","device"],
  "default": ["-p","ios"]
}
```

You can optionally modify `Project Specific Definitions` section in the `Gruntfile.js`

## Manually

 * `git clone https://github.com/dbankier/JAST.git`
 * `[sudo] npm install alloy tishadow`
 * `cd JAST && [sudo] npm install`
 * `grunt dev -p ios`

**Note**: the `grunt dev` command will start the tishadow server and launch a tishadow appified version of your app.
All code changes will be selectively precompiled and pushed (live-reload).

## Manual Install with Extras :+1:

If you want to:
 * use the `{{ }}` syntax in nano.
 * use selective alloy compilation for super fast live reloads.

You will need to install alloy from master and at least v.2.8.0 of tishadow - follow these steps.

 * `git clone https://github.com/dbankier/JAST.git`
 * `[sudo] npm install -g git://github.com/appcelerator/alloy.git`
 * `[sudo] npm install -g tishadow`
 * `tishadow config --boost`
 * `cd JAST && [sudo] npm install`
 * `grunt dev -p ios`

## Use the [Yeoman](http://yeoman.io) generator: [generator-alloy](https://github.com/dbankier/generator-alloy)

** NEEDS UPDATING - OUTDATED**
``` 
 npm install -g yo generator-alloy
 mkdir /path/to/new/app && cd $_
 yo alloy 
```


If you want to use 

# Structure

Make **ALL** changes in the `src` directory.
The **ENTIRE** `app` directory will be cleaned on `grunt clean`.

# Commands

 * `grunt` - compiles the jade, stss and es6 files and copies all the assets from `src` to `app`
 * `grunt dev [-p <platform>]` - auto compile and pushes with TiShadow (`p` flag is optional)
 * `grunt test [-p <platform>]` - run specs  (`p` flag is optional)
 * `grunt clean` - deletes all generated files
 * `grunt [iphone6|iphone7|ipad6|ipad7|appstore|adhoc|playstore]` - commands inspired by the work
    of @FokkeZB on [TiNy](https://github.com/FokkeZB/tn). Project specific settings are configured at
    the top of the `Gruntfile.js`.



License: MIT
