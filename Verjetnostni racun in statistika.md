### Uvod

17. stoletje: Fermat, Pascal, Bernoulli
18. in 19. stoletje: Laplace, Poisson, Cebisev, Markov
20. stoletje: **Kolmogorov** (1930), de Finetti

D: Statisticna definicija verjetnosti: eksperiment $\to$ dogodek A
$n$ - ponovitev
$f_n(A)$ - frekvenca dogodka A (stevilo ponovitev, v katerih se je A zgodil)
$P(A)$ - $lim_{n\to\infty}\frac{f_n(A)}{n}$ 

P: Met kocke
$A$ - pade 6ka
Koliko je $P(A)$

D: Klasicna definicija verjetnosti: dogodek A
izid - dogodki, ki so enako mozni, koncno mnogo

P: Homogena kocka $\to$ izidi: pade 1,2,3,4,5,6 in  
1. dogodek A: pade 6ka
$P(A)=\frac{\mbox{stevilo izidov, kjer se A zgodi}}{\mbox{stevilo vseh izidov}}$
$P(A)=\frac{1}{6}$
2. dogodek A: pade sodo stevilo
$P(A)=\frac{1}{2}$

P: Vrzemo 2 kocki. Koliksna je verjetnost da je vsota 7?
Moznosti za vsoto: $\{2,3,...,11,12\}$ - vseh je 11
Na prvo zogo: $P(A)=\frac{1}{11}$, vendar to ne bo veljali, saj te moznosti niso vse enako verjetne.

| 2\1   | 1   | 2   | 3   | 4   | 5   | 6   |
| ----- | --- | --- | --- | --- | --- | --- |
| **1** | 2   | 3   | 4   | 5   | 6   | 7   |
| **2** | 3   | 4   | 5   | 6   | 7   | 8   |
| **3** | 4   | 5   | 6   | 7   | 8   | 9   |
| **4** | 5   | 6   | 7   | 8   | 9   | 10  |
| **5** | 6   | 7   | 8   | 9   | 10  | 11  |
| **6** | 7   | 8   | 9   | 10  | 11  | 12  |
Vseh izidov je 36, za nas je ugodnih 6. Torej $P(A)=\frac{6}{36}=\frac{1}{6}$
7 je najbolj verjetna vsota dveh kock.

D: Geometrijska definicija verjetnosti:
$P(A)=\frac{\mbox{ploscina ugodnih izidov}}{\mbox{ploscina vseh izidov}}$

Zgled: Buffonova igla

P: 2 prijatelja sta se dogovorila, da se dobita med 11h in 12h. Prvi bo cakal drugega 20min, nato odsel. V vsakem primeru odideta ob 12h. Recimo da prideta slucajno enkrat med 11h in 12h. Koliksna je verjetnost, da se srecata?
![[Pasted image 20241003092458.png]]
Enota: 1h in prestavimo kvadrat med 0 in 1
Pogoji: $|y-x| \leq \frac{1}{3}$ in $0\leq x,y \leq 1$
Prihod prvega: 11+x
Prihod drugega: 11+y
A: $x-\frac{1}{3} \leq y \leq x + \frac{1}{3}$ 
$P(A)=\frac{1-(\frac{2}{3})^2}{1} = \frac{5}{9}$ 

Zgled (iz fizike): Imamo $m$ posod (stanja) in $n$ kroglic (delci), kjer $m>n$. Koliksna je verjetnost, da se pri slucajni porazdelitvi kroglic v posode zgodi, da je v prvih $n$ posodah v vsaki natanko ena kroglica?
1. Kroglice so med seboj razlicne
Vseh moznosti: $m^n$ 
Ugodnih moznosti: $n!$ 
$P(A)=\frac{n!}{m^n}$
2. Kroglice so vse enake (stene risemo)
Vseh moznosti: $\binom{n+m-1}{n} =\binom{n+m-1}{m-1}$
Ugodnih moznosti: 1
$P(A) = \frac{1}{\binom{n+m-1}{n}}= \frac{n!(m-1)!}{(n+m-1)!}$ 
3. Kroglice so enake, v vsaki posodi je najvec ena
Vseh moznosti: $\binom{m}{n}$ 
Ugodnih moznosti: 1
$P(A)=\frac{1}{\binom{m}{n}} = \frac{n!(m-n)!}{m!}$ 

