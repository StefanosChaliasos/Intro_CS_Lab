# Lab2

## Επανάληψη κάποιον εντολών και κάποιες εντολές που δεν αναφέραμε

### Cal

* cal -y

* cal 12 2017

### History

* history

* history 10

* arrows up / down (shortcuts)

* history -c

* history -d 2

* !22 (execute command number 22)

### df 

* df

* df -h

* df -h bin 

### free
ram

* free

* free -b/k/m/g

### help

* man command

* command --help

* use tab to autocomplete (shortcut)

### cat more less head tail
* cat (τυπώνει κατευθείαν το αρχείο και σου δείχνει το τέλος)
* more (σε ξεκινάει στην αρχή και κατεβένεις με βελάκια, για να βγεις q)
* less (περίπου σαν το more)
* head (σου δείχνει τις 10 πρώτες γραμμές. Αν δώσει πχ. head -3 θα σου δείξει τις τρεις)
* tail (σου δείχνει τις 10 τελευταίες. Αν δώσεις πχ. tail -3 ...)

### Dimitro commands
* cp -u *.html destination
* ls -l | less
* ls -l
	1. -rw-r--r--  1 sh  1798654287   1.1K Oct 21 22:35 README.md
	2. Όνομα, Ημερομινία μορφοποίησης, το μέγεθος σε bytes
	3. Τύπος αρχείου
		1. - (κανονικό αρχείο)
		2. d (κατάλογος)
		3. | (σύνδεσμος)
		4. c (character special file)
		5. s (socket)
		6. p (named pipe)
		7. b (block device)
	4. Άδειες
		1. άδειες χρήστη (user)
		2. άδειες ομάδας (group)
		3. άδειες υπολοίπων (world)
		4. r-w-x
	5. user name
* regex (χαρακτήρες μπαλαντέρ)
	1. * (οποιοδήποτε χαρακτήρα)
	2. ? (ένα χαρακτήρα)
	3. [charecters]
	4. [!characters]
		1. g*
		2. *.c

## Φροντιστήριο 2

* cp (-i option ask first)
	1. cp file1 file // αντιγραφή ενός αρχείου σε άλλο, αν δεν υπάρχει δημιουργείται
	2. cp file1 file2 directory // αντιγραφή αρχείων σε κατάλογο 
	3. cp -R dir1 dir2// αντιγράφει τα περιεχόμενα του φακέλου στον άλλον
* mv
	1. mv file1 file // μετονομασία (αν δεν υπάρχει), διαφορετικά τα περιεχόμενα του αντικαθιστώνται
	2. mv file1 file2 directory // μεταφορά αρχείων σε έναν κατάλογο
	3. mv dir1 dir2 // αν υπάρχει μεταφέρεται μέσα στον dir2 αλλιώς μετονομασία
* rm
	1. rm file1 file2
	2. rm -r dir1 dir2
* mkdir

	
## Άσκηση που είχαν για το σπίτι

* Σωληνώσεις: χτίζετε τες βήμα βήμα
* Εντολές:
	1. last (-w)
	2. grep (--color -i(ignore case) -n(line number) -r(search all files under a directory)
	3. cut -d " " -f 1, 3
	4. sort
	5. uniq (omit repeated lines)
	6. wc (print line, wordm byte counts) -l (only line numbers)

* Παράδειγμα: last | grep "Oct 16\|Oct 17" |cut -d " " -f 1 | sort |uniq|wc -l
* Ασκήσεις
	1. 57: last | grep "Oct 16\|Oct 17\|Oct 18" | cut -d " " -f1 | sort | uniq | wc -l
	2. tip (last -a) last -a | grep "Oct 16\|Oct 17\|Oct 18" | grep "otenet" | cut -d " " -f 1 | sort | uniq | wc -l

## Exercises Φροντ 2

Tip touch command

1. touch hello, mv hello hello.c
2. touch foo1 foo2 foo3, mv foo1 foo2 foo3 foo_files (ελέγξτε με tree)
3. mkdir foos, mv foo_files/foo1 foos/ (no mv foo_files/ foos/ )
4. rm -R foos, rm -R foo_files/

## Exercises

* Να εμφανησουν τις συνδέσης ενος φίλου τους με το ονομα του φιλου τους και το χρόνο που έμεινε μέσα (tip: -f 1, κάτι)
	1. last -w | grep "ndoureliadis" | cut -d " " -f 1,21
	2. last -w | grep "ndoureliadis" | cut -d " " -f 1,18
* Να πάνε στον φάκελο που είναι όλοι οι συμφοιτητές σας μέσα
	1. cd ../
	2. ls
	1. cd /disk2/shome/Students2017
	2. ls
* Να ψάξουν πόσοι συμφοιτητές έχουν κάτι την άσκηση με το stats.txt. Tip εντολή find 
	1. find -name stats.txt | wc -l
* Στο home directory τους να εμφανησουν το τρίτο αρχείο-κατάλογο τους με την εντολή ls και σωληνώσεις με head και tail
	1. ls | head -3 | tail -1

## Exercise C
	
1. cd ~/intro_ cs/lab_session
2. nano hello_goodbye.c
3. make hello_goodbye
4. ./hello_goodbye

```
#include <stdio.h>

int main() {
    printf("Hello, World\nGoodbye...\n");
}
```

## C intro



