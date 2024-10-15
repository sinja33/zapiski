## Numericno resevanje nelinearnih enacb

I: $f: D \subseteq \mathbb R \to \mathbb R$
Iscemo $\alpha \in D, f(\alpha)=0$. $\alpha$ je nicla funkcije $f$ ali $\alpha$ je resitev enacbe $f(\alpha)=0$.

P:
1. $e^{-x}-x=0$ ima natanko eno niclo
Dokaz: $f(0)=e^0=1$ in $f(1)=e^{-1}-1 < 0 \implies$ vsaj 1 nicla na $[0,1]$ 
Ce je $f$ monotono padajoca, potem je nicla ena sama.
$f'(x)=-e^{-x}-1 < 0 \implies f$ je padajoca
Ce $f$ ni monotono padajoca ne moremo sklepati na stevilo nicel:
2. $x^5-5x+1=0$ ima tri resitve.
3. $\tan x-x=0 \iff \tan x = x$ bo imela neskoncno resitev
![[Pasted image 20241004112846.png]]
4. $x^2+1 =0$ nima realne resitve

D: Nicla je enostavna, ce je $f(\alpha)=0$ in $f'(\alpha)\neq 0$.
Nicla je veckratna, ce je $f(\alpha)=0 = f'(\alpha)$.
Nicla je $m$-kratna ($m\in\mathbb N$), ce je $f(\alpha)=0$ in $f'(\alpha)=0, f^{(2)}(\alpha)=0,...,f^{(m-1)}(\alpha)=0$ in $f^{(m)}(\alpha)\neq 0$.

D: Kako natancno izracunamo niclo?
$\alpha$ nicla: $f(\alpha)=0$ 
Imamo priblizek $\widehat\alpha: f(\widehat\alpha)=\varepsilon$, kjer $\varepsilon < < 1$ 

SLIKCA

D: 
1. $\alpha$ enostavna nicla
$f(\alpha + \delta)= f(\widehat\alpha)= \varepsilon = f(\alpha)+ \delta f'(\alpha) + O(\delta^2)$ in velja: $\delta=\frac{\varepsilon}{f'(\alpha)}$ 
2. $\alpha$ je $m$-kratna nicla
$f(\alpha + \delta)= f(\widehat\alpha)= \varepsilon = f(\alpha)+ \delta f'(\alpha) + ... + \delta^{m-1}\frac{ f^{(m-1)}(\alpha)}{(m-1)!} + \delta^{m}\frac{ f^{(m)}(\alpha)}{m!} + O(\delta^{m+1})$  in $\delta^m = \frac{\varepsilon \cdot m!}{f^{(m)}(\alpha)}$ 

#### Bisekcija

D: $f: D \subseteq \mathbb R \to \mathbb R$, $D=[a,b]$
$f(a)f(b) < 0$ in $f$ zvezna, potem $\exists\alpha\in [a,b]: f(\alpha) = 0$ 
Zacetni interval je $[a,b]$
1. $c=\frac{a+b}{2}$
	- Ce je $f(c)f(a)<0 \implies b=c$
	- Ce je $f(c)f(a)>0 \implies a = c$
	- Ce je $f(c)f(a)=0 \implies f(c)=0$ in smo koncali.
2. Najdemo nov $c$.
Nicla je vedno na $[a,b]: a \leq \alpha \leq b$ 

V: Kdaj se ustavimo?
Kadar je $|b-a|< \varepsilon \implies$ niclo smo izracunali na $\varepsilon$ natancno.

V: Koliko korakov potrebujemo?
Recimo, da je $d$ dolzina zacetnega intervala. Potem vsak korak to dolzino razpolovi. $\to \frac{d}{2^k}<\varepsilon \implies 2^k > \frac{d}{\varepsilon} \implies k > \log_2 (\frac{d}{\varepsilon})$ 

Op: Bisekcija deluje ze samo na predznakih funkcije. (Ne potrebujemo vrednosti)

P: $d=1, \varepsilon=10^{-10}$ 
$k > \log_2 (\frac{1}{10^{-10}}) = \log_2 (10^{10}) = 10 \log_2 (10) = 30$ korakov

#### Navadna iteracija

D: $f(x)=0 \iff x=g(x)$ in zelim ohraniti nicle.
Mozne prevedbe:
1. $-f(x)=0 \iff x-f(x)=x$
2. $-cf(x)=0 \iff x-cf(x)=x$
3. $-h(x)f(x)=0 \iff x-h(x)f(x)=x$, kjer $h(\alpha)\neq 0$ 
4. ...
Najbolj uporabna za nas bo 3.

D: Recimo, da smo $f(x)=0$ prevedli na $x=g(x)$. Izberemo $x_0: x_{r+1}=g(x_{r}), \mbox{kjer }  r=0,1,... \implies \{x_r\}_{r=0}^{\infty}$
Ce zaporedje konvergira $\alpha=\lim_{r\to\infty}x_r$ in je $g$ zvezna funkcija, potem je $\alpha=g(\alpha)$ in $\alpha$ je negibna (fiksna) tocka.
$x_{r+1}=g(x_r)$, $\lim_{r\to\infty} x_{r+1}=\alpha=\lim_{r\to\infty} g(x_r)\overset {\mbox{zveznost}}= g(\lim_{r\to\infty} x_r)=g(\alpha)$ 

P: Nicla $\alpha$ funkcije $f$ je natanko negibna tocka funkcije $g$.

SLIKA

P:
1. $f(x)=x^3-5x+1=0$
$5x=x^3+1 \to x=\frac{x^3+1}{5}=g_1(x)$ 

D: Funkcija $f: I\to\mathbb R$ je Lipshitzova s konstanto $L$, ce za $\forall x,y\in I$ velja: $|g(x)-g(y)|\leq L |x-y|$.
DN: Vsaka Lipshitzova je zvezna.
Ce je $L<1$, potem je $g$ skrcitev.
(Ce je $g:I\to I$ skrcitev, potem $\exists x\in I: g(x)=x$, tudi za matricne prostore)