D: Aksiomatska definicija verjetnosti: Kolmogorov
Prostor izidov $\Omega$ - mnozica vseh moznih izidov
Dogodki so podmnozice v $\Omega$, pa ne nujno vse (nekatere podmnozice niso dogodki)
Mnozica dogodkov $\mathcal F$  ima strukturo $\sigma$-algebre:
1. $\mathcal F$ je neprazna
2. $\mathcal F$ je zaprta za komplemente: $A\in \mathcal F \implies A^C\in\mathcal F$ - ($A^C = \Omega \setminus A$)
3. $\mathcal F$ je zaprta za stevno neskoncne unije: $\{A_i\}_{i=1}^{\infty} \subseteq \mathcal F \implies \bigcup_{i=1}^{\infty} A_i\in\mathcal F$ 
Ostale lastnosti $\sigma$-algebre sledijo iz (1)-(3).
4. $B \subseteq A$ in $A\setminus B$ je komplement B v A $\implies$ $A=B \cup (A\setminus B)$ in $B \cap (A\setminus B) = \emptyset$ 
5. $\mathcal F$ je zaprta za koncne unije: $\{A_i\}_{i=1}^n \in \mathcal F$, $A_i=\emptyset$ za $i>n$ $\implies \bigcup_{i=1}^n A_i = \bigcup_{i=1}^{\infty} A_i$ ce je prazna mnozica v $\mathcal F$, potem $\implies \bigcup_{i=1}^n A_i \in\mathcal F$
6. Prazna mnozica je vedno v $\mathcal F$.
Dokaz: $\emptyset\in\mathcal F$ 
$\implies \Omega\in\mathcal F$ saj $(\emptyset)^C\in\mathcal F$ $\overset {(2)} \implies A^C \in \mathcal F$ $\implies A\cup A^C = \Omega \overset {(5)} \in \mathcal F$ $\implies \Omega^C = \emptyset \in \mathcal F$  
7. Najmanjsa mozna $\sigma$-algebra $\Omega$ je $\{\emptyset, \Omega\}$, najvecja pa $P(\Omega)$ oz $2^{\Omega}$ 
8. $\mathcal F$ je zaprta za stevne preseke: $(\bigcap_{i=1}^{\infty} A_i)^C = \bigcup_{i=1}^n A_i^C \overset {(3),(2)}\in \Omega$ uporabili smo de Morganovo pravilo 

Op: Dokaz (4) iz (8):
$A,B\in\mathcal F$, $B\subseteq A \to A\setminus B \in \mathcal F \approx A\cap B^C \in \mathcal F$ 

D: Operacije na dogodke (to so elementi $\mathcal F$):
- vsota (oz. unija) dogodkov $A+B=A\cup B$ 
- produkt (oz. presek) dogodkov $A*B=A\cap B$ 
Lastnosti:
1. Produkt in vsota sta komutativna, asociativna in idempotentna.
2. Velja distributivnost $(A\cup B)\cap C = (A\cap C)\cup (B\cap C)$ in $(A\cap B)\cup C = (A\cup C)\cap (B\cup C)$ 
3. de Morganovi zakoni:
	- $(A\cap B)^C = A^C \cup B^C$
	- $(A\cup B)^C = A^C \cap B^C$
	- $(\bigcap_{i=1}^{\infty}A_i)^C=\bigcup_{i=1}^{\infty}A_i^C$ 
	- $(\bigcup_{i=1}^{\infty}A_i)^C=\bigcap_{i=1}^{\infty}A_i^C$ 
nadaljujemo na operacije:
- razlika dogodkov $A-B=A\setminus B= A\cap B^C$, ce je $B\subseteq A$, potem je $A=B\cup (A\setminus B)$ in $B\cap (A\setminus B)=\emptyset$ 

D: Dogodka sta nezdruzljiva, ce je $A\cap B=\emptyset$.

P: Najmanjsa $\sigma$-algebra je $\{\emptyset, \Omega \}$ 
Ce $\mathcal F$ vsebuje $A$, ki ni prazen in $A\neq\Omega$, potem je tudi $A^C\in \mathcal F$. 
$\{\emptyset, A, A^C, \Omega \}$ je najmanjsa $\sigma$-algebra, ki vsebuje $A$.

D: Ce je $\mathcal F$ zaprta samo za koncne unije (in komplemente), potem recemo, da je $\mathcal F$ algebra dogodkov.
![[Pasted image 20241010083855.png]]
$\mathcal F=$ vse mozne unije $A_i$.
$A_i$ je atom za $\mathcal F$, ce $A_i\neq\emptyset$ in nobena prava podmnozica $A_i$ ni v $\mathcal F$.

D: $\{A_i\}_{i\in \mathcal I} \subseteq \mathcal P\Omega$. Potem najmanjso $\sigma$-algebro, ki vsebuje $A$ za vse $i$ imenujemo $\sigma$-algebra generirane z $\{A_i\}_{i\in \mathcal I}$ 

