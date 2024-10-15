## *Uvod*
#### *Asimptoticna notacija*

D: Naj bo dana funkcija $g: \mathbb N \to \mathbb N$. Potem za $f: \mathbb N \to \mathbb N$ pisemo
- $f(n) = \mathcal{O}(g(n))$, ce $\exists c > 0$, da je $lim_{n \to \infty} \frac {f(n)}{g(n)} \le c$. ($f$ narasca kvecjemu tako hitro kot $g$)
- $f(n) = \Omega(g(n))$, ce $\exists c > 0$, da je $c \le lim_{n \to \infty} \frac {f(n)}{g(n)}$. ($f$ narasca vsaj tako hitro kot $g$)
- $f(n) = \Theta(g(n))$, ce $\exists c_1,c_2 > 0$, da je $c_1 \le lim_{n \to \infty} \frac {f(n)}{g(n)} \le c_2$. ($f$ narasca podobno hitro kot $g$)
- $f(n) = o(g(n))$, ce je $lim_{n \to \infty} \frac {f(n)}{g(n)} = 0$. ($f$ narasca pocasneje kot $g$)
- $f(n) = \omega(g(n))$, ce je $lim_{n \to \infty} \frac {f(n)}{g(n)} = +\infty$. ($f$ narasca hitreje kot $g$)
- $f(n) \sim g(n)$, ce je $lim_{n \to \infty} \frac {f(n)}{g(n)} = 1$. ($f$ narasca tako hitro kot $g$)

D: Asimptoticne notacije lahko definiramo brez limit na ekvivalenten nacin:
- $f(n) = \mathcal{O}(g(n))$, ce $\exists c,n_0 > 0$, $\forall n \geq n_0: f(n) \le cg(n)$ 
- $f(n) = \Omega(g(n))$, ce $\exists c,n_0 > 0$, $\forall n \geq n_0: cg(n) \le f(n)$ 
- $f(n) = \Theta(g(n))$, ce $\exists c_1,c_2,n_0 > 0$, $\forall n \geq n_0: c_1g(n) \le f(n) \le c_2g(n)$ 
- $f(n) = o(g(n))$, ce $\forall c > 0$, $\exists n_0 \gt 0: \forall n \geq n_0: f(n) \lt cg(n)$
- $f(n) = \omega(g(n))$, ce $\forall c > 0$, $\exists n_0 \gt 0: \forall n \geq n_0: cg(n) \lt f(n)$ 

D: Osnovne lastnosti
1. $f(n) = \Theta(g(n)) \implies g(n) = \Theta(f(n))$ 
2. $f(n) = \Theta(g(n)) \iff f(n) = \Omega(g(n)) \land f(n) = \mathcal{O}(g(n))$ 
3. $c \neq 0$ konstanta $\implies \mathcal{O}(|c|\cdot g(n)) = \mathcal{O}(g(n))$ 
4. $f(n) = \mathcal{O}(h(n)) \land g(n) = \mathcal{O}(k(n)) \implies f(n) + g(n) = \mathcal{O}(max(h(n),k(n)))$ 
5. $f(n) = \mathcal{O}(h(n)) \land g(n) = \mathcal{O}(k(n)) \implies f(n) \cdot g(n) = \mathcal{O}(h(n)\cdot k(n))$ 
6. $f(n)\cdot \mathcal{O}(g(n)) = \mathcal{O}(f(n) \cdot g(n))$ 

D: Racunski problem je vsak problem, katerega resevanje zahteva kakrsno koli obliko racunanja, ki jo zmore izvesti Turingov stroj ali kak njemu ekvivalentni model racunanja.
Racunski problem $\Pi$ definiramo tako, da zanj relevantne formalne parametre povezemo v neko smiselno vprasanje.

D: Primerek (ali nalogo) $\pi$ problema $\Pi$ dobimo, ko v definiciji problema $\Pi$ nadomestimo vse formalne parametre z dejanskimi parametri.

D: Velikost primerka $\pi \in \Pi$ je dolzina besede $w(\pi)$ v kateri so kodirani dejanski parametri primerka $\pi$.

P: Za dani racunski problem $\Pi$ sestaviti algoritem $A$, ki bo sposoben izracunati resitev poljubnega primerka $\pi \in \Pi$. 
Algoritem $A$ bo imel casovno zahtevnost $T_A(n)$, ce bo med resevanjem poljubnega primerka velikosti $n$ opravil $T_A(n)$ korakov.
Funkcije $T_A(n)$ pogosto ne bomo znali natancno doloziti, ker je spremenljivka (ovidna od arhitekture in tehnoloskih lastnosti). Zato bomo poskusali ugotoviti, kaksna je njena hitrost narascanja.

