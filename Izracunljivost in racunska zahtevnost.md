Model racunanja je formalna definicija osnovnih pojmov in sestavin algoritmicnega racunanja. Strogo definira:
- pojem algoritma,
- okolje, ki je potrebno za izvedbo algoritma.
- izvajanje algoritma v tem okolju.
### *Končni avtomati in regularni izrazi*

*Sistem s koncno mnogo stanji je entiteta, ki*
- *je vedno v kakem od koncno mnogih stanj
- *korakoma bere diskretne podatke iz svoje okolice
- *in po vsakem branju lahko spremeni svoje stanje v novo
- *Stanje, v katerem je sistem v nekem trenutku, predstavlja dotlej prebrane podatke. Na podlagi stanj bo sistem dolocil svoj odzil na naslednji podatek iz okolice.

Koncni avtomat je matematicni model sistemov s koncno mnogo stanji.

##### *Deterministicni koncni avtomat*

D1: Deterministicni koncni avtomat (DKA) je peterka ( $Q, \Sigma, \delta, q_0, F$) kjer so:
- $Q$ koncna mnozica stanj,
- $\Sigma$ vhodna abeceda
- $q_0 \in Q$ zacetno stanje
- $F \subseteq Q$ mnozica koncnih stanj
- $\delta$ funkcija prehodov, $\delta: Q \times \Sigma \to Q$
Torej je $\delta(q,a)$ stanje v katerega DKA preide iz stanja $q$, ce prebere simbol $a$.

D2: Razsirjeno funkcijo prehodov $\hat \delta$ definiramo rekurzivo:
- $\hat \delta(q,\varepsilon) = q$
- $\hat \delta(q,wa) = \delta(\hat\delta(q,w),a)$ za vsak niz $w$ in vhodni simbol $a$

D3: DKA $M = (Q, \Sigma, \delta, q_0, F)$ sprejme besedo (niz) $x$, ce je $\delta(q_0,x) = p$ za nek $p \in F$.
Jezik, sprejet z DKA $M$ je mnozica vseh besed, ki jih sprejme $M$: $L(M) = \{x\in \Sigma^* | \ \delta(q_0,w) \in F\}$.
Jezik $L'$ je regularen, ce $L'$ sprejme kak DKA (ce $\exists$ DKA $M$: $L' = L(M)$).

##### *Nedeterministicni koncni avtomat*

D4: NKA sprejme vhodno besedno $x=a_1a_2...a_n$, ce obstaja (vsaj eno) zaporedje prehodov, oznaceno z $a_1a_2...a_n$, ki vodi iz zacetnega stanja v (katerokoli) koncno stanje.

D5:  Nedeterministicni koncni avtomat (NKA) je peterka ( $Q, \Sigma, \delta, q_0, F$) kjer so:
- $Q$ koncna mnozica stanj,
- $\Sigma$ vhodna abeceda
- $q_0 \in Q$ zacetno stanje
- $F \subseteq Q$ mnozica koncnih stanj
- $\delta$ funkcija prehodov, $\delta: Q \times \Sigma \to 2^Q$
Torej so v mnozici $\delta(q,a)$ natanko tista stanja, v katera NKA lahko preide iz stanja $q$, ce je prebral simbol $a$.

D6: Razsirjeno funkcijo prehodov $\hat \delta$ definiramo rekurzivo tako:
- $\hat \delta(q,\varepsilon) = \{q\}$
- $\hat \delta(q,wa) = \{p\in Q | \ \exists r \in \hat\delta(q,w): p \in \delta(r,a)\}$

D7: NKA $M = (Q, \Sigma, \delta, q_0, F)$ sprejme besedo (niz) $x$, ce $\delta(q_0, x)$ vsebuje kako koncno stanje $p\in F$ (tj. ce $\delta(q_0, x) \cap F \neq 0$).
Jezik, sprejet z NKA $M$ je mnozica vseh besed, ki jih sprejme $M$: $L(M) = \{x\in \Sigma^* | \ \delta(q_0, x)$ vsebuje neko koncno stanje iz $F\}$

##### *Ekvivalentnost DKA in NKA*

I1: Vsak DKA je tudi NKA.
Naj bo $L$ jezik, ki ga sprejme dani NKA $M$. Potem obstaja DKA $M'$, ki sprejme $L$.

##### *Koncni avtomati s tihimi prehodi*

D8: NKA s tihimi prehodi (NKA$_\varepsilon$) je peterka ( $Q, \Sigma, \delta, q_0, F$) kjer so:
- $Q$ koncna mnozica stanj,
- $\Sigma$ vhodna abeceda
- $q_0 \in Q$ zacetno stanje
- $F \subseteq Q$ mnozica koncnih stanj
- $\delta$ funkcija prehodov, $\delta: Q \times (\Sigma \cup \{\varepsilon) \} \to 2^Q$
V mnozici $\delta(q,a)$ so natanko tista stanja, kamor NKA lahko preide iz stanja $q$ po povezavah, ki so oznacene z $a$ ali $\varepsilon$.

D9: $\varepsilon$-Closure($q$) je mnozica vseh stanj, dosegljivih iz stanja $q$ samo s tihimi prehodi.
$\varepsilon$-Closure($S$) = $\bigcup_{q\in S}\varepsilon$-Closure($q$).

D10: Razsirjeno funkcijo prehodov $\hat\delta$ definiramo rekurzivno:
- $\hat\delta(q,\varepsilon) = \varepsilon$-Closure($q$)
- pri $w \in \Sigma^*$ in $a\in \Sigma$ je: $\hat\delta(q,wa) = \varepsilon$-Closure($P$) kjer je $P = \{p\ | \ \exists r \in \hat\delta(q,w): p \in \delta(r,a)\}$

D11: NKA$_\varepsilon$ $M = (Q, \Sigma, \delta, q_0, F)$ sprejme besedo (niz) $x$, ce $\hat\delta(q_0, x)$ vsebuje kako koncno stanje $p\in F$ .
Jezik, sprejet z NKA$_\varepsilon$ $M$ je mnozica vseh besed, ki jih sprejme $M$: $L(M) = \{x\in \Sigma^* | \ \hat\delta(q_0, x)$ vsebuje ne
ko koncno stanje iz $F\}$

##### *Ekvivalentnost NKA in NKA$_\varepsilon$*

I2: Naj bo $L$ jezik, ki ga sprejme dani NKA$_\varepsilon$ $M$. Potem obstaja NKA $M'$, ki sprejme $L$.
##### *Regularni izrazi*

D12: Naj bo $\Sigma$ abeceda ter $L_1$ in $L_2$ mnozici besed iz $\Sigma^*$. Stik $L_1L_2$ jezikov $L_1$ in $L_2$ je jezik, definiran z $L_1L_2 = \{xy \ | \ x \in L_1 \land y \in L_2\}$

D13: Naj bo $L \subseteq \Sigma^*$. Definirajmo $L^0 = \{\varepsilon\}$ in $L^i = LL^{i-1}$ za $i \geq 1$.

D14: Kleenejevo zaprtje $L^*$ jezika $L$ je jezik $L^* = \bigcup_{i=0}^{\infty} L^i$. 
Tranzitivno zaprtje $L^+$ jezika $L$ je jezik $L^+ = \bigcup_{i=1}^{\infty} L^i$.

D15: Naj bo  $\Sigma$  abeceda. Regularni izraz (r.i.) nad  $\Sigma$  in jezik, ki ga r.i. predstavlja, sta definirana induktivno takole:  
1)  $\emptyset$  je r.i., ki predstavlja jezik  $\emptyset$   
2)  $\varepsilon$ je r.i., ki predstavlja jezik  $\{\varepsilon\}$
3) Za vsak $a \in \Sigma$ , je  $a$ r.i., ki predstavlja jezik  $\{a\}$
4) Če sta r in s r.i. in predstavljata jezika $R$ in $S$ , potem:  
	-  $(r+s)$  je r.i., ki predstavljata jezika  $R \cup S$
	-  $(rs)$ je r.i., ki predstavlja jezik  $RS$
	-  $(r^*)$ je r.i., ki predstavlja jezik  $R^*$
