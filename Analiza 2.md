#### *Podmnozice v evklidskih prostorih*

D: Naj bo $a \in R, \varepsilon \gt 0$. Interval $(a-\varepsilon, a+\varepsilon)$ imenujemo $\varepsilon$-okolica stevila $a$. Mnozica $U \subset \mathbb R$ je okolica od $a$, ce obstaja kaksna $\varepsilon$-okolica od $a$, ki lezi v $U$. Mnozica $U \subset \mathbb R$ je odprta, ce za $\forall x \in U$ obstaja kaksna $\varepsilon$-okolica od $x$, ki lezi v $U$. Mnozica $Z \subset \mathbb R$  je zaprta, ce je njen komplement $\mathbb R\setminus Z$ odprt.

P: 
1.
- $(0,\infty)$ je odprta mnozica
- $(-\infty, 0]$ je zaprta mnozica (komplement prejsnje)
2.
- $(-2,-1) \cup (-1,0)$ je odprta mnozica
- $(-\infty, -2] \cup \{-1\} \cup [0,\infty)$ je zaprta mnozica
3.
- $A = \{\frac{1}{n}; n \in \mathbb N\}$ ni odprta, ker 1 ni notranja tocka
- $\mathbb R \setminus A = (-\infty,0] \cup (1,\infty) \cup (\cup_{n \in \mathbb N} (\frac{1}{n+1},\frac{1}{n}))$ ni odprta zaradi 0
- $B = A \cup \{0\}$ ni odprta, $\mathbb R \setminus B$ je odprt, zato je $B$ zaprta
4.
- Vecina mnozic v praksi ni ne odprtih ne zaprtih

T: Mnozica $A \subset \mathbb R$ je zaprta natanko tedaj ko za vsako zaporedje $(a_n)_n$ s cleni v $A$ velja: ce je $s$ stekalisce $(a_n)_n$ potem $s\in A$.
Dokaz: 
- $(\implies)$ denimo, da je $A$ zaprta. Izberemo poljubno zaporedje $(a_n)_n$ s cleni v $A$ in denimo, da je $s$ stekalisce od $(a_n)_n$. Dokazujemo $s\in A$: Denimo da $s \notin A$. Potem je $s\in\mathbb R\setminus A$, ki je odprta mnozica. Zato obstaja $\varepsilon$-okolica od $s$ v $\mathbb R \setminus A$: $(s-\varepsilon, s+\varepsilon) \subset \mathbb R \setminus A \ (*)$ za neki $\varepsilon \gt 0$. Ker je v vsaki $\varepsilon$-okolici od stekalisca neskoncno mnogo clenov zaporedja $(*)$ ni mogoce. $(\rightarrow\leftarrow)$
- $(\impliedby)$ Dokazujemo: $A$ je zaprta $B=\mathbb R\setminus A$ je odprta: Ce $B$ ni odprta, potem obstaja $x\in B$, ki ni notranja tocka mnozice $B$. Torej vsaka $\varepsilon$-okolica tocke $x$ seka $B^C = A$. Za vsak $n\in \mathbb N$  obstaja $a_n\in A$ in $a_n\in (x-\frac{1}{n}, x + \frac{1}{n})$. Zaporedje $(a_n)_n$ lezi v $A$ in konvergira proti $x$. $x$ je stekalisce $(a_n)_n$. Po predpostavki $x\in A$. $(\rightarrow\leftarrow)$

D: Pravimo, da je mnozica $A\subset\mathbb R$ kompaktna, ce je zaprta in omejena.