D: Algoritem $A$ ima casovno zahtevnost
- kvecjemu $\mathcal {O}(g(n))$ ce bomo ugotovili: $T_A(n) = \mathcal {O}(g(n))$,
- vsaj $\Omega(h(n))$ ce bomo ugotovili: $T_A(n) = \Omega (h(n))$,
- $\Theta(k(n))$ ce bomo ugotovili: $T_A(n) = \Omega (k(n))$ in $T_A(n) = \mathcal {O}(k(n))$.

D: Casovna zahtevnost lahko:
- konstantna, ce bo $T_A(n) = \mathcal{O}(1)$ 
- logaritmicna, ce bo $T_A(n) = \mathcal {O}(\log n)$
- polilogaritmicna, ce bo $T_A(n) =$ poly$(\log n)$ 
- polinomska, ce bo $T_A(n) =$poly$(n)$
- kvazipolinomska, ce bo $T_A(n) = 2^{poly(\log n)}$
- subeksponentna, ce bo $T_A(n) = 2^{\mathcal {O}(n)}$
- eksponentna, ce bo $T_A(n) = 2^{poly(n)}$

D: Algoritem $A$ ima tudi prostorsko zahtevnost $S_A(n)$, ce bo med resevanjem poljubnega primerka velikosti $n$ vsaj enkrat rabil $S_A(n)$ polmnilniskih besed. 

D: Funkcija $T_{\Pi}(n)$ bo casovna zahtevnost problema $\Pi$, ce bo za $\Pi$ obstajal algoritem $A$ s casovno zahtevnostjo $T_A(n) = T_{\Pi}(n)$.
## *Urejanje*
#### *Navadno urejanje*

D: Razsiritev z vstavljanjem:
```
procedure Vstavi&Razsiri(t[1..i]); 
begin 
	x:=t[i+1]; j:=i; 
	while j>=1 and x<t[j] do
		t[j+1]:=t[j]; j--
	endwhile; 
	t[j+1]:=x
end.
```
InsertionSort (navadno vstavljanje):
```
procedure NavadnoVstavljanje(t); 
begin 
	for i:=1 to n-1 do 
		Vstavi&Razsiri(t[1..i]) 
	endfor 
end.
```
Casovna zahtevnost je $\mathcal{O}(n^2)$:
- za Vstavi&Razsiri je najslabsi primer da moras prestaviti vseh i elemente: $R(i) = \mathcal{O}(i)$
- v NavadnoVstavljanje pa gremo cez celotno tabelo

D: Razsiritev z izbiranjem
```
procedure Izberi&Razsiri(t[1..i]); 
begin 
	j := i+1; 
	while j<=n do 
		if t[j]<t[i+1] then
			x:=t[j]; t[j]:=t[i+1]; t[i+1]:=x
		endif;
		j++
	endwhile
end.
```
Selection sort (navadno izbiranje):
```
procedure NavadnoIzbiranje(t); 
begin 
	for i:=1 to n-1 do 
		Izberi&Razsiri(t[1..i]) 
	endfor 
end.
```
Casovna zahtevnost je $\mathcal{O}(n^2)$:
- za Izberi&Razsiri moramo pregledati cel N da najdemo najmanjsega $R(i) = \Theta(n-i)$
- za NavadnoIzbiranje pa spet potujemo cez celo tabelo

D: Razsiritev z menjavanjem:
```
procedure Menjaj&Razsiri(t[1..i]); 
begin 
	for j:= n downto i+1 do 
		if t[j-1]>t[j] then 
			x:=t[j-1]; t[j-1]:=t[j]; t[j]:=x 
		endif 
	endfor
end.
```
Bubble sort (navadno menjavanje):
```
procedure NavadnoMenjavanje(t); 
begin 
	for i:=1 to n-1 do 
		Menjaj&Razsiri(t[1..i]) 
	endfor 
end.
```
Casovna zahtevnost je $\mathcal{O}(n^2)$:
- za Menjaj&Razsiri moramo med sprehodom po N opraviti n-i primerjav $R(i) = \Theta(n-i)$
- za NavadnoMenjavanje pa spet potujemo cez celo tabelo

S: Navadni algoritmi urejanja n stevil imajo casovno zahtevnost $\Theta(n^2)$.
#### *Spodnja meja casovne zahtevnosti urejanja*

