Mount drive:

```
sudo mount /dev/sdb2 /home/jean/Data/
```

Converts line breaks in a text file from DOS format (carriage return + Line feed) to Unix format (Line feed):

```
for file in $(find . -name *.sql -type f)
do
  dos2unix -r "$file"
done
```

Converts files encodings from UTF16LE to UTF-8:

```
for file in $(find . -name *.sql -type f)
do
  iconv -f UTF16LE -t UTF-8 -o "$file.new" "$file" && mv -f "$file.new" "$file"
done
```

Lists files of a folder sorting by size:

```
sudo du -a -h / | sort -n -r | head -n 20
```

Test if bucket is public:

```
https://buckets.grayhatwarfare.com/
```

Recuperar branch apagado:

```
https://ldiasrs.wordpress.com/2014/08/27/git-recuperando-branch-removidoapagado/
```
