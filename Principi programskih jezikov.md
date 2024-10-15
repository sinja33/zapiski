## *Programski jeziki in aritmeticni izrazi*

D: Anatomija programskega jezika
- Sintaksa: pravila, kako se piše kodo, na primer: »vsak oklepaj mora imeti svoj zaklepaj«
	- Konkretna - kar pise programer (source code)
	- Abstraktna - prevajalnik
- Statična semantika: preverjanje, ali je program smiseln, na primer: »spremenljivka `i` ni nikjer deklarirana« 
	- Preden se program izvede
	- Pomen programa
	- Preverjanje tipov (ce res uporabljas nek int a kot int in ne kot npr. float), izpeljava tipov, 
- Dinamična semantika: kako se program izvede
	- Ko se program izvaja
	- Tolmac (interpreter)
	- Prevajalnik (compiler)
	- JIT
- Denotacijska semantika: matematicni pomen programa
Programski jezik nima nujno vseh teh, vsaj sintakso in dinamicno semantiko pa imamo vedno.
Ostali pomembni deli so: metode za analizo programov in za dokazovanje pravilnosti.

D: Opis jezika je lahko
- neformalen dokument (Java, C++,...)
- formalen: podana je matematicna definicija
#### *Sintaksa aritmeticnih izrazov*

Postopek: $\mathbb Z, +, *, -$ 
Ker imamo le cela stevila nam staticna semantika odpade (le en tip namrec).

D: Konkretna sintaksa = niz, ki predstavlja izvorno kodo.
Na primer: "3$*$(8+7)"

D: Abstraktna sintaksa = drevo (kot podatkovna struktura), ki predstavlja strukturo
Na primer 
```
	  +
     / \
    y   *
       / \
      +   8
     / \
    5   *
       / \
      7   x
```
za izraz "y + (5 + 7 $*$ x) $*$ 8" 

D: 
Slovnicna gramatika; poenostavljena verzija (oblika BNF)
```
⟨izraz⟩ ::= ⟨aditivni-izraz⟩ EOF
⟨aditivni-izraz⟩ ::= ⟨multiplikativni-izraz⟩ | ⟨aditivni-izraz⟩ + ⟨multiplikativni-izraz⟩
⟨multiplikativni-izraz⟩ ::= ⟨osnovni-izraz⟩ | ⟨multiplikativni-izraz⟩ * ⟨osnovni-izraz⟩
⟨osnovni-izraz⟩ ::= ⟨spremenljivka⟩ | ⟨številka⟩ | ( ⟨aditivni-izraz⟩ )
⟨spremenljivka⟩ ::= [a-zA-Z]+
⟨številka⟩ ::= -? [0-9]+
```
Legenda:
- $::=$ def.
- EOF - end of file (gradnik)
- $|$ ali
- $+,*, ()$ gradniki (angl. token)
- $[...]$ regularni izraz, - interval, + ena ali vec ponovitev, ? nic ali ena ponovitev, $*$ nic ali vec ponovitev

Postopek:
- Konkretna $\underset{\mbox{razclenjevanje}}{\longrightarrow}$ Abstraktna (angl. parsing)
- Abstraktna $\underset{\mbox{izpis}}{\longrightarrow}$ Konkretna (angl. print)
##### Iz konkretne v abstraktno

D: Leksicna analiza (1.faza razclenjevanja)
- EOF, PLUS, KRAT, SPREMENLJIVKA(x), STEVILKA(n), OKLEPAJ/ZAKLEPAJ ... gradniki!
- Npr. `x * (5 + 8)` $\to$ SPREMENLJIVKA(x) KRAT OKLEPAJ STEVILKA(5) PLUS STEVILKA(8) ZAKLEPAJ
- Tudi neveljavne nize lahko razbijemo na gradnike
- Parser generator (razbijanje)

D: Gramatika je lahko dvoumna, to nam bo nakopalo kar nekaj tezav, vendar je veliko bolj pregledna kot nedvoumne. Zato lahko dvoumni gramatiki dodamo prioriteto in asociiranost:
- Prednost: $*$ ima prednost pred $+$
- Asociiranost: 
	- leva: $a*b*c = (a*b)*c$ 
	- desna: $a*b*c = a*(b*c)$ 



D: Iz abstraktne v konkretno

##### Iz abstraktne v konkretno

Postopek: Preprosta pretvorba, saj le obidemo sintakticno drevo in zgradimo ustrezni niz.