V: Kaksen je najmanjsi cas potreben za urejanje n stevil?
Najprej se bomo omejili le na primerjave, saj bojo aritmeticno-logicne operacije in premestitve na mesto vedno manj potratne kot primerjave. 
Pri primerjanju se ravnamo po odlocitvenem drevesu.
Zamisel:
Stevilom $a_1,a_2,...,a_n$ priredimo dvojisko drevo $T_n$ z naslednjimi lastnosti:
- vsako notranje vozlisce vsebuje neko primerjanje $a_i \lt a_j \ (i \neq j)$
- v listih so vse premutacije stevil $a_1,a_2,...,a_n$
- permutacija $a_{i_1},a_{i_2},...,a_{i_n}$ je v listu ce in samo ce $a_{i_1} \leq a_{i_2} \leq ... \leq a_{i_n}$ izpolnjuje izide vseh primerjanj na veji do tega lista
V splosnem lahko priredimo stevilom $a_1,a_2,...,a_n$ vec razlicnih dreves $T_n$. Kljub razlikam imajo vsa taka drevesa $n!$ listov.
(Teorija grafov): Ce je visina $h(T)$ drevesa $T$ definirana kot stevilo notranjih vozlisc na najdaljsi veji drevesa $T$, potem za vsako dvojisko drevo $T$ z $l$ listi velja $h(T) \geq \lceil {\log_2l} \rceil$ 
V nasem primeru 
- $T = T_n$
- $l = n!$
- $h(T_n) \geq \lceil {\log_2{n!}} \rceil$
Sklep: Vsak algoritem urejanja, ki uporablja operacijo primerjanja dveh stevil, zahteva za ureditev vsaj enega zaporedja $n$ stevil $\Omega(n\log n)$ operacij primerjanja.
#### *Heapsort*

= Algoritem, ki uporablja operacijo primerjanja in doseze najmanjso mozno casovno zahtevnost $\Theta(n\log n)$ 
D: Kopica stevil $s_1,...,s_n$ je dvojisko drevo $T(V,E)$ z lastnostmi:
- $V = \{s_1,...,s_n\}$ je mnozica vozlisc;
- ce ima vozlisce $s_i$ sina $s_j$, je $s_i \geq s_j$ (oce je vecji ali enak svojim sinom);
- za neki $d \in \mathbb N$ ima vsaka veja $d$ ali $d-1$ povezav (drevo je karseda nizko);
- daljse veje so levo od krajsih (drevo je levo poravnano).
Stevilom lahko priredimo vec razlicnih kopic.
Velja: $d = \lceil \log_2(n+1) - 1 \rceil$ 

Zamisel: 
1. Iz stevil $a_1,...,a_n$ sestavi zacetno kopico
2. Izloci koren kopice in ga shrani, na njegovo mesto prestavi enega od listov (npr. skrajno desnega na najnizjem nivoju)
3. Dobljeno drevo popravi v kopico. Prestavljeni list pogrezni vzdolz ustrezne veje na prvo mesto, kjer bo vecji ali enak od tamkajsnjih sinov.
4. Ponovi koraka (2,3) nad to kopico.

1: Stevila $a_1,...,a_n$ dana v tabeli $t$ z $n$ komponentami: $t[i] = a_i$. Tabelo interpretiramo kot zapis dvojiskega drevesa $T(t)$
- vozlisca drevesa $T(t)$ so stevila $t[1], t[2],..., t[n]$;
- koren drevesa $T(t)$ je stevilo $t[1]$;
- ce je $t[i]$ oce v $T(t)$ sta $t[2i]$ in $t[2i+1]$ njegov levi in desni sin
Ni se kopica, treba popravit! (PopraviVKopico(t,i,n), i indeks korena)
Casovna zahtevnost: $\Theta(n)$$

2: Zdaj tabela $t$ opisuje kopico $T(t)$.
Iz kopice moramo izlociti koren in ga nadomestiti z zadnjim listom. To naredimo tako, da zamenjamo prvo in $n$-to komponento tabele $t$ in zabelezimo, da prvih $n-1$ komponent opisuje drevo, $n$-ta komponenta pa izloceni koren. 

3: Popravimo v kopico (r je meja do kjer je v tabeli trenutno stanje in od kje dalje do n je ze urejeno)
```
procedure PopraviVKopico(t,r,i);
begin
	if i<=(r div 2) then 
	s:=2*i; 
		if s+1<=r then 
			if t[s]<t[s+1] then s++ endif
		endif;
		if t[i]<t[s] then
			x:=t[i]; t[i]:=t[s]; t[s]:=x; 
			PopraviVKopico(t,r,s) 
		endif 
	endif 
end.
```
Casovna zahtevnost (2,3): $\mathcal O(n\log n)$ 

