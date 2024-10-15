### *Integral s parametrom
##### Uvod

D1: Mozne variacije:
- Variacija integranda $F(x) = \int_a^b f(x,t)dt$
- Variacija meje $F(x) = \int_{u(x)}^{v(x)} f(t)dt$
- Oboje hkrati $F(x) = \int_{u(x)}^{v(x)} f(x,t)dt$

Pomen integralov:
- Elementarne funkcije (integrali)
- Resitve diferencialnih enacb
- Modeliranje

##### *Zveznost, odvedljivost in integrabilnost*

I1: Naj bo $f(x,t)$ zvezna na $[c,d] \times [a,b]$ , potem je $F(x) = \int_a^b f(x,t)dt$ zvezna na $[c,d]$.

I2: (Zadostni pogoji) Naj bo $f(x,t)$ zvezna na $[c,d] \times [a,b]$ in zvezno parcialno odvedljiva po x na temu pravokotniku. Potem je na $[c,d]$ odvedljiva tudi $F(x) = \int_a^b f(x,t)dt$  in zanjo velja: $F'(x) = \int_a^b {\frac {\partial f} {\partial x}}f(x,t)dt$ 

I3: Naj bosta $u,v: [c,d] \to [a,b]$ odvedljivi funkciji ene spremenljivke. Funkcija $f: [c,d] \times [a,b] \to \mathbb R$ pa zvezna in zvezno odvedljiva po x. Potem je tudi $F(x) = \int_{u(x)}^{v(x)} f(x,t)dt$ odvedljiva za $\forall x \in [c,d]$ in velja: $F'(x) = \int_{u(x)}^{v(x)} {\frac {\partial f} {\partial x}}f(x,t)dt \ + v'(x) f(x,v(x)) - u'(x) f(x,u(x))$ 

I4: Naj bo funkcija $f: [c,d] \times [a,b] \to \mathbb R$  zvezna, potem je $F(x) = \int_a^b f(x,t)dt$ integrabilna na $[c,d]$ in zanjo velja: $\int_c^d F(x)dx = \int_c^d (\int_a^b f(x,t)dt)dx = \int_a^b (\int_c^d f(x,t)dx)dt$ - (menjava vrstnega reda)

##### *Posploseni integral s parametrom*

Ponovitev:
- $\int_a^{\infty} f(t)dt = lim_{b \to \infty} \int_a^b f(t)dt = lim_{b \to \infty} F(b) - F(a)$ => konvergira ce gre $f(x) \to 0$ tako hitro kot $\frac {1} {x^p}$ za p > 1
- $\int_a^b f(t)dt = lim_{a' \to a} \int_{a'}^b f(t)dt = F(b) - lim_{a' \to a} F(a')$ => konvergira ce gre $f(x)$ okoli pola $a$ kot $\frac {1} {(x-a)^p}$ za p < 1

D2: Integral s parametrom $F(x) = \int_a^{\infty} f(x,t)dt$ je enakomerno konvergenten na $[c,d]$ ce za $\forall \varepsilon > 0 \ \ \exists \ B > a$ da za $b \geq B$ velja: $|\int_b^{\infty} f(x,t)dt| < \varepsilon$ za vse $x \in [c,d]$ 

Weierstrassov zadostni pogoj: Denimo, da $\exists$ zvezna funkcija $g:[a,\infty] \to \mathbb R$ za katero velja:
- $|f(x,t)| \lt g(t)$ za $x \in [c,d]$
- $\int_a^{\infty} g(t) dt \lt \infty$ 
potem je $F(x) = \int_a^{\infty} f(x,t)dt$ enakomerno konvergentna na $[c,d]$ 

