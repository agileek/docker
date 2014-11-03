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
alias ionic="docker run -ti -p 8100:8100 -p 35729:35729 -v \$PWD:/myApp:rw agileek/ionic-framework ionic"
```

you can follow the tutorial exactly (except for the ios part...) as if ionic was installed on your computer.

```bash
ionic start myApp tabs
cd myApp
ionic serve
```
open http://localhost:8100 and everything works.

# Coming next
Support for android emulation