4: Algoritem Heapsort
```
procedure Heapsort(t,n); 
begin 
	for i:=(n div 2) downto 1 do 
		PopraviVKopico(t,n,i); 
	endfor; 
	r:=n; 
	while r>1 do 
		x:=t[1]; t[1]:=t[r]; t[r]:=x; 
		r--; 
		PopraviVkopico(t,r,1) 
	endwhile 
end.
```

Casovna zahtevnost: $\Theta(n \log n)$ 

## *Deli in vladaj*
#### *Quicksort*

= Algoritem, ki uporablja operacijo primerjanja in doseze najmanjso mozno casovno zahtevnost $\Theta(n\log n)$

Prva zamisel:
1. Izberi eno izmed komponent tabele $t[1..n]$, denimo $t[m]$. Njeno vsebino $a_m$ oznacimo s $p$, torej $p=a_m$. To bo pivot oz. delilni element.
2. Prerazporedi vsebine komponent tabele $t$ tako, da bodo $t$ sestavljale tri tabele $t_1,t_2,t_3$ z lastnostmi 
	- $t_1$ (vsi $\leq p$)
	- $t_2 = p$
	- $t_3$ (vsi $\geq p$)
3. Uredi $t_1$ in $t_3$, in to kar z algoritmom, ki ga razvijamo v teh tockah (rekurzivno).

D: Quicksort
```
procedure Quicksort(t,r,s);
begin 
	if s<=r then return endif;
	p := Pivot(t,r,s); 
	j := Razdeli(t,r,s); 
	Quicksort(t,r,j-1);
	Quicksort(t,j+1,s)
end.
```

Postopek:
1. Izbiranje delilnega elementa - Pivot (`p=t[m], t[r...s]`)
	- $m=r$ 
	- $m=s$  
	- $m=\lfloor{\frac{r+s}{2}}\rfloor$ 
	- $m= \text{nakljucno izbran}$ 
	- $p=\text{mediana} \ t[r..s]$ 
2. Razdelitev tabele s prerazporejanjem - Razdeli
Radi bi, da bi prerazporejanje razmestilo vsebine komponent `t[r..s]` tako, da bo
	- za neki $j$ vsebina $t[j]$ dokoncno na svojem mestu v tabeli
	- vsebina vsake od komponent $t[r],...t[j-1]$ manjsa ali enaka vsebini $t[j]$
	- vsebina vsake od komponent $t[j+1],...t[s]$ vecja ali enaka vsebini $t[j]$

D: Razdeli
```
procedure Razdeli(t,r,s) return int; 
begin 
	p:=t[r]; i:=r; j:=s+1; 
	while true do 
		while t[++i]<p do if i=s break endif endwhile; 
		while p<t[--j] do if j=r break endif endwhile;
		if j<=i then break endif; 
		x:=t[i]; t[i]:=t[j]; t[j]:=x 
	endwhile;
	x:=t[r]; t[r]:=t[j]; t[j]:=x; 
	return j 
end;
```

Druga zamisel: 
1. Izberi v tabeli $t[1..n]$ pivot $p = t[m]$.
2. Prerazporedi vsebine komponent tabele $t$ tako, da bodo $t$ sestavljale tabele $t_1, t_2, t_3$, kjer bodo v $t_2$ vsebine vseh komponent $= p$, v $t_1$ vsebine vseh komponent $< p$, v $t_3$ pa vsebine vseh komponent $> p$
3. Uredi vsako od $t_1$ in $t_3$ rekurzivno (poklice samega sebe).

D:
```
procedure Quicksort(t,r,s); 
begin 
	if s<=r then return endif; 
	u:=r; i:=r+1; v:=s; 
	p:=Pivot(t,r,s); 
	(u,v):=Razdeli(t,r,s);
	Quicksort(t,r,u-1); 
	Quicksort(t,v+1,s) 
end.
```

Postopek:
1. Pivot ostane enak
2. Razdeli se spremeni, saj mora prerazporediti $t[r..s]$ v tri tabele (netrivialne) $t[r..u-1], t[u,v], t[v+1..s]$ in vrniti dva indeksa, $u, v$.

D: Razdeli
```
procedure Razdeli(t,r,s) return (int,int); 
begin 
	p:=t[r]; u:=r; v:=s; i:=r+1; 
	while i<=v do 
		if t[i]<p 
		then x:=t[u]; t[u]:=t[i]; t[i]:=x; u++; i++ 
		else if t[i]>p 
			then x:= t[i]; t[i]:=t[v]; t[v]:=x; v-- 
			else i++ 
			endif 
		endif 
	endwhile 
end;
```