#### *Operacijska semantika*

= racunanje dejanske vrednosti izraza (zaenkrat smo izraz razclenili v gradnike in spisali drevo)

D: Pravilo sklepanja - $\frac {p_1p_2 ... p_i}{S}$ 
- Stevec: premise / hipoteze / predpostavke
- Imenovalec: sklep
- $p_1p_2...p_i \implies S$ 

Primeri:
1. $\frac{}{0: \mathbb N}$ - nic je element naravnih stevil (zacetno pravilo ali AKSIOM), $\frac{n: \mathbb N}{n+1:\mathbb N}$ - vsak naslednjik stevila n (ki je naravno stevilo) je tudi naravno stevilo
1. $\frac{}{x=x}$ refleksivnost, $\frac{x=y}{y=x}$ simetricnost, $\frac{x=y \ \ y=z}{x=z}$ tranzitivnost

##### Semantika velikih korakov

= rekurzivno!

D: Okolje je preslikava, ki spremenljivke slika v njihove vrednosti. (npr. $[x \mapsto 3, y \mapsto 7]$ ali pa $[ \ ]$ - nobene spremenljivke nimamo definirane, angl. runtime environment)

D: Semantika velikih korakov (=relacija!)
$\eta \ | \ e \hookrightarrow n$ (preberemo: "V okolju $\eta$ se izraz $e$ evalvira v število $n$.")
- $\eta$ - okolje
- $e, e_1 ,...$ - izrazi
- $n$ - celo stevilo

Primer:
1. $[x \mapsto 3, y \mapsto 2, z \mapsto 5] \ | \ x + 2 * y \hookrightarrow 7$ 

D: Pravila
```
η(x) = n
----------      // ce je okolje od spremenljivke x enako n, potem bo izraz x kar enak n
 η | x ↪ n

---------       // aksiom
η | n ↪ n

  e₁ ↪ n₁     η | e₂ ↪ n₂    n₁ · n₂ = n
------------------------------------------  // mnozenje
             η | e₁ * e₂ ↪ n

 e₁ ↪ n₁     η | e₂ ↪ n₂    n₁ + n₂ = n
------------------------------------------  // sestevanje 
             η | e₁ + e₂ ↪ n
```
token $\to$ operacija

Opomba: V pravilu za seštevanje znak $+$ nad črto pomeni matematično operacijo seštevanje, pod črto pa je to del sintakse aritmetičnih izrazov, se pravi $+$ je samo simbol v izrazu. Pri mnozenju smo se izognili dvoumnosti ( $\cdot$ je matematicno mnozenje, $*$ pa simbol).

Primer:
![[Pasted image 20240314150522.png]]

##### Semantika malih korakov

= korak za korakom (kot so nas ucili v soli, prvo poracunas mnozenja in potem sestevanja)

D: Semantika malih korakov (relacija)
$\eta \ | \ e \mapsto e'$ (preberemo: V okolju $\eta$ se v enem koraku $e$ predela v $e'$)

D: Pravila
```
 η(x) = n
----------
η | x ↦ n


      η | e₁ ↦ e₁'
----------------------
η | e₁ + e₂ ↦ e₁' + e₂


      η | e₂ ↦ e₂'
----------------------
η | n₁ + e₂ ↦ n₁ + e₂'


  n₁ + n₂ = n
---------------
 η | n₁ + n₂ ↦ n


      η | e₁ ↦ e₁'
----------------------
η | e₁ * e₂ ↦ e₁' * e₂


      η | e₂ ↦ e₂'
----------------------
η | n₁ * e₂ ↦ n₁ * e₂'


  n₁ · n₂ = n
-----------------
 η | n₁ * n₂ ↦ n
```

Primer:
- $\eta = [x\mapsto 3, y\mapsto 2, z\mapsto 5]$ in $e = x + 2 * y$ 
```
x + 2 * y  ↦
3 + 2 * y  ↦
3 + 2 · 2  ↦
3 + 4      ↦
7
```

## *Ukazni programski jezik*

= jezik, ki ima prave spremenljivke, pogojne stavke in zanko while.
#### *Sintaksa*

