# Helpful-commands


>[Count instances of a character in a file](#count-instances-of-a-character-in-a-file)

## Count instances of a character in a file
```
sed 's/./&\n/g' file.txt | sort | uniq -ic
```
