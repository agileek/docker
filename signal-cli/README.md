# Simple image to run signal-cli
## Usage

Have a look here: https://github.com/AsamK/signal-cli

The image expects that the signal config will be at /config

```
docker run -ti --rm -v $PWD/.config/signal:/config agileek/signal-cli:0.5.6 -u yournumber receive
```
