# Unix-commands

du command :
du /directory name - print all the folders 
du -h /directory name - print all the size in human readbale format.
du -sh /directory name - total disk space usage of the directoy
du -a /directory name - displays the disk usage of all files and subdirectories.
du -ah /directoy name - displays the disk usage in human readable format.
du -k /directory name - displays the size in kilobytes
du -mh /directory name - displays the size in MB
du -ch /directory name - displays the size at the end of last line
du -ah --exclude ='*.txt' directory name
du -ha --time - display based on time.

Grep command :
to get the count of matching lines :
[u965713@svcawabd][/var/stage/inbound] > grep -c 'MS' lob.dat
1
to get only the matching lines :
[u965713@svcawabd][/var/stage/inbound] > grep -h 'MS' lob.dat
line of business▒MS▒MedSup▒01/01/1970▒12/31/2999
to get the data ignoring case match
[u965713@svcawabd][/var/stage/inbound] > grep -i 'ms' lob.dat
line of business▒MS▒MedSup▒01/01/1970▒12/31/2999

[u965713@svcawabd][/var/stage/inbound] > grep -h 'ms' lob.dat
to get the file name alone"
[u965713@svcawabd][/var/stage/inbound] > grep -l 'MS' lob.dat
lob.dat
the get the line number info:
[u965713@svcawabd][/var/stage/inbound] > grep -n 'MS' lob.dat
1:line of business▒MS▒MedSup▒01/01/1970▒12/31/2999

[u965713@svcawabd][/var/stage/inbound] > grep -n 'MED*' lob.dat
3:line of business▒ME▒MedHMO▒01/01/1970▒12/31/2999
6:line of business▒EH▒MEDEXHHMO▒01/01/1970▒12/31/2999
Not to get the matching lines :
[u965713@svcawabd][/var/stage/inbound] > grep -v 'MS' lob.dat
line of business▒MO▒MedPPO▒01/01/1970▒12/31/2999
line of business▒ME▒MedHMO▒01/01/1970▒12/31/2999
line of business▒PD▒MedRx▒01/01/1970▒12/31/2999
line of business▒MU▒MedSupOl▒01/01/1970▒12/31/2999
line of business▒EH▒MEDEXHHMO▒01/01/1970▒12/31/2999
[u965713@svcawabd][/var/stage/inbound] > grep -v 'MS' -v 'MedPPO' lob.dat
grep: can't open -v
grep: can't open MedPPO
lob.dat:line of business▒MO▒MedPPO▒01/01/1970▒12/31/2999
lob.dat:line of business▒ME▒MedHMO▒01/01/1970▒12/31/2999
lob.dat:line of business▒PD▒MedRx▒01/01/1970▒12/31/2999
lob.dat:line of business▒MU▒MedSupOl▒01/01/1970▒12/31/2999
lob.dat:line of business▒EH▒MEDEXHHMO▒01/01/1970▒12/31/2999
[u965713@svcawabd][/var/stage/inbound] > grep -v 'MS' | grep -v 'MedPPO' lob.dat
line of business▒MS▒MedSup▒01/01/1970▒12/31/2999
line of business▒ME▒MedHMO▒01/01/1970▒12/31/2999
line of business▒PD▒MedRx▒01/01/1970▒12/31/2999
line of business▒MU▒MedSupOl▒01/01/1970▒12/31/2999
line of business▒EH▒MEDEXHHMO▒01/01/1970▒12/31/2999

grep -e 'MS' -e 'MO' -e 'ME' -e 'PD' lob.dat - to filter multiple data

 grep -f lob.dat lob.dat
 
 
 Sed command :
 replace the line, print the lines with range, Print the lines with matching patterns, Delete the lines.
 
 sed 's/Welcome/wel/' sedcommand.txt
 sed 's/wel/Welcome/2' sedcommand.txt
 sed 's/Welcome/wel/g' sedcommand.txt
 sed 's/Welcome/wel/3g' sedcommand.txt
  sed 's/\(\b[A-Z]\)/\(\1\)/g' sedcommand.txt
  sed 's/Welcome/wel/p' sedcommand.txt
  sed -n 's/Welcome/wel/p' sedcommand.txt
   sed 'p' sedcommand.txt
   sed 'nd' sedcommand.txt
   sed '$d' sedcommand.txt
   sed 'n,$d' sedcommand.txt
   sed '/abc/d' sedcommand.txt
   sed 'x,yd' sedcommand.txt
   
 
 awk command :
 Print all lines, print matching patterns
 NF -last line
 NR - each record
 
 cut 
 cut -b
 cut -c
 cut -d " " -f 1 | grep |sort
 
 sort command 
 sort -o filename1 filename2
 sort -u -remove duplicates and sort
 sort -n - sort by bytes
 sort -nr - desc sort
 sort -r -desc sort
 sort -M - month sort
 
 diff - acd
 cmp - cmp bytes and say the difference
 comm - compare line by line and show the difference,
 
find command:
Find command is used to search in all directories 
find directory name -type f -r -name filename -exec grep grepcommand

scp, rsync
rsync command check for the files and moves it