Jezik, ki ga predstavlja r.i $r$ bomo oznacili z $L(r)$.

##### *Ekvivalentnost koncnih avtomatov in regularnih izrazov*

I3: Naj bo $r$ poljuben regularni izraz. Potem obstaja NKA$_\varepsilon \ M$, ki sprejme jezik $L(r)$.

I4: Naj bo $M$ poljuben DKA. Tedaj obstaja regularen izraz $r$, ki predstavlja jezik $L(M)$.
### *Lastnosti regularnih jezikov*
##### *Lema o napihovanju*

D16: Lema o napihovanju (za regularne jezike). Naj bo $L$ regularni jezik. Potem obstaja konstanta $n$ (odvisna samo od L), da velja naslednje : 
če je $z$ poljubna beseda z lastnostjo 
	$z \in L \land |z| \geq n$, 
potem obstajajo besede $u,v,w$, da velja 
	$z = uvw$ $\land$ 
	$\land$ $|uv|\leq n$ $\land$ 
	$\land$ $|v|\geq 1$ $\land$ 
	$\land$ $\forall i \geq 0: uv^iw \in L$.

D17: Lema o napihovanju (formalno): $L$ regular $\implies (\exists n)(\forall z) [z \in L \land |z| \geq n \implies (\exists u,v,w)[z=uvw \land |uv| \leq n \land |v| \geq 1 \land (\forall i \geq 0) uv^iw \in L]]$
D18: Metoda za dokazovanje: $(\exists z)(\forall u,v,w)(\exists i \geq 0)uv^iw \notin L \implies L$ ni regularen (tu so $n,z,u,v,w$ dobri - ustrezajo pogojem).

D19: Formalni jezik, ki ni regularen: $L = \{0^{i^2} | \ i \in \mathbb N\}$.

##### *Lastnosti zaprtosti*

D20: Razred regularnih jezikov je zaprt za dano operacijo, ce je rezultat te operacije pri argumentih, ki so regularni jeziki, spet regularni jezik.

D21: Zaprtost za dano operacijo je efektivna, če obstaja algoritem, ki na podlagi končnih opisov regularnih jezikov (ki so argumenti operacije) vrne končni opis regularnega jezika, ki je rezultat operacije.

I5: Razred regularnih jezikov je zaprt za operacije unija, stik in Kleenejevo zaprtje.

I6: Razred regularnih jezikov je zaprt za operaciji komplement in presek.

D22: Kvocient jezikov $L_1$ in $L_2$ je jezik $L_1/L_2$ definiran takole: $L_1/L_2 = \{x \ | \ \exists y \in L_2 : xy \in L_1\}$ 
I7: Razred regularnih jezikov je zaprt za operacijo kvocient s poljubnim jezikom (deliteljem).

##### *Odlocitveni problemi in algoritmi za regularne jezike*

D23: Računski problemi, ki sprašujejo po odgovoru DA/NE, so odločitveni problemi, algoritmi, ki rešujejo odločitvene probleme, pa odločitveni algoritmi.

I8: Jezik $L(M)$, ki ga sprejme končni avtomat $M$ z $n$ stanji, je: 
1) neprazen $\iff$ $M$ sprejme neko besedo dolžine $l$, kjer je $l < n$. 
2) neskončen $\iff$ $M$ sprejme neko besedo dolžine $l$, kjer je $n \leq l < 2n$.

D24: Končna avtomata $M_1,M_2$ sta ekvivalentna, če sprejmeta isti jezik, torej če je $L(M_1) = L(M_2)$.

I9: Obstaja algoritem, ki odloči, ali sta končna avtomata $M_1$ in $M_2$ ekvivalentna.

##### *Myhill-Nerodejev izrek*

D25: Bodi $L \subseteq \Sigma^*$ poljuben jezik. Definirajmo relacijo $R_L$ na $\Sigma^*$ takole:
$xR_Ly \iff \forall z \in \Sigma^*: xz \in L \iff yz \in L$.

D26: $R_L$ je ekvivalenčna relacija. Torej $R_L$ razdeli $L$ v ekvivalenčne razrede. Njihovemu številu pravimo indeks relacije $R_L$.

D27: Bodi $M = (Q,\Sigma,\delta,q_0,F)$ DKA. Definirajmo relacijo $R_M$ na $\Sigma^*$ takole: $xR_My \iff \delta(q_0,x) = \delta(q_0,y)$.

I10 (Myhill-Nerode) : Naslednje izjave so evivalentne: 
1) $L \subseteq \Sigma^*$ je regularen jezik. 
2) $R_L$ ima končen indeks. 
3) $L$ je unija (nekaterih) ekvivalenčnih razredov (neke) desno invariantne ekvivalenčne relacije s končnim indeksom.

I11 (najmanjši DKA): Najmanjši DKA, ki sprejme dani regularni jezik $L$, je enolično določen do izomorfnosti (tj.do preimenovanja stanj) natančno. 

### *Kontekstno neodvisne gramatike in jeziki* 
##### *KNG in KNJ*

D28: Kontekstno-neodvisna gramatika (KNG) je četverka $G = (V,T,P,S)$ , kjer so:
- $V$ končna množica vmesnih simbolov,
- $T$ končna množica končnih simbolov,
- $P$ končna množica produkcij oblike "... $\to$ ..." kjer
	- leva stran - poljuben vmesni simbol iz $V$
	- desna stran - poljubna beseda iz jezika $(V \cup T)^*$
- $S$ je poseben vmesni simbol, imenovan zacetni simbol

