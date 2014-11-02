Simple image to run ionic framework

#Usage
``` docker run -ti -p 8100:8100 -p 35729:35729 agileek/ionic-framework

If you have your own ionic sources, you can launch it with
``` docker run -ti -p 8100:8100 -p 35729:35729 -v /path/to/your/ionic-project/:/myApp:rw agileek/ionic-framework

# Coming next
Support for android emulation
