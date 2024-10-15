UREJANJE

bogosort

naravni algoritmi
- selection sort
- insertion sort
- bubble sort

zahtevnejsi
- mergesort
- quicksort

urejanje brez primerjav
- counting sort
- bucket sort -> radix sort

binary search - bisekcija


PODATKOVNI TIPI IN STRUKTURE

1. array 
- init, insert, get

2. stack
- CIFO, push, pop

3. list - (linked list, skip list)
- add, remove, size, empty, get, insert...
- linked: vsako vozlisce ima vrednost in kazalec na naslednje vozlisce
- skip: idk
- dynamic: alociras kapaciteto (x2)

4. queue (impl: linked list, dynamic array, krozno polje, dva sklada)
- FIFO,push, pop, front, size

5. heap
- dvojisko drevo, koren najmanjsi, visina logn
- priority: vsak element prioriteta, psuh, pop, front size
- heapsort ^

6. set
- ne vsebuje ponovitev, insert, add, remove, contains, size...
- implementacija z razprsenimi tabelami
- multiset: vec ponovitev 

7. map
- pari - (kljuc, vrednost) kljuc unikaten
- insert, remove, get, size...
- hashtable: collisions, verizenje, hash kljuc mod capacity


DREVESA

- vozlisce, povezava, koren, rekurzivna struktura, poddrevesa, listi (zunanji, notranji)

- stars -- otrok, sosedi, koren nima starsa, listi nimajo otrok, sorojenci - otroci istega starsa, potomci (po otrocih), predniki (vsi pred)

- st otrok = stopnja (deg), velikost = skupno st.vozlisc, globina = st.povezav na poti od korena do vozlisca, globina korena = 0, visina = max globina

- uravnotezena [kosata, ne globoka] h=O(logn)
in izrojena [globoka, ne kosata]

OBHODI
- premi, vmesni, obratni, nivojski

VRSTE
- dvojisko (k-tisko), 
- polno (max st otrok ali pa 0), 
  - poravnano (heap), 
  - popolna (polna && vsi listi na enaki globini)
- urejena in neurejena (pomemben\ne vrstni red otrok)
- iskalna (urejena, prvi otrok najmanjsa vrednost)
- crkovna/znakovna

   IMPLEMENTACIJE
1. BSTree (dvojisko iskalno, binary search)

Poizvedbe
A = [a1,..,an] --> q(l,r) --> al,..,a{r-1}
sestevanje (sum od l do r), odstevanje komulativne vsote (cr = sum ai od 0 do r-1) in potem cr-cl
minimum - naivna resitev: gres cez vse; bloki: razdelis na bloke in ze tam poracunas minimume; B = koren od n
staticno drevo - bloki v visino, podaljsamo tabelo do potence st 2, popolno dvojisko drevo

2. RMQ (range minimum query)

3. AVLTree (uravnotezen, bst, kjer visina l in r poddrevesa vedno razlikuje le za 1, rotiranje)

4. Red-Black tree
5. 2-3 tree
6. B-drevo (posplositev 2-3)
7. Splay tree
8. Treap


POZRESNI ALGORITMI

1. Car fueling
K kilometrov potovanja, T poln tank, N crpalk
- vedno napolnis gorivo do T; 
- ce je mogoce doseci naslednjo crpalko - preskocimo trenutno
- O(n)

2. Activity selection (interval scheduling)
N aktivnosti, i-ta aktivnost ai v obdobju (si,ei), cimvecja podmnozica aktivnosti da je presek dveh poljubnih prazen
- najzgodnejsi zacetek
- najkrajsi
- najmanj konflikten
- najzgodnejsi konec!!
   - O(nlogn)

3. Classroom scheduling (interval partitioning)
N predavanj v obdobju (si,ei), najmanjse stevilo predavalnic, ki jih potrebujemo
- max socasno potekanje = globina (tok bo zmer)
- uredis po zacetkih in ce je kej prosto das tja, ce ni odpres novo in dodelis
- min heap je O(nlogn)

4. Datoteke na traku (storing files on tape)
N datotek, di = (si,fi) s velikost, f pogostost dostopa, cena zapisa - vsota po xf, x zacetno mesto zapisa datoteke, optimalen razpored datotek in z njim povezana minimalna cena

5. Minimum lateness scheduling
N opravil, en racunalnik, oi = (ti,di), t cas izvajanja, d rok do kdajm ce si cas zacetka izvajanja se konca ob fi = si + ti, zamuda je zi = max(0, fi-di), minimiziramo najvecjo zamudo Z = max zi
- najkrajsi cas izvajanja
- najkrajsi prosti cas
- najzgodnejsi rok
  - narascujoce po rokih

DOKAZOVANJE pravilnosti
- prednost
- zamenjava
- struktura


GRAF

APT, mnozica vozlisc in povezav