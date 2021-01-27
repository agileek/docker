# Docker container for plantuml

## Based on outdated https://github.com/lindt/docker_plantuml
## Usage

The image expects that the signal config will be at /config

```
cat test.uml | docker run --rm -i agileek/plantuml:1.2021.0 > test.svg
```