I: Naj bo $A\subset\mathbb R$. Potem velja: $A$ je zaprta in omejena natanko tedaj, ko ima $\forall$ zaporedje $(a_n)_n$ s cleni v $A$ stekalisce v $A$.
Dokaz: 
- $(\implies)$ Vzamemo poljubno zaporedje $(a_n)_n$ s cleni v $A$. Ker je $A$ omejena je $(a_n)_n$ omejeno, torej ima stekalisce $s$. Ker je $A$ zaprta, po trditvi od prej velja $s\in A$.
- $(\impliedby)$ 
	- Dokazujemo: $A$ je omejena. Denimo, da $A$ ni omejena. Denimo, da ni navzgor omejena. Za $n\in\mathbb N \ \exists a_n\in A$, tako da $a_n \geq n$. Zaporedje $(a_n)_n$ nima stekalisc.  $(\rightarrow\leftarrow)$ 
	- Dokazujemo: $A$ je zaprta. Uporabimo trditev: izberemo poljubno zaporedje $(a_n)_n$ s cleni v $A$. Ce je $s$ stekalisce, potem $s\in A$. Ker je $s$ stekalisce, obstaja konvergentno podzaporedje $(a_{n_k})_k$ s cleni v $A$, ki konvergira proti $s$. Po predpostavki ima $(a_{n_k})_k$ stekalisce v $A$. Ker je $s$ njegova limita, je edino stekalisce, zato $s\in A$.

Opomba: Dokazali smo, da so vsa stekalisca zaporedja s cleni v kompaktni mnozici vsebovana v tej kompaktni mnozici, kar velja tudi za zaprte mnozice. Razlika: V kompaktni mnozici ima vsako zaporedje vsaj eno stekalisce.

D: Evklidski prostor v $\mathbb R^k$ je $\mathbb R^k = \mathbb R \times \mathbb R \times ... \times \mathbb R = \{(x_1,x_2,...,x_k) \ | \ x_i \in \mathbb R, i=1,2,...,k\}$ 

D: Naj bo $x\in\mathbb R^k$, $x=(x_1,..,x_k)$. Oddaljenost $x$ do izhodisca $0 \in \mathbb R^k$, $0 = (0,...,0)$ je $||x|| = \sqrt{{x_1}^2+{x_2}^2+...+{x_k}^2}$ kar imenujemo tudi dolzina vektorja $x$ ali norma $x$. Razdalja med $x,y\in \mathbb R^k$ je $||x-y||=\sqrt{(x_1-y_1)^2+...+(x_k-y_k)^2}$ 

T: Za vsak $x,y\in \mathbb R^k$ velja: $| \ ||x||-||y|| \ | \leq ||x+y|| \leq ||x||+||y||$ 

D: Naj bo $a\in \mathbb R^k, \varepsilon >0$. Potem je $\varepsilon$-okolica tocke $a$ je $K(a,\varepsilon)=\{x\in\mathbb R^k \ | \ ||x-a|| < \varepsilon\}$.

D: 
- Mnozica $A\subset \mathbb R^k$ je omejena, ce obstaja $M\in \mathbb R$, da velja $||x|| \leq M$ za vse $x\in A$.
- Mnozica $U\subset \mathbb R^k$ je odprta, ce za vsak $x\in U$ obstaja $\varepsilon >0$, da je $K(x,\varepsilon) \subset U$ 
- Mnozica $Z \subset \mathbb R^k$ je zaprta, ce je $\mathbb R^k  \setminus Z$ odprta.
- Tocka $a\in A \subset \mathbb R^k$ je notranja tocka mnozice $A$, ce $\exists \ \varepsilon>0$, da $K(a,\varepsilon)\subset A$ 
- Tocka $x\in\mathbb R^k$ je stekalisce mnozice $A$, ce vsaka $\varepsilon$-okolica tocke seka mnozico $A\setminus \{x\}$
- Tocka $a\in A \subset \mathbb R^k$, ki ni stekalisce od $A$ se imenuje izolirana tocka mnozice $A$

SLIKA!