D29: Naj bo $A \to \beta$ produkcija in $\alpha, \gamma \in (V \cup T)^*$* poljubni besedi. 
- Produkcijo $A \to \beta$  uporabimo na besedi $\alpha A\gamma$ tako, da v tej besedi zamenjamo $A$ z $\beta$ . Takrat rečemo, da smo iz $\alpha A\gamma$  neposredno izpeljali $\alpha \beta \gamma$  z uporabo produkcije $A \to \beta$ (oziroma, da smo $\alpha \beta \gamma$ razvili neposredno iz $\alpha A\gamma$  z uporabo produkcije $A \to \beta$ ). S
- Besedi $\alpha_i$ in $\alpha_j$ sta v relaciji $\alpha_i\ _G\implies \alpha_j$ , če je $\alpha_j$ neposredno izpeljiv iz $\alpha_i$ z uporabo neke produkcije gramatike $G$. 
- Naj bodo $\alpha_1, \alpha_2, ..., \alpha_m \in (V \cup T)^*$*, $m \geq 1$, nizi. Če velja $\alpha_1\ _G\implies \alpha_2 \land \alpha_2\ _G\implies \alpha_3 \land ... \land  \alpha_{m-1}\ _G\implies \alpha_m$ , potem to zapišemo z $\alpha_1\ _G\implies^* \alpha_m$ in rečemo, da iz $\alpha_1$ izpeljemo $\alpha_m$ po gramatiki $G$ (oz. da je $\alpha_m$ izpeljiv iz $\alpha_1$ po gramatiki $G$).

D30: Jezik kontekstno-neodvisne gramatike $G = (V,T,P,S )$ je $L(G) = \{w \ | \ w \in T^* \land S \ _G\implies^* w\}$.

D31: 
- Jezik $L$ je kontekstno-neodvisen (KNJ), če je $L = L(G)$ za neko (katerokoli) KNG $G$. 
- Niz $\alpha \in (V \cup T )^*$ imenujemo stavčna oblika, če velja $S \ _G\implies^* \ \alpha$. 
- Gramatiki $G_1$ in $G_2$ sta ekvivalentni, če velja $L(G_1) = L(G_2)$.

D32: Bodi $G = (V, T, P, S )$ poljubna KNG. Drevo $D_G$ je drevo izpeljav po gramatiki $G$, če velja naslednje: 
1) Vsaka točka $v \in D_G$ je označena z vmesnim ali končnim simbolom $(\in V \cup T \cup \{\varepsilon\})$. 
2) Koren drevesa $D_G$ je označen z začetnim simbolom $S$. 
3) Če je $v \in D_G$ notranja točka, je označena z vmesnim simbolom $(\in V )$. 
4) Če je $v \in D_G$ označena z vmesnim simbolom, npr. $A$, in so vsi njeni sinovi od leve v desno označeni z $X_1,X_2,…,X_k$, potem je $A \to X_1X_2…X_k$ produkcija. 
5) Če je $v \in D_G$ označena z $\varepsilon$, potem je $v$ list v $D_G$ in je edini sin svojega očeta.

D33: Oznake listov, izpisane med premim obhodom drevesa izpeljav $D_G$ , tvorijo rob drevesa $D_G$ .

D34: Poddrevo drevesa izpeljav $D_G$ v točki $v$ je drevo s korenom v točki $v$ ter vsemi točkami in povezavami, ki v $D_G$ sledijo točki $v$. Če je $v$ označena z $A \in V$, rečemo, da je poddrevo v tej točki $A$-drevo.

I12: Naj bo $G = (V, T, P, S )$ poljubna KNG. Tedaj velja: $S _G \implies^* \alpha$ če in samo če obstaja drevo izpeljav $D_G$ z robom $\alpha$ (krajše: $\alpha$ ima drevo izpeljav $D_G$).

D35: Izpeljava stavčne oblike po gramatiki $G$ je skrajno leva, če na vsakem koraku uporabimo produkcijo, ki razvije skrajno levi vmesni simbol trenutne stavčne oblike. Podobno je izpeljava stavčne oblike skrajno desna, če na vsakem koraku uporabimo produkcijo, ki razvije skrajno desni vmesni simbol trenutne stavčne oblike.

D36: KNG $G$ je dvoumna, če obstaja $w \in L(G)$, ki ima več kot eno drevo izpeljav.
KNJ $L$ je bistveno dvoumen, če je vsaka KNG za jezik $L$ dvoumna.

##### *Normalne oblike KNG*

D37: Bodi $G = (V, T, P, S)$ KNG. Simbol $X$ je potreben, če obstaja izpeljava $S _G\implies^* \alpha X \beta \ _G \implies^* w$, kjer sta $\alpha, \beta \in (V \cup T)^*$ in $w \in T^*$. Če $X$ ni potreben, je odvečen.

I13: Vsak neprazen KNJ generira neka KNG, ki je brez odvečnih simbolov.

D38: $\varepsilon$-produkcija je produkcija oblike $A\to \varepsilon$.

I14: Če je $L = L(G )$ za neko KNG $G = (V, T, P, S )$, potem jezik $L \setminus\{\varepsilon\}$generira neka KNG $G’$, ki je brez $\varepsilon$-produkcij.

D39: Enotska produkcija je produkcija oblike $A \to B$.

I15: Vsak KNJ brez $\varepsilon$ lahko generira KNG, ki je brez enotskih produkcij.

I16 (Normalna oblika Chomskega): Vsak KNJ, ki ne vsebuje $\varepsilon$, se dá generirati s KNG, katere produkcije so oblike: $A \to BC$ ali $A \to a$.

I17 (Normalna oblika Greibachove): Vsak KNJ, ki ne vsebuje $\varepsilon$, se dá generirati s KNG, katere produkcije so oblike: $A \to b\gamma$.

I18: KNJ $L = \{a^nb^nc^md^m | n,m \geq 1\} \cup \{a^nb^mc^md^n | n,m \geq 1\}$ je bistveno dvoumna. 
### *Skladovni avtomati* 
##### *Definicije*

D40: Skladovni avtomat (SA) je sedmerka $M = (Q, \Sigma, \Gamma, \delta, q_0, Z_0, F)$, kjer so 
- $Q$ koncna mnozica stanj,
- $\Sigma$ vhodna abeceda,
- $\Gamma$ skladovna abeceda,
- $q_0 \in Q$ zacetno stanje, 
- $Z_0 \in \Gamma$ zacetni skladovni simbol,
- $F \subseteq Q$ mnozica koncnih stanj, in
- $\delta$ funkcija prehodov, tj. preslikava iz $Q \times (\Sigma \cup \{\epsilon\}) \times \Gamma$ v podmnozice mnozice $Q \times \Gamma^*$.

