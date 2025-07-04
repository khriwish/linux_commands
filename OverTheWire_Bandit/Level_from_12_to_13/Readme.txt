first we create a temporary directory so we can work in:
run 'mktemp -d'
outcome: '/tmp/tmp.uvoKlW0Ss9'
then we 'cd /tmp/tmp.uvoKlW0Ss9'

then we copy data.txt from the home directory into our new temporary directory
run 'cp ~/data.txt /tmp/tmp.uvoKlW0Ss9'

okay since we that the file is "hexdump" so its (xxd) we use the command 'xxd -r data.txt > humanReadable' (the option -r is used to reverse the hexdump)

now we run 'file humanReadable' so we can know what type of compression is used\
outcome: humanReadable: gzip compressed data, was "data2.bin", last modified: Thu Apr 10 14:22:57 2025, max compression, from Unix, original size modulo 2^32 585
Thus its a gzip compression 

now we need to rename it since the file name is 'humanReadable' and gzip only works on files with '.gz' endings
so run 'mv humanReadable humanReadable.gz'

after renaming run 'gunzip humanReadable.gz'
outcome: "humanReadable: bzip2" so now the file type is compressed in 'bzip2' and file was renamed to 'humanReadable' again 

now we rename 'humanReadable' to 'humanReadable.bz2' to be able to decompress it
run 'mv humanReadable humanReadable.bz2'
then decompress 'bunzip2 humanReadable.bz2'

after decompressing we check the type of the file that we got
outcome: "humanReadable: gzip" now its decompressed again in a gzip so we need to rename is to humanReadable.gz
then we decompress it run 'gunzip humanReadable.gz'

after decompressing we check the file type and we can see that its now archived using (GNU)
outcome: "humanReadable: POSIX tar archive (GUN)" and we will use UNIX-style to do things
so now we can take see what are the archived files in humanReadable with the command 'tar --list --file= humanReadable'

then we extract the file(s) using the command 'tar xf humanReadable' since the (x) means extract and the (f) means use this file as the archive
outcome: we extract a file called "data5.bin" which we check its type 
outcome: "data5.bin: POSIX tar archive (GNU)" and its also the same as the one before so we extract again
outcome: we extract a file called "data6.txt" which we have to check its type

when we run 'file data6.bin' we get 'data6.bin: bzip2 compressed data, block size = 900k' which means that its compressed using "bzip2" and again we need to rename the file to end with .bz2 then see the contents in it.
so rename then run 'bunzip2 data6.bz2'
outcome: data6 now we check the file type which is again "data6: POSIX tar archive (GNU)" an archive so we see the contents then extract them
using the command 'tar xf data6'
outcome: data8.bin check its file type "data8.bin: gzip compressed data, was "data9.bin", last modified: Thu Apr 10 14:22:57 2025, max compression, from Unix, original size modulo 2^32 49" its compressed using gzip
so now we know that we need to rename it to end with .gz then decompress it
run ' gunzip data8.gz'
outcome: data8 now check the file type and its "data8: ASCII text"
since its human readable ASCII we run 'cat data8'

and then finally we are done :)
also don't forget to remove the tmp directory using 'rm -r directory_path';)