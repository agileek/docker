# Image to run Duplicity
## Usage

Have a look here: http://duplicity.nongnu.org/


## Examples
```
docker run --rm
  -v $PWD/.cache:/root/.cache/duplicity \
  -v $PWD/.gnupg:/root/.gnupg \
  -v /:/data:ro \
  agileek/duplicity:0.7.18.2 \
  --full-if-older-than=6M --allow-source-mismatch /data gs://my-bucket-name/some_dir
```