D41: $\delta(q,a,Z) = {(p_1,\gamma_1), (p_2,\gamma_2), …, (p_m,\gamma_m)}$ pomeni, da SA v stanju $q$, z vhodnim simbolom $a$ v oknu in skladovnim simbolom $Z$ na vrhu sklada, nedeterministično izbere $i$ ($1\leq i\leq m$) in stori naslednje: preide v stanje $p_i$, zamenja $Z$ z nizom $\gamma_i$ in premakne okno na naslednjo calico traku. To je navadna poveza.
$\delta(q,\varepsilon,Z) = {(p_1,\gamma_1), (p_2,\gamma_2), …, (p_m,\gamma_m)}$ pomeni, da SA v stanju $q$, s skladovnim simbolom $Z$ na vrhu sklada in neodvisno od vhodnega simbola v oknu nedeterministicno izbere $i$ ($1\leq i\leq m$) in stori naslednje: preide v stanje $p_i$ in zamenja $Z$ z nizom $\gamma_i$ (okno pusti pri miru). To je tiha poteza.

D42: Trenutni opis (TO) je trojka $(q,w,\gamma)$, kjer je $q$ stanje, $w$ niz vhodnih simbolov in $\gamma$ niz skladovnih simbolov.
- Če je $M = (Q, \Sigma, \Gamma, \delta, q_0, Z_0, F)$ SA, rečemo, da TO $(q, ax, Z\beta)$ neposredno preide v TO $(p_i , x, \gamma_i \beta)$ --- kar zapišemo $(q, ax, Z\beta) _M\vdash (p_i , x, \gamma_i \beta)$ --- če $\delta(q, a, Z)$ vsebuje $(p_i , \gamma_i )$. Tu je namesto vhodnega simbola $a$ lahko tudi $\varepsilon$.
- Refleksivno tranzitivno zaprtje relacije $_M \vdash$ je relacija $_M\vdash^*$. Če velja $I \ _M\vdash^* J$, rečemo, da TO $I$ preide v TO $J$. Če $I$ prede v $J$ v $k$ neposrednih prehodih, to pišemo kot $I \ _M\vdash^k J$.

D43: Vsak SA $M = (Q, \Sigma, \Gamma, \delta, q_0, Z_0, F)$ sprejme dva jezika:
- L(M), jezik sprejet s končnim stanjem, ki je definiran kot: $L(M) = \{w \in \Sigma^* | (q_0, w, Z_0) \vdash^* (p, \varepsilon, \gamma)$, kjer je $p \in F \land \gamma \in \Gamma^*\}$
- N(M), jezik sprejet s praznim skladom, ki je definiran kot: $N(M) = \{w \in \Sigma^* | (q_0, w, Z_0) \vdash^* (p, \varepsilon, \varepsilon)$, kjer je $p \in Q\}$

D44: SA $M = (Q, \Sigma, \Gamma, \delta, q_0, Z_0, F)$ je deterministicen, ce za $\delta$ velja: Za vsak par $q \in Q$ in $Z \in \Gamma$:
1. $\delta(q,\varepsilon, Z) \neq \emptyset \implies \forall a\in \Sigma: \delta(q,a,Z) = \emptyset$
2. $\forall a\in \Sigma \cup \{\varepsilon\}: |\delta(q,a,Z)| \leq 1$

##### *Skladovni avtomati in kontekstno-neodvisni jeziki*

I19: Če je $L=L(M_2)$ za nek SA $M_2$, potem je $L=N(M_1)$ za nek (drugi) SA $M_1$.

I20: Če je $L=N(M_1)$ za nek SA $M_1$, potem je $L=L(M_2)$ za nek (drugi) SA $M_2$.

I21: Razred jezikov, ki jih sprejmejo SA s končnim stanjem, je enak razredu jezikov, ki jih sprejemejo SA s prazni skladom.

I22: Ce je $L$ KNJ, potem obstaja SA $M$, da je $L = N(M)$.

I23: Ce je $L = N(M)$ za neki SA $M$, potem je $L$ KNJ.

I24: Razred vseh jezikov, sprejetih s SA, je enak razredu vseh KNJ.

I25: Jezik $\{ww^R \ |\ w \in (0+1)^*\}$ sprejme neki SA in noben DSA.

I26: DSA je po sposobnosti sprejemanja šibkejši od SA.

### *Lastnosti kontekstno neodvisih jezikov*
##### *Lema o napihovanju*

D45: Lema o napihovanju (za kontekstno-neodvisne jezike). Naj bo $L$ KNJ. Potem obstaja konstanta $n$ (odvisna samo od L), da velja naslednje : 
če je $z$ poljubna beseda z lastnostjo 
	$z \in L \land |z| \geq n$, 
potem obstajajo besede $u,v,w,x,y$, da velja 
	$z = uvwxy$ $\land$ 
	$\land$ $|vwx|\leq n$ $\land$ 
	$\land$ $|vx|\geq 1$ $\land$ 
	$\land$ $\forall i \geq 0: uv^iwx^iy \in L$.

##### *Zaprtost*

I27: Razred kontekstno-neodvisnih jezikov je zaprt za operacije 
- unija, 
- stik, 
- Kleeneovo zaprtje, 
- substitucija (in homomorizem), 
- inverzni homomorfizem.

I28: Razred kontekstno-neodvisnih jezikov ni zaprt za operaciji
- presek, 
- komplement.

I29: Če je $L$ KNJ in $R$ regularen jezik, potem je $L \cap R$ KNJ.

##### *Odločitveni problemi in algoritmi za KNJ*

I30: Obstajata odločitvena algoritma za ugotavljanje, ali je KNJ 
1) prazen; 
2) končen.

D46: Problem pripadnosti (za KNG) je vprašanje "Ali je $x \in L(G)$, kjer je $G = (V, T, P, S)$ dana KNG in $x \in T^*$ dana beseda?" --> algoritem CYK

### *Turingovi stroji* 
##### *Uvod*

I31: Teza o izračunljivosti (tudi Church-Turingova teza). Intuitivni osnovni pojmi algoritmičnega računanja so ustrezno formalizirani (strogo definirani) takole: 
- intuitivni pojem ‘‘algoritma’’ formalizira Turing program; 
- intuitivni pojem ‘‘računanja’’ formalizira izvajanje Turingovega programa; 
- intuitivni pojem ‘‘izračunljive funkcije’’ formalizira funkcija, izračunljiva s Turingovim programom.
Teza o izračunljivosti je vzpostavila most (zvezo) med intuitivnim razumevanjem osnovnih pojmov “algoritem,” “računanje” in “izračunljivost” in matematičnim, formalno definiranim razumevanjem teh pojmov s pomočjo modelov računanja.
##### *Turingov stroj*

D47: Turingov stroj (osnovna različica) ima naslednje enote: nadzorno enoto, v kateri je Turingov program; trak, ki ga sestavljajo celice; premično okno na traku, ki je povezano z nadzorno enoto.