Casovna zahtevnost: Prvi quicksort
$T(n)$ je vsota vseh prispevkov, $T(n)=\Theta(1) + \Theta(1) + \Theta(n) + T(j-1) + T(n-j) = T(j-1) + T(n-j) + \Theta(n)$
Resitev je odvisna od $j$, kjer se znajde pivot.
Za najslabsi primer (kjer $j=1$): $T(n) = \Theta(n^2)$
Za najboljsi primer (kjer $j \sim \frac{n-1}{2}$): $T(n) = \Theta(n\log n)$ 

Povprecna zahtevnost:
$\overline T(n) = \sum_{k=1}^n P(k) \lfloor {\overline T(k-1) + \overline T(n-k) + \Theta(n)}\rfloor$ 
- $\Theta(n)$ casovna zahtevnost Pivot in Razdeli
- $P(k)$ verjetnost dogodka, da je pivot po velikosti $k$-ti najmanjsi element

T: $\overline T(n) = cn + \frac{2}{n}\sum_{k=0}^{n-1}\overline T(k)$ 

T: $\overline T(n) \leq 2(b+c)n\ln n$, kjer $b,c\in\mathbb R$ 

Sklep: Algoritem `Quicksort(t,1,n)` ima pricakovano casovno zahtevnost $\Theta(n\log n)$.

#### *Deli in vladaj*

Bistvo: Nalogo $N$ problema $P$ razdeli na manjse podnaloge, te resi in iz njihovih resitev sestavi resitev naloge $N$.

D: Splosno ogrodje
```
procedure A(N); 
begin 
	if n<=1 then 
		Vrni_resitev(N) 
	else 
		Razdeli(N); 
		A(N_i_1); 
		... 
		A(N_i_a);
		Sestavi(N) 
	endif 
end.
```

Casovna zahtevnost:
$T(n)=T(n_{i_1}) + T(n_{i_2}) + ... + T(n_{i_a}) + R(n) + S(n)$
Velikosti $n_i$ niso znane, ce pa nam uspe razdeliti $N$ na priblizno enako velike $N_i$, potem za nek $c\geq 2$:
$T(n) = aT(\frac{n}{c}) + R(n) + S(n)$ 
Zapis:
$T(n) = \begin{cases} b & \text{ce} \ \ n\leq 1 \\ aT(\frac{n}{c}) + R(n) + S(n) & \text{ce} \ \ n\gt 1 \end{cases}$ ,  kjer so $a\geq 1,  \ b\gt 0, \ c\geq 2$ 

T: Za splosno funkcijo $f(n)$
$T(n) = n^{\log_c a} [b+\sum_{k=1}^{\log_c n}\frac{f(c^k)}{a^k}]$, kjer je $n\gt 1$ in $T(1)=b$ 

T: Za polinomsko funkcijo $f(n) = bn^d$, $d\geq 0$ 
$T(n) = bn^{\log_c a} [1+\frac{c^d}{a} + (\frac{c^d}{a})^2 + ... + (\frac{c^d}{a})^m]$, kjer $n\gt 1, \ m=\log_cn$ 

I: (Glavni izrek metode Deli in vladaj) Za resitev $T(n)$ enacbe:
$T(n) = \begin{cases} b & \text{ce} \ \ n = 1 \\ aT(\frac{n}{c}) + bn^d & \text{ce} \ \ n\gt 1 \end{cases}$ , kjer so $a\geq 1, \ b\gt 0, \ c\geq 2, \ d\geq 0$ velja naslednje:

$T(n) = \begin{cases} \Theta(n^d) & \text{ce} \ \ \frac{c^d}{a} \gt 1 \\ \Theta(n^d\log n) & \text{ce} \ \ \frac{c^d}{a} = 1 \\ \Theta(n^{\log_c a}) & \text{ce} \ \ \frac{c^d}{a} \lt 1 \end{cases}$ 

#### *Mnozenje stevil*

Vpr: Koliko mnozenj je potrebnih za izracun produkta dveh $n$-mestnih stevil?

S: Solski algoritem zmnozi dve $n$-mestni stevili v casu reda $\Theta(n^2)$ 

D: Karatsubov algoritem
```
procedure Karatsuba(a,b) return integer; 
begin 
	if a<B or b<B then return a*b 
	else 
		n := min(size(a),size(b)); 
		m := n div 2; 
		(aL,aD) := split(a,m); 
		(bL,bD) := split(b,m); 
		z0 := Karatsuba(aD,bD); 
		z2 := Karatsuba(aL,bL); 
		z1 := Karatsuba(aL+aD,bL+bD)-z2-z0; 
		return shift_left(z2,2*m)+shift_left(z1,m)+z0 
	endif 
end.
```
Casovna zahtevnost: $T(n)=\Theta(n^{\log_c a})$ 