D: Abstraktna sintaksa jezika
```
⟨aritmetični-izraz⟩ ::=
  ⟨spremenljivka⟩ |
  ⟨številka⟩
  ⟨aritmetični-izraz⟩ + ⟨aritmetični-izraz⟩ |
  ⟨aritmetični-izraz⟩ * ⟨aritmetični-izraz⟩

⟨boolov-izraz⟩ ::=
   true | false |
   ⟨aritmetični-izraz⟩ = ⟨aritmetični-izraz⟩ |
   ⟨aritmetični-izraz⟩ < ⟨aritmetični-izraz⟩ |
   ⟨boolov-izraz⟩ and ⟨boolov-izraz⟩ |
   ⟨boolov-izraz⟩ or ⟨boolov-izraz⟩ |
   not ⟨boolov-izraz⟩

⟨ukaz⟩ ::=
   skip |
   ⟨spremenljivka⟩ := ⟨aritmetični-izraz⟩ |
   ⟨ukaz⟩ ; ⟨ukaz⟩ |
   while ⟨boolov-izraz⟩ do ⟨ukaz⟩ done |
   if ⟨boolov-izraz⟩ then ⟨ukaz⟩ else ⟨ukaz⟩ end
```

Postopek: Da bomo blizje konkretni sintaksi, moramo podati se informacijo o prioriteti in asociativnosti. (Od najnizje do najvisje prioritete):
- ; (levo)
- or (levo)
- and (levo)
- not
- <,=
- + (levo)
- $*$ (levo)

#### *Operacijska semantika*

Postopek: Ce zelimo narediti svoj programski jezik potrebujemo prevajalnik ($P\to C$) kjer se koda $C$ dejansko izvede. Po vsej logiki prevajalnik ne dela napak, lahko ga samo mi narobe zapisemo, zato potrebujemo tudi opis delovanja, ki je neodvisen od prevajalnika in arhitekture. 

= matematicni opis delovanja

D: Nastavljanje spremenljivk v okolju
$\eta \ [x \mapsto n]$ (Beremo: vrednost $x$ je nastavljena na $n$)

Primer:
- $\eta = [x\mapsto 10, y\mapsto 3]$, potem $\eta [x\mapsto 20]$ pomeni da imamo $\eta = [x\mapsto 20, y\mapsto 3]$ 
##### Semantika malih korakov

**Operacijska semantika aritmetičnih in boolovih izrazov**

D: Pravila za aritmeticne izraze smo ze spoznali, se enkrat:
```
—————————-
η | n ↪ n


 η(x) = n
————————––
η | x ↪ n

η | e₁ ↪ n₁     η | e₂ ↪ n₂
———————————————————————–———     // prvi + le simbol, drugi + matematicna operacija
 η | e₁ + e₂ ↪ n₁ + n₂


η | e₁ ↪ n₁     η | e₂ ↪ n₂
———————————————————————–———
 η | e₁ - e₂ ↪ n₁ - n₂


η | e₁ ↪ n₁     η | e₂ ↪ n₂
———————————————————————–———
 η | e₁ * e₂ ↪ n₁ · n₂
```

D: Pravila za Boolove izraze
```
————————————————
 η | true ↪ true


————————————————–
η | false ↪ false


   η | b ↪ false
 ————————-––-—————   // lahko pa bi definirali kar z matematicno negacijo
 η | not b ↪ true


    η | b ↪ true
 —————————————————–
 η | not b ↪ false


     η | b₁ ↪ false      
———————————-–—————————–   
 η | b₁ and b₂ ↪ false   


 η | b₁ ↪ true     η | b₂ ↪ v₂
––———————————————————————————–
     η | b₁ and b₂ ↪ v₂


   η | b₁ ↪ true
————————————————————–
 η | b₁ or b₂ ↪ true


η | b₁ ↪ false     η | b₂ ↪ v₂
—————————————————————————————–
     η | b₁ or b₂ ↪ v₂


η | e₁ ↪ n₁    η | e₂ ↪ n₂     n₁ < n₂
————————————————————–—————————————————
        η | e₁ < e₂ ↪ true


η | e₁ ↪ n₁   η | e₂ ↪ n₂    n₁ ≥ n₂
————————————————————–———————————————
      η | e₁ < e₂ ↪ false
```

Opomba: (and) 
- "Short-circuit"
	- Izracunas 1.izraz, ce ze ta ni okej $\to$ sklep ni okej (2.izraz sploh ne gremo racunat)
	- Ce je 1.izraz okej, je sklep kar enak 2.izrazu