D48: Podrobnosti so: 
- Trak služi pisanju in branju vhodnih podatkov ter vmesnih in končnih rezultatov. Razdeljen je na enake celice in je potencialno neskončen v eno (desno) smer; tj. vsakokrat, ko je to potrebno, se (samodejno) podaljša s končno mnogo celicami. Vsaka celica vsebuje nek tračni simbol iz tračne abecede $\Gamma=\{z_1, …, z_t \}, t \geq 3$. Simbol $z_t$ je poseben: označuje, da je celica prazna. Običajno ga pišemo kot ⨆ in imenujemo simbol za prazen prostor. Poleg ⨆ sta v tračni abecedi še vsaj dva simbola: 0 in 1. (Ne da bi se s tem omejili, se dogovorimo, da je $z_1 = 0$ in $z_2 = 1$.) Vhodni podatki so zapisani v vhodni besedi; ta je sestavljena iz simbolov vhodne abecede $\Sigma$, za katero velja $\{0,1\}\subseteq \Sigma \subseteq \Gamma-\{$⨆$\}$. Torej $\Sigma$ zagotovo vsebuje vsaj 0 in 1, in zagotovo ne vsebuje simbola ⨆. Sprva je vhodna beseda vpisana v skrajno levih celicah (tj. na začetku traku), vse ostale celice traku pa so prazne (v vsaki je ⨆). 
- Nadzorna enota je vedno v kakem stanju iz končne množice stanj $Q ={q_1, …, q_s}$, $s\geq1$. q1 je začetno stanje. Nekatera stanja so končna; zbrana so v množici $F \subseteq Q$ ; ostala stanja so nekončna. Kadar indeks stanja ni pomemben, včasih uporabimo tudi oznaki $q_{da}$ oz. $q_{ne}$ za označevanje končnega oz. nekončnega stanja. V nadzorni enoti je Turingov program (TP), ki usmerja delovanje enot TS. Turingov program P je značilen za izbrani TS, tj. različni TS imajo različne TP. TP je parcialna funkcija $\delta: Q\times \Gamma \to Q\times \Gamma \times \{L,R,S\}$, imenovana funkcija prehodov. TS je po definiciji determinističen: za vsak par (stanje, tračni simbol) ima na voljo kvečjemu eno potezo.
- Okno se lahko premakne (korakoma, preko vmesnih celic) na poljubno celico. Nadzorna enota lahko iz celice pod oknom prebere simbol, v celico pod oknom pa lahko tudi vpiše simbol (tj. zamenja prejšnjega z novim). V enem koraku se okno lahko premakne le na sosednjo calico.

D49: Pred zagonom TS velja naslednje: 
- vhodna beseda je zapisana na začetku traku (tj. v skrajno levih celicah); 
- okno je premaknjeno na začetek traku (tj. nad skrajno levo calico); 
- nadzorna enota se nahaja v začetnem stanju. 
Odslej naprej TS deluje samostojno, mehanično in korakoma kot mu narekuje TP. Če je TS v stanju $q_i \in Q$ in vidi v celici pod oknom simbol $z_r \in \Gamma$, potem: 
	if $q_i$ je končno stanje, then TS se ustavi; 
	else, if $\delta(q_i , z_r)$↑ (tj. TP nima ukaza za par $q_i , z_r$) then TS se ustavi; 
	else, if  $\delta(q_i , z_r)$↓= $(q_j , z_w, D)$ then TS stori naslednje: 
		- preide v stanje $q_j$ ; 
		- vpiše $z_w$ skozi okno; 
		- premakne okno na sosednjo celico v smer $D$.

D50: V splošnem je TS sedmerka $T = (Q,\Sigma,\Gamma,\delta,q_1,$⨆$,F)$.

D51: Če je Turingov stroj $T$ v danem trenutku videti kot se beseda $I = \alpha_1q\alpha_2$ imenuje trenutni opis (TO) Turingovega stroja $T$. TO $I$ neposredno preide v TO $J$ -- kar zapišemo $I \vdash J$ -- če v TP stroja $T$ obstaja ukaz, katerega izvedba spremeni $I$ v $J$. Refleksivno tranzitivno zaprtje relacije $\vdash$ je relacija $\vdash^*$; če velja $I \vdash^* J$ , rečemo, da TO $I$ preide v TO $J$.

##### *Raba Turingovega stroja*

D52: Osnovne računske naloge, ki jih izvajajo Turingovi stroji, so tri:
- Računanje vrednosti funkcij
- Razpoznavanje množic
- Generiranje množic

D53: (Računanje vrednosti funkcij s TS) Bodi $T = (Q, \Sigma, \Gamma, \delta, q_1,$⨆$, F )$ TS in $k \geq 1$. k-mestna lastna funkcija stroja $T$ je parcialna funkcija $\phi_T^{(k)}: (\Sigma^*)^k \to \Sigma^*$ , definirana kot sledi: Če vhodne podatke stroja $T$ sestavlja $k$ besed $u_1,…, u_k \in \Sigma^*$, potem je vrednost funkcije $\phi_T^{(k)}$ pri argumetnih $u_1,…,u_k$ podana s $\phi_T^{(k)} (u_1,…,u_k) = \{v,$ ce se $T$ ustavi $\land$ vrne na traku besedo $v$ $\land$ $v \in \Sigma^*$; ↑, če se $T$ ne ustavi $\lor$ na traku ne vrne besede iz $\Sigma^*$.$\}$

D54: Naj bo $\phi_T^{(k)}: (\Sigma^*)^k \to \Sigma^*$ funkcija. Tedaj: 
- $\phi$ je izračunljiva, če $\exists$TS, ki izračuna $\phi$ povsod na dom($\phi$) $\land$ dom($\phi$) = $(\Sigma^*)^k$ ; 
- $\phi$ je parcialna izračunljiva (p.i.), če $∃$TS, ki izračuna $\phi$ povsod na dom($\phi$); 
- $\phi$ je neizračunljiva, če $\neg\exists$TS, ki izračuna $\phi$ povsod na dom($\phi$).

D55: (Razpoznavanje množic s TS) Bodi $T = (Q, \Sigma, \Gamma, \delta, q_1,$⨆$, F )$ TS in $w \in \Sigma^*$ beseda. $T$ sprejme $w$, če $q_1w \vdash^* \alpha_1p\alpha_2$ za neko stanje $p \in F$ in $\alpha_1\alpha_2 \in \Gamma^*$. Jezik, ki ga sprejme TS $T$, je množica $L(T) = \{w \ | \  w \in \Sigma^* \land$ $T$ sprejme $w\}$.

D56: Naj bo $S \subseteq \Sigma^*$ jezik. Potem:
- S je odločljiv, če $\exists$TS, ki odgovori DA/NE na vpr "Ali je $x \in S$?’' za poljuben $x \in \Sigma^*$
- S je polodločljiv, ce $\exists$TS, ki odgovori DA na vpr "Ali je $x \in S$?’' za poljuben $x \in S$
- S je neodločljiv, če $\neg\exists$TS, ki bi odgovoril DA/NE na vpr "Ali je $x \in S$?’' za poljuben $x \in \Sigma^*$

