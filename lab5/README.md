# Lab 5 (C loops)

## while

```c
while (expression) statement
```
```c
i = 1;while (i < n)	i = i * 2;
```
```c
while (i > 0) {	printf("T minus %d and counting\n", i);	i--; 
}
```
```c
i = 10;while (i > 0)	printf("T minus %d and counting\n", i--);
```
* Ατέρμων Βρόχος
	1. break
	2. return
	3. function

## do

* Εκτελείται πάντα τουλάχιστον μία φορά
* Πάντα αγκύλες


```c
do statement while (expression);
```

```c
i = 10;do {	printf("T minus %d and counting\n", i);	--i;} while (i > 0);
```

## for

* Βρόχους που έχουν μετρητή
* Σχεδόν πάντα μπορεί να αντικαταστήσει την while
* Βρόχοι αύξησης: < <=
* Βρόχοι μείωσεις¨> >=
* Χρήση ==
* Μπορούμε να παραλείψουμε κάποια τιμή παράστασης ή και όλες (ατέρμων) - expressions
* Μια μεταβλητή που έχει δηλωθεί μέσα στην for δεν είναι ορατή έξω από αυτήν
* Η for μπορεί να δηλώσει παραπάνω από μία εντολές


```c
for (expr1; expr2; expr3) statement
```

```c
for (i = 10; i > 0; i--)	printf("T minus %d and counting\n", i);
```

```c
for (; i > 0; --i) /* δεν πραγματοποιείται καμία αρχικοποίηση */
for (i = 10; i > 0;) /* Το σώμα είναι υπε'υθυνω για την εξασφάλιση ότι η τιμή θα γίνει ψευδείς (πχ --1 μέσα σε ένα printf) */
for (; i > 0;) /* ΜΕταμφιεσμένη while */
for (;;) /* ατέρμων βρόχος */
```

```c
for(inti=0;i< n;i++)	/* ... */
```

```c
for (int i = 0, j = 0; i < n; i++) 
	/* ... */
```

## break

* Χρησιμοποιώντας την εντολή break, είναι δυνατό να γράψουμε ένα βρόχο με ένα σημείο εξόδου στην μέση ή ένα βρόχο με περισσότερα από ένα σημεία εξόδου.
* έξοδο για ατέρμων βρόχους
* Δίαβασμα από χρήστη και εισαγωγή μιας τιμής
* Μία εντολή break μεταφέρει τον έλεγχο έξω από το το εσωτερικό while, do, for, ή switch.

```c
for (d = 2; d < n; d++)
	if (n % d == 0)		break;
```

```c
for (;;) {	printf("Enter a number (enter 0 to stop): "); scanf("%d", &n);	if (n == 0)		break;	printf("%d cubed is %d\n", n, n * n * n); }
```

## Continue

* Η continue μεταφέρει τον έλεγχο σε ένα σημείο ακριβώς πριν από το τέλος του σώματος του βρόχου.
* Με την continue, το πρόγραμμα παραμένει μέσα στο βρόχο.
* η break μπορεί να χρησιμοποιηθεί στις εντολές switch και στους βρόχους (while, do, and for), ενώ η continue μόνο σε βρόχους.

```c
n = 0;sum = 0;while (n < 10) {	scanf("%d", &i);
	if (i == 0)	continue; sum += i;	n++;   /* continue jumps to here */}
```