I5: Naj bo $f:[c,d] \times [a,\infty] \to \mathbb R$ funkcija in $F(x) = \int_a^{\infty} f(x,t)dt$ pripadajoci posploseni integral s parametrom. Velja:
- ce $f(x,t)$ zvezna na $[c,d] \times [a,\infty]$ in $F(x)$ enakomerno konvergentna na $[c,d]$ je $F(x)$ zvezna na $[c,d]$
- ce $f(x,t)$ zvezna in zvezno odvedljiva po $x$ na $[c,d] \times [a,\infty]$ in je $\int_a^{\infty} {\frac {\partial f} {\partial x}}f(x,t)dt$ enakomerno konvergentna na $[c,d]$ je $F(x)$ odvedljiva na $[c,d]$ in velja: $F'(x) = \int_a^{\infty} {\frac {\partial f} {\partial x}}f(x,t)dt$ 
- ce $f(x,t)$ zvezna na $[c,d] \times [a,\infty]$ in $F(x)$ enakomerno konvergentna na $[c,d]$ je $F(x)$ integrabilna na $[c,d]$ in velja: $\int_c^d F(x)dx = \int_c^d (\int_a^{\infty} f(x,t)dt)dx = \int_a^{\infty} (\int_c^d f(x,t)dx)dt$ 

Dodatek: Analogen izrek velja tudi za tip 2 posplosenih integralov s parametrom, tj. $F(x) = \int_a^b f(x,t)dt$ , kjer ima $f(x,t)$ pol v $t=a$. Velja:
- $F$ je enakomerno konvergentna na $[c,d]$ ce za $\forall \varepsilon > 0 \ \ \exists \ A > a$ da za $a' \in (a,A)$ velja: $|\int_a^{a'} f(x,t)dt| < \varepsilon$ za vse $x \in [c,d]$ 
- W-kriterij: ce $\exists g:[a,b] \to \mathbb R$ zvezna, da je $|f(x,t)| \leq g(t)$ in $\int_a^b g(t) dt \lt \infty$ 

##### *Gamma funkcija*

D3: $\Gamma (x) = \int_0^{\infty} t^{x-1} e^{-t}dt$ ,  $x \gt 0$   

T1: $\Gamma$ zvezna na $(0,\infty)$ 

T2: $\Gamma (x+1) = x \Gamma(x)$ 

Vemo: $\Gamma (1) = 1$ --> $\Gamma(n) = (n-1)\Gamma(n-1) = ... = (n-1)!$  za $n \in \mathbb N$. Funkcija $\Gamma$ je zvezna razsiritev (premaknjene) funkcije fakulteta.
$\Gamma(\frac {1}{2}) = \sqrt \pi$ 

##### *Beta funkcija*

D4: $B(p,q) = \int_0^1 t^{p-1}(1-t)^{q-1}dt$ , $p,q > 0$ 

T3: $B(p,q)$ je zvezna kot funkcija dveh spremenljivk na $(0,\infty) \times (0,\infty)$ 

T4: $B(p,q) = B(q,p)$ za $\forall p,q > 0$ 

I6: $B(p,q) = \frac {\Gamma(p)\cdot \Gamma(q)}{\Gamma(p+q)}$ za $\forall p,q$ 

L1: $B(p,q) = \int_0^{\infty} \frac {u^{p-1}}{(1+u)^{p+q}}du$  in $B(p,q) = 2\int_0^{\frac {\pi}{2}} sin^{2p-1}\phi \cdot cos^{2q-1}\phi \ d\phi$,  $p,q > 0$ 

### *Vecterni integral*
##### *Uvod*

D5: $A \subset \mathbb R$ ima mero nic, ce jo lahko pokrijes s stevno intervali, katerih skupna dolzina je poljubno majhna.

Intuicija: $\iint_D f(x,y)dxdy$ 
- Delilne tocke ($a = x_0 < x_1 < ... < x_n = b$, $c = y_0 < y_1 < ... < y_m = d$)
- Ploscine malega pravokotnika $S_{ij} = (x_i - x_{i-1})(y_j - y_{j-1})$ 
- Testne tocke na ploscinah: $(\xi_i, \zeta_j)$ 
- Riemanova: $R(f,D)$ = $\sum_{i,j = 1}^{n,m} f(\xi_i, \zeta_j)S_{ij}$ 
- Limita R, kjer $max_{0 \leq i \leq n}(x_i - x_{i-1}) \to 0$ in $max_{0 \leq j \leq m}(y_j - y_{j-1}) \to 0$

D6: Funkcije, ki so integrabilne:
- vse zvezne
- njihove mnozice nezveznosti imajo mero 0

D7: $A \subset \mathbb R^2$ ima mero nic, ce jo lahko pokrijes s stevno unijo krogov, katerih skupna ploscina je poljubno majhna.

