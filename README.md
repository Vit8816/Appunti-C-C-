
# Programmazione in C e C++

## Introduzione

La programmazione è il processo di scrittura, test e manutenzione del codice sorgente di programmi informatici. Serve per creare software che esegue specifici compiti su computer o altri dispositivi elettronici.

Il linguaggio C è stato sviluppato negli anni '70 da Dennis Ritchie presso i Bell Labs. È fondamentale perché molti altri linguaggi, come C++, Java e C#, derivano da esso. C è conosciuto per la sua efficienza e controllo a basso livello dell'hardware. C++ è un'estensione del C che incorpora la programmazione orientata agli oggetti (OOP). Include classi, oggetti e molte altre caratteristiche che non sono presenti nel C puro.

## Fondamenti di Programmazione in C

### Variabili e Tipi di Dati

In C, le variabili devono essere dichiarate con un tipo specifico, come `int`, `float`, `char`, ecc. Questo tipo determina la dimensione e il layout della variabile in memoria. Ad esempio:

```c
int main() {
    int numero = 10;  // Dichiarazione di una variabile intera
    float decimale = 3.14;  // Dichiarazione di una variabile float
    char carattere = 'A';  // Dichiarazione di una variabile char
    printf("Numero: %d, Decimale: %.2f, Carattere: %c\n", numero, decimale, carattere);  // Stampa delle variabili
    return 0;  // Fine del programma
}
```

- `int`: Tipo di dato che rappresenta un numero intero.
- `float`: Tipo di dato che rappresenta un numero in virgola mobile.
- `char`: Tipo di dato che rappresenta un singolo carattere.
- `printf`: Funzione della libreria standard che stampa una stringa formattata sullo schermo.
- `return 0`: Istruzione che termina il programma e ritorna il valore 0 al sistema operativo.

### Operatori e Espressioni

Gli operatori in C includono operatori aritmetici (`+`, `-`, `*`, `/`), logici (`&&`, `||`, `!`), relazionali (`==`, `!=`, `>`, `<`) e di assegnazione (`=`, `+=`, `-=`). Le espressioni combinano variabili e operatori per calcolare valori. Ecco un esempio:

```c
int main() {
    int a = 5, b = 3;
    int somma = a + b;  // Somma di due numeri
    int prodotto = a * b;  // Prodotto di due numeri
    int confronto = (a > b);  // Confronto tra due numeri
    printf("Somma: %d, Prodotto: %d, Confronto: %d\n", somma, prodotto, confronto);
    return 0;
}
```

- `a + b`: Operazione di somma.
- `a * b`: Operazione di moltiplicazione.
- `(a > b)`: Operazione di confronto che verifica se `a` è maggiore di `b`.
- `printf`: Stampa i risultati delle operazioni.

### Strutture di Controllo

Le strutture di controllo in C includono `if`, `else`, `switch` per il controllo di flusso condizionale, e `for`, `while`, `do-while` per i loop. Ecco un esempio di utilizzo delle strutture di controllo:

```c
int main() {
    int numero = 10;
    if (numero > 0) {
        printf("Numero positivo\n");
    } else {
        printf("Numero non positivo\n");
    }
    
    for (int i = 0; i < 5; i++) {
        printf("i = %d\n", i);
    }
    return 0;
}
```

- `if`: Struttura di controllo che esegue un blocco di codice se una condizione è vera.
- `else`: Struttura di controllo che esegue un blocco di codice alternativo se la condizione dell'`if` è falsa.
- `for`: Loop che itera un blocco di codice un numero specificato di volte.

### Funzioni e Modularità

Le funzioni sono blocchi di codice che eseguono compiti specifici e possono essere chiamate da altre parti del programma. La modularità aiuta a organizzare il codice in pezzi più gestibili e riutilizzabili. Ecco un esempio:

```c
void stampaMessaggio() {
    printf("Ciao dal C!\n");
}

int main() {
    stampaMessaggio();
    return 0;
}
```

- `void stampaMessaggio()`: Definizione di una funzione che non ritorna alcun valore.
- `stampaMessaggio()`: Chiamata della funzione.

## Gestione della Memoria

### Allocazione Dinamica della Memoria

