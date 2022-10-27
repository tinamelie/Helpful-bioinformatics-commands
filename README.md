# Helpful bioinformatics commands

Most of these will be built in utilities, but there will be the inclusion of some other programs like bioawk


>[Count instances of a character in a file](#count-instances-of-a-character-in-a-file)
>
>[Print the length of each sequence in a fasta file](print-the-length-of-each-sequence-in-a-fasta-file)

## Count instances of a character in a file
```
sed 's/./&\n/g' input.txt | sort | uniq -ic
```

## Print the length of each sequence in a fasta file
```
bioawk -c fastx '{ print $name, length($seq) }' inputsequences.fasta
```
## Remove sequences from multiline fasta based on header
```
cat input.fasta| awk '/>SEQUENCE_HEADER_HERE/ {getline; while(!/>/) {getline}} 1' > output.fasta
```

## Replace fasta headers with filename_#
```
for f in *.fasta; do awk '/^>/{print ">" FILENAME "_" (++i); next} 1' $f > ${f%}.names.fasta; done
```