Intuicija: Integracija po omejenem obmocju $D \subset \mathbb R^2$ 
- Pravokotnik, da $D \subset [a,b] \times [c,d]$ 
- $\overline f = \{f,$ na D in $0,$ na $[a,b] \times [c,d] \setminus D$  
- $\iint_D f(x,y)dxdy$ = $\iint_{[a,b]\times[c,d]} \overline f(x,y)dxdy$ 

D8: Funkcija na obmocju D integrabilna, ko ima mnozica njenih nezveznosti na D mero nic in ima rob $\partial D$ mero nic, saj je v mnozici nezveznosti za $\overline f$.

Dodatek: Intuicija enaka za n=3. $R(f,D)$ = $\sum_{i,j,k = 1}^{n,m,s} f(\xi_i, \zeta_j, \tau_k)V_{ijk}$ 

##### *Fubinni*

I7 (Fubinni): Ce je f integrabilna na $[a,b] \times [c,d]$ in je $y \to f(x,y)$ integrabilna na $[c,d]$ za $\forall x \in [a,b]$ velja: $\iint_{[a,b]\times[c,d]} f(x,y)dxdy = \int_a^b (\int_c^d f(x,y)dy)dx$ - (x,y lahko zamenjamo)

Posledica (Fubinni): $g,h: [a,b] \to \mathbb R$ zvezni, $D = \{(x,y) \in \mathbb R^2; \ a \leq x \leq b, \ g(x) \leq y \leq h(x)\}$ velja: $\iint_D f(x,y)dxdy = \int_a^b (\int_{g(x)}^{h(x)} f(x,y)dy)dx$  - (x, y nista vec simetricni)

I8 (Fubinni za n=3): Ce je f integrabilna na $[a,b] \times [c,d] \times [p,q]$ za $\forall$ par $(x,y) \in [a,b] \times [c,d]$ je $z \to f(x,y,z)$ integrabilna na $[p,q]$. Velja: $\iiint_S f(x,y,z)dxdydz = \iint_{[a,b]\times[c,d]} (\int_p^q f(x,y,z)dz)dxdy$ - (prevedemo na fubinnija za n=2)

Posledica (F za n=3): $\Omega = \{(x,y,z) \in \mathbb R^3; (x,y) \in D, \ g(x,y) \leq z \leq h(x,y)\}$ velja: $\iiint_{\Omega} f(x,y,z)dxdydz = \iint_D (\int_{g(x,y)}^{h(x,y)} f(x,y,z)dz)dxdy$ 

##### *Zamenjava spremenljivk*

Intuicija: $g(u,v) = (x(u,v), y(u,v))$ in Jakobijeva matrika

D9: Jakobijeva matrika
- $J_{g(u,v)} =$ $\begin{pmatrix}x_u & x_v\\\ y_u & y_v\end{pmatrix}$

I10:  Naj bo $g: \Omega \to D$ difeomorfizem z zveznimi parcialnimi odvodi in lastnostjo $detJ_g \neq 0$. Potem velja: $\iint_D f(x,y)dxdy = \iint_{\Omega} f(g(u,v)) |detJ_{g(u,v)}|dudv$  

##### *Prakticni pomen*

Pomen:
- Ploscina in volumen
- Masa in masno sredisce
- Vztrajnostni moment

D10: $\delta_o = \frac {m}{V}$ => $\delta_o \cdot V = m$. Ce telo/lik ni homogen, gostota podaja to razmerje v vsaki tocki. Prevedba $m(D) = \iint_D \delta(x,y)dxdy$  in $m(\Omega) = \iiint_{\Omega} \delta(x,y,z)dxdydz$   

D11: Masno sredisce ($\overline x = \frac {1}{m} \iint_D x \delta(x,y)dxdy$ , $\overline y = \frac {1}{m} \iint_D y \delta(x,y)dxdy$)

D12: Vztrajnostni moment ($J = mr^2$). Velja: $J = \iint_D (x^2 + y^2) \ \delta(x,y)dxdy$ in $J = \iiint_{\Omega} (x^2 + y^2) \ \delta(x,y,z)dxdydz$ 

##### *Izlimitirani vecterni integrali*

D13: Mozne variacije:
- $D \subset \mathbb R^2$ neomejen lik --> izberemo $K_n$ tako da
	- $K_n \subset K_{n+1}$
	- $\bigcup_{n=1}^{\infty} K_n = \mathbb R^2$ 
	- $\iint_D f(x,y)dxdy = lim_{n\to \infty} \iint_{D \cap K_n} f(x,y)dxdy$ 
-  $D \subset \mathbb R^2$ omejeno, $f$ neomejena blizu $p$ 
	- $K_{n+1} \subset K_n$
	- $\bigcap_{n=1}^{\infty} K_n = \{p\}$ 
	- $\iint_D f(x,y)dxdy = lim_{n\to \infty} \iint_{D \setminus K_n} f(x,y)dxdy$ 

T5: Ce $f \geq 0$ povsod na $D$ (razen v koncno mnogih polih) potem zaporedji $(\iint_{D \cap K_n} f(x,y)dxdy)_{n\in \mathbb N}$ in  $(\iint_{D \setminus K_n} f(x,y)dxdy)_{n\in \mathbb N}$ narascujoci. Torej ali zaporedje neomejeno in integral divergira ali pa zaporedje omejeno in integral konvergira.

T6: V 2.opciji (konvergenca integrala in omejeno zaporedje) je limita neodvisna od izbire $(K_n)_{n \in \mathbb N}$ za $f \geq 0$ 
Zaradi tega lahko obicajen Fubinni uporabljamo.

D14: $f$ je absolutno konvergentna na $D$ ce konvergira $\iint_D |f(x,y)|dxdy$ 

I11: Za absolutno konvergentne integrale velja posploseni Fubinijev izrek.

##### *Krivuljni in ploskovni integrali*

Podajanje:
- Eksplicitno ($y = f(x)$ in $z = f(x,y)$)
- Implicitno ($F(x,y) = 0$ ali pa $F(x,y,z) = 0$ in $G(x,y,z) = 0$ (presek teh dveh je krivulja, ena pa je za ploskve))
- Parametricno ($\vec r:[\alpha, \beta] \to \mathbb R^{2/3}$ in $|\dot {\vec r}(t)| \neq 0$ , za ploskve pa $\vec r:D \subset \mathbb R^2 \to \mathbb R^3$ in $|\vec r_u \times \vec r_v| \neq 0$)

D15: Naj parametrizacija $\vec r:[\alpha, \beta] \to \mathbb R^2$ podaja krivuljo $\gamma$. Dolzina:
- $dl_j \approx |\dot {\vec r}(t_j)|dt$ 
- $l = \int_{\alpha}^{\beta} |\dot {\vec r}(t)|dt$ 

D16: Skalarno polje $\delta(x,y,z): \mathbb R^3 \to \mathbb R$. Masa:
- $dm_j \approx \delta(\vec r(t_j))\cdot|\dot {\vec r}(t_j)|dt$ 
- $I_1 = \int_{\gamma} \delta ds = \int_{\alpha}^{\beta} \delta(\vec r(t))\cdot|\dot {\vec r}(t)|dt$ 

D17: Vektorsko polje $\vec V: \mathbb R^3 \to \mathbb R^3$ 
- $I_2 = \int_{\gamma} \vec V d\vec s = \int_{\alpha}^{\beta} \vec V(\vec r(t))\cdot \dot {\vec r}(t)dt$ 

I12: Obe definiciji sta neodvisni od parametrizacije, integral druge vrste je do predznaka natancno odvisen od orientacije.

D18: Naj bo $P$ ploskev in parametrizacija $\vec r: D \subset \mathbb R^2 \to \mathbb R^3$. Ploscina:
- $S = |\vec r_u \times \vec r_v| = \sqrt {EG - F^2}$ 
- $E = \vec r_u \cdot \vec r_u$ , $G = \vec r_v \cdot \vec r_v$ , $F = \vec r_u \cdot \vec r_v$ 
- $Pov(P) = \iint_D |\vec r_u \times \vec r_v|dudv = \iint_D \sqrt {EG - F^2}dudv$ 

D19: Skalarno polje $\delta(x,y,z): \mathbb R^3 \to \mathbb R$. Masa:
- $I_3 = \iint_P \delta dS = \iint_D \delta(\vec r(u,v))\cdot |\vec r_u \times \vec r_v|dudv = \iint_D \delta(\vec r(u,v))\cdot \sqrt {EG - F^2} dudv$ 

D20: Vektorsko polje $\vec V$
- $I_4 = \iint_P \vec V d\vec S = \iint_D \vec V(\vec r(u,v))\cdot \vec n(u,v) \sqrt {EG - F^2}dudv = \iint_D \vec V(\vec r(u,v))\cdot (\vec r_u \times \vec r_v)dudv = +- \iint_D [\vec V, \vec r_u, \vec r_v]dudv$  

### *Kompleksna analiza*
##### *Uvod*

D21: Kompleksna funkcija: $D \subset \mathbb C \to \mathbb C$. Kompleksno stevilo $z \in \mathbb C \ , \ z = x+iy \ , \ x,y \in \mathbb R \ , \ i = \sqrt {-1}$ --> $f(z) = u(z) + iv(z) \  , \ u,v: D \to \mathbb R$. Velja tudi Eulerjeva formula: $z = |z|(cos\phi + isin\phi)$ kjer $\phi = Arg(z)$. 

D22: Preslikava v realno funkcijo. $f_{\mathbb R}(x,y) = (u(x,y), v(x,y))$ 

D23: Preslikava v kompleksno funkcijo. $f(z) = u(\frac {z+\overline z}{2}, \frac {z-\overline z}{2i}) + iv(\frac {z+\overline z}{2}, \frac {z-\overline z}{2i}))$.

