# labelsPics
Use a neural net to identify pictures on your drive

## Automatically tag your pictures

This uses the inception 5h trained model to guess the subject of your pictures.

## Use


```
go get -u github.com/donomii/labelsPics
go build github.com/donomii/labelsPics
./labelPics myPic.jpg
```

labelPics only processes one picture at a time.  If you have more, you can do something like this:

```bash
 #!/bin/bash
 for filename in *jpg  ; do
         explosion "$filename"
         labelsPics  -dir imageClassifierModel -image "$filename" 2> /dev/null
         #read -n1 -r -p "Press space to continue..." key
 done
 ```
