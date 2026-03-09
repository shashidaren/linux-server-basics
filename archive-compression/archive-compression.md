# Linux Archive and Compression

Archiving and compression tools are used to package multiple files into a single file and reduce storage space.

Common tools include:

tar  
gzip  
bzip2  
zip  

---

## Create Archive with tar

Create archive:

tar -cvf archive.tar files/

Example:

tar -cvf backup.tar /home/shashi

Options:

c → create archive  
v → verbose output  
f → specify filename  

---

## Extract tar Archive

Extract archive:

tar -xvf archive.tar

Extract to specific directory:

tar -xvf archive.tar -C /tmp

---

## Create Compressed Archive (gzip)

Create compressed archive:

tar -czvf archive.tar.gz directory/

Example:

tar -czvf backup.tar.gz /home/shashi

Options:

z → gzip compression

---

## Extract gzip Archive

tar -xzvf archive.tar.gz

---

## Create bzip2 Archive

tar -cjvf archive.tar.bz2 directory/

---

## Extract bzip2 Archive

tar -xjvf archive.tar.bz2

---

## Compress File with gzip

gzip file.txt

Result:

file.txt.gz

---

## Decompress gzip File

gunzip file.txt.gz

---

## Compress with bzip2

bzip2 file.txt

---

## Decompress bzip2 File

bunzip2 file.txt.bz2

---

## Create zip Archive

zip archive.zip file1 file2

Example:

zip backup.zip file1.txt file2.txt

---

## Extract zip Archive

unzip archive.zip

---

## View Archive Contents

tar -tvf archive.tar

---

## Backup Example

Create backup of /etc directory:

tar -czvf etc-backup.tar.gz /etc

---

## Troubleshooting

Check archive file:

file archive.tar.gz

Check archive contents:

tar -tvf archive.tar.gz

