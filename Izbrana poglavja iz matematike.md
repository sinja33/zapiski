# Predavanja
## *Teorija obsegov (in kolobarjev)* 

Primeri:
- Stevila
	- $\mathbb N$ - naravna stevila ((0), 1, 2...) ($\mathbb N_0$)
	- $\mathbb Z$ - cela stevila (... , -2, -1, 0, 1, 2, ...)
	- $\mathbb Q$ - racionalna stevila ($\frac {p}{q}$, stevila ki jih lahko predstavimo kot razmerje celih kolicin -ekvivalencni razredi = okrajsave)
	- $\mathbb R$ - realna stevila
	- $\mathbb C$ - kompleksna stevila
	- $\mathbb H$ - kvaternioni (Hamiltonova stevila)
- Polinomi nad K
	- $K[x] = k_0 + k_1x + k_2x^2 + ... + k_nx^n$, $k_i \in K$ 
	- $K(x)$ vrsta
- Vektorski prostori (nad $\mathbb {Q,R,C}$...)
- Matrike nad K - $K^{m \times n}$
- Funkcije ($f: X \to K$)
	- $(f+g)(x) = f(x) + g(x)$
	- $(fg)(x) = f(x) \cdot g(x)$
- Stevila modulo n (ostanki pri deljenju z n) - $\mathbb Z_n \ , \mathbb Z/_n$ 

D: V kolobarjih imamo 2 operaciji, eno oznacimo s +, in eno s $\cdot$ (sestevanje, mnozenje).
Imamo $(K,+,\cdot)$ kolobar:
- $(K,+)$ - komutativna (oz. Abelova) grupa 
	- asociativnost,
	- komutativnost
	- obstoj nevtralnega elementa (0)
	- obstoj inverza
- $(K,\cdot)$
	- notranja operacija
	- distributivnost
		- $a\cdot (b+c) = a\cdot b + a\cdot c$ --> leva distributivnost
		- $(a + b) \cdot c  = a\cdot c + b\cdot c$  --> desna distributivnost
- ce je/ima $(K,\cdot)$ 
	- asociativno - K je asociativni kolobar
	- komutativno - K je komutativni kolobar
	- nevtralni element (1) - K je kolobar z enoto, "unitalni" kolobar
	- $(K\backslash\{0\}, \cdot)$ inverze - K je kolobar z deljenjem

D: Obseg je asociativen, komutativen, unitaren kolobar z deljenjem.

Terminologija 1: Obseg = asociativen, unitaren, z deljenjem
Polje = komutativen obseg

Terminologija 2: Kolobar z deljenjem = asociativen, unitaren, z deljenjem
Obseg = komutativni kolobar z deljenjem
Mi se drzimo te!

Primeri: 
- $\mathbb Z$ - asociativen, komutativen, unitaren kolobar (ni deljenja $\to$ ni obseg)
- $2\cdot \mathbb Z$ - soda stevila - asociativen, komutativen kolobar (nima enote) 
	- lastnosti operacije se podedujejo na podmnozice, obstoji pa ne
- $\mathbb {Q,R,C}$ - obsegi
- $\mathbb H$ - kolobar z deljenjem (ni komutativen $\to$ ni obseg)
- $K[x]$ - podedujejo lastnosti K, odpove pa deljenje (nimajo inverzov -> lastnost polinoma, ne pa nujno K)
- $M_n(K)$ (kar privzamemo kvadratne) - podedujejo lastnosti operacij od K, odpove pa komutativnost (za $n \geq 2$)
- $(2^X, \cup \ , \cap)$ - asociativnost, komutativnost, distributivnost, pri uniji nam odpove inverz (komutativni, asociativni kolobarji z enoto - Boolovi kolobarji) 
	- lahko popravimo $(2^X, \oplus \ , \cap)$ , $\oplus$ simetricna razlika oz. direktna vsota
	- $A \oplus B = (A - B) \cup (B - A)$

Postopek: Transformacija kolobarja v obseg
Zelimo startat iz K, ki more bit komutativen, asociativen (ker se te lastnosti podedujejo na podmnozico) in unitaren (enoto lahko tudi umetno dodamo, ampak za enostavnost) IN brez deliteljev nica.
Vsiliti hocemo deljenje, ideja $a,b,... \in K: \{\frac {a}{b}| \ a,b \in K\}$ bo "predvidoma" obseg.
Dva problema
- Enolicnost zapisa $\frac {a}{b} = \frac {k\cdot a}{k\cdot b}$ -velja-> $\frac {a}{b} \sim \frac {c}{d} \iff a\cdot d = b \cdot c$  --> je relacija ekvivalence $\{[\frac {a}{b}] \ | \ a,b \in K \land b \neq 0\}$ 
- Imenovalec $\neq 0$ 
	- $[\frac {a}{b}] + [\frac {c}{d}] := [\frac {ad + bc}{bd}]$
	- $[\frac {a}{b}] \cdot [\frac {c}{d}] := [\frac {ac}{bd}]$

#### *Deljitelji nica*

D: $a \in K$ je delitelj nica, ce je $a \neq 0$ in obstaja $b \neq 0$ tako da $a\cdot b = 0$. (modulo!)

I: Delitelj nica ne more biti obrnljiv.
Dokaz: Recemo, da je a delitelj nica ($a \neq 0$) in obrnljiv ($a\cdot a' = a'\cdot a = 1$).
$a\cdot b = 0$ --> $a' \cdot a = 1$ $/ \cdot b$ 
		   $a' \cdot a \cdot b = b$
		   $a' \cdot 0 = b$
$\rightarrow\leftarrow$ 

I: Ce je K komutativen, asociativen, unitaren kolobar brez deliteljev nica. Potem je $K^* := (\{[\frac {a}{b}] \ | \ a \in K , b \in K\backslash \{0\}\}, +, \cdot)$  obseg (obseg ulomkov za K).

D: Mnozica ekvivalencnih razredov:
$K^* = K \times (K-\{0\})/_{\sim}$ $\frac{a}{b}\sim \frac{a'}{b'} \to ab' = a'b$.
$(K^*,+,\cdot)$ je obseg!

Opomba: $K$ gledamo kot podmnozico v $K^*$ tako, da vsak element enacimo kot: $a \leftrightarrow [\frac{a}{1}]$ (isti fenomen kot pri obicajnih ulomkih).