D57: (Generiranje množic s TS) Naj bo $T = (Q, \Sigma, \Gamma, \delta, q_1,$⨆$, F )$ TS. Pravimo, da je $T$ generator, če na trak izpiše zaporedje (nekih) besed iz $\Sigma^*$, razmejenih s simbolom # $\in \Gamma - \Sigma$. Jezik, ki ga generira $T$, je mnozica $G(T) = \{w \ | \ w \in \Sigma^* \land T$ izpise $w\}$.

D58: Mnozica $S$ je izracunljivo prestevna (i.p), ce obstaja TS $T$ da je $S = G(T)$. ($S$ je i.p, ce jo lahko generira kak Turingov stroj - da se jo ostevilciti).

I32: $S$ je izracunljivo prestevna natanko tedaj, ko je $S$ polodlocljiva.

##### *Razlicice Turingovega stroja*

Vse so enakovredne osnovnemu modelu TS (ceprav zgledajo mocnejse).

D59: TS s koncnim pomnilnikom: Ta razlicica V ima v nadzorni enoti ima koncno velik pomnilnik, ki lahko hrani $k \geq 1$ tracnih simbolov. $\delta_V: Q \times \Gamma \times \Gamma^k \to Q \times \Gamma \times \{L,R,S\} \times \Gamma^k$.

D60: TS z vecslednim trakom: Ta različica V ima trak razdeljen na $tk \geq 2$ vzporednih sledi, okno vidi $tk$-terko tracnih simbolov. $\delta_V: Q \times \Gamma^{tk} \to Q \times \Gamma^{tk} \times \{L,R,S\}$.

D61: TS z neomejenim trakom: Ta različica V ima trak, ki je (potencialno) neomejen v obe smeri. $\delta_V: Q \times \Gamma \to Q \times \Gamma \times \{L,R,S\}$.

D62: Večtračni TS: Ta varianta V ima $tp \geq 2$ neomejenih trakov. Vsak trak ima svoje okno, ki se lahko premika neodvisno od ostalih. $\delta_V: Q \times \Gamma^{tp} \to Q \times (\Gamma \times \{L,R,S\})^{tp}$.

D63: TS z večdimenzionalnim trakom: Ta različica V ima d-dimenzionalen trak, $d \geq 2$. $\delta_V: Q \times \Gamma \to Q \times \Gamma \times \{L_1,R_1,L_2, R_2,...,L_d,R_d,S\}$.

D64: Nedeterministični TS: Ta V ima Turingov program, ki vsakemu paru $(q_i, z_r)$ priredi končno množico možnih prehodov $\{(q_j,z_w,D_1), (q_k,z_v,D_2), ...\}$, stroj V (nadzorna enota) pa izbere enega med njimi (s cudezno sposobnostjo).

##### *Univerzalni Turingov stroj*

D65: Kodiranje Turingovih strojev
Naj bo $T = (Q, \Sigma, \Gamma, \delta, q_1,$⨆$, F )$ poljuben osnovni model TS. Stroj zelimo zakodirati nad kodirno abecedo.
- Naj bo kodirna abeceda kar mnozica $\{0,1\}$.
- Zakodiramo funkcijo $\delta$, saj iz nje lahko izluscimo vse
- $\delta(q_i , z_j) = (q_k , z_l , D_m )$ ukaz v funkciji, ga predstavimo z besedo $K = 0^i10^j10^k10^l10^m$ kjer $D_1 = L, D_2 = R, D_3 = S$.
- Tako predstavimo vsak ukaz iz $\delta$.
- Iz dobljenih besed $K_1,...,K_r$ sestavimo kodo $\langle \delta \rangle$ takole: $\langle \delta \rangle = 111K_111K_211...11K_r111$.
- $\langle T \rangle := \langle \delta \rangle$

D66: Kodo $\langle T \rangle$ lahko interpretiramo kot dvojiski zapis nekega naravnega stevila. Temu pravimo indeks TS T. Ce $n\in \mathbb N$ nima prave oblike, mu priredimo prazni TS (povsod nedefiniran, za vsako vhodno besedo se ustavi). 

I33: Vsako naravno število je indeks natanko enega Turingovega stroja.

D67: Obstaja zaporedje Turingovih strojev - $T_1,T_2,...$ kjer so spodaj indeksi.

I34: Obstaja Turingov stroj U, ki lahko izračuna vse, kar se da izračunati s katerimkoli (drugim) Turingovim strojem.

D68: Definiramo razrede UTS(s,t), s je stevilo stanj in t stevilo tracnih simbolov. UTS(4,6) ima najmanj ukazov - 22.

D69: Odkritje UTS je bil teoretični dokaz, da je splošno-namenski računski stroj vsaj načeloma možen. Možno je fizično realizirati računski stroj, ki zmore izračunati vse, kar je izračunljivo na kateremkoli drugem TS. (racunalnik)

D70: Glavni pomnilnik (≈trak), program (≈Turingov program), procesor (≈nadzorna enota), spominska lokacija (≈celica), naslov (≈”zaporedna številka celice”) - von Neumannova arhitektura.

I35: Naj bodo $S, A, B$ poljubne množice. Velja naslednje:
- $S$ je odlocljiva $\implies$ $S$ je polodlocljiva
- $S$ je odlocljiva $\implies$ $\overline S$ je odlocljiva
- $S$ in $\overline S$ sta polodlocljivi $\implies$ $S$ je odlocljiva
- $A$ in $B$ sta polodlocljivi $\implies$ $A\cup B$ in $A \cap B$ sta polodlocljivi
- $A$ in $B$ sta odlocljivi $\implies$ $A\cup B$ in $A \cap B$ sta odlocljivi

### *Neodločljivost*
##### *Racunski problemi*

D71: Vrste racunskih problemov:
- Odločitveni problemi (DA/NE problemi)
- Problemi iskanja (mnozica $S$ in lastnost $P$, resitev je $x\in S$, ki ima lastnost $P$)
- Problemi preštevanja (mnozica $S$ in lastnost $P$, resitev je stevilo takih elementov $x\in S$, ki imajo lastnost $P$)
- Problemi generiranja (mnozica $S$ in lastnost $P$, resitev je zaporedje elementov $x\in S$, ki imajo lastnost $P$)

D72: Jezik odlocitvenega problema
- Naj bo $D$ poljuben odločitveni problem
- Naj bo $d$ primerek problema $D$.
- Naj bo koda : $D \to \Sigma^*$ kodirna funkcija.
- Zberimo kode vseh pozitivnih primerkov problema $D$ v množici $L(D)$.
$L(D) = \{\langle d\rangle \in \Sigma^* \ | \ d$ je pozitiven primerek odlocitvenega problema $D\}$.

I35: $d\in D$ je pozitiven primerek $\iff$ $\langle d \rangle \in L(D)$. Reševanje odločitvenega problema $D$ prevedemo na razpoznavanje množice $L(D)$ v $\Sigma^*$.

