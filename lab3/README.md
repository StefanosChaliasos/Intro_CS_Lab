# Lab 3

## vim
* vim filename
* i a I A o O
* ESC
* :w :wq :q! 
* x
* s
* h j k l
* w b
* όλα συνδιάζονται με αριθμούς π.χ. 3w
* 0 $
* gg G 5G
* u
* d dw d3j dd
* yy
* p
* /search (n or N)


## stdin, stdout, redirections

1. stdin(0)
	* give stdin to a command
	* <
	* cat < hello.txt

2. stdout(1)
	* write to a file
	* >
	* ls -al myfile > longlisting
	* cat > myfile.txt
	* >> (append)
	cat file1 >> file2

3. stderr
	* redirect errors somewhere
	* 2>
	* 2> /dev/null
	
* Άσκηση: Βρείτε πόσοι συμφοιτητές σας έφτιαξαν ένα αρχείο stats.txt και γράψτε το αποτέλεσμα σε ένα αρχείο result.txt. Επίσης κάντε redirect τα errors σε ένα αρχείο errors.log
	* find /disk2/shome/Students2017 -name stats.txt 2> errors.log | wc -l > result.txt
* Άκσηση: Φτιάξτε ένα αρχείο (unsorted_file.txt) με αριθμούς σε τυχαία σειρά (τουλάχιστον έναν διψήφιο) και με redirections φτιάξτε ένα αρχείο με τους αριθμούς ταξινομημένους (sorted_file.txt) χρησιμοποιήστε την εντολή sort.
	* sort -n < unsorted_file.txt > sorted_file.txt

	
## Permissions chmod
* permissions
* -rw-r--r--  1 schaliasos users     38 Oct 30 22:55 hello.txt
	1. file type
		1. - regular file
		2. d catalogue
		3. l link
		4. c character special
		5. s socket
		6. p named pipe
		7. b block device
	2. permissions
	3. number of links
	4. owner name
	5. owner group
	6. file size
	7. time of last modification
	8. file/directory name
* chmod
	1. u: user, g: group, o: others, a: all (ugoa)
	2. r: read, w: write, e:execute
	3. - or +
	4. chmod a+r sample.txt
	5. chmod ug-wx sample.txt
* 0000: uid, owner, group, world
* 4 = r, 2 = w, 1 = x
	1. chmod 0700 file.txt (full permissions owner)
	2. chmod 0755 file.txt (full, read+execute)
	3. chmod 0644 file.txt (r+w, r)
* Άσκηση: Δημιουργήστε έναν κατάλογο με όνομα permissions και φτιάξτε πέντε αρχεία: file1, file2, ... . Με τα εξής permissions:
	1. file1: r--r--r-- (chmod u-w file1)
	2. file2: rw-r----- (chmod o-r file2)
	3. file3: rw-rw-r-- (chmod g+w file3)
	4. file4: rwxr-x--x (chmod ugo+x file4, chmod o-r file4)
	5. file5: r-------- (chmod go-r file5, chmod o-w file5)

## public_html


## mail
* mail -s "Subject" user@yourdomain.com # ctrl+d to send
* mail -s "Subject" user@yourdomain.com < stats.txt
* echo "This is the message body" | mail -s "Subject" user@yourdomain.com
* mail -s "Subject" user@yourdomain.com -c user2@yourdomain.com
* mail -s "Subject" user@yourdomain.com, user2@yourdomain.com
* mail -s "hello" -a stats.txt user@yourdomain.com
* Άσκηση: Στείλτε δύο email στο προσωπικό σας mail. 
	1. Ένα που να έχει τίτλο: (Sorted file) και body το περιεχόμενο του αρχείου sored_file.txt.
		* mail -s "Sorted File" stefanos.halaliasos@gmail.com < sorted_file.txt
	2. Ένα που να έχει τίτλο: (Exercise 1), body: (Άσκηση 1) και επισυνημμένο το stats.txt.
		* echo "Άσκηση 1" | mail -s "Exercise 1" -a stats.txt stefanos.halaliasos@gmail.com

## Δεύτερη εργαστηριακή άσκηση
1. du -h -d 2 /usr/ 2> /dev/null | sort -hr
2. vim diskreport.log
3. du -h -d 2 /usr/ 2> /dev/null | sort -hr >> diskreport.log 
4. mail -s "DiskReport" stefanos.halaliasos@gmail.com < diskreport.log