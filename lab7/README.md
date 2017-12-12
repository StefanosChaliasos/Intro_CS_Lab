# Lab7 - Functions

Απλή συνάρτηση

```c
double average(double a, double b)
{
	return (a + b) / 2; 
}
```

* Τα **ορίσματα** μπορούν να είναι και τιμές και εκφράσεις και μεταβλητές


## Δήλωση συνάρτησης


```c
double average(double a, double b); /* DECLARATION */

int main(void) 
{
	/* body */ 
}

double average(double a, double b) /* DEFINITION */
{
	return (a + b) / 2; 
}
```

## Κλήσεις

* μπορούμε να παραλείψουμε την τιμή επιστροφής

## Ορίσματα

* τα ορίσματα περνάνε κατ’ αξία

## Μετατροπές ορισμάτων

* Από γενικό σε ειδικό

## Πίνακες ως ορίσματα

```c
int f (int a[], LEN) /* DEFINITION */

total = f(f, LEN); /* CALL */
```

* Περνάει ο κανονικός πίνακας και όχι αντίγραφο 
* Πολυδιάστατος

```c
#define LEN 10
int sum_two_dimensional_array(int a[][LEN], int n) {}
```

## return 

* return;
* return 50;
* return x;
* return x >= 0 ? x : 0;

## Τερματισμός Προγράμματος

* #include <stdlib.h>
* exit(0);
* exit(EXIT_SUCCESS);
* exit(EXIT_FAILURE);
* return expression; = exit(expression);
* Η διαφορά μεταξύ του return και του exit είναι ότι το exit τερματίζει το πρόγραμμα σε όποια συνάρτηση και αν βρίσκεται.

## Αναδρομή

* Μια συνάρτηση είναι αναδρομική (recursive) όταν καλεί τον εαυτό της.
* Όλες οι αναδρομικές συναρτήσεις χρειάζονται μια «συνθήκη τερματισμού».

## Τοπικές μεταβλητές

* εμβέλεια μπλοκ
* static int i; (παραμένει η ίδια μεταβλητή σε κάθε κλήση)

## Εξωτερικές Μεταβλητές

* εμβέλεια αρχείου