D73: Izracunljivost problema $D$:
- $L(D)$ je odlocljiv $\implies$ obstaja algoritem, ki na poljuben $d \in D$ odgovori DA/NE
- $L(D)$ je polodlocljiv $\implies$ obstaja algoritem, ki 
	- na vsak pozitiven $d \in D$ odgovori DA;
	- na negativen $d \in D$ odgovori NE ali pa sploh ne odgovori
- $L(D)$ je neodlocljiv $\implies$ ni algoritma, ki bi na poljuben $d \in D$ odgovoril DA/NE

D74: Razpoznavanje odlocitvenega problema
- problem $D$ je odločljiv (ali izračunljiv) če je jezik $L(D)$ odločljiv;
- problem $D$ je polodločljiv če je jezik $L(D)$ polodločljiv;
- problem $D$ je neodločljiv (ali neizračunljiv) če je jezik $L(D)$ neodločljiv

##### *Problem ustavitve*

D75: Problem ustavitve $D_{Halt}$ je odlocitveni problem: $D_{Halt} =$ 'Ali se TS $T$ pri vhodni besedi $w \in \Sigma^*$ ustavi?'

I36: Problem ustavitve $D_{Halt}$ je neodlocljiv.

D76: Univerzalni jezik, je jezik Problema ustavitve torej $K_0 = L(D_{Halt}) = \{\langle T,w\rangle \ | \ T$ se pri vhodu $w$ ustavi$\}$. Ce zahtevamo da je $w := \langle T \rangle$ dobimo diagonalni jezik, torej $K = \{\langle T,T\rangle \ | \ T$ se pri vhodu $\langle T\rangle$ ustavi$\}$.

I37: $K$ je neodlocljiva mnozica.

I38: $K_0$ je polodlocljiva mnozica.

I39: $K_0$ je neodlocljiva in polodlocljiva mnozica.

I40: $\overline K_0$ ni polodlocljiva mnozica.

### *Računska zahtevnost* 
##### *DTIME in DSPACE*

D77: Naj bo $M = (Q, \Sigma, \Gamma, \delta, q_1,$⨆$, F )$ DTS s $k \geq 1$ neomejenimi trakovi. Pravimo, da ima DTS $M$ (deterministično) časovno zahtevnost $T(n)$, če za vsako vhodno besedo $w \in \Sigma^*$ dolžine $|w|= n$ naredi kvečjem $T(n)$ korakov (potez), preden se ustavi.

D78: Jezik $L$ ima (deterministično) časovno zahtevnost $T(n)$, če obstaja DTS $M$ z (det). časovno zahtevnostjo $T(n)$, za katerega je $L = L(M)$. Razred vseh jezikov z (det.) čas. zahtevnostjo $T(n)$ je DTIME$(T(n)) = \{L \ | \ L$ je jezik $\land \ L$ ima det. casovno zahtevnost $T(n)\}$.

D79: Naj bo $M = (Q, \Sigma, \Gamma, \delta, q_1,$⨆$, F )$ DTS z 1 vhodnim trakom in $k \geq 1$ delovnimi trakovi. Pravimo, da ima DTS $M$ (deterministično) prostorsko zahtevnost $S(n)$, če za vsako vhodno besedo $w \in \Sigma^*$ dolžine $|w|= n$ porabi kvečjem $S(n)$ celic na vsakem delovnem traku, preden se ustavi.

D80: Jezik $L$ ima (deterministično) prostorsko zahtevnost $S(n)$, če obstaja DTS $M$ z (det). prostorsko zahtevnostjo $S(n)$, za katerega je $L = L(M)$. Razred vseh jezikov z (det.) pro. zahtevnostjo $S(n)$ je DSPACE$(S(n)) = \{L \ | \ L$ je jezik $\land \ L$ ima det. pro. zahtevnost $S(n)\}$.

D81: Naj bo $N = (Q, \Sigma, \Gamma, \delta, q_1,$⨆$, F )$ nedeterministicni TS s $k \geq 1$ trakovi. Pravimo, da ima NTS $N$ nedeterministično časovno zahtevnost $T(n)$, če za vsako vhodno besedo $w \in \Sigma^*$ dolžine $|w|= n$ obstaja izracun, v katerem naredi kvečjemu $T(n)$ korakov (potez), preden se ustavi.

D82: Jezik $L$ ima nedeterministično časovno zahtevnost $T(n)$, če obstaja NTS $N$ z nedet. časovno zahtevnostjo $T(n)$, tako da je $L = L(N)$. Razred vseh jezikov z nedet. cas. zahtevnostjo je NTIME$(T(n)) = \{L \ | \ L$ je jezik $\land \ L$ ima nedet. casovno zahtevnost $T(n)\}$.

D83: Naj bo $N = (Q, \Sigma, \Gamma, \delta, q_1,$⨆$, F )$ NTS z 1 vhodnim trakom in $k \geq 1$ delovnimi trakovi. Pravimo, da ima NTS $N$ nedeterministično prostorsko zahtevnost $S(n)$, če za vsako vhodno besedo $w \in \Sigma^*$ dolžine $|w|= n$ obstaja izracun, v katerem $N$ porabi kvečjemu $S(n)$ celic na vsakem delovnem traku, preden se ustavi.

D84: Jezik $L$ ima nedeterministično prostorsko zahtevnost $S(n)$, če obstaja NTS $N$ z nedet. prostorsko zahtevnostjo $S(n)$, tako da je $L = L(N)$. Razred vseh jezikov z nedet. pro. zahtevnostjo je NSPACE$(S(n)) = \{L \ | \ L$ je jezik $\land \ L$ ima nedet. prostorsko zahtevnost $S(n)\}$.

D85: DTIME$(T(n)) = \{L \ | \ L$ je jezik $\land \ L$ ima det. casovno zahtevnost $T(n)\}$.
DSPACE$(S(n)) = \{L \ | \ L$ je jezik $\land \ L$ ima det. prostorsko zahtevnost $S(n)\}$.
NTIME$(T(n)) = \{L \ | \ L$ je jezik $\land \ L$ ima nedet. casovno zahtevnost $T(n)\}$.
NSPACE$(S(n)) = \{L \ | \ L$ je jezik $\land \ L$ ima nedet. prostorsko zahtevnost $S(n)\}$.
Enako za odlocitvene probleme: $\{D \ | \ D$ je odlocitveni problem $\land \ L(D)$ ima ___ zahtevnost$\}$.

D86: Stiskanje traku: Ideja - zakodirajmo vec simbolov z enim simbolom iz vecje tracne abecede. 

I41: Za poljuben $c \gt 0$ je DSPACE$(S(n))$ = DSPACE$(cS(n))$ in NSPACE$(S(n))$ = NSPACE$(cS(n))$.

D87: Linearna pohitritev: Ideja - vec korakov zdruzimo v nov, vecji korak.

