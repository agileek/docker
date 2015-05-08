Simple image to run ionic framework

#Usage

```
docker run -ti -p 8100:8100 -p 35729:35729 agileek/ionic-framework
```
If you have your own ionic sources, you can launch it with:

```
docker run -ti -p 8100:8100 -p 35729:35729 -v /path/to/your/ionic-project/:/myApp:rw agileek/ionic-framework
```

## Automation
With this alias:

```
alias ionic="docker run -ti -p 8100:8100 -p 35729:35729 --privileged -v /dev/bus/usb:/dev/bus/usb -v \$PWD:/myApp:rw agileek/ionic-framework ionic"
```

> Due to a bug in ionic, if you want to use ionic serve, you have to use --net host option :

```
alias ionic="docker run -ti --net host --privileged -v /dev/bus/usb:/dev/bus/usb -v \$PWD:/myApp:rw agileek/ionic-framework ionic"
```

you can follow the [ionic tutorial](http://ionicframework.com/getting-started/) (except for the ios part...) without having to install ionic nor cordova nor nodejs on your computer.

```bash
ionic start myApp tabs
cd myApp
ionic serve
```
open http://localhost:8100 and everything works.

## Android tests
You can test on your android device, just make sure that debugging is enabled.

```bash
cd myApp
ionic platform add android
ionic build android
ionic run android
```

#FAQ
    * The application is not installed on my android device
        * Try `docker run -ti -p 8100:8100 -p 35729:35729 --privileged -v /dev/bus/usb:/dev/bus/usb -v \$PWD:/myApp:rw agileek/ionic-framework adb devices` your device should appear

# Coming next
Support for android emulation with X11 forwarding

```bash
ionic platform emulate android
```