Sklep: Kompleksne funkcije $f: D \subset \mathbb C \to \mathbb C$ in realne preslikave $f_{\mathbb R}: D \subseteq \mathbb R^2 \to \mathbb R^2$ so v bijektivni korespondenci.

Posledica: $f$ zvezna v $a \in D$ ali na $D \subseteq \mathbb C$  $\iff$ $f_{\mathbb R}$ zvezna v $a \in D$ ali na $D \subseteq \mathbb R^2$.   

##### *Integral kompleksne funkcije vzdolz krivulje*

D23: Preslikavo $f_{\mathbb R}: D \subset \mathbb R^2 \to \mathbb R^2$ lahko razumemo kot vektorsko polje in ga integriramo po krivulji $\gamma \subset D$ 
- $\int_{\gamma} f_{\mathbb R} d\vec S = \int_{\alpha}^{\beta} f_{\mathbb R}(\gamma(t))\cdot \dot \gamma(t)dt$ --> skalarni produkt
- $\int_{\gamma} f(z) dz = \int_{\alpha}^{\beta} f(\gamma(t))\cdot \dot \gamma(t)dt$ --> produkt dveh kompleksnih stevil

##### *Odvod kompleksne funkcije*

D24: Vsaki realni preslikavi $f_{\mathbb R} = (u,v): D \subseteq \mathbb R^2 \to \mathbb R^2$ lahko priredimo Jakobijevo matrijo $J_{f_{\mathbb R}} = \begin{pmatrix}u_x & u_y\\\ v_x & v_y\end{pmatrix}$ 

