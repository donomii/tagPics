# tagPics
Use a neural net to identify pictures on your drive

## Automatically tag your pictures

This uses the inception 5h trained model to guess the subject of your pictures.

## Use


```
go get -u github.com/donomii/tagPics
go build github.com/donomii/tagPics
./labelPics myPic.jpg
```

![Image of tiger](DSD03565_02.jpg)

```
BEST MATCH: (79% likely) tiger
BEST MATCH: (16% likely) tiger cat
BEST MATCH: ( 2% likely) lynx
```
tagPics only processes one picture at a time.  If you have more, you can do something like this:

```bash
 #!/bin/bash
 for filename in *jpg  ; do
         explosion "$filename"
         tagPics  -dir imageClassifierModel -image "$filename" 2> /dev/null
         #read -n1 -r -p "Press space to continue..." key
 done
 ```