Primeri:
- $\mathbb Z \leadsto \mathbb Q$  
- $K \leadsto K[x] \leadsto (K[x])[y]$ ... poljubni kolobar $\leadsto$ polinomi v spremenljivki x $\leadsto$ polinomi v dveh spremenljivkah
	- Iz $K$ v $K[x]$ se prenesejo lastnosti kot so asociativnost, komutativnost, unitarnost...
	- Edino kar moramo preveriti so deljitelji nica:
	- $(a_0 +a_1x +a_2x^2 + ... + a_nx^n)(b_0 +b_1x + ... + b_nx^n) = a_0b_0 + (a_1b_0 + a_0b_1)x + ...$
	- Ce je $K$ brez deljiteljev nica, potem je $K[x]$ tudi brez deljiteljev nica

Primer (konkretno za $K[x]$):
1. $\mathbb R[x]$ je asociativen, komutativen, unitaren, brez deljiteljev nica, saj to vse velja za $\mathbb R$. Torej lahko tvorim obseg ulomkov
	- $\mathbb R[x] \leadsto (\mathbb R[x])^*$ = racionalne funkcije... standardna oblika: $\mathbb R(x)$
2. $\mathbb Z[x] \leadsto (\mathbb Z[x])^* = \mathbb Q(x)$
3. Mejni primer
	- Denimo, da je $K$ obseg, kaj je $K^*$?
	- $\frac {a}{b} \sim \frac {a:b}{1}$ oz. $ab^{-1} \to K^* =K$.
4. $\mathbb Z_n$ elementi so bodisi obrnljivi ali pa deljitelji nica 
	- ![[Pasted image 20240309234354.png]]
5. Matrike: $M_n(\mathbb R)$ 
	- $A \in M_n (\mathbb R)$ ni obrnljiva, potem obstaja en vektor $x$, da velja $A\vec x = 0$
	- $A(\vec x,..., \vec x) = 0$ --> $n$-krat. 
	- Torej velja isto kot pri 4.)
6. $\mathbb Z$ 
	- ![[Pasted image 20240309234731.png]] 