D: 
1. Zaporedje s cleni v $\mathbb R^k$ je preslikava $\mathbb N\to\mathbb R^k$, $n \mapsto a_n=({a_n}^{(1)},...,{a_n}^{(k)})$ 
2. Zaporedje $(a_n)_n$ s cleni v $\mathbb R^k$ konvergira proti $a\in \mathbb R^k$, ce za $\forall \varepsilon>0$ obstaja $N\in\mathbb N$, da velja: ce $n\geq N$ potem $||a_n-a||<\varepsilon$. V tem primeru $a\in \mathbb R^k$ imenujemo limita zaporedja $(a_n)_n$ 
3. Tocka $s\in \mathbb R^k$ je stekalisce zaporedja $(a_n)_n$ s cleni v $\mathbb R^k$, ce lezi v vsaki $\varepsilon$-okolici od $s$ neskoncno mnogo clenov zaporedja.

D: Podobno kot v $\mathbb R$ velja:
1. Vsako konvergentno zaporedje je omejeo in ima natanko eno limito, ki je njegovo edino stekalisce.
2. Vsako omejeno zaporedje ima stekalisce.
3. Stekalisce zaporedja je limita konv. podzaporedja in obratno
4. $A \subset \mathbb R^k$ je zaprta $\iff$ vsako stekalisce zaporedja s cleni v $A$ je vsebovano v $A$

D: Mnozica $A \subset \mathbb R^k$ je kompaktna, ce je zaprta in omejena.

I:
1. Mnozica $A \subset \mathbb R^k$ je kompaktna natanko tedaj, ko ima vsako zaporedje $(a_n)_n$ s cleni v $A$ stekalisce v $A$.
2. Ce so $A_1,A_2,...,A_k$ kompaktne v $\mathbb R$, potem je $A_1 \times A_2 \times \dots \times A_k$ kompaktna v $\mathbb R^k$.

Primer:
1. $[a_1,b_1] \times [a_2,b_2] \times \dots \times [a_k,b_k]$ zaprt pravokotnik je kompakten
2. $\overline K(a,r)=\{x\in \mathbb R^k \ | \ ||x-a|| \leq r\}$ zaprta kroznica s srediscem v $a$ in polmerom $r$.

#### *Funkcije vec spremenljivk*

D: Naj bo $D \subset \mathbb R^k$ in $f: D \to \mathbb R$ preslikava. Ce je $k \geq 2$ potem $f$ imenujemo funkcija vec spremenljivk ali funkcija $k$-spremenljivk. Mnozica $\Gamma_{f} \{(x, f(x)) \in\mathbb R^{k+1} \ | \ x\in D\} \subset \mathbb R^k \times \mathbb R = \mathbb R^{k+1}$ se imenuje graf funkcije $f$.

P: $f(x,y) = x^2 + y^2$, $D = \mathbb R^2$ 
Pri risanju grafa si pomagamo z izohipsami t.j. krivulje, ki povezujejo tocke z isto funkcijsko vrednostjo $c\in\mathbb R: \{(x,y)\in D \ | \ f(x,y)=c\}$ - izohipsa.
$x^2 + y^2 = c$, ce je $c > 0$ je to kroznica s srediscem v $(0,0)$ in polmerom $\sqrt {c}$.

SLIKA

D: Naj bo $D \subset \mathbb R^k$ , $f: D \to \mathbb R$ funkcija. Naj bo $a\in\mathbb R^k$ stekalisce mnozice $D$. Stevilo $L \in\mathbb R$ je limita funkcije $f$ v tocki $a$, ce za vsak $\varepsilon \gt 0$ obstaja $\delta \gt 0$, da ce vsak $x\in D, \ x\neq a$ in $||x-a|| \lt \delta$, potem $|f(x) - L| \lt \varepsilon$.
Formalno: $\forall \varepsilon \gt 0 \ \ \exists \delta \gt 0 \ \ \forall x \in D, \ x \neq a: ||x-a|| \lt \delta \implies |f(x) - L| \lt \varepsilon$ 

Opomba: Pri funkcijah ene spremenljivke poznamo levo in desno limito. Pri funkcijah vec spremenljivk je obnasanje bolj zapleteno. 

