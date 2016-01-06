[![](https://badge.imagelayers.io/agileek/cpuset-test:latest.svg)](https://imagelayers.io/?images=agileek/cpuset-test:latest 'Get your own badge on imagelayers.io')


You can use this to experiment with the --cpu-share, --cpuset-cpus flags of docker run.
see here: http://agileek.github.io/docker/2014/08/06/docker-cpuset/ 

USAGE (depending on the number of cpus in your machine, numbers are from 0 to n):

    sudo docker run -it --rm --cpuset-cpus=0,1 agileek/cpuset-test
    sudo docker run -it --rm --cpuset-cpus=3 agileek/cpuset-test



**install sysstat for monitoring (if memstat not available)**

    $ sudo apt-get install sysstat

    $ memstat -P ALL 2 10
  
  
  
e.g. burn cpu's number 1 and 6

    $ docker run -ti --rm --cpuset-cpus=1,6 agileek/cpuset-test

    $ memstat -P ALL 2  #update every 2 seconds
```
13:56:32     CPU    %usr   %nice    %sys %iowait    %irq   %soft  %steal  %guest  %gnice   %idle
13:56:34     all   29.80    0.00    0.38    0.69    0.00    0.00    0.00    0.00    0.00   69.13
13:56:34       0   13.43    0.00    1.00    2.49    0.00    0.00    0.00    0.00    0.00   83.08
13:56:34       1  100.00    0.00    0.00    0.00    0.00    0.00    0.00    0.00    0.00    0.00
13:56:34       2    2.03    0.00    0.00    0.00    0.00    0.00    0.00    0.00    0.00   97.97
13:56:34       3   14.78    0.00    0.99    2.46    0.00    0.00    0.00    0.00    0.00   81.77
13:56:34       4    2.51    0.00    0.50    0.50    0.00    0.00    0.00    0.00    0.00   96.48
13:56:34       5    0.00    0.00    0.00    0.00    0.00    0.00    0.00    0.00    0.00  100.00
13:56:34       6  100.00    0.00    0.00    0.00    0.00    0.00    0.00    0.00    0.00    0.00
13:56:34       7    4.50    0.00    0.50    0.50    0.00    0.00    0.00    0.00    0.00   94.50
```