I (Wedderburnov izrek): Koncen kolobar (asoc. in unitaren) brez deljiteljev nica je obseg. 
(V koncnem kolobarju je ? - iz slike pod konkretnim primerom 4) - prazen)
Dokaz: 
- $a\in K - \{0\}$ ... trdimo, da obstaja $a'$ tako da velja $a\cdot a' = a' \cdot a = 1$.
- Mnozica $\{a\cdot x \ |\ x \in K - \{0\}\}$
- Ce $a\cdot x = a \cdot y \to a (x-y) = 0$
- Ker nimamo deljiteljev nica $a \neq 0 \to x-y = 0$ 
- Vsi elementi so razlicni, $K$ je koncen
- $\exists a': a\cdot a' = 1$
- Identicno lahko naredimo mnozico $\{x\cdot a \ |\ x \in K - \{0\}\}$
- Torej obstaja: $a'' \cdot a = 1$
- $a'' \cdot a \cdot a' = (a'' \cdot a) \cdot a' = a'' \cdot(a \cdot a')$
- Vidimo: $a'' = a' \to a$ je obrnljiv
Pokazali smo, da ce imamo asociativni in unitaren kolobar brez deljiteljev nica $K$ je to kolobar z deljenjem (dobimo tudi komutativnost? DA).

D: Center kolobarja so vsi $x \in K$ za katere velja $a\cdot x = x \cdot a$ za vse $a$. To nam da obseg, ki lezi znotraj kolobarja.

I (Wedderburnov izrek - nadaljevanje): $K$ je enak svojemu centru. $K$ je komutativen.

Opomba: Kolobar je vektorski prostor nad podobsegom.

#### *Karakteristika*

D: Karakteristika kolobarja:
ce je $K$ kolobar, potem recemo, da je karakteristika kolobarja najmanjse naravno stevilo $n \in \mathbb N$, ki ima lastnost: $n\cdot a = 0$ za $\forall a \in K$, ce tak $n$ obstaja oziroma 0, ce tak $n$ ne obstaja. Oznaka: char$K$.
char$K = \begin{cases} 0,  \nexists n: na = 0 \ \forall a \in K \\ n,  \exists n: na = 0 \ \forall a \in K \end{cases}$ 

Pazi: $n\in \mathbb N, \ a\in K$ sledi: $n\cdot a = a + a \ + ... + \ a$ ($n$-krat) ni mnozenje el. iz kolobarja ampak vbistvu sestevanje enega in istega elementa.

T:
1. char$K = min\{n\ | \ n1 = 0\}$
2. Ce K nima deljiteljev nica, potem char$K$ je prastevilo ali pa 0.
Dokaz: 
1. char$K = n \ \to  \ n\cdot 1 = 0$. Obratno, ce je $n1 = 0$.
	$n1 = (1+1 \ + ... + \ 1) = 1$ ($n$-krat) potem je tudi $a + a \ + ... + \ a = 0$ ($n$-krat)
	saj $a + a \ + ... + \ a = a (1+1 \ + ... + \ 1) = a \cdot 0 = 0$ 
2. s protislovjem
	char$K = n \ \to  \ n = k\cdot l$, kjer $k,l \gt 1$ (ni prastevilo)
	$n1 = (1+1 \ + ... + \ 1)\cdot (1+1 \ + ... + \ 1) = 0$ (prvi oklepaj $k$-krat, drugi $l$-krat), saj ker $k,l \gt 1$ in $n=k\cdot l \to n \gt k,l \to$ deljitelja nica

Posledica: Karakteristika obsega je nic ali pa prastevilo!

Primeri: 
1. char$\mathbb Z = 0 =$ char$\mathbb Q =$ char$\mathbb R =$ char$\mathbb C = 0$ 
2. char$\mathbb Z_n = n$
3. char$K[x] =$ char$K$
4. $M_n(K) =$ char$K$

Postopek: 
Privzemimo char$K = p$ prastevilo
$0 \in K$
$1 \in K$
$1+1 \in K$
$1+1+1 \in K$
...
$(1+1+1+...+1) \in K$ ((p-1)-krat)
$\mathbb Z_p$ lahko gledamo kot podkolobar $K$.

Komentar: Elemente $\mathbb Z_p$ oznacimo z $r$, $x$ pa je poljuben element kolobarja $K$ je za sestevanje Abelova grupa:
- $(K,+)$ ... Abelova grupa
- $r(x+y) = rx + ry$ ... distributivnost
- $(rs)x = r(sx)$ ... asociativnost
- $(r+s)x = rx + sx$ ... (desna) distributivnost
- $1x = x$ 
Prepoznamo vektorski prostor.

T: char$K = p$  prastevilo je $K$ vektorski prostor nad $\mathbb Z_p$.

Posledica: $K$ je koncen kolobar s karakteristiko, ki je prastevilo potem je: $|K| = p(\dim_{\mathbb Z_p}K)$ 

D: $K$ obseg, char$K = p$
$\displaylines {\to \mathbb Z_p \subseteq K \\ \mathbb Q \subseteq K}$ ... char$K = 0$ 
$\mathbb Z_p, \mathbb Q$ - praobsegi

Primeri:
1. $X$ mnozica 
$(2^X, +, \cap)$ je kolobar... Koliko je karakteristika tega kolobarja?
$A+A = \emptyset \to$ karakteristika je 2
(spomnimo: $2^X$ ima $2^{|X|}$ elementov)

#### *Homomorfizem*

D: $K$ in $L$ naj bosta kolobarja, potem je $f:K \to L$ homomorfizem, ce velja (za $\forall x,y \in K$)
 - $f(x+y) = f(x) + f(y)$ ... aditivnost
 - $f(x\cdot y) = f(x) \cdot f(y)$ ... multiplikativnost
 - implicira $f(0)=0$ in $f(-x) = -f(x)$
 - $f(1_K) = 1_L$ ... unitalnost (slika enoto v enoto) - unitalen homomorfizem

Primeri:

1. $\mathbb Z\hookrightarrow \mathbb Q \hookrightarrow \mathbb R\hookrightarrow \mathbb C$ (znak za inkluzijo - gledas kot podmnozico) ... so homomorfizmi (unitarni)

2. $\mathbb Z \to \mathbb Z_n$ kjer $k\to k\mod n$ ... unitarni homomorfizem

3. $\mathbb C: z \to \overline z$ konjugiramo kompleksna stevila ... unitarni homomorfizem
Velja:
- $\overline {(z+w)} = \overline z + \overline w$ 
- $\overline {(zw)} = \overline z \cdot \overline w$ 
-  $\overline 1 = 1$ 

4. $\mathbb R \to M_n(\mathbb R)$ slikamo realna stevila v matrike. Vec opcij:
- $x\to \begin{bmatrix}x & 0\\0 & x\end{bmatrix}$ ... unitaren homomorfizem ($\begin{bmatrix}1 & 0\\0 & 1\end{bmatrix}$ enota)
- $x\to \begin{bmatrix}x & 0\\0 & 0\end{bmatrix}$ ... ni unitaren homomorfizem

5. $\mathbb R[x] \to \mathbb R$ (najpomembnejsi primer) 
Preslikava: $a\in \mathbb R, \ p(x) \to p(a)$ (izracunamo ta polinom v a)
To funkcijo oznacimo kot $\varphi_a$. Velja $\varphi_a(p(x)) = p(a)$ 
- $\varphi_0(a_0 + a_1x+...) = a_0$
- $\varphi_1(a_0 + a_1x+...) = a_0 + a_1 + ... + a_n$ 
- $\varphi_{-1}(a_0 + a_1x+...) = - a_0 - a_1 - ... - a_n$ 
Homomorfizem:
- $\varphi_a(p(x) + q(x)) = p(x) + q(x) = \varphi_a(p(x)) + \varphi_a(q(x))$
- $\varphi_a(p(x) \cdot q(x)) = p(x) \cdot q(x) = \varphi_a(p(x)) \cdot \varphi_a(q(x))$ 
- Lahko recemo: $a\in K: \ \varphi_a: K[x] \to K$ 

6. $f\to f'$ (odvajanje)
Velja:
- $(f+g)' = f' + g'$ ... aditiven
- $(f\cdot g)' = f'g + fg'$ ... ni multiplikativen
Ni homomorfizem.

7. $f\to f^2$ (kvadriranje)
Velja:
- $(x+y)^2 = x^2 + 2xy + y^2$ ... ni aditivno
- $(xy)^2 = x^2y^2$ ... multiplikativno
Ni homomorfizem. Kaj pa ce je karakteristika kolobarja = 2?
- $(x+y)^2 = x^2 + 2xy + y^2 = x^2 + y^2$ ... aditivno
- $(xy)^2 = x^2y^2$ 
Dobimo aditivnost $\to$ kvadriranje postane homomorfizem.

8. $f\to f^3$
Velja: 
- $(x+y)^3 = x^3+ 3x^2y + 3xy^2 + y^3$
- $(xy)^3 = x^3y^3$ 
Spet ni homomorfizem, a postane ce je karakteristika 3.

T: Ce je karakteristika kolobarja enaka prastevilu $p$, potem je $f(x) = x^p$ homomorfizem iz $K$ v $K$ ($K$ je komutativni kolobar).
Dokaz: Vidno je multiplikativen, kaj pa aditivnost?
$(x+y)^p = x^p + \binom{p}{1}x^{p-1}y + \ ... \ + \binom{p}{i}x^{p-i}y^i + \ ... \ + y^p$  
$\binom{p}{1}$ in $\binom{p}{p-1}$ sta $=0$. 
Splosni clen pa $\binom{p}{i} = \frac{p\cdot (p-1)\cdot \ ... \ \cdot (p-i+1)}{i!}$ ($i$ je celo stevilo ... je deljiv s $p$ ... vsi vmesni cleni odpadejo)
Ostane: $x^p + y^p$ 
$\rightarrow$ Frobeniusov avtomorfizem (spomnimo: avtomorfizem = bijektiven homomorfizem sam vase)

T: $f: K\to L$ homomorfizem, potem je $Im(f) = \{f(x) \ | \ x\in K\}$  oz. $Im(f) = f(K)$. Velja, da je $Im(f)$ podkolobar $L$.
Dokaz:
- $f(x), f(x')\in Im(f)$
	- $f(x)+f(x') = f(x+x')$ 
	- $\to f(x)\cdot f(x') = f(x\cdot x')$ 
- $f(0) = 0$ oz. $f(0_K) = 0_L$ 
- $f(-x) = -f(x)$
Torej $Im(f)$ je Abelova grupa za sestevanje, distributivnost pa sploh ni treba pregledati $\to$ je podkolobar.

Ponovitev: Injektivnost - $\forall x,y$
$f(x) = f(y) \to x=y$ 
To pomeni: $f(x) - f(y) = 0 \to f(x-y) = 0$ 
Na drugi strani: $x-y = 0$
Torej: $f(x-y)=0 \to x-y = 0$ 
Tako je $f$ injektivna, ce iz $f(x) = 0$ sledi $x=0$.

#### *Jedro*

Jedro homomorfizma: $Ker(f) = \{x\in K \ | \ f(x) = 0\} = f^{-1}(0_L)$ - kernel / jedro / nicelna mnozica 
Oznaka: $N(f)$ 

Ponovitev: $X,Y$ mnozici, $f:X\to Y$ funkcija
$\mathcal P(X) \overset{f_*}{\longrightarrow} \mathcal P(Y)$ in $\mathcal P(Y) \overset{f^*}{\longrightarrow} \mathcal P(X)$ kjer:
- $f_*(A) = \{f(a) \ | \ a\in A\} \subseteq Y, \ A \subseteq X$ ... slika 
- $f^*(B) = \{x\in X \ | \ f(x) \in B\} \subseteq X, \ B\subseteq Y$ ... praslika
Torej: $f^{-1} = f^*$ 

T: $f:K\to L$ homomorfizem, potem je $Ker(f)$ podkolobar v $K$.
$x,y\in Kerf$
$f(x) = f(y) = 0$
$f(x+y) = f(x) + f(y) = 0$
$f(xy) = f(x) \cdot f(y) = 0$ 
Pomembna lastnost: $x\in Kerf$ in poljuben $y\in K$
$f(xy)=f(x)\cdot f(y) = 0\cdot f(y) = 0$
$\to x\cdot y\in Kerf$ ... tudi obratno ce zamenjamo vlogi $x$ in $y$

T: $Kerf$ absorbira mnozenje s poljubnim elementom $K$

#### *Ideali*

D: Podkolobar $I \leq K$ je ideal, ce absorbira mnozenje s poljubnim elementom $K$ ($\forall a \in K, \ \forall x \in I \implies a\cdot x \in I,\ x \cdot a \in I$, oziroma krajse $K \cdot I \subseteq I, \ I \cdot K \subseteq I$)
Simbol: $I \lhd K$.

I: Za poljuben homomorfizem $f: K \to L$ je $Ker f$ (jedro) ideal v $K$. Velja: $Ker f \lhd K$.

Primeri (idealov):
- $K$:
	- $\{0\} \lhd K$, $K \lhd K$ - trivialna oz. neprava ideala
- $\mathbb Z$:
	- $2\cdot\mathbb Z \lhd \mathbb Z$ - soda stevila
	- $n\cdot\mathbb Z \lhd \mathbb Z$ - splosneje ($n\in\mathbb Z$)
- $\mathbb Q$
	- $I \lhd \mathbb Q, \ I \neq \{0\}$ 
	$\to$ obstaja $0 \neq q \in I$
	$x \in \mathbb Q$ poljuben, $x = \frac {x}{q}\cdot q$ 
	$q \in I \implies \frac {x}{q}\cdot q \in I \implies x \in I$ 
	$\implies I = \mathbb Q$ 
- $K$ obseg $\to$ edina ideala v $K$ sta $\{0\}$ in $K$ (velja tudi obratno)
	$1 \in I \implies x = x\cdot 1 \in I$
	$q\in K$ obrnljiv, 
	$q \in I \implies x = (x\cdot q^{-1})\cdot q \in I$ 
	Pravi ideal $I \lhd K$ ne vsebuje obrnljivih elementov.
- $\mathbb R[x]$ 
	- $I = \{p(x) \ | \ a_0 = 0 \} \lhd \mathbb R[x]$ 
	- $I = x \cdot \mathbb R[x] = Ker \varphi_0$  ($\varphi_0:p(x) \to p(0)$) je jedro homomorfizma

T: Vsak ideal v kolobarju celih stevil $\mathbb Z$ je oblike $n\cdot\mathbb Z$ za neko naravno stevilo $n$. 
D: $I \lhd \mathbb Z$.
Naj bo $n$ najmanjsi pozitivni element $I$ in trdim da je $I = n \cdot \mathbb Z$.
Vzemimo $x \in I$, ta $x$ lahko delimo z $n$ in dobimo kolicnik $q$ in ostanek $r$.
$x = nq + r, \ 0 \leq r \leq n$  
- $x \in I$ (po def)
- $n \in I \implies nq \in I$ 
- $x-nq\in I \implies r \in I \implies r = 0$ 
To pomeni $x = nq$.

T: $K$ obseg. Vsak ideal $I \lhd K[x]$ je oblike $p(x)\cdot K[x]$ za nek polinom $p(x)$.
D: Zelimo $I$, naj bo $p(x)$ polinom najnizje stopnje v $I$ z vodilnim koeficientom 1.
Vzamemo $g(x) \in I$. Delimo $g(x):p(x) = q(x) + r(x)$, ostanek $r$ za katerega velja $0 \leq \deg r(x) \leq \deg p(x)$.
$g(x) = q(x)\cdot p(x) + r(x)$
- $g(x) \in I$
- $p(x) \in I \implies q(x)\cdot p(x) \in I \implies r(x) \in I$
- To pomeni $g(x) \in p(x)\cdot K[x]$
Trditev ne velja, ce $K$ ni obseg. 
- $x:2x = 0$, ostanek $x$ v $\mathbb Z$
- $x:2x = \frac {1}{2}$, ostanek 0 v $\mathbb Q$ ali $\mathbb R$

Oznaka: $K$ kolobar, $x\in K$
$(x) = x\cdot K$, ideal vseh $x$-kratnikov elementov $K$
glavni ideal (generiran s $x$)
#### *Podkolobar*

Ponovitev:
$K \rhd I$ ideal
Podkolobar:
- $K\cdot I \subseteq I \land I\cdot K \subseteq I$ 
- $f: K \to L$ homomorfizem
$\leadsto Kerf \lhd K$ (dvostranski ideal)

Primer: $\mathbb Z_3$
$2+5 = 1$
Po korakih:
$((2+1) + 2)+2$
$(0 + 2)+2$ 
$(2+2)$
$1$
- $\{0,3,6,9,...,-3,...\} \leadsto 3\mathbb Z$    
- $\{1,4,7,...,-2,...\} \leadsto (1+3\mathbb Z)$ 
- $\{2,5,8,...,-1,-4,...\} \leadsto (2+3\mathbb Z)$ 
Mnozico $\mathbb Z_3$ smo razdelili na tri podmnozice, to so ekvivalencni razredi
Algoritem:
$a$ in $b$ sta ekvivalentna $a\sim b$ ce je $3|a-b$  oziroma $a-b \in 3\mathbb Z$ 

Splosno: $I \lhd K$ dvostranski ideal
$a\sim b \iff a-b \in I$

T: $\sim$ je ekvivalencna relacija.
Dokaz: 
- $a\sim a$ ocitno velja ker $a-a = 0\in I$
- $a\sim b \implies b\sim a$
	- $a-b \in I \leadsto b-a\in I$
- $a\sim b, b\sim c$
	- $a-b \in I, b-c \in I$
	- $a-c = (a-b)+(b-c) \in I \implies a \sim c$

D: $K / \sim$ mnozica ekvivalencnih razredov 
$= K / I$ ($K$ po idealu $I$ oziroma $K$ po ekvivalencni relaciji, ki jo je generiral ideal $I$) elemente te mnozice obicajno pisemo $x+I, x\in K$ 
Velja: $x+I = y + I$, ce je $x-y\in I$ 
Na $K / I$ prenesemo $+,\cdot$ iz $K$. Zelimo:
- $(x+I)+ (y+ I) = (x+y) + I$ ... vsota
- $(x+I)\cdot (y+ I) = (x \cdot y) + I$ ... produkt

Definicija $+, \cdot$ je dobra $\to$ neodvisna od izbire predznaka
- $x+I = x' + I, \ x-x'\in I$
- $y+I = y' + I, \ y-y'\in I$ 
- $(x+y)+I = (x'+y') + I, \ (x+y) - (x'+y')\in I$
Dokazujemo: 
$\displaylines{(x\cdot y)+I = (x'\cdot y') + I \\ (x\cdot y) - (x'\cdot y') = \\ = x\cdot y - x'\cdot y' + x'\cdot y - x'\cdot y = \\ = y(x-x') + x' (y-y')}$  
		$\in I$ 		       $\in I$ 
Ideal absorbira mnozenje (z obeh strani tako da sta oba clena v $I$ )
Vsota dveh elementov iz ideala je spet element v $I$ (tako da je celotni izraz v $I$)

D: $(K/I, +, \cdot)$ 
- Nicla je $0 + I = I$
- Nasprotni element od $x + I$ je $-(x + I)$ neg. predznak!
$K / I$ je podkolobar, ki podeduje:
- Asociativnost, komutativnost, enoto od $K$ 
- Recemo: K modulo I

Primer:
- $K$ 
	- $(0) \lhd K$ sledi $K / (0) = K$
	- $K \lhd K$ sledi $K/K = \{0\}$ 
- $(n) = n\mathbb Z \lhd \mathbb Z$ 
	- $\mathbb Z / (n) = \mathbb Z_n$ oziroma $\mathbb Z / n\mathbb Z$ 
- $\mathbb R[x]$
	- Zanima nas $R[x] / (x)$, kjer $(x) = x\cdot \mathbb R[x]$ 
	- $(a_0 +a_1x +a_2x^2 + ... + a_nx^n)\sim (b_0 +b_1x + ... + b_nx^n)$ ce je $(a_0-b_0) + (a_1-b_1)x \ + \ ... \in (x)$ tj. ce velja $a_0 - b_0 = 0, \ a_0 = b_0$ 
	- Vsak ekvivalencni razred v kvocientu predstavimo z ostankom pri deljenju z x. Torej: $\displaylines{(a_0 + (x)) + (b_0 + (x)) = (a_0+b_0)(x) \\ (a_0 + (x)) \cdot (b_0 + (x)) = (a_0 \cdot b_0)(x)}$ 
	- $\mathbb R[x] / (x) \cong \mathbb R$ ... izomorfnost z $\mathbb R$ 
- $\mathbb R[x] / (x^2)$ 
	- predstavniki: $a_0 + a_1x + (x^2)$
	- Sestevanje: $(a_0,a_1) + (b_0,b_1) = (a_0 + b_0, a_1 + b_1)$ po komponenti
	- Mnozenje: $(a_0,a_1) \cdot (b_0,b_1) = a_0b_0 + (a_0b_1 + a_1b_0)x + (a_0b_2 + a_1b_1 + a_2b_0) x^2 \ + \ ...$ 
							 ----predstavnik----        ----od tu naprej deljivo z $x^2$
	- Na koncu dobimo: $(a_0,a_1) \cdot (b_0,b_1) = a_0b_0 + (a_0b_1 + a_1b_0)x + (x^2)$ 
- $\mathbb R[x] / (x^2 + 1)$
	- predstavniki: $a+bx + (x^2 + 1)$ in $c+dx + (x^2 + 1)$
	- Sestevanje: $(a+c) + (b+d)x + (x^2 + 1)$
	- Mnozenje: $(a+bx)\cdot (c+dx) = ac + (ad+bc)x + (bd)x^2 = ac + (ad+bc)x + (bd)(x^2+1) -bd$ (ostanek: -$bd$) $= (ac-bd) + (ad+bc)x + (x^2+1)$ 
	- $\displaylines{(a,b) + (c,d) = (a+c,b+d) \\(a,b) \cdot (c,d) = (ac - bd, ad + bc)}$ kot kompleksna stevila!
	- Modulo $(x^2+1)$ se obnasa kot $i$ 

I: (izrek o izomorfizmu): Imamo homomorfizem kolobarjev $f: K \to L$. $Ker f$ je dvostranski ideal v $K$ in imamo izomorfizem $\overline f:K / Kerf \to Im f$, ki je definiran: $x + Ker f \mapsto f(x)$ 
Dokaz: 
$\overline f:K / Kerf \to Im f$ 
$\overline f(x + Kerf) = f(x)$ doloca homomorfizem
Dobro definiran $\overline f$:
- $x + Kerf = x' + Kerf$ ko $x-x' \in Kerf$ 
- $f(x) - f(x') = f(x-x') = 0$ 
$Im \overline f = Im f$ ocitno
$Ker \overline f = \{x + Kerf \ | \ f(x) = 0\} = 0 + Kerf$ je trivialna
$\leadsto \overline f$ je bijektiven.

Primer (dalje):
- $\varphi_i: \mathbb R[x] \to \mathbb C$ | $\varphi_i: \mathbb C[x] \to \mathbb C$ 
- $\varphi_i: p(x) \mapsto p(i)$
- surjektivna $\varphi_i: a+bx |_{x= i} = a+bi$ 
- $Ker\varphi_i$ 
- $p(x) \leadsto p(i) = 0$, potem je tudi $p(-i) = 0$ 
  $\in \mathbb R$                  $\leadsto (x-1)(x-i)|p(x)$ 
			 $\leadsto p(x) \in (x^2+1)$ 

T: $p(x) \in \mathbb R[x], z \in \mathbb C$
Velja: $p(z) = 0 \iff p(\overline z) = 0$ 
Dokaz:
$p(x) = a_0 +a_1x +a_2x^2 + ... + a_nx^n$, $a_i \in \mathbb R$ 
$0 = p(z) = a_0 +a_1z +a_2z^2 + ... + a_nz^n$
$0 = \overline a_0 + \overline a_1 \overline z + \overline a_2 {\overline z}^2 + ... + \overline a_n \overline z^n = a_0 + a_1 \overline z + ... +  a_n \overline z^n = p(\overline z)$ 

Primeri:
- $\mathbb R[x]/(x^2)$
- $\mathbb R[x]/(x^2 + 1) \cong \mathbb C$ ... obseg (ni deljiteljev nica)

T: Kdaj je $K / I$ obseg? (Kaksen mora biti $I$, da je $K / I$ obseg)
Komutativen kolobar $K$ je obseg natanko takrat, ko nima pravih idealov.
Dokaz:
- $(\rightarrow)$ smo ze
- $(\leftarrow)$: 
$0 \neq x \in K$... $x$ nenicelni element v $K$
$(x) = x\cdot K \lhd K$ ... ideal v $K$
$\implies (x) = K$, tj. $\exists \ x'$ tako da: $x\cdot x' = 1$ 
$x'$ je obrnljiv element.

T: Ali je $K/I$ obseg? (Kaj so ideali v $K/I$?)
$g:K\to K/I$, $x\mapsto x+ I$ je surjektiven (x-u priredi njegov ekvivalencni razred)
$\to$ jedro je $I$ ... $Kerg$ ideal

Postopek: $K \lhd I$, kdaj je $K/I$ obseg? 
Vemo: $K$ je obseg $\iff$ nima pravih idealov. 
Prevedli smo na vprasanje: Kaj so ideali v $K/I$? 
- $g: K \to K/I$ 
- $\mathcal J \to g(\mathcal J)$ 
- $g^*(J’) \to J’$ 
Velja:
1. $K \lhd \mathcal J$ in $K/I \lhd g(\mathcal J)$ 


#### Konstruktibilna stevila

- Pravilni poligoni
- Podvojitev kocke
- Kvadratura kroga
- Trisekcija kota

D: Konstruktibilna stevila so stevila, ki jih lahko dobimo kot rezultat izmerno mnogo ponovitev naslednjih korakov.

Velja:
- $1$ je konstruktibilno stevilo
- $x,y$ sta konstruktibilni stevili $\iff$ $(x,y)$ je konstruktibilna tocka
- $(x,y), (x',y')$ konstruktibilni tocki, potem lahko konstruiramo
	- Premico skozi $(x,y)$ in $(x',y')$
	- Kroznico skozi $(x',y')$ s srediscem v $(x,y)$

T: Preseki 
- dveh konstruktibilnih premic,
- dveh konstruktibilnih kroznic
- konstruktibilne premice in konstruktibilne kroznice,
so konstruktibilne tocke.
(Tocke ki se sekajo so konstruktibilne)

T: Naj bo $K$ mnozica konstruktibilnih stevil. $K$ je obseg (podobseg $\mathbb R$)
Dokaz: SLIKA

Postopek: Razsiritev
$K^{\mbox{obseg}} \subseteq F^{\mbox{obseg}}$ 
$F$ je razsiritev obsega $K$, $K \leq F$. 

Primer:
- $\mathbb Q \leq K \leq \mathbb R \leq \mathbb C$
- $\mathbb Q \leq \mathbb Q(\sqrt 2) \leq K$ 
- $\mathbb Q \leq \mathbb Q(\sqrt[3] 2) \leq K$ 
- $\mathbb Q(\sqrt[3] 2) \leq \mathbb R$  
- med $\mathbb R \leq \mathbb C$ ni vmesnih obsegov!

Postopek:
$K\leq F \leadsto F$ je vektorski prostor nad $K$:
$\dim_K F =: [F:K]$ 
- Koncna razsiritev
- Neskoncna razsiritev

Primeri:
- $[\mathbb Q(\sqrt 2): \mathbb Q] = 2$ 
- $[K:\mathbb Q] =$ neskoncna
- $[\mathbb C: \mathbb R]= 2$ 
- $[\mathbb Q(\sqrt[3]2):\mathbb Q] = 3$

I: $K \leq F \leq  E=[E:K]=[E:F]:[F:K]$ 
Dokaz:
- Za neskoncne razsiritve velja (trivialno)
- Za koncne:
Naj bo $x_1,..,x_n\in F$ baza $F$ nad $K$.
Naj bo $y_1,...,y_m\in E$ baza $E$ nad $F$.
$\{x_iy_j \ | \ i=1,...,n \ , \ j=1,..,m\}$ je baza $E$ nad $K$.
- Razpenja
- Linearno neodvisno
$e\in E$
$f_j = \sum_{i=1}^n k_{ij}x_i$ 
$e = \sum_{j=1}^m f_jy_j = \sum_{i=1}^n\sum_{j=1}^m k_{ij}(x_iy_j)$
$0 = \sum_{\displaylines{i= 1,...,n \\ j=1,...,m}} k_{ij}x_iy_j = \sum_{j=1}^m(\sum_{i=1}^n k_{ij}x_i)y_j \leadsto \sum_{i=1}^n k_{ij}x_i = 0$ za vse $j$
$x_i$ linearno neodvisen nad $K$ $\leadsto k_j=0 \ \ \forall i,j$ 

D: $K \leq F, \ a\in F$
$K[a]=\{p(a) \ | \ p(x)\in K[x]\}$ - najmanjsi podkolobar $F$, ki vsebuje $K$ in $a$
$K(a) = \{\frac{p(a)}{q(a)} \ | \ p(x),q(x)\in K[x], \ \ q(a)\neq 0\}$ - najmanjsi podobseg $F$, ki vsebuje $K$ in $a$
$K[a]\subseteq K(a)$

Primeri:
- $\mathbb Q[\sqrt 2] = \mathbb Q(\sqrt 2)$ 
- $\mathbb Q[\sqrt[3] 2] = \mathbb Q(\sqrt[3] 2)$
- $\mathbb Q[\pi] \neq \mathbb Q(\pi)$ (netrivialni izrek)

Kljucni korak:
$\varphi_a: K[x]\to F$, $p(x)\mapsto p(a)$ 
$K[a] = Im\varphi_a \cong K[x]/Ker\varphi_a$  
$= K(a)$ 
$\varphi_a: K[x]\to F$
- $Ker\varphi_a = (0)$ (tj. $\varphi_a$ je injektiven) $\to$ $a\in F$ je transcendenten nad $K$, ce ni nicla nobenega polinoma iz $K[x]$ 
- $Ker\varphi_a \neq (0)$ (tj. $\varphi_a$ ni injektiven) $\to$ $a\in F$ je algebraicen nad $K$, ce je nicla nekega polinoma iz $K[x]$ 
$Ker\varphi_a =$ polinomi v $K[x]$, ki imajo niclo $a$ (npr. $\sqrt 2$ je nicla $x^2=2$ nad $\mathbb Q$; 
$\varphi_{\sqrt 2}: \mathbb Q[x]\to\mathbb R$, $x^2-2\in Ker\varphi_{\sqrt 2}$)

Vpr: Katera stevila so konstruktibilna?
$\mathbb Q \leq K_1 \leq K_2 \leq ... \leq \cup K_n = K \lneq \mathbb R$ 
$K\leq F$,  $a\in F$,  
- $K\leq K(a)\leq F$
- $K\subseteq K[a] \subseteq K(a)\leq F$ 
$K[a]=Im(\varphi_a: K[x]\to F)$ 
$K[a] \cong K[x]/_{Ker\varphi_a}$ ($Ker\varphi_a$ - polinomi, ki imajo niclo v $a$)  

I: (o izomorfizmu)
1. Moznost: 
$Ker\va$


...???

Posledica: $a\in F, \ F$ koncna razsiritev $K \implies \deg g_a(x)\ |\ [F:K]$ 
Dokaz:
$K\leq K(a)\leq F$
$[F:K] = [F:K(a)]\cdot [K(a):K]$, 
$[K(a):K]$ pa je ravno $\deg g_a(x)$ 

I: Konstruktibilna stevila so natanko vsa realna stevila, katerih stopnja minimalnega polinoma nad $\mathbb Q$ je potenca stevila 2.
Dokaz: 
$a$ konstruktibilno $\implies$ obstajajo $a_1,a_2,...,a_n$ 
$\mathbb Q \leq \mathbb Q(a_1) \leq \mathbb Q(a_1,a_2) \leq ... \leq \mathbb Q(a_1,a_2,...,a_n) \ni a$   

???

Primeri:
- podvojitev kocke ni 


## *Topologija*
#### *Kompaktnost*
#### *Povezanost*
## *Fourierjeva analiza*
#### *Fourierjeva vrsta*
#### *Fourierjeva transformacija*


# Ucenje
## Kolobarji
### P1

D: Imamo $(K,+,\cdot)$ kolobar:
- $(K,+)$ - komutativna (oz. Abelova) grupa 
	- asociativnost,
	- komutativnost
	- obstoj nevtralnega elementa (0)
	- obstoj inverza
- $(K,\cdot)$
	- notranja operacija
	- distributivnost
		- $a\cdot (b+c) = a\cdot b + a\cdot c$ --> leva distributivnost
		- $(a + b) \cdot c  = a\cdot c + b\cdot c$  --> desna distributivnost
- ce je/ima $(K,\cdot)$ 
	- asociativno - K je asociativni kolobar
	- komutativno - K je komutativni kolobar
	- nevtralni element (1) - K je kolobar z enoto, "unitalni" kolobar
	- $(K\backslash\{0\}, \cdot)$ inverze - K je kolobar z deljenjem

D: Obseg je asociativen, komutativen, unitaren kolobar z deljenjem.

D: $a \in K$ je delitelj nica, ce je $a \neq 0$ in obstaja $b \neq 0$ tako da $a\cdot b = 0$. (modulo!)

I: Delitelj nica ne more biti obrnljiv.
Dokaz: Recemo, da je a delitelj nica ($a \neq 0$) in obrnljiv ($a\cdot a' = a'\cdot a = 1$).
$a\cdot b = 0$ --> $a' \cdot a = 1$ $/ \cdot b$ 
		   $a' \cdot a \cdot b = b$
		   $a' \cdot 0 = b$
$\rightarrow\leftarrow$ 

P: Zelimo startat iz K, ki more bit komutativen, asociativen (ker se te lastnosti podedujejo na podmnozico) in unitaren (enoto lahko tudi umetno dodamo, ampak za enostavnost) IN brez deliteljev nica.
Vsiliti hocemo deljenje, ideja $a,b,... \in K: \{\frac {a}{b}| \ a,b \in K\}$ bo "predvidoma" obseg.
Dva problema
- Enolicnost zapisa $\frac {a}{b} = \frac {k\cdot a}{k\cdot b}$ -velja-> $\frac {a}{b} \sim \frac {c}{d} \iff a\cdot d = b \cdot c$  --> je relacija ekvivalence $\{[\frac {a}{b}] \ | \ a,b \in K \land b \neq 0\}$ 
- Imenovalec $\neq 0$ 
	- $[\frac {a}{b}] + [\frac {c}{d}] := [\frac {ad + bc}{bd}]$
	- $[\frac {a}{b}] \cdot [\frac {c}{d}] := [\frac {ac}{bd}]$

I: Ce je K komutativen, asociativen, unitaren kolobar brez deliteljev nica. Potem je $K^* := (\{[\frac {a}{b}] \ | \ a \in K , b \in K\backslash \{0\}\}, +, \cdot)$  obseg (obseg ulomkov za K).

I (Wedderburnov izrek): Koncen kolobar (asoc. in unitaren) brez deljiteljev nica je obseg. 
(V koncnem kolobarju je ? - iz slike pod konkretnim primerom 4) - prazen)
Dokaz: 
- $a\in K - \{0\}$ ... trdimo, da obstaja $a'$ tako da velja $a\cdot a' = a' \cdot a = 1$.
- Mnozica $\{a\cdot x \ |\ x \in K - \{0\}\}$
- Ce $a\cdot x = a \cdot y \to a (x-y) = 0$
- Ker nimamo deljiteljev nica $a \neq 0 \to x-y = 0$ 
- Vsi elementi so razlicni, $K$ je koncen
- $\exists a': a\cdot a' = 1$
- Identicno lahko naredimo mnozico $\{x\cdot a \ |\ x \in K - \{0\}\}$
- Torej obstaja: $a'' \cdot a = 1$
- $a'' \cdot a \cdot a' = (a'' \cdot a) \cdot a' = a'' \cdot(a \cdot a')$
- Vidimo: $a'' = a' \to a$ je obrnljiv
Pokazali smo, da ce imamo asociativni in unitaren kolobar brez deljiteljev nica $K$ je to kolobar z deljenjem (dobimo tudi komutativnost? DA).

D: Karakteristika kolobarja:
ce je $K$ kolobar, potem recemo, da je karakteristika kolobarja najmanjse naravno stevilo $n \in \mathbb N$, ki ima lastnost: $n\cdot a = 0$ za $\forall a \in K$, ce tak $n$ obstaja oziroma 0, ce tak $n$ ne obstaja. Oznaka: char$K$.
char$K = \begin{cases} 0,  \nexists n: na = 0 \ \forall a \in K \\ n,  \exists n: na = 0 \ \forall a \in K \end{cases}$ 

T:
1. char$K = min\{n\ | \ n1 = 0\}$
2. Ce K nima deljiteljev nica, potem char$K$ je prastevilo ali pa 0.
Dokaz: 
1. char$K = n \ \to  \ n\cdot 1 = 0$. Obratno, ce je $n1 = 0$.
	$n1 = (1+1 \ + ... + \ 1) = 1$ ($n$-krat) potem je tudi $a + a \ + ... + \ a = 0$ ($n$-krat)
	saj $a + a \ + ... + \ a = a (1+1 \ + ... + \ 1) = a \cdot 0 = 0$ 
2. s protislovjem
	char$K = n \ \to  \ n = k\cdot l$, kjer $k,l \gt 1$ (ni prastevilo)
	$n1 = (1+1 \ + ... + \ 1)\cdot (1+1 \ + ... + \ 1) = 0$ (prvi oklepaj $k$-krat, drugi $l$-krat), saj ker $k,l \gt 1$ in $n=k\cdot l \to n \gt k,l \to$ deljitelja nica

Posledica: Karakteristika obsega je nic ali pa prastevilo

T: char$K = p$  prastevilo je $K$ vektorski prostor nad $\mathbb Z_p$.

Posledica: $K$ je koncen kolobar s karakteristiko, ki je prastevilo potem je: $|K| = p(\dim_{\mathbb Z_p}K)$ 

### P2

D: $K$ in $L$ naj bosta kolobarja, potem je $f:K \to L$ homomorfizem, ce velja (za $\forall x,y \in K$)
 - $f(x+y) = f(x) + f(y)$ ... aditivnost
 - $f(x\cdot y) = f(x) \cdot f(y)$ ... multiplikativnost
 - implicira $f(0)=0$ in $f(-x) = -f(x)$
 - $f(1_K) = 1_L$ ... unitalnost (slika enoto v enoto) - unitalen homomorfizem

T: Ce je karakteristika kolobarja enaka prastevilu $p$, potem je $f(x) = x^p$ homomorfizem iz $K$ v $K$ ($K$ je komutativni kolobar).
Dokaz: Vidno je multiplikativen, kaj pa aditivnost?
$(x+y)^p = x^p + \binom{p}{1}x^{p-1}y + \ ... \ + \binom{p}{i}x^{p-i}y^i + \ ... \ + y^p$  
$\binom{p}{1}$ in $\binom{p}{p-1}$ sta $=0$. 
Splosni clen pa $\binom{p}{i} = \frac{p\cdot (p-1)\cdot \ ... \ \cdot (p-i+1)}{i!}$ ($i$ je celo stevilo ... je deljiv s $p$ ... vsi vmesni cleni odpadejo)
Ostane: $x^p + y^p$ 
$\rightarrow$ Frobeniusov avtomorfizem (spomnimo: avtomorfizem = bijektiven homomorfizem sam vase)

T: $f: K\to L$ homomorfizem, potem je $Im(f) = \{f(x) \ | \ x\in K\}$  oz. $Im(f) = f(K)$. Velja, da je $Im(f)$ podkolobar $L$.
Dokaz:
- $f(x), f(x')\in Im(f)$
	- $f(x)+f(x') = f(x+x')$ 
	- $\to f(x)\cdot f(x') = f(x\cdot x')$ 
- $f(0) = 0$ oz. $f(0_K) = 0_L$ 
- $f(-x) = -f(x)$
Torej $Im(f)$ je Abelova grupa za sestevanje, distributivnost pa sploh ni treba pregledati $\to$ je podkolobar.