P:
1. $f(x,y) = \frac{xy}{x^2+y^2}$ 
$D_{f} = \mathbb R^2 \setminus \{(0,0)\}$
Ali obstaja limita v $(0,0)$?
$f(x,0) = 0, \ x \neq 0$    $f(x,x) = \frac{1}{2}, \ x \neq 0$
$f(0,y) = 0, \ y \neq 0$    $f(x,-x) = -\frac{1}{2}, \ x \neq 0$
Torej limita v $(0,0)$ ne obstaja:
$\varepsilon = \frac{1}{4}$ izberemo polj. $\delta \gt 0$. 
$(x,x) \in K((0,0), \delta)$ 
$|f(x,x)-0| = \frac{1}{2} \gt \frac{1}{4}$

2. $f(x,y) = \frac{x^2y^2}{x^2+y^2}$ 
$D_{f} = \mathbb R^2 \setminus \{(0,0)\}$
Ali obstaja limita v $(0,0)$?
$y = kx$ 
$g(x,kx) = \frac{k^2x^4}{x^2 + k^2x^2} = \frac{k^2x^2}{1 + k^2} \to_{x\to 0} 0$  
Izberemo polj. $\varepsilon \gt 0$: $|g(x,y) - 0| = |\frac{x^2y^2}{x^2+y^2}| = \frac{x^2}{x^2+y^2}\cdot y^2$ (ulomek $\leq 1$) $\leq y^2 \leq x^2 + y^2 = {||(x,y) - (0,0)||}^2$
${||(x,y)||}^2 \lt \varepsilon \ \ {||(x,y)||}^2 \lt \delta^2 \lt \varepsilon$ 
$\delta^2 \lt \varepsilon \implies \delta = \frac{1}{2} \sqrt{\varepsilon}$ 

D: $D \subset\mathbb R^k, \ f,g: D \to \mathbb R$ funkciji. Funkcije $f+g, f-g, f\cdot g: D \to \mathbb R$ definiramo s predpisi: $(f \pm g)(x) = f(x) \pm g(x), \ x\in D$ (enako za mnozenje). Ce $g$ nima nicel na $D$ potem funkcijo $\frac{f}{g}: D\to\mathbb R$ definiramo s predpisom: $(\frac{f}{g})(x) = \frac{f(x)}{g(x)}$ 

I: Naj bosta $f:D_f\to\mathbb R$ in $g:D_g\to\mathbb R$ funkciji $k$ spremenljivk in $a\in\mathbb R^k$, ki je stekalisce $D_f\cap D_g$. Ce obstajata $\lim_{x\to a} f(x)$ in $\lim_{x\to a} g(x)$, potem obstajajo tudi limite vsote, razlike in produkta v tocki $a$ in velja: $\lim_{x\to a} (f\pm g)(x) = \lim_{x\to a} (f(x)\pm g(x)) = \lim_{x\to a} f(x) \pm \lim_{x\to a} g(x)$ (enako za mnozenje).
Ce je $\lim_{x\to a} g(x) \neq 0$ in je $a$ stekalisce $\{x\in D_f \cap D_g: \ g(x)\neq 0\}$ potem ima $\frac{f}{g}$ limito v tocki $a$ in velja: $\lim_{x\to a} \frac{f}{g}(x) = \frac{\lim_{x\to a} f(x)}{\lim_{x\to a} g(x)}$ 

D: Naj bo $D \subset\mathbb R^k$ in $f: D \to \mathbb R$ funkcija, $a\in D$. Funkcija $f$ je zvezna v tocki $a$, ce za vsako $\varepsilon$-okolico tocke $f(a)$ obstaja $\delta$-okolica tocke $a$, da velja: $x\in D$ in $||x-a|| \lt \delta$, potem $|f(x)-f(a)| \lt \varepsilon$. Funkcija $f:D\to\mathbb R$ je zvezna, ce je zvezna v vsaki tocki $a\in D$.