P: $\Omega = \mathbb N$
$\{n\}, n\in\mathbb N$ 
$\{\{n\}, n\in\mathbb N\}$ 
Najmanjsa $\sigma$-algebra, ki vsebuje mnozico $\{\{n\}, n\in\mathbb N\}$ je $\mathcal P\mathbb N$. Najmanjsa algebra dogodkov, ki vsebuje $\{\{n\}, n\in\mathbb N\}$ pa je mnozica vseh koncnih mnozic in mnozic, ki imajo koncne komplemente. Ta ne vsebuje mnozice vseh sodih stevil, torej ni enaka $\mathcal P \mathbb N$.

P: $\Omega = \mathbb R$ 
$(a,b)$ in $[a,b]$ 
Najmanjso $\sigma$-algebro generirano z vsemi odprtimi intervali v $\mathbb R$ imenujemo Borelova $\sigma$-algebra.

D: Borelova $\sigma$-algebra na $(a,b)$ ali na $[a,b]$ je $\sigma$-algebra generirana z vsemi odprtimi podintervali.
Enako dobimo, ce vzamemo vse zaprte podintervale. Velja, da $\mathcal B \subsetneq \mathcal P\mathbb R$ 
Oznaka: $\mathcal B$ 

D: Ce za koncno (oz. stevno) druzino podmnozic $A_i$ velja:
- $A_i\cap A_j=\emptyset$, kjer $A_{i,j} \neq \emptyset$ 
- $\bigcup_{i=1}^{n(\infty)}A_i=\Omega$ 
potem $\{A_i\}_{i=1}^{n(\infty)}$ imenujemo popoln sistem dogodkov.

D: $\Omega,\mathcal F$ in verjetnost
$P: \mathcal F \to [0,1]$ 
$(\Omega, \mathcal F, P)$ definirajo verjetnosti prostor 

D: $P$ verjetnost je preslikava, za katero velja:
1. $P(A)\geq 0$
2. $P(\Omega)= 1$
3. Za poljubno stevno druzino $\{A_i\}_{i=1}^{\infty}$ paroma nezdruzljivih dogodkov velja: $P(\bigcup_{i=1}^{\infty}A_i)=\sum_{i=1}^{\infty}P(A_i)$ 
Recemo da je $P$ $\sigma$-aditivna. ($\sigma$ dodamo, ce velja za stevno neskoncno)

D: Lastnosti verjetnosti:
1. $A\in\mathcal F \implies P(A^C)= 1-P(A)$ 
Dokaz: $A\cup A^C=\Omega$ in $A\cap A^C=\emptyset$ 
!!!
2. $P(\emptyset)=0$
Dokaz: $\{A,A^C,\emptyset,...\}$:
$1=P(\Omega)=P(A)+P(A^C)+P(\emptyset)$
$P(\emptyset)=0$
$P(A^C)=1-P(A)$ 
3. $P$ je aditivna
$\{A_i\}_{i=1}^{n}$ in $A_i\cap A_j=\emptyset$ za $i\neq j$
$\implies P(\bigcup_{i=1}^{n}A_i)=\sum_{i=1}^{n}P(A_i)$ 
4. $P$ je monotona
$A\subseteq B\implies P(A)\leq P(B)$
Dokaz: $B=A\cup (B\setminus A)$ 
$A\cap (B\setminus A)=\emptyset$ 
$P(B)=P(A)+P(B\setminus A)\implies P(A)\leq P(B)$ 
5. $P$ je zvezna
	- iz $A_1\subseteq A_2 \subseteq ...$ stevna narascujoca druzina dogodkov, $\{A_i\}_{i=1}^{\infty}$ kjer $A_i \subseteq A_{i+1}$ za vse, bo veljalo: $\lim_{n\to\infty}P(A_n)=P(\bigcup_{i=1}^{\infty}A_i)... A_n=\bigcup_{i=1}^{\infty}A_i$ 
	- iz $A_n\subseteq A_{n-1} \subseteq ...$  $\{A_i\}_{i=1}^{\infty}$ kjer $A_{i+1} \subseteq A_i$ za vse, potem bo veljalo: $\lim_{n\to\infty}P(A_n)=P(\bigcap_{i=1}^{\infty}A_i)$ 
Dokaz: Naj bo
$B_1=A_1$
$B_2=A_2\setminus A_1$
$B_3=A_3\setminus A_2$
itd
$B_i\cap B_j = \emptyset \overset{\mbox{stevna aditivnost}}\implies P(\bigcup_{i=1}^{\infty}B_i)=\sum_{i=1}^n P(B_i)=\lim_{n\to\infty} \sum_{i=1}^n P(B_i)=\lim_{n\to\infty}P(\cup_{i=1}^n B_i)=\lim_{n\to\infty} P(A_n)$ 
P: $\Omega=\{1,2,...,n\}$ 
$\mathcal F=P(\Omega)$ 
$P(\{i\})=\frac{1}{n}\implies P(A)=\frac{|A|}{n}=\frac{|A|}{|\Omega|}$ (klasicna definicija verjetnosti)