In C, l'allocazione dinamica della memoria viene gestita tramite le funzioni `malloc`, `calloc`, `realloc` e `free`. Queste funzioni permettono di allocare e deallocare memoria a runtime. Ecco un esempio:

```c
int main() {
    int *puntatore;
    puntatore = (int *) malloc(10 * sizeof(int));
    if (puntatore == NULL) {
        printf("Allocazione della memoria fallita\n");
        return 1;
    }
    free(puntatore);
    return 0;
}
```

- `malloc`: Funzione che alloca memoria dinamicamente.
- `free`: Funzione che dealloca la memoria precedentemente allocata.

### Puntatori e Aritmetica dei Puntatori

I puntatori sono variabili che memorizzano gli indirizzi di altre variabili. L'aritmetica dei puntatori consente di navigare attraverso blocchi di memoria. Questo è cruciale per l'uso efficiente della memoria e per manipolare array e strutture complesse. Ecco un esempio:

```c
int main() {
    int array[5] = {1, 2, 3, 4, 5};
    int *p = array;
    for (int i = 0; i < 5; i++) {
        printf("Valore di array[%d] = %d\n", i, *(p + i));
    }
    return 0;
}
```

- `*p`: Operatore di dereferenziazione che accede al valore memorizzato all'indirizzo puntato.

## Strutture Dati Complesse

### Array e Stringhe

Un array è una raccolta di elementi dello stesso tipo memorizzati contiguamente in memoria. Le stringhe in C sono array di caratteri terminati da un carattere null ('\0'). Ecco un esempio:

```c
int main() {
    char stringa[] = "Hello, World!";
    printf("Stringa: %s\n", stringa);
    return 0;
}
```

- `char stringa[]`: Dichiarazione di un array di caratteri (stringa).

### Strutture e Unioni

Le strutture (`struct`) sono tipi di dati composti che raggruppano variabili di diversi tipi sotto un singolo nome. Le unioni (`union`) sono simili, ma utilizzano la stessa posizione di memoria per memorizzare diversi tipi di dati, uno alla volta. Ecco un esempio:

```c
struct Punto {
    int x;
    int y;
};

int main() {
    struct Punto p1;

    p1.x = 10;
    p1.y = 20;
    printf("Punto: (%d, %d)\n", p1.x, p1.y);
    return 0;
}
```

- `struct Punto`: Definisce una struttura chiamata `Punto` con due membri `x` e `y`.
- `p1`: Istanza della struttura `Punto`.

## Input/Output

### File I/O

Le operazioni di input/output su file in C sono gestite tramite funzioni come `fopen`, `fclose`, `fread`, `fwrite`, `fprintf` e `fscanf`. Queste funzioni permettono di leggere e scrivere dati su file. Ecco un esempio:

```c
int main() {
    FILE *file = fopen("esempio.txt", "w");
    if (file == NULL) {
        printf("Errore nell'apertura del file\n");
        return 1;
    }
    fprintf(file, "Hello, file!\n");
    fclose(file);
    return 0;
}
```

- `fopen`: Apre un file e restituisce un puntatore al file.
- `fprintf`: Scrive una stringa formattata su un file.
- `fclose`: Chiude un file aperto.

### Input e Output Standard

Le funzioni `printf` e `scanf` sono usate per l'input e l'output standard. `printf` formatta e stampa i dati sullo schermo, mentre `scanf` legge input dall'utente. Ecco un esempio:

```c
int main() {
    int numero;
    printf("Inserisci un numero: ");
    scanf("%d", &numero);
    printf("Hai inserito: %d\n", numero);
    return 0;
}
```

- `printf`: Stampa una stringa formattata sullo schermo.
- `scanf`: Legge l'input dall'utente.

## Programmazione Avanzata in C

### Librerie Standard del C

La libreria standard del C include funzioni per la manipolazione di stringhe, matematica, gestione della memoria e input/output. Alcune delle librerie comuni sono `stdio.h`, `stdlib.h`, `string.h` e `math.h`. Ecco un esempio:

```c
#include <string.h>

int main() {
    char src[] = "Hello";
    char dest[20];
    strcpy(dest, src);
    printf("Copia della stringa: %s\n", dest);
    return 0;
}
```

