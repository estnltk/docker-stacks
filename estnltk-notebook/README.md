
This is a basic jupyter notebok docker image with estnltk installed in the python 3 kernel.

To run:

```

docker run -d -p 8888:8888 estnltk/estnltk-notebook
```
Then open your browser and navigate to `localhost:8888`


##for developers:
To build and upload to https://hub.docker.com/r/estnltk/
```
docker build -t estnltk/estnltk-notebook:latest .
docker push  estnltk/estnltk-notebook:latest
```
