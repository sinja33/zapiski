# Predavanja
## Uvod

Intuicija: Optimizacijski problem je maksimiziranje oz. minimiziranje neke realne funkcije na neki mnozici.
- max - za "dobre" pomene (povprecna ocena, denar, zadovoljstvo, korist)
- min - za "slabe" stvari (stroski, cas, prostor)
Optimizacijska naloga je optimizacijski problem s konkretnimi podatki.
Namen predmeta je najti sistematicne nacine oz. postopke (=algoritmi) za resevanje optimizacijskih problemov in nalog. 
Lahko se lotimo matematicno ali pa formalno.

D: Optimizacijska naloga je urejena trojica $(D,f,opt)$, kjer velja:
- $D$ je mnozica dopustnih resitev
- $f: D \to \mathbb R$ je ciljna funkcija (kriterijska funkcija)
- $opt$ $\in \{max, min, inf, sup\}$ je vrsta ekstrema
Zanima nas $opt\{f(x) \ | \ x \in D\}$ ali $opt \ f(x)$ p.p $x \in D$ (p.p - pri pogojih = s.t - subject to/such that)
Optimizacijska naloga je optimizacijski problem s konkretnimi podatki.

D: Optimalna resitev je $x^* \in D$, za katero velja $f(x^*) = opt\{f(x) \ | \ x \in D\}$ (tocka kjer dosezemo ekstrem). Ni nujno da obstaja optimalna resitev.

Opomba: Izven matematike se besedna zveza optimalna resitev uporablja drugace.
*optimum - najboljsa* (nemoremo reci: Moja resitev je bolj optimalna od tvoje.)

Komentar: $D$ podana implicitno (opis mnozice).
Vcasih je pa $D = \emptyset$ in to ni jasno. 
Vsak $x \in D$ je dopustna resitev (obstajajo le dopustne in optimalne resitve, beseda "resitev" se ne uporablja za optimizacijske naloge).
#### *Taksonomija optimizacijskih nalog*

D: Optimizacijske naloge $(D, f, opt)$ se delijo glede na:
$D = \emptyset$ ?
- $D = \emptyset$ --> nedopustna naloga (1)
- $D \neq \emptyset$ --> dopustna naloga
	$opt\{f(x) \ | \ x \in D\} = +/- \infty$ ?
	- da --> neomejena (2)
	- ne --> omejena
		obstaja optimalna resitev ?
		- da --> "optimalna" (3)
		- ne --> "neoptimalna" (4)

Primeri delitev: 
(1): ($D = \{x \in \mathbb R \ | \ x^2 + 1 \leq 0\}$, $f(x) = x$, max)

(2): ($D = \{x \in \mathbb R \ | \ 0 \lt x \lt 1\}$, $f(x) = \frac {1}{x}$, max/sup) -- $f(x) = (1, +\infty)$
($D = (0,1)$, $f(x) = \frac {1}{x}$, min) je omejena in (4)

(3): ($D = [0,1]$, $f(x) = x^2$, min) -- $x^* = 0$ je optimalna resitev
($D = [-1,1]$, $f(x) = x^2$, max/sup) 	$x^* = 1$ in $x^* = -1$ 
 
#### *Primeri optimizacijskih problemov*

1. Maksimum funkcije
Poisci maksimum funkcije $f(x) = -x^2 - 2x +4$ na $[-2,2]$
max$\{-x^2 - 2x + 4 \ | \ x \in [-2,2] \}$ 
- $D = [-2,2] \subset \mathbb R$ mnozica dopustnih resitev
- $f(x) = -x^2 - 2x + 4$
- $opt$ $=$ max
Optimalna resitev $x^* = -1$.
Preverimo: $-(-1)^2 - 2(-1) + 4 = 5$.

Optimizacijski problem je genericna oblika tega.
- podatki $a_0,a_1,...,a_n \in \mathbb Z; \ b,c \in \mathbb Q$
- naloga: max $a_0 + a_1x + ... + a_nx^n = \sum_{i=0}^n a_ix^i$ 
- p.p $x \geq b$ in $x \le c$ 
(ali pa
- podatki $a_0,a_1,...,a_n$ in $b_0,b_1,...,b_n$ in $b,c$
- max $\frac {\sum_{i=0}^n a_ix^i}{\sum_{j=0}^n b_jx^j}$ 
- p.p $x \geq b$ in $x \le c$ )


2. Kmetija (linearni problem)
Kmetija ima 50ha. Kmet bo posejal psenico, koruzo ali/in krompir.
Na razpolago je:
- 24K $\texteuro$ kapitala
- 5000 clovek-dni delovne dobe

| Poljscina | Potrebna delovna sila (clovek-dni/ha) | Stroski ($\texteuro$/ha) | Cisti dobicek ($\texteuro$/ha) |
| --------- | ------------------------------------- | ------------------------ | ------------------------------ |
| Psenica   | 60                                    | 400                      | 240                            |
| Koruza    | 80                                    | 600                      | 400                            |
| Krompir   | 100                                   | 480                      | 320                            |
Modeliranje
$x_1$ ... $\#$ha psenice
$x_2$ ... $\#$ha koruze
$x_3$ ... $\#$ha krompirja

- max $\{240x_1 + 400x_2 + 320x_3\}$ 
- p.p:
	- $60x_1 + 80x_2 + 100x_3 \le 5000$
	- $400x_1 + 600x_2 + 480x_3 \le 24000$
	- $x_1 + x_2 + x_3 \le 50$ 
	- ($x_1, x_2, x_3 \geq 0$)
To je primer linearnega problema.


3. Razdelitev jabolk
Imamo $2n$ jabolk z masami: $w_1,w_2,...,w_{2n}$. Hocemo jih razdeliti na 2 kosari tako, da ima vsaka kosara $n$ jabolk in je razlika v masi cim manjsa (optimizacijski problem, ne naloga).

Modeliranje:

a) prva moznost
- min | $\sum_{i \in A} w_i - \sum_{j \in [2n]\backslash A} w_j$ |
- p.p:
	- $A \subseteq [2n]$ ... mnozica indeksov
	- $|A| = n$  

b) druga moznost
- min | $\sum_{i \in [2n]} w_i x_i$ |
- p.p:
	- $\sum_{i \in [2n]} x_i = 0$ ... linearen pogoj
	- $x_1,x_2,...,x_{2n} \in \{-1,1\}$  $\forall i \in [2n]: x_i \in \{-1,1\}$ 

Neresljiv v polinomskem casu!


4. Bridge and torch problem
Ana, Barbara, Cvetka in Darja morejo ponoci preckati dolgi, ozek in sibek most. Cez most lahko gresta najvec dve osebi hkrati. Imajo eno svetilko, ki jo morajo uporabiti za preckanje mostu. Cas hoje cez most je
- A - 1min
- B - 2min
- C - 5min
- D - 10min
Ko hodita dva skupaj se steje maksimalen cas.

![[Pasted image 20240306175648.png]]

Modeliranje:

Uporabimo graf
- $V(G) = \{(S,b) \ | \ S \subseteq \{A,B,C,D\}, \ b \in \{0,1\}\}$ 
	- $S$ - osebe na levem (originalnem) bregu
	- $\{A,B,C,D\}\setminus S$ na desnem
	- $b =0$ svetilka na originalnem bregu