I42: Ce $inf_{n\to\infty} T(n)/n = \infty$ in $k \geq 2$, potem za poljuben $c \gt 0$ je DTIME$(T(n))$ = DTIME$(cT(n))$ in NTIME$(T(n))$ = NTIME$(cT(n))$.

I43: Ce $L \in$ DTIME$(T(n))$ pri $k \gt 1$, potem je $L \in$ DTIME$(T^2(n))$ pri $k=1$. 
Ce $L \in$ NTIME$(T(n))$ pri $k \gt 1$, potem je $L \in$ NTIME$(T^2(n))$ pri $k=1$. 
Ce $L \in$ DTIME$(T(n))$ pri $k \gt 2$, potem je $L \in$ DTIME$(T(n)logT(n))$ pri $k=2$. 
Ce $L \in$ NTIME$(T(n))$ pri $k \gt 2$, potem je $L \in$ NTIME$(T(n)logT(n))$ pri $k=2$. 

I44: Ce $L \in$ DSPACE$(S(n))$ pri $k \gt 1$, potem je $L \in$ DSPACE$(S(n))$ pri $k=1$. 
Ce $L \in$ NSPACE$(S(n))$ pri $k \gt 1$, potem je $L \in$ NSPACE$(S(n))$ pri $k=1$. 

I45: DTIME$(T(n)) \subseteq$ DSPACE$(T(n))$.
$L \in$ DSPACE$(S(n)) \land S(n) \geq log_2n \implies \exists c: L \in$  DTIME$(c^{S(n)})$.
$L \in$ NTIME$(T(n)) \implies \exists c: L \in$  DTIME$(c^{T(n)})$.
NSPACE$(S(n)) \subseteq$ DSPACE$(S^2(n))$, ce $S(n) \geq log_2n \land S(n)$ popolnoma prostorsko predstavljiva.

D88: Funkcija $S(n)$ je prostorsko predstavljiva, če obstaja TS $M$ s prostorsko zahtevnostjo $S(n)$ in naslednjo lastnostjo: za vsak $n \in \mathbb N$ obstaja vhodna beseda dolžine $n$, pri kateri $M$ med računanjem uporabi natanko $S(n)$ celic traku. Ce pa za vsak $n \in \mathbb N$ pri vsaki vhodni besedi dolžine $n$ stroj $M$ uporabi natanko $S(n)$ celic, rečemo, da je $S(n)$ popolnoma prostorsko predstavljiva.

D89: Funkcija $T(n)$ je časovno predstavljiva, če obstaja TS $M$ s časovno zahtevnostjo $T(n)$ in naslednjo lastnostjo: za vsak $n \in \mathbb N$ obstaja vhodna beseda dolžine $n$, pri kateri $M$ med računanjem napravi natanko $T(n)$ korakov. Ce pa za vsak $n \in \mathbb N$ pri celo vsaki vhodni besedi dolžine $n$ stroj $M$ napravi natanko $T(n)$ korakov, rečemo, da je $T(n)$ popolnoma časovno predstavljiva.

##### *Razredi zahtevnosti*

D90: P $= \bigcup_{i \geq 1}$DTIME$(n^i)$
NP $= \bigcup_{i \geq 1}$NTIME$(n^i)$
PSPACE $= \bigcup_{i \geq 1}$DSPACE$(n^i)$
NPSPACE $= \bigcup_{i \geq 1}$NSPACE$(n^i)$

I46: P $\subseteq$ NP $\subseteq$ PSPACE $=$ NPSPACE
- Vsak DTS polinomske časovne zahtevnosti je trivialni NTS (vsak ukaz da na izbiro kvečjemu en prehod) enake (polinomske) časovne zahtevnosti.
- Če je $L \in$ NP, potem (po definiciji) $\exists k$ , da je $L \in$ NTIME$(n^k)$. Zato je (po enem od osnovnih izrekov) $L \in$ NSPACE$(n^k)$, in zato (po Savitchevem izreku) $L \in$ DSPACE$(n^{2k})$. Sledi (iz definicije PSPACE), da je $L \in$ PSPACE.
- Vsak DTS polinomske prostorske zahtevnosti je trivialni NTS (v katerem vsak ukaz da na izbiro $\leq 1$ prehod) enake (polinomske) prostorske zahtevnosti. 
- NPSPACE $= \bigcup_{i \geq 1}$NSPACE$(n^i)$ $\subseteq$ (Savitchev izrek) $\subseteq$ $\bigcup_{i \geq 1}$DSPACE$(n^{2i})$ $\subseteq$ PSPACE.

D91: Problem $D \subseteq$ NP je polinomsko-časovno prevedljiv na problem $D’$, tj. $D \leq^p D ’$ , če obstaja deterministični TS $M$ polinomske časovne zahtevnosti, ki preslika poljuben primerek $d \in D$ v primerek $d’ \in D’$, tako velja $d$ je pozitiven $\iff d’$ je pozitiven. Relaciji $\leq^p$ rečemo polinomska-časovna prevedba.

D92: Problem $D^*$ je NP-težek, če za vsak $D \in$ NP velja $D \leq^p D^*$. Problem je NP-poln, ce velja:
- $D^* \in$ NP
- $D \leq^p D^*$ za vsak $D \in$ NP
NP poln $\iff$ problem je v razredu NP $\land$ problem je NP-tezek.

D93: Logični izraz (Boolov izraz) induktivno definiramo takole: 
- Logične spremenljivke $x_1, x_2, …$ so logični izrazi.
- Če sta $E$ in $F$ logična izraza, so $\neg E, E \lor F$ in $E \land F$ logični izrazi.

D94: Logični izraz $E$ je izpolnljiv, če obstaja prireditev logičnih vrednosti RESNIČNO/NERESNIČNO njegovim spremenljivkam, da ima $E$ logično vrednost RESNIČNO.

D95: Problem izpolnljivosti je odločitveni problem SAT = 'Ali je logični izraz $E$ izpolnljiv?'

I47: (Cook-Levin): SAT je NP-poln problem.

I48: Naj bo $D \leq^p D'$. Potem velja:
- $D' \in$ P $\implies D \in$ P
- $D' \in$ NP $\implies D \in$ NP

I49: Relacija $\leq^p$ je tranzitivna.

I50: Velja:
- $D^*$ je NP-težek $\land \ D^* \leq^p D^✩ \implies D^✩$ je NP-težek 
- $D^*$ je NP-poln $\land \ D^* \leq^p D^✩ \land D^✩ \in$ NP $\implies D^✩$ je je NP-poln

I51: Ce P $\neq$ NP potem
- NPC je razred vseh NP-polnih problemov
- NPI je razred vseh NP-vmesnih problemov

I52: Če P $\neq$ NP, potem v NP obstaja problem, ki ni niti v P niti v NPC. Rekli bomo, da je tak problem NP-vmesen.

I53: Ce P $\neq$ NP potem:
Če je problem v NPC ali NPI, potem njegova deterministična časovna zahtevnost ni polinomsko omejena.

V P so problemi obvladljivi. 