- Lahko pa bi izracunali oba izraza in glede na tabelo dobili sklep
"Short-circuit" opcija: Ni vec "and" po definiciji boolove algebra, kar pomeni, da ni nujno komutativno! (Vcasih je 1.pogoj potrebno izpolnit da preveris drugega, v tem primeru ko zamenjas pogoja dobis napako --> if(0<i<length(tabela) and tabela$[i]$ < == "neki") ko zamenjamo pogoja znamo dobit napako za i k je out of bounds)

**Operacijska semantika ukazov**

D: Semantika malih korakov je podana z dvema relacijama:
- relacija $(\eta, c) \mapsto \eta'$ pomeni: v okolju $\eta$ ukaz $c$ v enem koraku konča v okolju $\eta'$. (ukaz konca izvajanje)
- relacija $(\eta, c) \mapsto (\eta',c')$: v okolju $\eta$ ukaz $c$ v enem koraku spremeni okolje v $\eta'$ in se nadaljuje z ukazom $c'$.

D: Pravila:
```
—–————————————–
(η, skip)  ↦  η


       η | e ↪ n
————————————––—————————–
(η, (x := e))  ↦  η[x↦n]


       (η, c₁) ↦ (η', c₁')
—————————————––—————————–——————————
(η, (c₁ ; c₂))  ↦  (η', (c₁' ; c₂))


          (η, c₁) ↦ η'
—————————————––—————————–——————————
   (η, (c₁ ; c₂))  ↦  (η', c₂)


             η | b ↪ true
———————————————————————–—————————————————
(η, (if b then c₁ else c₂ end)) ↦ (η, c₁)


             η | b ↪ false
———————————————————————–—————————————————
(η, (if b then c₁ else c₂ end)) ↦ (η, c₂)


      η | b ↪ false
———————————––—————————–——————
(η, (while b do c done)) ↦ η


                      η | b ↪ true
—————————————––—————————–—————————–——————————————————————-
 (η, (while b do c done))  ↦ (η, (c ; while b do c done))
```

#### *Denotacijska semantika*

= matematicni pomen programov

D: Matematicni pomen komponent
- pomen aritmeticnega izraza $e$ je neko stevilo $[[e]] \in \mathbb Z$ 
- pomen boolovega izraza $b$ je neka **resničnostna vrednost** $[[b]] \in \{\top, \bot\}$ 
- pomen programa $c$ je nekaj **preslikava** $[[c]] : \mbox{Env} → \mbox{Env}$ iz okolij v okolja.

Opomba: $[[\ ]]$ je oznaka za matematicni pomen.

#### *Ekvivalenca programov*

D: Evalvacijski kontekst $C[\ \ ]$ je del programske kode $C$, ki ima "luknjo" $[\ \ ]$.

D: Programska koda $A$ je ekvivalentna programski kodi $B$, ce za vse kontekste $C[\ \ ]$ velja, da imata $C[A]$ in $C[B]$ enak rezultat in enako spreminjata okolje.

Primer: Ekvivalentna programa
```
i := 1 ;
s := 0 ;
while i < 101 do
  s := s + i ;
  i := i + 1
done
```
in pa 
```
i := 101
s := 5050
```
Ce bi v drugem programu imeli le $s$, programa ne bi bila ekvivalentna, saj je okolje drugacno!

Opomba: Ce zelis pokazati, da kodi nista ekvivalentni najdes konkreten primer kjer se spremeni okolje.

Primer: Ekvivalentni zanki
```
for(A;p;B) {
	C
}

A;
while(p) {
	C;
	B;
}
```

#### *Prevajalnik*

D: Jezik `comm` vsebuje naslednje komponenete:
- aritmeticne in boolove izraze
- spremenljivke
	- dekleracija nove lokalne spremenljivke (`let x := e in c` ---> nova spremenljivka velja za celotni naslednji ukaz)
	- nastavljanje vrednosti (`x := e`)
- pogojni stavek
- while zanka
- ukaz skip
- sestavljeni ukaz
- ukaz print 

D: Prevajalnik jezika comm program pretvori neposredno v strojno kodo, pri pravih jezikih to poteka vecstopenjsko.

## *Dokazovanje pravilnosti programov*



## *$\lambda$-racun*
## *Deklaritivno programiranje*
## *Rekurzija in rekurzivni tipi*
## *Izpeljava tipov*
## *Specifikacija, implementacija, abstrakcija*
## *Logicno programiranje*
## *Logicno programiranje z omejitvami*
## *Podtipi in objekti*
## *Objektno programiranje*