Opomba:
1. Ce je $a\in D$ in je $a$ stekalisce mnozice $D$, potem velja: $f$ je zvezna v tocki $a$ natanko tedaj, ko obstaja limita funkcije $f$ v tocki $a$ in je enaka $f(a)$.
2. Ce je $a$ izolirana tocka mnozice $D$, potem je $f$ zvezna v tocki $a$.
3. $x=a+h$. $f$ je zvezna v tocki $a$: $\forall \varepsilon \gt 0 \ \exists\delta\gt 0 \ \ a+h \in D, \ ||h|| \lt \delta \implies |f(a+h)-f(a)| \lt \varepsilon$ 

I: (Operacije z zveznimi funkcijami): Naj bosta $f,g$ funkciji $k$ spremenljivk. Ce sta $f$ in $g$ zvezni v tocki $a$, potem so $f+g, f-g$ in $f\cdot g$ zvezne v tocki $a$. Ce $g(a) \neq 0$, potem je $\frac{f}{g}$ zvezna v tocki $a$.
Dokaz: Ce je $a$ izolirana tocka definicijskega obmocja, potem je funkcija zvezna v tocki $a$. Sicer je $a$ stekalisce definicijskega obmocja in velja ustrezni izrek za limite.

I: Naj bo funkcija $f$ $k$ spremenljivk zvezna v tocki $a\in\mathbb R^k$ in naj bo $g$ funkcija ene spremenljivke, ki je zvezna v tocki $f(a)\in \mathbb R$. Potem je kompozitum $g\circ f$ zvezen v tocki $a$.
Dokaz: SLIKA
Izberemo polj. $\varepsilon \gt 0$. 
Ker je $g$ zvezna v tocki $f(a)$, obstaja $\delta \gt 0$: $y \in D_g$ in $|y-f(a)| \lt \delta \implies |g(y) - g(f(a))| \lt \varepsilon$. ($\cdot$)
Ker je $f$ zvezna v tocki $a$ obstaja $\alpha \gt 0$: $a$ je $x\in D_f$ in $|x-a| \lt \alpha \implies |f(x)-f(a)|\lt \delta$. ($\cdot\cdot$)
$x\in D_{g \ \circ \ f}$, $||x-a|| \lt \alpha \ddot\implies |f(x)-f(a)| \lt \delta \dot\implies |g(f(a)) - g(f(a))| \lt \varepsilon$. 

Opomba: Za funkcijo $x\mapsto (f_1(x), f_2(x),...,f_n(x))$ recemo, da je zvezna, ce so vse $f$ zvezne funkcije ene ali vec spremenljivk.

I: (Obstoj globalnih ekstremov): Naj bo $A\in\mathbb R^k$ kompaktna mnozica (zaprta&omejena) in $f: A \to \mathbb R$ zvezna funkcija. Potem je omejena in doseze maksimum in minimum.
Dokaz (za k=1): Dokazujemo: $f$ je navzgor omejena.
Denimo, da to ni res, za vsak $n\in\mathbb N$ obstaja $a_n\in A: f(a_n) \geq n$. $(a_n)_n$ je zaporedje v $A$, $A$ je kompaktna, zato ima stekalisce $s\in A$. Obstaja podzaporedje $(a_{n_k})_k$, ki konvergira proti $s$. $f$ je zvezna v tocki $s$, $(f(a_{n_k}))_k \geq n_k$  $\rightarrow\leftarrow$ 
Ker je $f$ omejena, obstaja $\sup f$ in $\inf f$.
$\sup f = \max f$ 
Za vsak $n\in \mathbb N$ obstaja $b_n\in A: f(b_n) \in (\sup f - \frac{1}{n}, \sup f]$ 
$(b_n)_n$ ima stekalisce $b\in A$
Obstaja podzaporedje $(b_{n_l})_l$, ki konvergira k $b$.
Iz zadnjih treh predpostavk sledi $f(b) =\sup f$ 