- `strcpy`: Copia una stringa in un'altra.

### Preprocessore C

Il preprocessore C esegue direttive come `#include`, `#define`, e `#if` prima della compilazione. Questo permette l'inclusione di file, la definizione di macro e la compilazione condizionale. Ecco un esempio:

```c
#define PI 3.14
#define AREA(r) (PI * (r) * (r))

int main() {
    float r = 5.0;
    float area = AREA(r);
    printf("Area del cerchio: %.2f\n", area);
    return 0;
}
```

- `#define`: Definisce una macro.
- `AREA(r)`: Macro che calcola l'area di un cerchio.

### Debugging e Testing

Il debugging è il processo di identificazione e correzione degli errori nel codice. Gli strumenti comuni includono `gdb` per il debugging e `Valgrind` per il rilevamento delle perdite di memoria.

## Introduzione al C++

### Origini del C++

C++ è stato sviluppato da Bjarne Stroustrup nei primi anni '80 come estensione del C per includere la programmazione orientata agli oggetti.

### Sintassi di Base del C++

C++ mantiene gran parte della sintassi del C, aggiungendo però caratteristiche come classi e oggetti. Include anche funzioni e operatori sovraccaricati, e altre caratteristiche avanzate. Ecco un esempio:

```cpp
class Punto {
public:
    int x, y;
    Punto(int a, int b) : x(a), y(b) {}
};

int main() {
    Punto p1(10, 20);
    printf("Punto: (%d, %d)\n", p1.x, p1.y);
    return 0;
}
```

- `class Punto`: Definisce una classe chiamata `Punto`.
- `Punto(int a, int b)`: Costruttore della classe `Punto`.

### OOP in C++

L'OOP in C++ include concetti come incapsulamento, ereditarietà e polimorfismo. Le classi definiscono i tipi di dati complessi che possono includere metodi e attributi.

### Funzioni e Overloading

C++ permette il sovraccarico delle funzioni, il che significa che più funzioni possono avere lo stesso nome ma diversi tipi di parametri.

## Gestione della Memoria in C++

### Costruttori e Distruttori

I costruttori sono funzioni speciali che inizializzano gli oggetti di una classe. I distruttori sono chiamati quando un oggetto è distrutto per liberare risorse.

### Gestione delle Eccezioni

La gestione delle eccezioni in C++ è fatta tramite i blocchi `try`, `catch` e `throw`. Questo permette di gestire errori runtime in modo strutturato.

### Smart Pointers

Gli smart pointers, come `std::unique_ptr` e `std::shared_ptr`, aiutano a gestire la memoria automaticamente, prevenendo perdite di memoria e migliorando la sicurezza del codice.

## Strutture Dati Avanzate in C++

### Classi e Oggetti

Le classi sono blueprint per creare oggetti. Ogni oggetto è un'istanza di una classe con i propri dati e metodi.

### Contenitori STL

La Standard Template Library (STL) include una varietà di contenitori come `vector`, `list`, `map` e `set`, che forniscono strutture dati efficienti e flessibili.

### Algoritmi STL

La STL include anche molti algoritmi standard, come `sort`, `find` e `transform`, che possono essere usati con i contenitori STL.

## Programmazione Generica in C++

### Template e Metaprogrammazione

I template permettono la scrittura di funzioni e classi generiche. La metaprogrammazione template permette l'esecuzione di calcoli a tempo di compilazione per ottimizzare il codice.

### Funzioni Lambda

Le funzioni lambda sono funzioni anonime che possono essere definite all'interno di altre funzioni per compiti temporanei. Sono particolarmente utili con gli algoritmi STL.

## Conclusioni e Prospettive Future

I linguaggi di programmazione continuano ad evolversi per migliorare la sicurezza, l'efficienza e la facilità d'uso. Le nuove versioni di C e C++ introducono caratteristiche che rispondono alle esigenze moderne di sviluppo software. Le future evoluzioni del C e C++ probabilmente si concentreranno su una migliore gestione della memoria, parallelismo, e supporto per nuove architetture hardware. C++ continua a evolversi con nuove versioni come C++20 e C++23, introducendo caratteristiche che migliorano la programmazione concorrente e funzionale.