- $s$ = zacetno stanje $(\{A,B,C,D\}, 0)$
- $t$ = koncno stanje $(\emptyset, 1)$ 
- Najkrajsa pot v tem grafu od $s$ do $t$
- $E(G)$ povezave so
- $(S,b) \sim (S',b') \iff \displaylines{\{b+b' = 1\} \\ \{b=0 \to 1 \subseteq |S \backslash S'| \leq 2 \land S' \subseteq S\} \\ \{b=1 \to 1 \subseteq |S' \backslash S| \leq 2 \land S \subseteq S'\}}$ 

![[Pasted image 20240307192348.png]]

- Povezava $(S,b)(S',b')$ dobi "dolzino" max$_{x \in S \Delta S'}$ cas(x) - ($\Delta$ je simetricna razlika)
- Dolzina poti v tem grafu je vsota dolzin povezav, iscemo najkrajso
- Velikost grafa je $2^4\cdot 2 = 2^5 = 32$ ($\#$ vozlisc), v splosnem ($n$ oseb) bomo rabili $2^n \cdot 2$ vozlisc


5. Trener plavalne ekipe zeli sestaviti mesano plavalno stafeto 4x100m. Na razpolago je 6 plavalcev, cas posameznega plavalca na vsakem slogu:

| Plavalec | Hrbtno | Prsno | Delfin | Prosto |
| ---- | ---- | ---- | ---- | ---- |
| 1 | 65 | 73 | 63 | 57 |
| 2 | 67 | 70 | 65 | 58 |
| 3 | 68 | 72 | 69 | 55 |
| 4 | 67 | 75 | 70 | 59 |
| 5 | 71 | 69 | 75 | 57 |
| 6 | 69 | 71 | 66 | 59 |
Kako lahko trener doloci ekipo, ki plava najhitrejse?

Modeliranje:
Uporabimo dvodelni graf G
- $V(G) = \{1,2,3,4,5,6\} \sqcup \{H,Ps,D,Pt\}$ 
- {osebe} in {slogi}
- $E(G) = \{$is$\ |\ i \in \{osebe\}, s \in \{slogi\}\}$
- Vsaka povezava is ima tezo $w($is$) =$ cas da porabi oseba i s slogom s

![[Pasted image 20240307193042.png]]
Iscemo prirejanje velikosti 4, ki minimizira skupno vsoto utezi.
Prirejanje (matching) = podmnozica povezav brez skupnega vozlisca
- $D = \{$prirejanje moci 4$\}$ 
- $f: D \to \mathbb R$ 
- $M \to \sum_{e\in M}w(e)$ 
- opt = min

Optimizacijski problem
- Podatki: dvodelni graf $G = (A \sqcup B, E)$, $w: E \to \mathbb R$
- Naloga: min $\sum_{e\in M}w(e)$
- p.p 
	- $M \subseteq E$
	- $\sqcap$ prirejanje
	- $|\sqcap| = min\{|A|,|B|\}$ -> dotikamo vsa vozlisca v najmanjsem delu

Opomba: $n! \sim 2^{n\log n}$ 


6. Trgovski predstavnik Ljubljanske firme mora obiskati London, Madrid, Pariz in Rim ter na koncu nazaj v Ljubljano. Cene vozovnice (v 100euro) so

|     | Lj  | Lo  | Ma  | Pa  | Ri  |
| --- | --- | --- | --- | --- | --- |
| Lj  |     | 5   | 10  | 5   | 10  |
| Lo  | 5   |     | 10  | 1   | 5   |
| Ma  | 10  | 10  |     | 5   | 5   |
| Pa  | 5   | 1   | 5   |     | 1   |
| Ri  | 10  | 5   | 5   | 1   |     |
Kako cim ceneje?

Modeliranje:
Uporabimo graf G
- $V(G) = \{Lj,Lo,Ma,Pa,Ri\}$
- poln graf == vse povezave
- $w(x,y):$ cena od x do y (Ta primer je simetricen)

Optimizacijski problem:
- $D =$ Hamiltonov cikel
- $f: D \to \mathbb R$
- opt = min
- cikel $C \mapsto \sum_{e \in E(G)} w(e)$ 

- n mest 
	- $n!$ moznosti
	- DP (dinamicno) $2^n n^2$ 

Opombe:
V teoreticnem racunalnistvu imamo rajse odlocitvene probleme (DA/NE odgovori).
Optimizacijske probleme lahko vidimo kot odlocitvene probleme
$(D,f,opt) \to$ "Ali je za podan $\lambda \in \mathbb R$ : max$\{f(x) \ | \ x \in D\} \lt /\gt \lambda$ "
Ce znamo resevati optimizacijski problem, bomo znali resevati odlocitveni problem, obratno ne nujno. Obratno lahko, ce imamo dodatne predpostavke (na primer opt vrednost $\in \mathbb Z$).

## *Linearno programiranje*

D: Linearni program je optimizacijski problem (ali naloga) $(D,f,opt)$ pri cemer:
- $D\in \mathbb R^n$ je podana z linearnimi enakostmi in neenakostmi sorte ($\leq$ in $\geq$, ne velja pa $\lt,\gt$)
- $f$ je linearna
- $opt$ je bodisi $\max$ ali $\min$

Primer: $\min$ $2x_1 - 3x_2 + x_3$
p.p:
 $\displaylines {x_1 + x_2 \leq 4 \\ 3x_1 - x_2 - x_3 \geq 1 \\ 2x_2 - 5x_3 = -2 \\ x_1 \geq 0 \\ x_3 \leq 0}$   
 (...implicitno $x_2 \in R$)
- Pazi: $x_2 \neq 3$ tega ni v l.p! Ker to lahko pomeni $x_2 \gt 3$ ali $x_2 \lt 3$

D: Standardna oblika linearnega programa:
Linearni program je v standardni obliki, ko:
- iscemo $\max$
- vsi pogoji so tipa $\leq$ (brez $=, \geq$) - spremenljivke so na levi strani (oblike: $x_1+x_2 \leq k$ ali pa $f_i(x) \leq b_i$)
- vse spremenljivke so $\geq 0$ 

D: Ekvivalencnost programov = enostavno lahko dobimo optimalne resitve za en l.p. kot drugi l.p.

T: Vsak l.p. lahko ekvivalentno zapisemo v standardni obliki.
Dokaz: 
- $\min {f(x_1,...,x_n)} \leadsto -\max {-f(x_1,...,x_n)}$
- pogoj $f_i(x_1,...,x_n) \geq b_i \leadsto -f_i(x_1,...,x_n) \leq -b_i$ , pogoj $f_i(x_1,...,x_n) = b_i \leadsto \{\displaylines{f_i(x_1,...,x_n) \leq b_i \\ -f_i(x_1,...,x_n) \leq -b_i}\}$
- pogoj $x_i \leq 0 \leadsto$ nova spremenljivka $x_i' = -x_i$ (zamenjamo $x_i$ z $x_i'$) dobimo $x_i' \geq 0$  
- $x_i \in \mathbb R \leadsto$ nova spremenljivka $x_i'$ in $x_i'': x_i = x_i'-x_i''$ kjer $x_i' \geq 0$ in $x_i'' \geq 0$ 

Opomba: nenegativno $\neq$ pozitivno (prva vsebuje 0, druga ne).

Primer: 
- $\min 2x_1 - 3x_2 + x_3$ 
- p.p:
$\displaylines {x_1 + x_2 \leq 4 \\ 3x_1 - x_2 - x_3 \geq 1 \\ 2x_2 - 5x_3 = -2 \\ x_1 \geq 0 \\ x_3 \leq 0}$
...implicitno $x_2 \in\mathbb R$ 
Preoblikujemo v standardno obliko:
- $\displaylines{x_1 \geq 0 \\ x_2' - x_2'' \geq 0 \\ x_3 \geq 0}$
- $\max -2x_1 + 3(x_2'-x_2'') - (-x_3)$ oziroma $\max -2x_1 + 3x_2'- 3x_2'' +x_3$ 
- p.p:
$\displaylines {x_1 + x_2' - x_2'' \leq 4 \\ -3x_1 + x_2' -x_2'' + x_3 \leq -1 \\ 2x_2' - 2x_2'' + 5x_3' \leq -2 \\ -2x_2' + 2x_2'' - 5x_3' \leq 2}$ 

T: Ce originalni linearni program nima $n$ spremenljivk in $m$ pogojev, bomo dobili standardni l.p. ki ima najvec $2n$ spremenljivk in $2m$ pogojev
- $x_i\geq 0$ za $\forall$ spremenljivko ne stejemo kot pogoj

T: LP v standardni obliki lahko napisemo matricno ali z matricno notacijo
- $\max c^T\cdot x$ 
- p.p:
$\displaylines{Ax \leq b \\ x \geq 0}$ 
$c = \begin{bmatrix}c_1\\...\\ c_n\end{bmatrix} \in \mathbb R^n$ podane stevilke, $x = \begin{bmatrix}x_1\\...\\ x_n\end{bmatrix}$ spremenljivke

Primer (od prej - matricno):
- $\max \begin{bmatrix} -2 & 3 & -3 & 1 \end{bmatrix} \cdot \begin{bmatrix}x_1\\ x_2\\ x_3\\ x_4\end{bmatrix}$ 
- p.p:
$\begin{bmatrix} 1 & 1 & -1 & 0 \\ -3 & 1 & -1 & -1 \\  0 & 2 & -2 & -5 \\  0 & -2 & 2 & -5 \end{bmatrix} \cdot \begin{bmatrix}x_1\\ x_2\\ x_3\\ x_4\end{bmatrix} \leq \begin{bmatrix}4 \\ -1\\ -2\\ 2\end{bmatrix}$ , $x,c \in \mathbb R^n$ in $A\in\mathbb R^{m\times n}$  

$\begin{bmatrix}x_1\\ x_2\\ x_3\\ x_4\end{bmatrix} \geq \begin{bmatrix}0\\ 0\\ 0\\ 0\end{bmatrix} = 0_4$ 
- $D = \{x\in\mathbb R^n \ | \ Ax \leq b, x \geq 0\}$ - mnozica dopustnih resitev $D$ so vektorji, ki izpolnjujejo pogoja

#### *Nekaj malega o konveksnosti*

D: $A \subseteq \mathbb R^n$ je konveksna, ko:
- $\iff \forall x,y\in A \ \ \forall \lambda \in [0,1]$ velja: $(1-\lambda)x + \lambda y \in A$  
- $\iff \forall x,y\in A$ velja: $\{(1-\lambda)x + \lambda y \ | \ \lambda\in [0,1]\} \subseteq A$ 
- $\iff \forall x,y\in A$ velja $\overline {xy} \subseteq A$ (daljica ki povezuje x in y)

Primeri:
- $\mathbb R^2$
- ![[Pasted image 20240317090536.png]]

Opomba: 
- $x,y\in\mathbb R^n$
- Premica skozi x in y: $\{(1-\lambda)x + \lambda y \ | \ \lambda\in\mathbb R\} = \{\alpha x + \beta y \ | \ \alpha +\beta = 1\}$ 
- Daljica $\overline {xy} = \{(1-\lambda)x + \lambda y \ | \ \lambda\in [0,1]\} = \{\alpha x + \beta y \ | \ \alpha +\beta = 1, \alpha \geq 0, \beta \geq 0\}$  

D: Se nekaj lastnosti tock v $\mathbb R^n$
Za tocke $p_1,p_2,...,p_k \in \mathbb R^n$:
1. $\alpha_1p_1+\alpha_2p_2 + ... = \sum_{i=1}^k \alpha_ip_i$ pri cemer velja $\alpha_1+\alpha_2 + ... = \sum_{i=1}^k \alpha_i = 1$. Vse tocke ki jih lahko narisemo na ta nacin so afine kombinacije tock $p_1,p_2,...,p_k$.
2. $\sum_{i=1}^k \alpha_ip_i$ pri cemur $\sum_{i=1}^k \alpha_i = 1$ in $\alpha_1,\alpha_2,...,\alpha_k \geq 0$ so konveksne kombinacije tock $p_1,p_2,...,p_k$.
- daljica je mnozica vseh konveksnih kombinacij dveh tock
3. Prazna mnozica je konveksna mnozica.

T: Presek konveksnih mnozic je konveksna mnozica.
Dokaz: Naj bo $A_i, i\in I$ druzina konveksnih mnozic. $X = \cap_{i\in I} A_i$. Hocemo pokazati, da je $X$ konveksna mnozica.
$\forall x,y\in X:\displaylines{x\in \cap_{i\in I}A_i \to \forall i\in I: x\in A_i \\ y\in \cap_{i\in I}A_i \to \forall i\in I: y\in A_i}\} \implies A_i$ je konveksna. $\forall a\in I: \overline{xy}\in A_i$ 
Daljica je notri: $\overline{xy}\subseteq \cap_{i\in I}A_i = X$

T: Unija konveksnih mnozic ni konveksna mnozica.

T: Polprostor $\{x\in\mathbb R^n \ | \ a^Tx \leq b\}, a\in\mathbb R^n, b\in\mathbb R$ je konveksen.
Dokaz: Definiramo $A = \{x\in\mathbb R^n \ | \ a^Tx \leq b\}$ 
$\forall x\in A: a^Tx \leq b$
$\forall y\in A: a^Ty \leq b$
$\forall \lambda \in [0,1]: a^T((1-\lambda)x + \lambda y) = (1-\lambda)a^Tx + \lambda a^T y \leq (1-\lambda)b + \lambda b = b$ 
$\implies (1-\lambda)x + \lambda y \in A$.

Posledica: $\forall a\in\mathbb R^n, b\in \mathbb R$ je afin prostor $\{x\in\mathbb R^n \ | \ a^Tx = b\}$ je konveksen
Dokaz: $\{x\in\mathbb R^n \ | \ a^Tx = b\}$ je presek dveh polprostorov:
- $a^Tx\leq b$ 
- $-a^Tx\geq -b$ 
Presek dveh konveksnih polprostorov je konveksen.

D: Politop je presek polprostorov.

T: 
1. Mnozica dopustnih resitev l.p. je konveksna.
2. Mnozica optimalnih resitev l.p. je konveksna.
Dokaz:
1. Mnozica dopustnih resitev je $D=\{x\in\mathbb R^n \ | \ x\geq 0, A^Tx \leq b\}$ politop (presek polprostorov), torej presek konveksnih mnozic.
2. 
- Ce ne obstajajo optimalne resitve $\to$ prazna mnozica je konveksna
- Ce obstajajo: gledamo optimalno vrednost
Naj bo $v^*$ optimalna vrednost. Mnozica optimalnih resitev je $\{x\in\mathbb R^n \ | \ x\geq 0, A^Tx\leq b, c^Tx = v^*\}$ (kot dopustne resitve z dodatkom: optimalnost teh resitev) politop, kar je zopet presek konveksnih mnozic.

#### *Graficno resevanje LP za $n=2$*

Primer: 
$\max 2x+y$
p.p. 
$\displaylines{2x+5y \leq 22 \\ x+y\leq 5 \\ 3x+y \leq 9 \\ x,y\geq 0}$ 
![[Pasted image 20240318152042.png]]
Rdeca linija je funkcija, ki jo zelimo maksimizirati (pri 2x+y=3, potuje cez cel omejen del).
Ogljisca obmocja bodo optimumi.

#### *Simpleksna metoda (sx)*

D: Predpostavimo standardno obliko:
$\max c^T x$ 
p.p:
$\displaylines{A^Tx \leq b \\ x \geq b}$ 
Dodatno predpostavimo $b\geq 0$ ($\to x=0$ je dopustna resitev)
$Ax\leq b = \displaylines{{a_1}^Tx\leq b_1 , \ b_1\geq 0 \\ {a_2}^Tx\leq b_2 , \ b_2\geq 0 \\ ... \\ {a_m}^Tx\leq b_m , \ b_m\geq 0}$ 

D: Slovar je sistem linearnih enacb, kjer $m$ spremenljivk izmed $\{x_1,..,x_n,x_{n+1},...,x_m\}$, takoimenovane bazne spremenljivke zapisemo v odvisnosti od drugih spremenljivk imenovane nebazne spremenljivke.

D: Slovar je dopusten, ce so vsi prosti cleni nenegativni.
Vsakemu dopustnemu slovarju ustreza ena bazna dopustna resitev (BDR).
- Nebazne spremenljivke imajo vrednost 0
- Bazne spremenljivke imajo vrednost prostega clena

**Primer: Kmetija

$\max \ 3x_1 + 5x_2 + 4x_3$
p.p
$\displaylines{3x_1 + 4x_2 + 5x_3 \leq 250 \\ 10x_1 + 15x_2 + 12x_3 \leq 600 \\ x_1 + x_2 + x_3 \leq 50 \\ x_1,x_2,x_3 \geq 0}$ 

Za vsak pogoj ${a_i}^Tx \leq b_i$ vpeljemo novo spremenljivko $x_{n+i} = b^T - {a_i}^Tx$ 
$\begin{cases} x_1,...,x_n &\text{prvotne spremenljivke} \\ x_{n+1},...,x_{n+m} &\text{dopolnilne spremenljivke} \end{cases}$ 

Dodamo pogoj $x_{n+i} \geq 0 \ \forall i\in \{1,..,m\}$ 
$\max \ 3x_1 + 5x_2 + 4x_3$
p.p
$\displaylines{3x_1 + 4x_2 + 5x_3 + x_4 = 250 \\ 10x_1 + 15x_2 + 12x_3 + x_5 = 600 \\ x_1 + x_2 + x_3 + x_6 = 50 \\ x_1,...,x_6 \geq 0}$ 

Predstavljeno v obliki slovarja 
$\displaylines{x_{n+1} = b_1 - {a_1}^Tx \\ x_{n+2} = b_2 - {a_2}^Tx \\ ... \\ x_{n+m} = b_m - {a_m}^Tx}$ (leve strani so bazne, x-i na desni pa nebazne)
Funkcional $z = c^Tx$ 

Resimo:
$\displaylines{x_4 = 250 - 3x_1 - 4x_2 - 5x_3  \\ x_5 = 600 - 10x_1 - 15x_2 - 12x_3 \\ x_6 = 50 - x_1 - x_2 - x_3 \\ z=3x_1 + 5x_2 +4x_3}$  
- leva stran = bazne
- stevilke = prosti cleni
- vsi ostali $x$-i = nebazne
- celostna stvar = slovar
- $z$ = funkcional

To je prvi oziroma zacetni slovar. Ker je $b\geq 0$ je zacetni slovar dopusten. Doloci eno bazno dopustno resitev (BDR).
$(x_1=0,x_2=0,x_3=0,x_4=250,x_5=600,x_6=50)$ 

Ena iteracija: Zamenjamo eno nebazno spremenljivko z eno bazno. Ena spremenljivka vstopi v bazo, druga izstopi (ne nakljucno).
- Za vstopajoco spremenljivko izberemo poljubno nebazno spremenljivko s pozitivnim koeficientom. (V nasem primeru bomo izbrali $x_2$)
- Za izstopajoco spremenljivko izberemo tisto, ki najvec omejuje vstopajoco spremenljivko

$x_4 \geq 0 \to 250-4x_2 \geq 0 \to x_2 \leq \frac{250}{4}$
$x_5 \geq 0 \to 600-15x_2 \geq 0 \to x_2 \leq \frac{600}{15}=40$ (najbolj omejuje $\implies x_5$ izstopa) 
$x_6 \geq 0 \to\ 50-x_2 \geq 0 \to x_2 \leq 50$ 

Pivotna vrstica $x_5 = 600 - 10x_1-15x_2-12x_3$ 

Izrazimo: $x_2 = \frac{600}{15} -\frac{10}{15}x_1 - \frac{12}{15}x_2 - \frac{1}{15}x_5$ 

Drugi slovar:
$\displaylines{x_2 = 40 -\frac{2}{3}x_1 - \frac{4}{5}x_2 - \frac{1}{15}x_5 \\ x_4 = 90 - \frac{1}{3}x_1 - \frac{9}{5}x_3 + \frac{4}{15}x_5  \\ x_6 = 10 - \frac{1}{3}x_1 - \frac{1}{5}x_3 + \frac{1}{15}x_5 \\ z=200 - \frac{1}{3}x_1 +(0\cdot x_3) -\frac{1}{3}x_5}$ 

![[Pasted image 20240318164816.png]]

BDR:  $(x_1=0,x_2=0,x_3=0,x_4=250,x_5=600,x_6=50) \leadsto (x_1=0,x_2=40,x_3=0,x_4=90,x_5=0,x_6=10)$ 

Ker $x_1\geq 0$ in $x_5 \geq 0$ velja, da $z$ doseze najvecjo vrednost $200$. Po drugi strani $z=200$ dosezemo, ce $x_1=x_3=x_5=0$, to pomeni, da je $200$ optimalna vrednost in trenutna b.d.r je optimalna resitev.


P:
V splosnem ko dosezemo funkcional, kjer so vsi koeficienti nepozitivni, dobimo optimalno vrednost in sicer pri prostem clenu. BDR v tem trenutku je optimalna resitev.
Optimalna resitev
$\to$ samo za linearni program (brez dopolnilnih spremenljivk)
$\to$ za originalni problem bi vzeli $x_1,x_3=0, x_2=40$ 

Na koncu:
$z=200-\frac{x_1}{3}- \frac{x_5}{5}$ 
Pri $x_3$ imamo fleksibilnost, ker se ne pojavi v $z$. Moramo paziti, da vse spremenljivke ostanejo $\geq 0$.
- $x_2 \geq 0 \to 40-\frac{4}{5}x_3 \geq 0 \to x_3 \leq 50$
- $x_4 \geq 0 \to 90-\frac{9}{5}x_3 \geq 0 \to x_3 \leq 50$
- $x_6 \geq 0 \to 10-\frac{1}{5}x_3 \geq 0 \to x_3 \leq 50$ 
Vsak $x_3\in[0,50]$ doloci eno optimalno resitev.

Torej za to optimalno nalogo imamo druzino optimalnih resitev:
$\text{opt} = \{(x_1=0,x_2=40-\frac{4}{5}t,x_3=t) \ | \ t\in[0,50]\} =$ daljica med $(0,40,0)$ in $(0,0,50)$ 

Podobno se zgodi, ko v zadnjem slovarju so nebazne spremenljivke z koeficientom 0 pri $z$.
Ce so vsi koef $\lt 0$, je b.d.r edina resitev.

T:
- V funkcionalu lahko izberemo poljubno spremenljivko z pozitivnim koeficientom za vstopajoco spremenljivko.

Primer:
$x_5 = 10 - x_2 + x_3 -10x_4$ ... $x_5\geq 0 \to 10+x_3 \geq 0$ in $x_3\geq 0 \to x_3 \leq \infty$ nimamo zgornje meje
.
.
.
$z = 100 + \dots + \underline{2x_3} - 3x_4$ 
vstop: $x_3$ 

T:
- Ce je v enacbi slovarja vstopajoca spremenljivka z pozitivnim koeficientomm ta vrstica nikoli ne omejuje in nikol ni pivotna vrstica
- Ce je pri vseh enacbah slovarja vstopajoca spremenljivka s pozitivnim koeficientom potem je naloga/program neomejena in lahko dobimo poltrak znotraj mnozice dopustnih resitev, kjer se ciljna funkcija poveca.

Primer:
$x_5 = 10 - x_2 + x_3 - 10x_4, \ \ x_3\leq\infty$
$x_1 = 20 - 3x_2 + 2x_3 - 5x_4, \ \ x_3\leq\infty$
$x_6 = 15 + 4x_3 + 3x_4, \ \ x_3\leq\infty$  
$z=100+\underline{2x_3}+3x_4$ (vstopi)
Dopustna resitev za $\forall t\geq 0$: $(x_1= 20+2t, x_2=0,x_3=t,x_4=0,x_5=10+t,x_6=15+4t)$ -dobimo tocke 
Doseze vrednost: $100+2t$ 

T:
- Prosti clen funkcionala se ne zmanjsa, lahko pa ostane nespremenjen

Primer:
$x_4=-3x_3+4x_5,$    $x_4\geq 0 \to x_3 \leq 0$  ... ta najbolj omejuje, torej $x_4$ izstopi
.
.
.
$z=100 + \underline{2x_3} - 3x_5$
Dobimo nov $z=100+2(4x_5-x_4)-3x_5 = 100 \pm ...$ prosti clen se ne spremeni

D: Ko je v enacbi, kjer izstopa spremenljivka, prosti clen enak 0, imamo izrojeno bazo.

T:
- Prosti koeficienti so nenegativni

Vpr: Ali se postopek konca? 
Da in ne.
Stevilo baz = $\binom{n+m}{n} = \binom{n+m}{m}$ 
Baza = izberemo $m$ spremenljivk izmed vseh
Lahko imamo cikle $b_1\to b_2\to ... \to b_k \to ... \to b_k$ npr. imamo cikel pri bazi $k$ 
V praksi ni ciklov, ampak teoreticno je mogoce.

D: Blandova pravila (Bland's rule): 
- Med kandidatkami za vstopajoco spremenljivko (koeficient $\gt 0$) izberemo tisto z najmanjsim indeksom
- Med kandidatkami za izstopajoco spremenljivko, ki omejujejo isto, izberemo tisto z najmanjsim indeksom

I: Simpleksni postopek z Blandovim pravilom se ustavi po koncno mnogih korakih.

Postopek:
- Stevilo korakov oz. ucinkovitost 
	- v praksi - odlicno
	- $\sim m\cdot \log n \sim 3m$ korakov (koraki = $\#$slovarjev)

Vpr: Kako izberemo vstopajoco spremenljivko?
- Blandova pravila
- Spremenljivko z najvecjim koeficientom 
- Spremenljivko, ki bo najvec povecala prosti koeficient funkcionala v enem koraku
- Nakljucno izmed spremenljivk s koeficientom $> 0$ 
Za nobeno pravilo vemo, da dela v polinomskem casu. Za vsako deterministicno pravilo ljudje najdejo primer, ki porabi eksponencialno stevilo korakov.

D: Klee-Minty cubes
Pravzaprav, ce bi uporabil najkrajso pot v prostoru slovarjev, ne vemo koliko slovarjev rabimo. 

T:
- BDR je ogljisce $D = \{x\in\mathbb R^n \ | \ Ax \leq b, \ x \geq 0\}$ (sx metoda gre od ogljisca do ogljisca v $D$)
- Simpleksna metoda (osnovna) za $b \geq 0$ 
	$\to$ Ne moremo izbrati izstopajoco spremenljivko $\to$ Naloga je neomejena (dobimo poltrak)
	$\to$ Postopek konca, dobimo optimalno resitev, ki je BDR
- Dvofazna simpleks metoda, kaj delamo ko $b\ngeq 0 \ (=\exists i: b_i\lt 0)$ 

D: Dvofazna simpleks metoda
1. Faza: Uporabimo sx metodo (osnovno), da dolocimo, ali je problem dopusten in dobimo BDR oz. zacetni slovar.
2. Faza: Uporabimo sx metodo z zacetnim slovarjem.

Zgled: Imamo dve vrsti vitaminskih granulat: polirit in olirit
Vsebujeta vitamine B, C, D
Sestava in dnevne potrebe:

| Vrsta              | B   | C   | D   | Cena |
| ------------------ | --- | --- | --- | ---- |
| P                  | 1   | 4   | 1   | 12   |
| O                  | 1   | 1   | 2   | 10   |
| Dnevne <br>potrebe | 7   | 13  | 8   |      |
Zapisemo kot linearni program:
$x_1$ ... $\#$P
$x_2$ ... $\#$O
Program:
- $\min 12x_1 + 10x_2 \leadsto \max -12x_1-10x_2$ 
- p.p:
$\displaylines{x_1 + x_2 \geq 7 \\ 4x_1 + x_2 \geq 13 \\ x_1 + 2x_2 \geq 8 \\ x_1,x_2\geq 0} \leadsto \displaylines{-x_1 - x_2 \leq 7 \\ -4x_1 - x_2 \leq -13 \\ -x_1 - 2x_2 \leq -8 \\ x_1,x_2\geq 0}$ 
$x_1,x_2 = 0$ ni dopustna resitev
Ideja: Vpeljemo novo spremenljivko $x_0 \geq 0$ in resujemo 
- $\min x_0$
- p.p:
$\displaylines{-x_1-x_2 \leq -7+x_0 \\ -4x_1 - x_2 \leq 13 +x_0 \\ -x_1 - 2x_2 \leq -8+x_0 \\ x_1,x_2,x_0 \geq 0}$ ... damo $x_0=13$ in dobimo $x_1=x_2=0$ dopustno resitev

Vpr: Kaj delamo?
Geometrijsko premikamo pogoje.

D: V splosnem
- $\max c^Tx \leadsto \min x_0$ 
- p.p:
$\displaylines{Ax\leq b \\ x\geq 0} \leadsto \displaylines{Ax\leq b+ \begin{bmatrix} x_0 \\ ... \\ x_0 \end{bmatrix} \\ x_0 \geq 0 \\ x\geq 0}$  (program $\pi\to\tilde{\pi}$ )

T: $\pi$ je dopusten program, natanko tedaj ko ima $\tilde{\pi}$ optimalno vrednost 0.
Dokaz:
- $(\rightarrow)$ 
Recimo, da $\pi$ je dopusten, $\exists$ vektor $x=(x_1,...,x_n)$, ki zadosca $Ax\leq b$ in $x\geq 0$.
Sledi: Vektor $\begin{bmatrix} x_0 = 0 \\ ... \\ x_n \end{bmatrix}$ je dopustna resitev za $\tilde \pi$ in je optimum z vrednostjo 0.
- $(\leftarrow)$
 $\tilde \pi$ ima optimalno resitev $\begin{bmatrix} {x_0}^*\\ ... \\ {x_n}^* \end{bmatrix}$, ki doseze vrednost 0. Torej ${x_0}^* = 0$ in $\begin{bmatrix} {x_1}^*\\ ... \\ {x_n}^* \end{bmatrix}$ je dopustna resitev za $\pi$.

D:
1. Faza: Uporabimo sx. metodo za resevanje pomoznih problemov - $\tilde \pi$. Imamo pa posebna pravila:
	- V bazo vstopi $x_0$
	- Iz baze izstopi spremenljivka z najmanjsim prostim clenom in tako dobimo BDR

Primer (nadaljevanje):
Dopolnilne spremenljivke
$x_4 = -7 + x_0 + x_1 + x_2$
$x_5 = -13 + x_0 + 4x_1 + x_2$
$x_6 = -8 + x_0 + x_1 + 2x_2$
$w=-x_0$ (w namesto z - zgodovinsko)
Velja: $\min x_0 = -\max(-x_0)$ 
Vstopi $x_0$, izstopi pa $x_5$, ker $-13\leq -7$ in $-13\leq -8$.

$x_2\leq 13$ ... $x_0 = 13-4x_1-x_2+x_5$
$x_2\lt \infty$ ... $x_4=...=6-3x_1+x_5$     $13,6,5\geq 0$ nenegativni
$x_2\lt \infty$ ... $x_6 = 5-3x_1 + x_2-x_5$ 
$\downarrow$ izstopi   $w=-13+4x_1+x_2-x_5$ (vstopi $x_2$, lahko tudi $x_1$)
$x_0$
Zdaj imamo BDR za pomozni program

Nov slovar (3):
$x_2 = 13-x_0-4x_1+x_5$
$x_4 = 6-3x_1+x_5$ 
$x_6=18-x_0-7x_1+2x_5$ 
$w=-13+4x_1+13-x_0-4x_1+x_5-x_5 = -x_0$ 
Optimalna vrednost pomoznega problema $\tilde\pi$ je $w^* = 0$ in ena optimalna resitev je $(x_0=0,x_1=0,x_2=13,x_4=6,x_5=0,x_6=18)$ 
$(x_1=0,x_2=13,x_4=6,x_5=0,x_6=18)$ pa je dopustna resitev prvotnega problema $\pi$.

Spremenimo funkcional in zbrisemo $x_0$ 
$x_2 = 13-4x_1+x_5$
$x_4 = 6-3x_1+x_5$ 
$x_6=18-7x_1+2x_5$ 
$z=-12x_1-10x_2 = -12x_1 - 10(13-4x_1+x_5) = -130 +28x_1-10x_5$ 

Nadaljujemo: $x_1$ vstopi, $x_4$ izstopi
$x_1=2-\frac{1}{3}x_4 + \frac{1}{3}x_5$
$x_2=5+\frac{4}{3}x_4 - \frac{1}{3}x_5$
$x_6=4+\frac{7}{3}x_4 - \frac{1}{3}x_5$
$z=-74-\frac{27}{3}x_4-\frac{2}{3}x_5$

Konec, ker so vsi koef < 0. Optimalna vrednost $z^*=-74$. Optimalna resitev $x_1=2,\ x_2=5$ 
- 2g od P
- 5g od O
- cena je 74 na dan
7 enot Vit B, 13 enot Vit C, 12 enot Vit D(prevec)

D: Na koncu 1.faze so 3 moznosti:
- $w^* \lt 0 \to$ prvotni problem nima dopustne resitve
- $w^*=0\to$ zacnemo 2.fazo
- $w^* = 0$ in na koncu $w=-x_0$ 
Te moznosti se izogibamo, tako da:
Ce je $x_0$ v bazi in lahko izstopi, izstopi. S tem skrbimo, da je $x_0$ na desni strani
S tem imamo na koncu:
$w=-x_0 \ +$ nekaj odvisno od drugih spremenljivk ($=0$)

Shema:
![[Pasted image 20240320162907.png]]

I: Linearni program (v standardni obliki). Velja:
- ce ima dopustno resitev ima BDR
- ce ima optimalno resitev ima bazno optimalno resitev
- LP je lahko:
	- bodisi nedopusten
	- bodisi neomejen
	- bodisi ima optimalno resitev
(Ne more biti neomejen in brez optimalne resitve).

Opomba: 
- sx. metoda ne dela v polinomskem casu
- so drugi algoritmi, ki delajo v polinomskem casu ob predpostavki, da so vhodni podatki v $\mathbb {Z, Q}$ 
- ellipsoid method (teoreticno-polinomsko, v praksi ne)
- euteniov-point method (teoreticno in v praksi - polinomsko)

### *4.predavanje*

1. Denimo, da so vhodni podatki cela stevila $\beta$ bitov 
$|a_{ij}| \leq 2^{\beta}$, $|b_i| \leq 2^{\beta}$, $|c_j| \leq 2^{\beta}$ za $\forall i,j$
Optimalna resitev $x^*$ je resitev linearnega sistema:
$A'x = b'$, 
- $A'$ podmatrika $A$
- $b'$ podvektor $b$
- $A'$ kvadratna
Zaradi Cramerjevega pravila velja: 
- ${x_1}^* = \frac{\det (A'_j)}{\det (A')}$ ($A_j'$ kjer v $A'$ $j$-ti stolpec zamenjamo z $b'$)
- $\det (A') \leq n! (2^{\beta})^n$ 
LP:
- $\max c^T \cdot x$
- p.p:
$\displaylines{Ax \leq b \\ x \geq 0 \\ Ax + \begin{bmatrix} x_{n+1} \\ ... \\ x_{n+m} \end{bmatrix} = b}$ enakost nam da sistem linearnih enacb

$\#$ bitov $= \log_2(n!(2^3)^n) \leq n\log_2 n+n\cdot \beta$  ($n!\leq n^n$)

Ne poznamo algoritma, ki uporabi polinomsko stevilo aritmeticnih operacij. To je relevantno, ko so vzhodni podatki iracionalni ($\sqrt 2, \sqrt 2 \cdot \sqrt3$)
Obstajajo zelo dobri algoritmi, ko stevilo spremenljivk $n = O(1)$.

Linearno programiranje se se zmeraj veliko raziskuje (npr. LP with violations - ne upostevas kaksnega pogoja, Smooth analysis - simpleksna metoda, ...)

## *Dualnost pri linearnem programiranju*

Notacija: 
- $D(\pi)$ - mnozica dopustnih resitev za LP $\pi$
- Uporabimo $i$ kot indeks za pogoje, $j$ kot indeks za spremenljivke 
- $\begin{bmatrix}A\end{bmatrix}$ (stolpci - $j\in[n]$, vrstice - $i\in[m]$), velikost matrike je $n\cdot m$  
- Torej:
	- $\pi = \max \sum_{j=1}^n c_jx_j$ 
	- p.p: (v standardni obliki)
 $\displaylines{\sum_{j=1}^n a_{ij}x_j \leq b_i \\ x_j \geq 0}$ (za $i \in [m]$ in $j \in [n]$)

D: Dualni program za
- $\pi = \max c^T \cdot x$
- p.p:
$\displaylines{Ax \leq b \\ x \geq 0}$ 
je 
- $\pi' = \min b^T y$
- p.p:
$\displaylines{A^Ty \geq c \\ y \geq 0}$ 

D: Dualni problem (brez matricne notacije)
- $\pi' = \min \sum_{i=1}^m b_iy_i$
- p.p:
$\displaylines{\sum_{i=1}^m a_{ij}y_i \geq b_j \\ y_i \geq 0}$  (za $j \in [n]$ in $i \in [m]$)

Primer:
- $\max 3x_1 + 5x_2 + 4x_3$
- p.p 
$\displaylines {3x_1 + 4x_2 + 5x_3 \leq 250 \\ 10x_1 + 15x_2 + 12x_3 \leq 600 \\ x_1 + x_2 + x_3 \leq 50 \\ x_1,x_2,x_3 \geq 0}$  $\displaylines{/\cdot y_1 \\ /\cdot y_2 \\ /\cdot y_3 \\ \ }$ 

Dualni program:
- $\min 250y_1 + 600y_2 + 50y_3$
- p.p
$\displaylines {3y_1 + 10y_2 + y_3 \geq 3 \\ 4y_1 + 15y_2 + y_3 \geq 5 \\ 5y_1 + 12y_2 + y_3 \geq 4 \\ y_1,y_2,y_3 \geq 0}$ 

?????

#### *5.predavanje*

I: (Dualno dopolnjenje - DD) Imamo program $\pi$ v standardni obliki, $x\in D(\pi), y\in D(\pi')$ 
$\displaylines{x\in \mbox{Opt}(\pi) \\ \\ y\in \mbox{Opt}(\pi')} \iff \displaylines{\mbox{za} \ \  i=1,...,m \ \ \mbox{je} \ \sum_{j=1}^n a_{ij}x_i=b_i \ \ \mbox{ali}\ \ y_i=0 \\ \mbox{za} \ \ j=1,...,n \ \ \mbox{je} \ \sum_{i=1}^m a_{ij}y_i=c_j \ \ \mbox{ali} \ \ x_j=0}$ 
in
$A\lor B = \neg B \to A = \neg A \to B \iff \displaylines{\mbox{za} \ \  i=1,...,m \ \ \mbox{ce} \ \sum_{j=1}^n a_{ij}x_i\lt b_i \ \ \mbox{potem}\ \ y_i=0 \\ \mbox{za} \ \ j=1,...,n \ \ \mbox{ce} \ x_j\gt 0 \ \ \mbox{potem} \ \sum_{i=1}^m a_{ij}y_i=c_j}$ 
Dokaz: Sledi dokaz ŠID:
$(L:=)= c^Tx=\sum_{j=1}^nc_jx_j \leq \sum_{j=1}^n(\sum_{i=1}^ma_{ij}y_i)x_j = \sum_{i=1}^m(\sum_{j=1}^na_{ij}x_j)y_i \leq \sum_{i=1}^mb_iy_i = b^Ty = (=:D)$ 
Ker velja:
- $c\leq A^Ty, \ x\geq 0$
- $y\geq 0, \ Ax \leq b$ 
KID:
$L=D \iff x\in\mbox{Opt}(\pi) \ \mbox{in} \ y\in\mbox{Opt}(\pi')$ ($\Leftarrow$ KID, $\Rightarrow$ SID)
$\displaylines{x\in \mbox{Opt}(\pi) \\ \\ y\in \mbox{Opt}(\pi')} \iff \displaylines{(\sum_{i=1}^m a_{ij}y_i)x_j=c_jx_j \ \ j=1,...,n \\ (\sum_{j=1}^n a_{ij}x_j)y_i=b_iy_i \ \ i=1,...,m} \iff \displaylines{(\sum_{i=1}^m a_{ij}y_i - c_j)x_j=0 \ \ j=1,...,n \\ (\sum_{j=1}^n a_{ij}x_j-b_i)y_i=0 \ \ i=1,...,m} \overset{(A\cdot B=0 \implies A=0 \ \mbox{ali} \ B=0)}{\iff} \displaylines{\sum_{i=1}^m a_{ij}y_i = c_j \ \ \mbox{ali} \ \ x_j=0 \ (j=1,...,n) \\ \sum_{j=1}^n a_{ij}x_j=b_i \ \ \mbox{ali} \ \ y_i=0 \ (i=1,...,m)}$ 
Primer: 
- $\max 3x_1 + 5x_2 + 4x_3$
- p.p 
$\displaylines {3x_1 + 4x_2 + 5x_3 \leq 250 \\ 10x_1 + 15x_2 + 12x_3 \leq 600 \\ x_1 + x_2 + x_3 \leq 50 \\ x_1,x_2,x_3 \geq 0}$ 

...???

Intuicija: Za neizvojene primere imamo neko sorto zveznosti: iste enacbe dolocijo optimum za dovolj mejhne perturbacije. ?
- KID
$z^* = c^Tx^* = b^Ty^*$ 
$(b^T + \Delta b^T)y^* = b^Ty^* + (\Delta b^T)y^* = z^* + \Delta z^*$ 

Primer: Kmetija
- $\max 3x_1 + 5x_2 + 4x_3$
- p.p 
$\displaylines {3x_1 + 4x_2 + 5x_3 \leq 250 \\ 10x_1 + 15x_2 + 12x_3 \leq 600 \\ x_1 + x_2 + x_3 \leq 50 \\ x_1,x_2,x_3 \geq 0}$ 

|                       | $x^*_1 = 0$ | $x^*_2 = 40$     | $x^*_3 = 0$     |            |
| --------------------- | ----------- | ---------------- | --------------- | ---------- |
| $y^*_1 = 0$           | $3\cdot 0$  | $+ \ 4\cdot 40$  | $+ \ 5\cdot 0$  | $\leq 250$ |
| $y^*_2 = \frac{1}{3}$ | $10\cdot 0$ | $+ \ 15\cdot 40$ | $+ \ 12\cdot 0$ | $\leq 600$ |
| $y^*_3 = 0$           | $0$         | $+ \ 40$         | $0$             | $\leq 50$  |
Ce bo kmet povecal $600 + \Delta b_2$, za dovolj majhen $\Delta b_2$, bo dobicek povecal za $\Delta z^* = \frac{1}{3}\Delta b_2$ .
$600$ je denar/kapital. Kmetu se splaca posojilo, ce bo placal nazaj manj kot $33\%$ (oz. tretjina). Moramo upostevati vse stroske, ki spadajo notri: obresti, zavarovanje, cas za urejanje...

$Y_i^*$ - mejna vrednost iste dobrine (shadow price)

#### *Dual splosnega LP*

I: Ce je 
$\pi = \max \sum_{j=1}^n c_jx_j$ in
p.p 
$\displaylines{\sum_{j=1}^n a_{ij}x_j \leq b_i \ (i=1,...,m') \\ \sum_{j=1}^n a_{ij}x_j = b_i \ (i=m'+1,...,m) \\ x_j\geq 0 \ (j=1,...,n') \\ x_j\in\mathbb R \ (j=n'+1,...,n)}$ 
potem je dualni program
$\pi' = \min \sum_{i=1}^m b_iy_i$ in
p.p 
$\displaylines{\sum_{i=1}^m a_{ij}y_i \geq c_j \ (j=1,...,n') \\ \sum_{i=1}^m a_{ij}y_i = c_j \ (j=n'+1,...,n) \\ y_i\geq 0 \ (i=1,...,m') \\ y_i\in\mathbb R \ (i=m'+1,...,m)}$ 

I: Matricni vidik
$\pi = \max {c_1}^Tx_1 + {c_2}^Tx_2$
p.p
$\displaylines{A_{11}x_1+A_{12}x_2 \leq b_1 \\ A_{21}x_1+A_{22}x_2 = b_2 \\ x_1\geq 0 \ \ x_1\in\mathbb R^{n'} \\ x_2\in\mathbb R^{n-n'}}$ 
Dualni program:
$\pi' = \min {b_1}^Ty_1 + {b_2}^Ty_2$
p.p
$\displaylines{{A_{11}}^Ty_1+{A_{21}}^Ty_2 \geq c_1 \\ {A_{12}}^Ty_1+{A_{22}}^Ty_2 = c_2 \\ y_1\geq 0 \ \ y_1\in\mathbb R^{m'}\\ y_2\in\mathbb R^{m-m'}}$ 

| $A_{11}$ | $A_{12}$ | $m'$   |
| -------- | -------- | ------ |
| $A_{21}$ | $A_{22}$ | $m-m'$ |
| $n'$     | $n-n'$   |        |
Dokaz:
??? SLIKA

??? 

## Matricne igre

??????

Primer: $A$ matricna igra $m\times n$
	  j
i $\begin{bmatrix} . & ... & . \\ . & a_{ij} & . \\ . & ... & . \end{bmatrix}$ 
Koliko placa prvi igralec drugemu (i-prvi, j-drugi).
Prvi igralec uporabi mesano strategijo (cisto strategijo - ??)
$\Delta_1 = \{ x =\begin{bmatrix} x_1 \\ ... \\ x_m \end{bmatrix} \ |$ za katero velja $\sum_{i\in [m] }x_i =1 \ \land \ x_1,...,x_m \geq 0\}$ 
= mnozica strategij za 1. igralca
SLIKE

Za 2.igralca:
$\Delta_2 = \{ \begin{bmatrix} y_1 \\ ... \\ y_n \end{bmatrix}\in\mathbb R^n \ |$ za katero velja $\sum_{j = 1}^n y_j =1 \ \land \ y_1,...,y_n \geq 0\}$ 
$E(x,y) =$ pricakovano placilo 2.igralca 1.igralcu.
Ko 1.igralec uporabi x in 2.igralec uporabi y.
= $\sum_{i,j}x_iy_ja_{ij} = sum_{i=1}^m\sum_{j=1}^n x_iy_ja_{ij} = x^TAy = \sum_{i=1}^m(\sum_{j=1}^n a_{ij}y_j)x_i = \sum_{i=1}^m ([Ay]_i)x_i = \langle x,Ay\rangle = \langle A^Tx,y\rangle$ 
($x_iy_j$ - verjetnost da v igri izbereta $(i,j)$)

Ce 1.igralec uporabi x, bo vsaj dobil
$\min_{y\in\Delta_2} x^TAy$
Ce 2.igralec uporabi y, bo najvec placal
$\max_{x\in\Delta_1} x^TAy$ 

T: Velja
$\max_{x\in \Delta_1} \min_{y\in\Delta_2} x^TAy \leq \min_{y\in\Delta_2} \max_{x\in \Delta_1} x^TAy$
Dokaz:
$\forall x\in\Delta_1,\ y\in\Delta_2$
$\min_{y'\in\Delta_2} x^TAy' \leq x^TAy \leq  \max_{x'\in \Delta_1} (x')^TAy \ \ /\max_x  /\min_y$ 
$\max_{x\in \Delta_1} \min_{y'\in\Delta_2} x^TAy' \leq \ \ \ \leq \min_{y\in\Delta_2} \max_{x'\in \Delta_1} (x')^TAy$ 

D: Ciste strategije:
$x^{(i)}=\begin{bmatrix}0 \\ ... \\ 0 \\ 1 \\ 0 \\ ... \\ 0\end{bmatrix}i$, $\forall i\in [m]$ 
$y^{(j)} = \begin{bmatrix}0 \\ ... \\ 1 \\ ... \\ 0\end{bmatrix}j$, $\forall j\in [n]$ 
$x^TAy^{(j)} = [x^TA]_j =$ element s polozajem j v vektorju $x^TA$
$(x^{(i)})^TAy = [Ay]_i =$ element na i-tem mestu v vektorju $Ay$ 

T: $\forall x\in\Delta_1:$ $\min_{y\in\Delta_2} x^TAy = \min_{j\in[n]} x^TAy^{(j)} =$  min. element v vektorju $x^TA$ 
Dokaz:
Intuicija: $x^TAy$ = utezeno povprecje stevil: $\displaylines{[x^T]_1 \\ [x^T]_2 \\ ... \\ [x^T]_n }$ 
Definiramo $s=\min_{j\in[n]}x^TAy^{(j)}$
$\min_{y\in\Delta_2} x^TAy \leq \min_{y\in [n]} X^TAy^{(j)} = s$ (velja ker: $y^{(j)} \in \Delta_2$)
$\forall y\in\Delta_2: x^TAy = \sum_{j=1}^n ([x^TA]_j)y_j = \sum_{j=1}^n (x^TAy^{(j)})y_j \geq \sum_{j=1}^n s\cdot y_j = s\cdot \sum_{j=1}^n y_j = s$ 
Torej: $\min_{y\in\Delta_2} x^TAy \geq s$

Podobno:
T: $\forall y\in\Delta_2:$ $\max_{x\in\Delta_1} x^TAy = \max_{i\in[m]} (x^{(i)})^TAy =$  max. element v vektorju $Ay$ 

Na vsako strategijo nasprotnika se lahko igralec brani s cisto strategijo

Postopek:
Prvega igralca zanima $\max_{x\in\Delta_1}(\min_{y\in\Delta_2} x^TAy) = \max_{x\in\Delta_1} \ \min_{j\in[n]} x^TAy^{(j)} = \max_{x\in\Delta_1}  \min_{j\in[n]} \sum_{i\in[m]}a_{ij}x_i$ 
D: $\pi_1 = \max s$ 
p.p. $\sum_{i\in[m]}a_{ij}x_i \geq s$ 
$x_1+...+x_m=1$   $(y_j \geq 0)$ 
$x_1,...,x_m \geq 0$ 
$s\in\mathbb R$   ($t\in\mathbb R$)

Primer: 
- $\max \min \{2x+3y, 3x+4y\}$
- p.p: $\displaylines {x+y = 1 \\ x+y \leq 10 \\ ...}$ 
Se preoblikuje:
- $\max s$
- p.p $\displaylines{2x+3y \geq s \\ 3x+4y \geq s \\ x+y = 1 \\ x+y \leq 10 \\ ...}$ 
D: oziroma
$\pi_1 = \max s$ 
p.p. $\sum_{i\in[m]}(-a_{ij})x_i + s \leq 0$  ($j=1,..,n$) 
$\sum_{i\in[m]}x_i=1$ 
$x_1,...,x_m \geq 0$ 
$s\in\mathbb R$ 

Postopek: Podobno za 2.igralca
$\min_{y\in\Delta_2} \max_{x\in\Delta_1} x^TAy =\min_{y\in\Delta_2} \max_{i\in[m]} (x^{(i)})^TAy = \min_{y\in\Delta_2} \max_{i\in[m]} \sum_{j=1}^n a_{ij}y_j$ ($\leq t$)

D: $\pi_2 = \min t$ 
p.p. $\sum_{j=1}^n a_{ij}y_j \leq t$  ($i=1,..,m$)
$y_1 +... + y_n =1$   $(x_i \geq 0)$ 
$y_1,...,y_n \geq 0$ 
$t\in\mathbb R$   ($s\in\mathbb R$)
oziroma:
$\pi_2 = \min t$ 
p.p. $\sum_{j=1}^n (-a_{ij})y_j + t \geq 0$  ($i=1,..,m$)
$\sum_{j\in[n]}y_j=1$ 
$y_1,...,y_n \geq 0$ 
$t\in\mathbb R$ 

T: $\pi_1$ in $\pi_2$ sta dualna. 
Dokaz:
$s = \begin{bmatrix}0 & ... & 0 & 1\end{bmatrix}  \cdot \begin{bmatrix}x_1 \\ ... \\ x_m \\ s\end{bmatrix}$ 
$t = \begin{bmatrix}0 & ... & 0 & 1\end{bmatrix}  \cdot \begin{bmatrix}y_1 \\ ... \\ y_n \\ t\end{bmatrix}$ 
SLIKA?

Opomba: $\pi_1$ in $\pi_2$ sta dopustna. 
KID pravi, da imata $\pi_1$ in $\pi_2$ isto optimalno vrednost.

I: (Minimax izrek; von Neumann) Za vsako matricno igro $A$ velja
- $\max_{x\in\Delta_1}\min_{y\in\Delta_2} x^TAy = \min_{y\in\Delta_2}\max_{x\in\Delta_1} x^TAy$ 

D: Vrednost igre je 
$v(A) = \max_{x\in\Delta_1}\min_{y\in\Delta_2} x^TAy$ 

D: Igra je postena, ko $v(A) = 0$.

D: $x^* \in\Delta_1$ je optimalna, ce velja: 
- $\min_{y\in\Delta_2} (x^*)^TAy = v(A)$ 
$y^*\in\Delta_2$ je optimalna, ce:
- $\max_{x\in\Delta_1} x^TAy^* = v(A)$ 

Postopek: Matricne igre so linearni programi, zato jih lahko "resujemo" (racunamo $v(A)$) z uporabo simpleksne metode. Preverjanje optimalnosti je enostavna, ce podamo $x^*,y^*$. Preverimo:
- $x^*\in\Delta_1$
- $y^*\in\Delta_2$
- $\min_j [(x^*)^TA]_j = \max_i [Ay^*]_i$ 
Ce to vse velja je situacija vzporedna z LP.

Zgled: 
Blotto
$\begin{bmatrix}4 & 2 & 1 & 0 \\ 1 & 3 & 0 & -1 \\ -2 & 2 & 2 & -2 \\ -1 & 0 & 3 & 1 \\ 0 & 1 & 2 & 4 \end{bmatrix}$ 
Ali sta 
- $x = \begin{bmatrix}\frac{4}{9} & 0 & \frac{1}{9} & 0 & \frac{4}{9}\end{bmatrix}^T$ in $y = \begin{bmatrix}\frac{7}{90} & \frac{32}{90} & \frac{48}{90} & \frac{3}{90}\end{bmatrix}^T$ optimalna?

SLIKA

Postopek: Kako zamenjamo vlogo igralcev?
$A\to -A^T$ 
Igra je simetricna, ko velja $A = -A^T$.

Primeri: 
- Kamen, skarje, papir
- Dvoprsna morra: Vsak igralec z levico pokaze ena ali dva prsta, z desnico pa napove koliko prstov bo pokazal nasprotnik. Ce en zadane, drug pa ne, zmagovalec dobi od nasprotnika toliko enot kot sta skupaj pokazala prstov na levici.
$(1,1) \ (1,2) \ (2,1) \ (2,2)$ 
$\begin{bmatrix}0 & 2 & -3 & 0 \\ -2 & 0 & 0 & 3 \\ 3 & 0 & 0 & -4 \\ 0 & -3 & 4 & 0 \end{bmatrix}$ $\displaylines{(1,1) \\ (1,2) \\ (2,1) \\ (2,2)}$ 
Optimalni strategiji?
$x=y=\begin{bmatrix}0 & \frac{3}{5} & \frac{2}{5} & 0\end{bmatrix}^T$ 

T: Simetricna igra je postena. Torej $v(A) = 0$ 
Dokaz:
$A=-A^T \implies A$ je $m\times n$ in $\Delta_1 = \Delta_2$
$v(A) = \max_{x\in\Delta_1}\min_{y\in\Delta_2} x^TAy = \max_{x\in\Delta_1}\min_{y\in\Delta_2} (x^T(-A^T)y)^T =$
$= \max_{x\in\Delta_1}\min_{y\in\Delta_2} -y^TAx = -\min_{x\in\Delta_1}\max_{y\in\Delta_2} y^TAx =$ (simetricna $x\leftrightarrow y$) 
$= -\min_{y\in\Delta_1}\max_{x\in\Delta_2} x^TAy = -v(A)$
$v(A) = -v(A) \implies v(A) = 0$.

T: $A$ je simetricna
Ce je $x$ optimalna za 1.igralca, potem je $x$ optimalna za 2.igralca.
DN

D: Dominacije
$a\in\mathbb R^n$ dominira $b\in\mathbb R^n \iff a\geq b \iff \forall i \ a_i \geq b_i$ (vektorji)
SLIKA

T: 
1. Ce i-ta vrstica placilne matrike dominira j-to vrstico placilne matrike, je vrednost igre nespremenjen ce odstranimo j-to vrstico. Vsaka optimalna strategija nove igre je optimalna strategija originalne igre.
2. Ce i-ti stolpec placilne matrike dominira j-ti stolpec placilne matrike, je vrednost igre nespremenjena, ce odstranimo i-ti stolpec. Vsaka optimalna strategija nove igre je optimalna strategija originalne igre.

Primer:
SLIKE

???

Poenostavljen poker:
- 2 igralca $A$ in $B$
- 3 karte: 1,2,3 (visja karta je boljsa)
- Vsak igralec dobi 1 karto
- Zacetna stava: $1\texteuro$ vsak

Potek igre:
SLIKA

Strategija za 1.igralca:
$A1$: Stavi 0, ce $B$ stavi 

???




## Problem razvoza

D: $G=(V,E)$ usmerjen graf.
$V$ - mesta
$E$ - usmerjene ceste
$\forall e\in E$ : $c_e\geq 0$ - utez
$\forall v\in V$ : $b_v = \begin{cases} b_v \gt 0 & \text{povprasevanje} \\ b_v \lt 0 & \text{ponudba oz. proizvodnja}\end{cases}$ 
Predpostavimo (zaenkrat): $\sum_{v\in V}b_v=0$ 
Iscemo LP:
- $\min c^Tx=\sum_{e\in E}c_ex_e$ (Kirchhoffov zakon)
- p.p 
$\sum_{e:\text{Konec(e)}=v}x_e - \sum_{e:\text{Zac(e)}=v}x_e = b_v$  ($\forall v\in V$)
$x_e\geq 0$  $\forall e\in E$

D: Matricni zapis
$\min c^Tx$ 
p.p $Ax = b$ 
$x\geq 0$ 

D: Spremenljivke
$x=(x_e)_{e\in E}$ - spremenljivke
$c=(c_e)_{e\in E} \in \mathbb R^E$ - podatki
$b=(b_v)_{v\in V} \in \mathbb R^V$ - podatki
$A = \begin{bmatrix} a_{ve} \end{bmatrix}_{v\in V, \ e\in E}$ - incidencna matrika
	E:
V: $\begin{bmatrix} 0/1/-1 \end{bmatrix}$ 
$a_{ve}=\begin{cases}1, & \text{ce Konec(e)=v} \\ -1, & \text{ce Zac(e)=v} \\ 0, & \text{sicer}\end{cases}$ 

Primer:
SLIKA GRAFA
Notacija:
SLIKA
LP:
$\min 1x_{13}+3x_{12}+6x_{23}+1x_{32}$ 
p.p 
$-x_{13}-x_{12}=-7$
$x_{12}+x_{32}-x_{23}=3$
$x_{13}+x_{23}-x_{32}=4$
$x_{13},x_{12},x_{23},x_{32}\geq 0$ 

Primer: (Matricno)
$\min \begin{bmatrix}1 & 3 & 6 & 1\end{bmatrix}$ $\begin{bmatrix}x_{13}\\ x_{12}\\ x_{23} \\ x_{32}\end{bmatrix}$ 
p.p
$\begin{bmatrix}-1 & - 1 & 0 & 0 \\ 0 & 1 & -1 & 1 \\ 1 & 0 & 1 & -1\end{bmatrix} \begin{bmatrix}x_{13}\\ x_{12}\\ x_{23} \\ x_{32}\end{bmatrix} = \begin{bmatrix}-7 \\ 3\\ 4 \end{bmatrix}$ (vrstice so V, stolpci E)
$x\geq 0$ 

D: Dual
Matricni zapis je:
$\min c^Tx$ 
p.p $Ax = b$ 
$x\geq 0$ 
$\leadsto$ 
$\max -c^Tx$
p.p $(-A)x=-b$
$x\geq 0$ 
$\leadsto$ 
$\min (-b^T)y$
p.p $-A^Ty \geq -c$
$y\in\mathbb R^V$
$y\in [y_v]_{v\in V}$ 
Matricni zapis duala:
$\max b^Ty$
p.p $A^Ty \leq c$ 

Primer (dual): 
$\max -7y_1 + 3y_2 + 4y_3$ 
p.p $y_3-y_1 \leq 1$
$y_2-y_1\leq 3$
$y_3-y_2 \leq 6$
$y_2-y_3\leq 1$ 

Pogoji:
Za $i\to j: ij$
$y_j-y_i \leq c_{ij}$

Za kasneje:
$\begin{bmatrix}A^Ty\end{bmatrix}_{ij}=y_j-y_i$  $\forall i,j\in E$ 

Izrek o DD (dualno dopolnjevanje):
$x\in D(\pi)$, $y\in D(\pi')$ 
$\displaylines{x\in Opt(\pi) \\ y\in Opt(\pi')} \iff \begin{cases}\forall i: \sum_{j=1}^n a_{ij}x_j=b_i \  \text{ali} \ y_i=0 \\ \forall j: \sum_{i=1}^m a_{ij}y_i=c_j \  \text{ali} \ x_j=0 \end{cases}$ 

Vpr: Kdaj bosta dopustni resitvi $x,y$ optimalni?
$x,y$ optimalna $\leftrightarrow$ $\forall i,j\in E: x_{ij}=0 \ \text{ali} \ y_j-y_i=c_{ij}$ 
Iscemo torej $x,y$, ki zadoscata $y_j = c_{ij}+y_i$ 
Simpleksna metoda na omrezjih.

Postopek: $G$ je povezan (brez usmerjenih povezav: $i\to j \leadsto i\leftrightarrow j$) 
$T$ vpeto drevo v $G$, ce:
- $ij\in T \Rightarrow ij\in E(G)$  ali $ji\in E(G)$ 
- $T$ je drevo (povezan in brez ciklov)
- $V(T)=V(G)$ 

D: $x$ je dopustna resitev za PR (problem razvoza)
$x$ je drevesna dopustna resitev za PR, ce obstaja vpeto drevo $T$, da je $x_{ij}=0 \ \ \forall i,j\notin T$ ($x_{ij} \gt 0 \Rightarrow ij\in T$)
Intuicija: DDR = baza v sx

Primer:
SLIKA
DDR:
SLIKA

T: Ce obstaja dopustna resitev, obstaja drevesna dopustna resitev.
Dokaz:
$x$ poljubna dopustna resitev. 
Denimo, da $x$ ni ddr. Potem obstaja cikel C, kjer $x_e\gt 0$ za $\forall e\in C$. Za C izberemo smer (pozitivna orientacija).
SLIKA
Imamo preme in obratne povezave. Lahko izberemo nek "majhen" $t\gt 0$ in spremenimo $\pm t$ vse povezave.
Preme: Povecamo za $t$: $x_e \mapsto x_e+t = x'_e$ 
Obratne: Zmanjsamo za $t$: $x_e \mapsto x_e-t = x'_e$ 
SLIKE
Dokler velja nov $x_e'\geq 0 \ \ \forall e\in C$ imamo dopustno resitev. Vzamemo 
$t=\min \{x_e \ | \ e$ je obratna povezava v $C\}$.
Potem dobimo eno povezavo v $C$, kjer $x_e=0$. Ce $C$ nima obratne povezave, zamenjamo smer (oz. izberemo smer tako, da obstaja obratna povezava). 
S tem zmanjsamo $\# \{e\in G \ | \ x_e\gt 0\}$ za vsaj 1. (stevilo povezav)
Na koncu dobimo graf brez ciklov v $\{e\in G \ | \ x_e\gt 0\}$.

Za podano ddr $(x_e)_{e\in E}$ pripadajoci drevesu $T$ definiramo prevozno ceno: $(y_v)_{v\in V}$ kot enolicno resitev:
- izberemo $v\in V$ (koren)
- $y_j=y_i+c_{ij}$, $\forall i,j\in T$ 
SLIKA

Opomba: Ta $(y_v)_{v\in V}$ ni dopustna resitev duala. (...na koncu bo...) 

Postopek:
Zacnemo z ddr in ga postopoma izboljsujemo:
$ddr_1 \to ddr_2 \to ... \to ddr_{Opt}$ 
Zaenkrat predpostavimo, da imamo ddr. Kasneje bomo videli dvofazno sx metodo na omrezjih, da dobimo se zacetni ddr.
1. Izracunamo prevozne cene $(y_v)_{v\in V}$ 
T1: $x$ ddr in $y$ pripadajoce prevozne cene
Potem velja: $c^Tx=b^Ty$ (ce zmanjsamo prevozne cene, bomo zmanjsali vrednost).
2. Poiscemo $ij\in G\setminus T$ za katerega velja: $y_i+c_{ij} \lt y_j$. Potem dodamo v drevo povezavo $ij$ in odstranimo neko povezavo, da dobimo nov ddr.
T2: Ce $\forall i,j\in G$  velja $y_i+c_{ij}\geq y_j$ potem je $(x_e)_{e\in E}$ optimalna resitev.
3. Dodamo v $T$ povezavo $ij$ iz 2.tocke. Dobimo natancno en cikel $C$. Nova povezava $ij$ doloci smer v $C$ in razdeli povezave na obratne in preme ($ij$ je prema). Na premih povezavah povecamo za $t$, na obratnih zmanjsamo za $t$, kjer je $t=\min\{x_e \ | \ e\in C,\ e$ obratna$\}$. Povezava $f$, kjer je $\min$ dosezen, povezavo odstranimo, da donimo novo drevo. SLIKA. Ce $t\gt 0$ ta operacija zmanjsa stroske, ce $t=0$ je izrojen primer.

Primer: 
SLIKA_a
ful slik

T (T1): $x$ ddr in $y$ pripadajoce prevozne cene
Potem velja: $c^Tx=b^Ty$. Nekateri pisejo tudi: $\langle c,x\rangle = \langle b,y\rangle$.
Dokaz:
Uporabimo $\begin{bmatrix}A^Ty\end{bmatrix}_{ij}=y_j-y_i$  $\forall i,j\in E$. Naj bo $T$ pripadajoce drevo za $x$.
Ce je $x$ dopustni velja $b^T = (Ax)^T$.
Spomnimo se: $\begin{cases} \text{ce} \ \ ij\in T: y_j-y_i=c_{ij} \\ \text{ce} \ \ ij\notin T: x_{ij}=0 \end{cases}$  vedno bo pa veljalo: $x_{ij}(y_j-y_i)=c_{ij}x_{ij}$ 
$b^Ty= (Ax)^Ty=x^T(A^Ty)=\sum_{ij\in E}x_{ij}\begin{bmatrix}A^Ty\end{bmatrix}_{ij} = \sum_{ij\in E}x_{ij}(y_j-y_i) = \sum_{ij\in E} c_{ij}x_{ij}=c^Tx$.

T (T2): Ce $\forall i,j\in G$  velja $y_i+c_{ij}\geq y_j$ potem je $x$ optimalna resitev.
Dokaz: 
Naj bo $\overline x$ poljubna dopustna resitev. 
$c^T\overline x = \sum_{ij\in E} c_{ij}\overline x_{ij} \geq \sum_{ij\in E}\begin{bmatrix}A^Ty\end{bmatrix}_{ij}\overline x_{ij} = x^T(A^Ty)=x^Tb=b^Ty=c^Tx$ 


# Ucenje
## Linearno programiranje
### Optimizacijski problem in taksonomija

D: Optimizacijski problem je urejena trojica $(D,f,opt)$, kjer velja:
- $D$ je mnozica dopustnih resitev
- $f: D \to \mathbb R$ je ciljna funkcija (kriterijska funkcija)
- $opt$ $\in \{max, min, inf, sup\}$ je vrsta ekstrema
Zanima nas $opt\{f(x) \ | \ x \in D\}$ ali $opt \ f(x)$ p.p $x \in D$ (p.p - pri pogojih = s.t - subject to/such that)
Optimizacijska naloga je optimizacijski problem s konkretnimi podatki.

D: Optimalna resitev je $x^* \in D$, za katero velja $f(x^*) = opt\{f(x) \ | \ x \in D\}$ (tocka kjer dosezemo ekstrem). Ni nujno da obstaja optimalna resitev.

D: Optimizacijske naloge $(D, f, opt)$ se delijo glede na:
$D = \emptyset$ ?
- $D = \emptyset$ --> nedopustna naloga (1)
- $D \neq \emptyset$ --> dopustna naloga
	$opt\{f(x) \ | \ x \in D\} = +/- \infty$ ?
	- da --> neomejena (2)
	- ne --> omejena
		obstaja optimalna resitev ?
		- da --> "optimalna" (3)
		- ne --> "neoptimalna" (4)

### Linearni program v standardni in v splošni obliki

D: Linearni program je optimizacijski problem (ali naloga) $(D,f,opt)$ pri cemer:
- $D\in \mathbb R^n$ je podana z linearnimi enakostmi in neenakostmi sorte ($\leq$ in $\geq$, ne velja pa $\lt,\gt$)
- $f$ je linearna
- $opt$ je bodisi $\max$ ali $\min$ 

D: Standardna oblika linearnega programa:
Linearni program je v standardni obliki, ko:
- iscemo $\max$
- vsi pogoji so tipa $\leq$ (brez $=, \geq$) - spremenljivke so na levi strani (oblike: $x_1+x_2 \leq k$ ali pa $f_i(x) \leq b_i$)
- vse spremenljivke so $\geq 0$ 

$\max c_1x_1+c_2x_2+\dots+c_nx_n$ 
p.p $\displaylines{a_{11}x_1+a_{12}x_2+\dots+a_{1n}x_n \leq b_1 \\ a_{21}x_1+a_{22}x_2+ \dots +a_{2n}x_n \leq b_2 \\ \dots \\ a_{m1}x_1+a_{m2}x_2+\dots+a_{mn}x_n \leq b_m}$ 

D: LP v standardni obliki lahko napisemo matricno ali z matricno notacijo
$\max c^T\cdot x$ 
p.p: $\displaylines{Ax \leq b \\ x \geq 0}$ 
$c = \begin{bmatrix}c_1\\...\\ c_n\end{bmatrix} \in \mathbb R^n$ podane stevilke, $x = \begin{bmatrix}x_1\\...\\ x_n\end{bmatrix}$ spremenljivke, $A = \begin{bmatrix} a_{ij} \end{bmatrix}_{i\in[m],j\in[n]}$ 

T: Vsak l.p. lahko ekvivalentno zapisemo v standardni obliki.
Dokaz: 
- $\min {f(x_1,...,x_n)} \leadsto -\max {-f(x_1,...,x_n)}$
- pogoj $f_i(x_1,...,x_n) \geq b_i \leadsto -f_i(x_1,...,x_n) \leq -b_i$ , pogoj $f_i(x_1,...,x_n) = b_i \leadsto \{\displaylines{f_i(x_1,...,x_n) \leq b_i \\ -f_i(x_1,...,x_n) \leq -b_i}\}$
- pogoj $x_i \leq 0 \leadsto$ nova spremenljivka $x_i' = -x_i$ (zamenjamo $x_i$ z $x_i'$) dobimo $x_i' \geq 0$  
- $x_i \in \mathbb R \leadsto$ nova spremenljivka $x_i'$ in $x_i'': x_i = x_i'-x_i''$ kjer $x_i' \geq 0$ in $x_i'' \geq 0$ 

### Graficno resevanje

Primer: 
$\max 2x+y$
p.p. 
$\displaylines{2x+5y \leq 22 \\ x+y\leq 5 \\ 3x+y \leq 9 \\ x,y\geq 0}$ 
![[Pasted image 20240318152042.png]]
Rdeca linija je funkcija, ki jo zelimo maksimizirati (pri 2x+y=3, potuje cez cel omejen del).
Ogljisca obmocja bodo optimumi.

D: Za splosen $n$: $\Omega$ je politop (presek polprostorov), mnozica optimalnih resitev (ce obstaja) je lice politopa (ogljisce za n=2, stranice, stranska ploskev). Lahko je neomejena mnozica, tem primeru je linearni program lahko neomejen.

Op: Optimalna vrednost je dosezena v ogljiscih dopustne mnozice.

### Osnovna varianta metode simpleksov

D: Predpostavimo standardno obliko:
$\max c^T x$ 
p.p:
$\displaylines{Ax \leq b \\ x \geq 0}$ 
Dodatno predpostavimo $b\geq 0$ ($\to x=0$ je dopustna resitev)
$Ax\leq b = \displaylines{{a_1}^Tx\leq b_1 , \ b_1\geq 0 \\ {a_2}^Tx\leq b_2 , \ b_2\geq 0 \\ ... \\ {a_m}^Tx\leq b_m , \ b_m\geq 0}$ 

D: Slovar je sistem linearnih enacb, kjer $m$ spremenljivk izmed $\{x_1,..,x_n,x_{n+1},...,x_m\}$, takoimenovane bazne spremenljivke zapisemo v odvisnosti od drugih spremenljivk imenovane nebazne spremenljivke, in funkcional (kriterijska funkcija).
Opomba: V prvem slovarju so nebazne spremenljivke = prvotne, bazne = dopolnilne

D: Slovar je dopusten, ce so vsi prosti cleni baznih spremenljivk nenegativni. Ce je $b\geq 0$ je prvi slovar dopusten (dopustna resitev je x=0). Ce je slovar dopusten nam da bazno dopustno resitev (BDR): {
- Bazne spremenljivke = prosti clen
- Nebazne spremenljivke = 0

Postopek:
1. Za vsak pogoj ${a_i}^Tx \leq b_i$ vpeljemo novo spremenljivko $x_{n+i} = b^T - {a_i}^Tx$ 
$\begin{cases} x_1,...,x_n &\text{prvotne spremenljivke} \\ x_{n+1},...,x_{n+m} &\text{dopolnilne spremenljivke} \end{cases}$ 
Dodamo pogoj $x_{n+i} \geq 0 \ \forall i\in \{1,..,m\}$ 

2. Predstavljeno v obliki slovarja 
$\displaylines{x_{n+1} = b_1 - {a_1}^Tx \\ x_{n+2} = b_2 - {a_2}^Tx \\ ... \\ x_{n+m} = b_m - {a_m}^Tx}$ (leve strani so bazne, x-i na desni pa nebazne)
Funkcional $z = c^Tx$ 

3. Iteracija: Zamenjamo eno nebazno spremenljivko z eno bazno. Ena spremenljivka vstopi v bazo, druga izstopi (ne nakljucno).
- Za vstopajoco spremenljivko izberemo poljubno nebazno spremenljivko s pozitivnim koeficientom. Kasneje pravila
- Za izstopajoco spremenljivko izberemo tisto, ki najvec omejuje vstopajoco spremenljivko (ce vec taksnih - izberemo poljubno)
Op: Pivotna vrstica je vrstica, ki izraza izstopno spremenljivko.
Vstopajoco spremenljivko izrazimo iz pivotne vrstice, izrazavo dodamo v ostale spremenljivke in dobimo nov slovar.

Op: Vsi slovarji so dopustni, ce kateri ni, smo izbrali napacno izstopno spremenljivo (ali pa naredili racunsko napako).

4. Koncamo, ko so vsi koeficienti pred spremenljivkami v funkcionalu nepozitivni. 

D:
- Ce je v enacbi slovarja vstopajoca spremenljivka z pozitivnim koeficientomm ta vrstica nikoli ne omejuje in nikol ni pivotna vrstica
- Ce je pri vseh enacbah slovarja vstopajoca spremenljivka s pozitivnim koeficientom potem je naloga/program neomejena in lahko dobimo poltrak znotraj mnozice dopustnih resitev, kjer se ciljna funkcija poveca.

Vpr: Ali se vedno ustavi?
Moznih slovarjev je $\binom{n+m}{m}$. Ce se algoritem ne ustavi je prislo do ciklanja (en slovar se ponovi). V praksi ni problem.

D: Ko je v enacbi, kjer izstopa spremenljivka, prosti clen enak 0, imamo izrojeno bazo. (optimalna vrednost se ne povecuje)

D: Blandova pravila (Bland's rule): 
- Med kandidatkami za vstopajoco spremenljivko (koeficient $\gt 0$) izberemo tisto z najmanjsim indeksom
- Med kandidatkami za izstopajoco spremenljivko, ki omejujejo isto, izberemo tisto z najmanjsim indeksom

I: Simpleksni postopek z Blandovim pravilom se ustavi po koncno mnogih korakih.

Casovna zahtevnost:
- $m\cdot \log n$ ponavadi
- Klee-Minty: 
	- najvecji koeficient: $2^n-1$ 
	- najvecje povecanje: $1$

Vpr: Kako izberemo vstopajoco spremenljivko?
- Blandova pravila
- Spremenljivko z najvecjim koeficientom 
- Spremenljivko, ki bo najvec povecala prosti koeficient funkcionala v enem koraku
- Nakljucno izmed spremenljivk s koeficientom $> 0$ 
Za nobeno pravilo vemo, da dela v polinomskem casu. Za vsako deterministicno pravilo ljudje najdejo primer, ki porabi eksponencialno stevilo korakov.

Op: Ce ima kaksna spremenljivka v zadnjem funkcionalu koeficient 0 dobimo fleksibilnost (ga oznacimo s spremenljivko t) in ugotovimo omejitve za t (bazne >= 0), da dobimo druzino optimalnih resitev.
### Dvofazna simpleksna metoda

D: Uporabljamo jo ko $b \ngeq 0$ (obstaja $i$, da $b_i \lt 0$)

Ideja:
1. Faza: Preverjamo dopustnost problema
2. Faza: Za dopustne probleme izvedemo sx metodo.

1.Faza: Vpeljemo novo spremenljivko $x_0 \geq 0$ in resujemo 
D: V splosnem
- $\max c^Tx \leadsto \min x_0$ 
- p.p:
$\displaylines{Ax\leq b \\ x\geq 0} \leadsto \displaylines{Ax\leq b+ \begin{bmatrix} x_0 \\ ... \\ x_0 \end{bmatrix} \\ x_0 \geq 0 \\ x\geq 0}$  (program $\pi\to\tilde{\pi}$ )

Op: Geometrijsko premikamo pogoje.

T: $\pi$ je dopusten program, natanko tedaj ko ima $\tilde{\pi}$ optimalno vrednost 0.
Dokaz:
- $(\rightarrow)$ 
Recimo, da $\pi$ je dopusten, $\exists$ vektor $x=(x_1,...,x_n)$, ki zadosca $Ax\leq b$ in $x\geq 0$.
Sledi: Vektor $\begin{bmatrix} x_0 = 0 \\ ... \\ x_n \end{bmatrix}$ je dopustna resitev za $\tilde \pi$ in je optimum z vrednostjo 0.
- $(\leftarrow)$
 $\tilde \pi$ ima optimalno resitev $\begin{bmatrix} {x_0}^*\\ ... \\ {x_n}^* \end{bmatrix}$, ki doseze vrednost 0. Torej ${x_0}^* = 0$ in $\begin{bmatrix} {x_1}^*\\ ... \\ {x_n}^* \end{bmatrix}$ je dopustna resitev za $\pi$.

T: Pri fazi dobimo moznosti:
- $w^* < 0$ : prvotni problem ni dopusten
- $w^* = 0$, $x_0$ zapusti bazo ($w=-x_0$) : prvotni problem je dopusten, zacnemo z 2.fazo
- $w^*=0$, $x_0$ ne zapusti baze : v tem primeru bi $x_0$ lahko zapustil bazo (za to uporabimo pravilo: ce je $x_0$ med kandidati za izstopno spremenljivko jo izberemo)

### Osnovni izrek linearnega programiranja

![[Pasted image 20240724121056.png]]

I: Osnovni izrek linearnega programiranja.
- Ce ima P dopustno resitev, ima bazno dopustno resitev.
- Ce ima P opitmalno resitev, ima P bazno optimalno resitev.
- P je lahko
	- nedopusten
	- neomejen
	- optimalen

### Dualni linearni program

Notacija: 
- $D(\pi)$ - mnozica dopustnih resitev za LP $\pi$
- Uporabimo $i$ kot indeks za pogoje, $j$ kot indeks za spremenljivke 
- $\begin{bmatrix}A\end{bmatrix}$ (stolpci - $j\in[n]$, vrstice - $i\in[m]$), velikost matrike je $n\cdot m$  
- Torej:
	- $\pi = \max \sum_{j=1}^n c_jx_j$ 
	- p.p: (v standardni obliki)
 $\displaylines{\sum_{j=1}^n a_{ij}x_j \leq b_i \\ x_j \geq 0}$ (za $i \in [m]$ in $j \in [n]$)

D: Dualni program za
- $\pi = \max c^T \cdot x$
- p.p:
$\displaylines{Ax \leq b \\ x \geq 0}$ 
je 
- $\pi' = \min b^T y$
- p.p:
$\displaylines{A^Ty \geq c \\ y \geq 0}$ 

D: Dualni problem (brez matricne notacije)
- $\pi' = \min \sum_{i=1}^m b_iy_i$
- p.p:
$\displaylines{\sum_{i=1}^m a_{ij}y_i \geq c_j \\ y_i \geq 0}$  (za $j \in [n]$ in $i \in [m]$)

T: $\pi''=\pi$ 
Dokaz: 
1. Dual v standardni obliki:
- $\max (-b^T)y$
- p.p 
$(-A^T)y \leq -c$
$y\geq 0$ 

2. Dual duala
- $\min (-c^T)x$
- p.p 
$(-A^T)^Tx \geq -b$
$x\geq 0$ 

3. Dual duala v standardni obliki
- $\max c^Tx$ 
- p.p 
$Ax \leq b$
$x\geq 0$ 

### SID - Sibki izrek o dualnost

I: Ce velja:
- $x$ je dopustna resitev za $\pi$, 
- $y$ je dopustna resitev za $\pi'$ 
Potem je $c^Tx\leq b^Ty$.
Dokaz: 
1. Varianta:
$c^Tx \leq (A^Ty)^Tx = y^TAx \leq y^Tb = b^Ty$ 
(za prvo neenakost uporabimo $c\leq A^Ty$ in $x\geq 0$, za drugo pa $Ax\leq b$ in $y\geq 0$)
(velja $(ab)^T=b^Ta^T$ in $a^Tb=b^Ta$)
2. Varianta:
$\sum_{j=1}^nc_jx_j \leq \sum_{j=1}^n(\sum_{i=1}^ma_{ij}y_i)x_j = \sum_{i=1}^m(\sum_{j=1}^na_{ij}x_j)y_i \leq \sum_{i=1}^mb_iy_i$ 
(pri dvojnem sestevanjem lahko zamenjamo vrstni red, pri prvi enakosti smo $y_i$ "izpostavili", saj je v vsakem clenu enak)

Posledica 1:
- $x$ je dopustna resitev za $\pi$, 
- $y$ je dopustna resitev za $\pi'$ 
- $c^Tx = b^Ty$
Potem je $x$ optimalna resitev za $\pi$ in $y$ optimalna resitev za $\pi'$.

Op: Optimalnost $x^*$ lahko dokazemo tako, da najdemo dopustno resitev $y^*$ da velja: $c^Tx^*=b^Ty^*$.

Posledica 2: Ce je $\pi$ neomejen, je $\pi'$ nedopusten.
Dokaz: Dopustna resitev za $\pi'$ nam da zgornjo mejo za kriterijsko funkcijo od $\pi$, torej ce je kriterijska neomejena, ni nobene dopustne resitve za dual.

### KID - Krepki izrek o dualnost

I: $x^*$ je optimalna resitev za $\pi$. Potem ima $\pi'$ tudi optimalno resitev $y^*$ in velja $c^Tx^*=b^Ty^*$.
Dokaz: 
Imamo program $\pi$ in uporabimo simpleksno metodo na njem, zaradi predpostavke dobimo zadnji slovar.
$z=v^* + \sum_{i=1}^{n+m}c^*_ix_i = v^* + \sum_{j=1}^nc^*_jx_j + \sum_{i=1}^mc^*_{i+n}x_{i+n}$ (razdelimo na prvotne in dopolnilne, $c^*$ koeficienti v zadnjem slovarju)
- $c_i^* \leq 0$ (za bazne = 0)
- $x_{i+n}=b_i-\sum_{j=1}^na_{ij}x_j$ - dopolnilne spremenljivke
Uganemo resitev dualnega problema:
$y^*_i=-c_{i+n}^*$ za $i=1,...,m$ 
Trdimo, da so $y_1^*,...,y_m^*$ dopustna resitev in $\sum_{j=1}^n c_jx_j^* = \sum_{i=1}^m b_iy_i^*$ (c - koeficienti v kriterijski funkciji).
$z = v^* + \sum_{j=1}^nc^*_jx_j + \sum_{i=1}^mc^*_{i+n}x_{i+n} =$ 
$= v^* + \sum_{j=1}^nc^*_jx_j + \sum_{i=1}^m(-y_i^*)(b_i-\sum_{j=1}^na_{ij}x_j) =$
$= v^* - \sum_{i=1}^m b_iy^*_i + \sum_{j=1}^nc^*_jx_j +\sum_{j=1}^n(\sum_{i=1}^ma_{ij}y_i^*)x_j) =$
$= (v^* - \sum_{i=1}^m b_iy^*_i) + \sum_{j=1}^n(c^*_j + \sum_{i=1}^ma_{ij}y_i^*)x_j$  (najprej stevilke potem pa izpostavljen x)
Prisli smo do izrazave zadnjega funkcionala s prvotnimi spremenljivkami, za kar pa poznamo se eno izrazavo (prvotna kriterijska funkcija). PAZI c-je
$= \sum_{j=1}^nc_jx_j$ 
Istolezni koeficienti so enaki, kar pomeni 
- $(v^* - \sum_{i=1}^m b_iy^*_i) = 0 \implies v^* = \sum_{i=1}^m b_iy^*_i \implies \sum_{j=1}^n c_jx^*_j=\sum_{i=1}^m b_iy^*_i$  (sledi iz definicije optimalne resitve in optimalne vrednosti)
- $c^*_j + \sum_{i=1}^ma_{ij}y_i^* = c_j \implies \sum_{i=1}^ma_{ij}y_i^* = c_j - c^*_j \geq c_j$ (vemo da so cji v koncnem funkcionalu nepozitivni)
- $y^*_i= -c_{i+n}^*\geq 0$ 
Iz drugih dveh alinej sledi da je $y^*$ dopustna resitev za $\pi'$.
Imamo dopustni resitvi $x^*$ za $\pi$ in $y^*$ za $\pi'$. Prva alineja nam pove da velja $c^Tx^*=b^Ty^*$.
Po prvi posledici SID-a vemo, da sta $x^*$ in $y^*$ optimalni resitvi.

D: Mozne kombinacije za $\pi$ in $\pi'$.

| $\pi$ in $\pi'$ | Nedopusten         | Neomejen           | Optimalen          |
| --------------- | ------------------ | ------------------ | ------------------ |
| **Nedopusten**  | $\checkmark$       | $\checkmark_{SID}$ | // $_{KID}$        |
| **Neomejen**    | $\checkmark_{SID}$ | // $_{SID}$        | // $_{KID}^{SID}$  |
| **Optimalen**   | // $_{KID}$        | // $_{KID}^{SID}$  | $\checkmark_{KID}$ |
Op: Kjer pise SID je misljena 2.posledica SID-a in nedopusten-nedopusten se izkaze da je res, glede na primer.

Posledica: 
Za $\pi,\pi'$ velja natanko ena od moznosti:
- Oba sta optimalna
- Oba sta nedopustna
- Eden je neomejen, drugi je nedopusten
 
### DD - Dualno dopolnjevanje

I: Imamo $x\in D(\pi)$ in $y\in D(\pi')$.
Velja:
$\displaylines{x\in \mbox{Opt}(\pi) \\ \\ y\in \mbox{Opt}(\pi')} \iff \displaylines{\mbox{za} \ \  i=1,...,m \ \ \mbox{je} \ \sum_{j=1}^n a_{ij}x_j=b_i \ \ \mbox{ali}\ \ y_i=0 \\ \mbox{za} \ \ j=1,...,n \ \ \mbox{je} \ x_j=0  \ \ \mbox{ali} \ \ \sum_{i=1}^m a_{ij}y_i=c_j}$ 

Ekvivalentno: 
$A\lor B = \neg B \to A = \neg A \to B \iff \displaylines{\mbox{za} \ \  i=1,...,m \ \ \mbox{ce} \ \sum_{j=1}^n a_{ij}x_i\lt b_i \ \ \mbox{potem}\ \ y_i=0 \\ \mbox{za} \ \ j=1,...,n \ \ \mbox{ce} \ x_j\gt 0 \ \ \mbox{potem} \ \sum_{i=1}^m a_{ij}y_i=c_j}$ 
Dokaz: 
Sledi dokaz ŠID:
$(L:=)= c^Tx=\sum_{j=1}^nc_jx_j \leq \sum_{j=1}^n(\sum_{i=1}^ma_{ij}y_i)x_j = \sum_{i=1}^m(\sum_{j=1}^na_{ij}x_j)y_i \leq \sum_{i=1}^mb_iy_i = b^Ty = (=:D)$ 
Ker velja:
- $c\leq A^Ty, \ x\geq 0$
- $y\geq 0, \ Ax \leq b$ 
KID:
$L=D \iff x\in\mbox{Opt}(\pi) \ \mbox{in} \ y\in\mbox{Opt}(\pi')$ ($\Leftarrow$ KID, $\Rightarrow$ SID)
$\displaylines{x\in \mbox{Opt}(\pi) \\ \\ y\in \mbox{Opt}(\pi')} \iff \displaylines{(\sum_{i=1}^m a_{ij}y_i)x_j=c_jx_j \ \ j=1,...,n \\ (\sum_{j=1}^n a_{ij}x_j)y_i=b_iy_i \ \ i=1,...,m} \iff \displaylines{(\sum_{i=1}^m a_{ij}y_i - c_j)x_j=0 \ \ j=1,...,n \\ (\sum_{j=1}^n a_{ij}x_j-b_i)y_i=0 \ \ i=1,...,m} \overset{(A\cdot B=0 \implies A=0 \ \mbox{ali} \ B=0)}{\iff} \displaylines{\sum_{i=1}^m a_{ij}y_i = c_j \ \ \mbox{ali} \ \ x_j=0 \ (j=1,...,n) \\ \sum_{j=1}^n a_{ij}x_j=b_i \ \ \mbox{ali} \ \ y_i=0 \ (i=1,...,m)}$

### Ekonomski vidik dualnosti

Op: Imamo program $\pi$, z optimalno resitvijo $x^*$. Pogledamo neenacbe slovarja (z optimalno resitvijo). Ce si predstavljamo da se nam desne strani lahko povecajo (npr. povrsina, delavci itd)
- ne splaca se nam povecati $b$-ja pri neenacbah ki so strogo manjse (saj ze zdaj ne dosegamo maksimuma) - $y_i^* = 0$
- splaca pa se nam povecati $b$ tam kjer imamo enakost, saj smo ze maksimalno izkoristili dano vrednost, mogoce jo lahko se bolje
Resitev dualnega nam pove za koliko se bo spremenila optimalna vrednost.

I: Linearni program $\pi$, obstaja neizrojena bazna optimalna resitev (v zadnjem slovarju so vse konstante vecje od 0). Potem $\exists \ \varepsilon \gt 0$, da velja $\Delta z^* = \sum_{i=1}^m y_i^*\Delta b_i$ za $|\Delta b_i| \leq \varepsilon$ 

Op: $z$ je kriterijska funkcija, $z^*$ optimalna vrednost. 
$y_i^*$ mi da trzno ceno dobrino.

### Dualni linearni program splošnega programa

D: Splosni problem
- $\max \sum_{j=1}^n c_jx_j$ 
- p.p
$\displaylines {\sum_{j=1}^n a_{ij}x_j \leq b_i \ \ \mbox{za} \ \ i=1,...,m' \\ \sum_{j=1}^n a_{ij}x_j = b_i \ \ \mbox{za} \ \ i=m'+1,...,m \\ x_j \geq 0 \ \ \mbox{za} \ \ j=1,...,n'}$ 
(ne nujno vse spremenljivke)

Dual splosnega problema je:
- $\min \sum_{i=1}^m b_iy_i$ 
- p.p
$\displaylines {\sum_{i=1}^m a_{ij}y_i \geq c_j \ \ \mbox{za} \ \ j=1,...,n' \\ \sum_{i=1}^m a_{ij}y_i = c_j \ \ i=n'+1,...,n \\ y_i \geq 0 \ \ i=1,...,m'}$ 

Za neenakost pri problemu dobim nenegativno spremenljivko v dualu, za enakosti pa poljubno.

D: Matricno:
$\pi = \max c_1^Tx_1 + c_2^Tx_2$
p.p
$\displaylines{A_{11}x_1+A_{12}x_2 \leq b_1 \\ A_{21}x_1+A_{22}x_2 = b_2 \\ x_1 \geq 0 \\ x_2 \in \mathbb R^{n-n'}}$ 
Dual
$\pi' = \min b_1^Ty_1 + b_2^Ty_2$
p.p
$\displaylines{{A_{11}}^Ty_1+{A_{21}}^Ty_2 \geq c_1 \\ {A_{12}}^Ty_1+{A_{22}}^Ty_2 = c_2 \\ y_1 \geq 0 \\ y_2 \in \mathbb R^{m-m'}}$ 

D: Dualno dopoljevanje za $\pi$ in $\pi'$.
$\displaylines{x\in \mbox{Opt}(\pi) \\ \\ y\in \mbox{Opt}(\pi')} \iff \displaylines{\ \ \mbox{je} \ \sum_{j=1}^n a_{ij}x_j=b_i \ \ \mbox{ali}\ \ y_i=0 \ \ \mbox{za} \ \  i=1,...,m' \\ \mbox{za} \ \ j=1,...,n' \ \ \mbox{je} \ x_j=0  \ \ \mbox{ali} \ \ \sum_{i=1}^m a_{ij}y_i=c_j}$ 
(za $m'+1,...,m$ ze velja)
Dokazi

## Matricne igre
### Matricne igre, sedlo, dominacije

Op: Teorija iger

Intuicija: Imamo dva igralca, oba imata strategije. 
1. igralec ima $n$ strategij, 
2. igralec ima $m$ strategij.
$a_{ij}$ je znesek, ki ga 2.igralec placa 1.igralcu, ce izbere 1.igralec $i$-to strategijo, 2.igralec pa $j$-to. (ce $a_{ij} \lt 0$ - 1.igralec placa 2.igralcu)

D: $\begin{bmatrix} a_{ij} \end{bmatrix}_{\displaylines{i=1,..,n \\ j=1,..,m}} \in \mathbb R^{n \times m}$ je placilna matrika.

D: Princip najmanjsega tveganja - izbereta strategije, kjer 1. najvec zasluzi, 2. najmanj zgubi.
1. igralec: $\max_i \min_j a_{ij} = M_1$ 
2. igralec: $\min_j \max_i a_{ij} = M_2$ 

T: $M_1 \leq M_2$
Dokaz: 
$M_1$ dosezen v vrstici $i$, stolpec $j$. $M_2$ dosezen v vrstici $i'$, stolpcu $j'$.
Izberemo element $a_{ij'}$. Velja: $M_1 \leq a_{ij'} \leq M_2$.

D: $(i_0,j_0)$ je sedlo placilne matrike $A$, ce je $a_{i_0j_0}$ najmanjsi v svoji vrstici in najvecji v svojem stolpcu.

T: Matrika $A$ ima sedlo $\iff M_1=M_2$ 
Dokaz:
$(\Rightarrow)$ $(i_0,j_0)$ sedlo matrike $A$.
$a_{i_0j_0} = \min_j a_{i_0j} \leq M_1$
$a_{i_0j_0} = \max_i a_{ij_0} \geq M_2$ 
$M_1 \geq M_2$, od prej pa vemo $M_1 \leq M_2$ torej $M_1=M_2$
$(\Leftarrow)$ $M_1$ je dosezen v vrstici $i$ in stolpcu $j$. 
$M_2$ je dosezen v vrstici $i'$ in stolpcu $j'$.
Izberemo element $a_{ij'}$.
Vemo da je 
- $M_1 \leq a_{ij'}$
- $M_2 \geq a_{ij'}$
Glede na to da sta $M_1=M_2$ je tudi $a_{ij'}=M_1=M_2$. Trdimo da je ta element sedlo.
Sedlo more bit najmanjsi v vrstici, $M_1$ je najmanjsi v svoji vrstici. Mora biti tudi najvecji v svojem stolpcu, kar $M_2$ je $\implies$ element je sedlo.

D: Ce ima $A$ sedlo v $(i_0,j_0)$ je $i_0$ optimalna strategija za 1.igralca in $j_0$ za 2.igralca.

Op: V tem primeru je $(i_0,j_0)$ Nashevo ravnovesje, nobenemu igralcu se ne splaca spremeniti strategije.

D: Mesana strategija:
1. igralec izbere $(x_1,...,x_n)$
$x_i$ je verjetnost da 1. igralec izbere $i$-to strategijo.
2. igralec izbere $(y_1,...,y_m)$
$y_j$ je verjetnost da 2. igralec izbere $j$-to strategijo.
Veljati mora:
- $\sum x_i = 1$ in $x_i \geq 0$
- $\sum y_j = 1$ in $y_j \geq 0$

Op: Verjetnost da 1. zbere $i$, 2. pa $j$: $x_iy_j$ (ce sta dogodka neodvisna).
Matematicno upanje izplacila za 1.igralca je $\sum_{i=1}^n\sum_{j=1}^m a_{ij}x_iy_j = \sum_{i=1}^n(\sum_{j=1}^m a_{ij}y_j)x_i = \sum_{i=1}^n (Ay)_i x_i = x^TAy$ 

D: Princip najmanjsega tveganja
1. igralec izbere $x$
2. igralec izbere $y$
V najslabsem primeru dobi 1. igralec: $\min_y x^TAy$
- $\max_x \min_y x^TAy$
Podobno za 2. igralca (skrbi ga): $\max_x x^TAy$
- $\min_y \max_x x^TAy$ 
To sta problema za 1. in 2. igralca.

D: Cista strategija $x_i = 1$ in $x_j = 0$ za $j \neq i$. Izgleda kot enotski vektor $x = (0,...,0,1,0,..,0)$ 

Op: Ce 2. igralec izbere cisto strategijo: $x^TAy = \sum_{i=1}^n \sum_{j=1}^m a_{ij}x_iy_j = \sum_{i=1}^n a_{ij}x_i$

T: Naj bo $x$ fiksiran. Potem je $$