D25: Kompleksna funkcija $f:D \subset \mathbb C \to \mathbb C$ je kompleksno odvedljiva v $a \in D$, ce obstaja limita $f'(a) = lim_{h \to 0} \frac {f(a+h) - f(a)}{h}$ 

D26: Ce $f$ kompleksno odvedljiva v $\forall a \in D \subset \mathbb C$, pravimo da je $f$ holomorfna na $D$.

I13: $f = u +iv: D \subseteq \mathbb C \to \mathbb C \ , \ u,v$ zvezno odvedljivi. $f$ je holomorfna na $D \iff$ $u_x = v_y$ in $u_y = - v_x$  (Cauchy-Riemanov sistem - CRS)

Praksa: Funkcija ni holomorfna, ce v njej nastopa $\overline z$. 

##### *Integral kompleksne funkcije*

I14 (Cauchyev izrek): Naj bo $D \subseteq \mathbb C$ enostavno povezano obmocje (brez lukenj). Naj bo $f: D \to\mathbb C$ holomorfna in $\gamma \in D$ sklenjena krivulja. Potem: $\int_{\gamma}f(z)dz = 0$ 

Posledica: Integral ni odvisen od izbire poti ampak le od zacetne in koncne tocke.

I15 (Cauchyeva integracijska formula): Naj bo $D \subset \mathbb C$ enostavno povezano in omejeno obmocje. Naj bo $f$ holomorfna na $D$ in zvezna na $\overline D$. Potem za $\forall z \in D$ velja: $f(z) = \frac {1}{2\pi i} \int_{\partial D} \frac {f(x)}{w-z}dw \ , \ w \in \partial D$ 

I16: Holomorfne funkcije so gladke ($\infty$-krat odvedljive). $f^{(n)}(z) = \frac {n!}{2\pi i} \int_{\partial D} \frac {f(w)}{(w-z)^{n+1}}dw$ 

I17: Vse holomorfne funkcije lahko v vsaki tocki razvijes v "kompleksno" razliko Taylorjevega razvoja. $f(z) = \sum_{n=0}^{\infty} \frac {f^{(n)}(a)}{n!}(z-a)^n$ , dober za $|z-a| \lt R \ , \ R \gt 0$ konvergencni polmer 

I18: Mnozica nicel holomorfne funkcije je diskretna. (tj. za $\forall$ niclo $a \ \exists$ okolica, da $f(z)=0$ le za $z=a$)

Posledica: Ce velja za holomorfni funkciji $f,g$ da se ujemata na mnozici s stekaliscem, se ujemata povsod kjer sta definirani.

Morala: I16,17,18 pricajo o tem, da je realnih funkcij ki ustrezajo holomorfnim funkcijam razmeroma malo. (holomorfnost bistveno mocnejsa od zveznosti, gladkosti...)

##### *Izrek o residuih*

D27: Za splosen $a \in \mathbb C$ dobimo Laurentov razvoj v okolici singularnosti: $f(z) = \sum_{-\infty}^{\infty} c_n (z-a)^n = ... + \frac {c_{-2}}{(z-a)^2} + \frac {c_{-1}}{(z-a)} + c_0 + c_1(z-a) + ...$ 

D28: Delitev singularnosti:
- ce je $c_{-n} = 0$ za vse $n \in \mathbb N$ je f holomorfna v a
- ce je $c_{-n} = 0$ za vse $\forall n \gt m \in \mathbb N$ ima f v $a$ pol stopnje $m$
- ce je neskoncno mnogo koeficientov $c_{-n} \ , \ n \in \mathbb N$ nenicelnih, ima $f$ v $a$ bistveno singularnost

Sklep: $\int_{\gamma} f(z)dz = 2\pi i \ c_{-1}$ - integral odvisen le od clena $c_{-1}$, ki mu recemo residum oziroma ostanek in ga oznacimo z $c_{-1} = Res(f,a)$ 

I19: $U \subseteq \mathbb C$ brez lukenj, $f$ holomorfna povsod razen v tockah $a_1, a_2,...,a_k$. Naj bo $\gamma \subset U$ sklenjena krivulja, ki te singularnosti obkrozi enkrat v pozitivni smeri. Po tem je integral po tej krivulji enak: $\int_{\gamma} f(z)dz = \sum_{j=1}^k Res(f,a_k) \cdot 2\pi i$ 

##### *Analiticni in geometrijski pomen holomorfnosti*

D29: ($f$ holomorfna $\iff$ CRS  && $f$ holomorfna $\iff$ $f$ gladka). Za $u \in C^2(D,\mathbb R)$ definiramo Laplaceov operator $\Delta u = u_{xx} + u_{yy}$ 

D30: Realnim funkcijam $u: D \subseteq \mathbb R^2 \to \mathbb R$, ki zadoscajo $\Delta u = 0$, pravimo harmonicne.

Posledica: Ce $f=u+iv: D \subseteq \mathbb C \to \mathbb C$ holomorfna, sta $u=Re(f)$ in $v = Im(f)$ harmonicni na $D$.

I20: Ce $D \subseteq \mathbb C$ enostavno povezano (tj. brez lukenj) za $\forall$ harmonicno funkcijo $u: D \subseteq \mathbb R^2 \to \mathbb R$ $\exists$ harmonicna funkcija $v: D \subseteq \mathbb R^2 \to \mathbb R$, da je $f=u+iv: D \subseteq \mathbb C \to \mathbb C$ holomorfna. Taki funkciji pravimo harmonicna konjugiranka od $u$ in je dolocena do realne konstante natancno.

D31: Preslikavam, ki ohranjajo orientacijo in kote pravimo konformne.