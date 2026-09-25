+++
title = "Ecuația dreptei"
type = "docs"
slug = "ecuatia-dreptei"
+++

# Ecuația dreptei

{{< material-author >}}
Adrian Manea, `adrianmanea@poligon-edu.ro`
{{< /material-author >}}

Dreapta este un obiect matematic atât de simplu, încât nici nu are definiție.
O înțelegi intuitiv și geometric mai întâi, iar apoi, prin ecuații algebrice.

Dacă punctul marchează un loc, dar fără posibilitatea de mișcare, dreapta este
pasul imediat următor, prin care un punct se deplasează într-o direcție. De aceea,
dreapta este un *obiect unu-dimensional*, fiindcă permite o singură informație:
direcția de deplasare a unui punct. Sau, fiindcă are lungime infinită, poți să-i spui
direcția pe care se află trei, patru, cinci sau o infinitate de puncte coliniare.

Când ai doar două puncte, ești sigur că ai și o dreaptă: cea care le unește.
*Dreapta este cea mai scurtă cale între orice două puncte din plan*, de fapt.
Când ai mai multe puncte, însă, trebuie verificări suplimentare, cum o să-ți
arăt imediat.

Dar dreapta înseamnă mult mai mult decât imaginea geometrică a celei mai simple
linii. Este și un obiect algebric, care modelează o ecuație de gradul întâi.
Atât de strânsă este legătura între cele două, încât, în general, o expresie
de gradul întâi, adică una care nu folosește ridicări la pătrat sau alte puteri,
se numește *liniară*, căci este reprezentată geometric de o linie (dreaptă).

Aici este una dintre cele mai importante legături:

> Funcțiile de gradul întâi și dreptele în plan sunt unul și același lucru.

Când te gândești la o corespondență de tipul $f(x) = 3x - 1$, automat ai
descris și dreapta de ecuație $y = 3x - 1$. Dreapta, ca obiect geometric,
este reprezentarea grafică a funcției, iar coordonatele $(x, y)$ ale punctelor
de pe dreaptă se află în relația dată de funcție, $y = f(x)$.

Legătura aceasta adaugă o componentă vizuală ecuațiilor abstracte.
Reciproc, dintr-o imagine geometrică poți să extragi ecuații cu care
să lucrezi algebric, prin calcule. Proprietăți geometrice precum paralelismul,
perpendicularitatea, unghiul dintre două drepte sau distanța dintre ele
au verificări prin calcul. Nu mai trebuie să ți se pară sau să folosești
raportorul ca să verifici că două drepte sunt paralele sau că un unghi anume
chiar are măsura de $90\degree$ sau $180\degree$; faci un calcul rapid și te convingi.

## Coeficienții și interpretările lor

În ecuația unei drepte (sau în expresia unei funcții de gradul întâi)
întâlnești doi coeficienți: unul se înmulțește cu variabila $x$, iar celălalt,
se adună la rezultat.

O dreaptă de forma $y = 3x + 1$, descrisă de funcția cu aceeași expresie,
se poate înțelege ca o procedură care primește numere reale ca date de intrare
și le prelucrează pe toate la fel: le înmulțește cu 3 și la rezultat adaugă 1.
Primești $x = 1$, obții $y = 4$; primești $y= - 1,5$, obții $y = -3,5$ și așa
mai departe, iar în loc de $ y $ poți să scrii $ f(x) $ și înseamnă același lucru.

Când vorbești despre același tip de expresie, dar gândită ca o dreaptă, de ecuație
standard $ y = ax + b $, $ a $ și $ b $ au nume care le arată interpretările
geometrice: $ a $ se numește *pantă* (sau *înclinare*), iar $ b $ se numește
*ordonată la origine*. Denumirile o să le înțelegi foarte bine de îndată
ce facem reprezentarea în plan. Cum orice două puncte distincte determină
o dreaptă unică, nu ai decât să le unești. Deci este suficient să poți calcula
coordonatele a două puncte și, unindu-le, apoi prelungind, obții dreapta întreagă.

---

Iată un exemplu: dreapta de ecuație $ y = x + 3 $.

Punctele de pe graficul ei au coordonatele $ (x, y) $, deci alegi două valori pentru $ x $,
calculezi valorile corespunzătoare pentru $ y $ și gata.

Să zicem $ x = 1 $, deci $ y = 1 + 3 = 4 $ și $ x = -2 $, deci $ y = -2 + 3 = 1 $.
Am obținut punctele $ A(1, 4) $ și $ B(-2, 1) $, prin care trece dreapta căutată.
Reprezentarea grafică arată ca în figura de mai jos.

<figure id="fig-dreapta-prin-2-puncte">
<img src="/images/figures/fig1.svg" alt="Dreapta de ecuație y = x + 3" style="width:75%;">
<figcaption>Dreapta de ecuație y = x + 3</figcaption>
</figure>

---

Chiar dacă poți să folosești orice două puncte vrei pentru reprezentarea unei drepte,
sunt două care au o semnificație aparte și, de multe ori, oricum ai nevoie de ele
în studiul dreptei. Așa că le poți folosi de la început și în reprezentare.
Este vorba despre *punctele de intersecție cu axele de coordonate, Ox și Oy*.

Ca să le calculezi, ajută să te gândești că axa orizontală (*Ox* sau *axa absciselor*)
arată lățimea, deplasarea laterală față de origine, adică dacă punctul este
la dreapta sau la stânga lui zero. Similar, axa verticală (*Oy* sau *axa ordonatelor*)
arată deplasarea pe înălțime față de origine, adică dacă punctul curent este
mai sus sau mai jos față de zero.

Văzute așa lucrurile, intersecția cu axa *Ox* înseamnă înălțime zero („la parter”),
iar intersecția cu axa *Oy* înseamnă lățime zero („în centru”). În consecință,
punctul de intersecție cu axa *Ox* va fi de forma $ P(x_P, 0) $, iar punctul de intersecție
cu axa *Oy* va fi de forma $ Q(0, y_Q) $.
Calculul coordonatelor lipsă se obține imediat, din ecuația dreptei, care dă legătura
între perechile de coordonate $(x, y)$ pentru orice două puncte.

Spre exemplu, pentru dreapta desenată anterior, de ecuație $ y = x + 3 $, găsim imediat:

- pentru punctul $ P $, $ 0 = x_P + 3 \Rightarrow x_P = -3 $, deci $ P(-3, 0) $;
- pentru punctul $ Q $, $ y_Q = 0 + 3 \Rightarrow y_Q = 3 $, deci $ Q(0, 3) $.

Putem completa desenul cu ele, iar punctele anterioare, $ A $ și $ B $, devin două
puncte oarecare, fără vreo importanță anume.

<figure id="fig-dreapta-intersectii-axe">
<img src="/images/figures/fig2.svg" alt="Dreapta de ecuație y = x + 3 și intersecțiile cu axele" style="width:75%;">
<figcaption>Dreapta de ecuație y = x + 3 și intersecțiile cu axele</figcaption>
</figure>

E clar acum de ce termenul liber din ecuația dreptei se numește *ordonată la origine*.
Pentru dreapta $ y = ax + b $, punctul de coordonate $ Q(0, b) $ este intersecția
cu axa ordonatelor.

Ca să înțelegi și mai bine interpretările geometrice ale pantei și ordonatei la origine,
ajută să le izolezi. Cu alte cuvinte, să te gândești la o dreaptă care conține doar pe unul
dintre ei (celălalt fiind egal cu 0) și astfel, să vezi ce se întâmplă când se schimbă
cel rămas.

Uită-te la reprezentarea din figura de mai jos, unde dreapta $ y = ax + b $ are $ b = 0 $,
adică ecuația este doar $ y = ax $ și am reprezentat pentru câteva valori ale lui $ a $.

<figure id="fig-dreapta-b-0">
<img src="/images/figures/fig3.svg" alt="Reprezentarea mai multor drepte de forma y = ax"
style="width:75%;">
<figcaption>Reprezentarea mai multor drepte de forma y = ax</figcaption>
</figure>

Poți să desenezi fiecare dreaptă prin câte două puncte care se găsesc pe ea.
Dacă încerci să calculezi intersecțiile cu axele, vei găsi că toate dreptele trec prin
origine, deci conțin punctul $ O(0, 0) $. Așa că e mai util să iei câte două puncte
cu coordonate de valori aleatorii, dar bine alese încât să-ți fie calculele cât
mai ușoare. De exemplu, cele pe care le-am marcat pe desen:

- Pentru dreapta <span style="color:var(--navy) !important;">$ y = 2x $</span>, am luat
<span style="color:var(--navy) !important;">(1, 2)</span> și <span style="color:var(--navy) !important;">(-1, -2)</span>;
- Pentru dreapta <span style="color:var(--burgundy) !important;">$ y = 3x $</span>, am
folosit <span style="color:var(--burgundy) !important;">(1, 3)</span> și
<span style="color:var(--burgundy) !important;">(-1, -3)</span>;
- Pentru <span style="color:var(--teal) !important;">$ y = -\dfrac{1}{2} x $</span>,
am folosit <span style="color:var(--teal) !important;">(2, -1)</span> și
<span style="color:var(--teal) !important;">(-2, 1)</span>;
- În fine, pentru <span style="color: black !important;">$y = -3x$</span>, am calculat
<span style="color: black !important;">(-1, 3)</span> și
<span style="color: black !important;">(1, -3)</span>.

Se vede, deci, că rolul coeficientului $ a $ este să rotească dreapta în jurul
originii. De fapt, *$ a $ rotește dreapta în jurul punctului de intersecție cu axa Ox*,
care s-a întâmplat să fie originea când $ b = 0 $. Ca să te convingi, reprezintă grafic aceleași
patru drepte, dar folosește acum $ b = 1 $.

Rolul lui $ b $ e mai simplu de văzut. Punem $ a = 0 $ și dreapta devine $ y = b $.
Altfel spus, indiferent de valoarea lui $ x $, punctele de pe dreaptă vor avea același $ y $.
Câteva reprezentări găsești în figura de mai jos, unde fiecare dreaptă a fost desenată
prin câte două puncte de pe ea, dar nu le-am mai reprezentat, ca să nu încarc figura.

<figure id="fig-dreapta-a-0">
<img src="/images/figures/fig4.svg" alt="Reprezentarea mai multor drepte de forma y = b"
style="width:75%;">
<figcaption>Reprezentarea mai multor drepte de forma y = b</figcaption>
</figure>

E clar de aici că o dreaptă cu $ a = 0 $ este orizontală. Lucrul acesta se leagă
și de interpretarea lui $ a $ ca înclinare a dreptei, deci era de așteptat.
Funcția corespunzătoare este $ f(x) = b $, care este o *funcție constantă*, pentru că,
indiferent de valoarea lui $ x $, $ f(x) $ este mereu $ b $.

Rolul lui $ b $, așa cum se vede din figură, este să mute dreapta în lungul axei *Oy*,
adică mai sus sau mai jos. Și acest lucru era de așteptat, fiindcă punctul de coordonate
$ (0, b) $ dă intersecția dintre dreaptă și axa *Oy*, iar acest punct se va afla mereu
pe axa verticală. Deci orice modificare a lui $ b $ deplasează punctul doar
pe această axă.

{{% highlight %}}

# Transformări geometrice prin coeficienți

Dacă pui cap la cap interpretările celor doi coeficienți, $ a $ și $ b $, poți înțelege
cum funcționează două transformări geometrice simple: *rotația și translația pe verticală*.
Să zicem că pornești cu o dreaptă oarecare, de ecuație $ y = ax + b $.

- Cu cât valoarea lui $ a $ este mai mare, cu atât dreapta este „mai abruptă la urcare
spre dreapta”, adică face un unghi mai mare cu axa *Ox*, însă unghiul este mereu ascuțit.
Când $ a $ este negativ, cu cât valoarea lui absolută este mai mare, cu atât dreapta
este „mai abruptă la stânga”, cu un unghi față de axa *Ox* din ce în ce mai mic, însă
mereu obtuz.

- Când valoarea lui $ b $ crește, dreapta se ridică, adică se mută paralel mai sus.
Când valoarea lui $ b $ scade, dreapta coboară. Asta pentru că $ b $ controlează
punctul de intersecție cu axa *Oy*, deci variații ale lui $ b $ influențează
această valoare.

{{% /highlight %}}

### Panta dreptei

Înclinarea unei drepte poate fi măsurată precis. În afară de faptul că este
descrisă de o anumită valoare a lui $ a $ în ecuația dreptei, care este o interpretare
algebrică, există și o metodă geometrică de a o găsi.

Să ne uităm, pentru început, la un caz foarte simplu: cel când $ a = 1 $ și $ b = 0 $,
adică dreapta este $ y = x $, care se mai numește și *prima bisectoare* (dacă nu e clar
de ce, te vei lămuri imediat). Iată desenul.

<figure id="fig-prima-bisectoare">
<img src="/images/figures/fig5.svg" alt="Prima bisectoare" style="width:75%;">
<figcaption>Prima bisectoare, adică dreapta de ecuație y = x</figcaption>
</figure>

Dacă iei orice punct $ P(x_P, y_P) $ de pe dreaptă, el va avea coordonatele $ x_P = y_P $.
Asta înseamnă că orice astfel de punct conduce la un triunghi dreptunghic isoscel,
în care ipotenuza este dreapta noastră. Rezultă imediat că unghiul pe care îl face
dreapta cu axa *Ox*, pe care l-am notat $ \alpha $ în figură, este de $ 45\degree $.
Însă $ \mathrm{tg}(45\degree) = 1 $, care este chiar valoarea coeficientului $ a $.
Să fie o coincidență?

Nu, întâmplarea are loc în general: valoarea lui $ a $, adică panta dreptei, este
egală cu tangenta unghiului pe care îl face dreapta cu axa *Ox*.
Chiar și când nu trece prin origine, chiar și când unghiul este obtuz,
relația rămâne adevărată.

Te poți convinge tot cu ajutorul unor triunghiuri dreptunghice, construite potrivit.
De exemplu, am reprezentat mai jos câteva drepte:

$$
\begin{matrix}
\textcolor{#3b4758}{d_1:} & \textcolor{#3b4758}{y = x + 2} \\
\textcolor{#aa424e}{d_2:} & \textcolor{#aa424e}{y = 2x - 1} \\
\textcolor{#008e80}{d_3:} & \textcolor{#008e80}{y = -\dfrac{1}{2} x + 1}
\end{matrix}
$$

<figure id="fig-pante-drepte">
<img src="/images/figures/fig6.svg" alt="Calculul pantelor unor drepte prin triunghiuri dreptunghice" style="width:90%;">
<figcaption>Calculul pantelor unor drepte cu triunghiuri dreptunghice</figcaption>
</figure>

Pentru fiecare dintre ele, poți să construiești câte un triunghi dreptunghic cu
vârful în punctul de intersecție a dreptei cu axa *Ox*. Cu metoda aplicată anterior,
obții imediat <span style="color:var(--navy);">$A(-2, 0)$</span>,
<span style="color:var(--burgundy);">$B\left( \dfrac{1}{2}, 0 \right)$</span>
și <span style="color:var(--teal);">$C(2, 0)$</span>.

Apoi, mai alegi câte un punct pe grafic, ca să poți construi triunghiurile.
De exemplu, <span style="color:var(--navy);">$A^\prime(-1, 1)$</span>,
<span style="color:var(--burgundy);">$B^\prime(2, 3)$</span> și
<span style="color:var(--teal);">$C^\prime(0, 1)$</span>. Formezi triunghiuri
dreptunghice dacă duci paralele la axele de coordonate din aceste puncte,
mai puțin în cazul <span style="color:var(--teal);">$d_3$</span>, unde s-a întâmplat
ca punctele alese să fie chiar intersecțiile cu axele de coordonate.

În fine, cel de-al treilea punct pentru formarea fiecărui triunghi îl iei prin
proiecția punctelor anterioare pe axa *Ox*. Adică
<span style="color:var(--navy);">$A^{\prime\prime}(-1, 0)$</span>,
<span style="color:var(--burgundy);">$B^{\prime\prime}(2, 0)$</span> și
<span style="color:var(--teal);">$C^{\prime\prime}(0, 0)$</span> $ = O $.

Acum, pe rând, în cele trei triunghiuri dreptunghice, vom calcula tangentele
unghiurilor pe care le fac dreptele corespunzătoare cu axa *Ox*, cu ajutorul
lungimilor catetelor pe care le-am delimitat.

- În $ \Delta AA^\prime A^{\prime\prime}, \mathrm{tg}(\alpha) = \dfrac{A^\prime A^{\prime\prime}}{AA^{\prime\prime}} = 1 $;

- În $ \Delta BB^\prime B^{\prime\prime}, \mathrm{tg}(\beta) = \dfrac{B^\prime B^{\prime\prime}}{BB^{\prime\prime}} = 2 $;

- În $ \Delta CC^\prime C^{\prime\prime} $, unghiul care ne interesează este $ \gamma $
și este un unghi obtuz. Însă vom putea calcula tangenta suplementului său, unghiul
ascuțit al triunghiului pe care l-am construit. Îl notăm cu
$ c = \widehat{C^\prime B^{\prime\prime} O} $ și avem
$ \mathrm{tg}(c) = \dfrac{C^\prime O}{OB^{\prime\prime}} = \dfrac{1}{2} $.
Acum, cu o formulă trigonometrică,
$$ \mathrm{tg}(c) = -\mathrm{tg}(180\degree - c) = -\mathrm{tg}(\gamma), $$ rezultă
$ \mathrm{tg}(\gamma) = -\dfrac{1}{2} $.

În concluzie, cum am anunțat, pantele dreptelor corespund tangentelor unghiurilor
pe care le fac reprezentările grafice cu axa *Ox*. Aceste unghiuri se măsoară
în sens invers acelor de ceasornic (numit și *sens trigonometric* sau *direct*),
astfel încât uneori pot fi obtuze.

{{% highlight %}}

# Panta unei șosele

Dacă înțelegi așa panta, anume prin tangenta unui unghi în triunghiul dreptunghic
unde dreapta este ipotenuză, e ușor de interpretat și înclinarea dată ca procent,
cum vezi în semne de circulație.
<img src="/images/figures/slope_diy.svg" style="display: block; margin: auto; width:50%" />

O înclinare de 10%, de exemplu, înseamnă că, pentru fiecare 100 de metri
parcurși pe ipotenuză, ai urcat 10 metri (față de orizontală). În legătură
cu ecuația dreptei, înseamnă că ipotenuza, adică drumul înclinat pe care urci,
face parte dintr-o dreaptă cu panta de 10% = 0,1, adică are o ecuație de forma
$ y = 0,1 x + b $, cu $ b $ necunoscut (și irelevant).

{{% /highlight %}}

## Paralelism și perpendicularitate
Tot prin interpretarea pantei ca înclinare rezultă imediat o proprietate utilă.

{{% important %}}

# Condiția de paralelism al două drepte

Două drepte sunt paralele dacă și numai dacă au aceeași pantă.

{{% /important %}}

Altfel spus, dreptele de ecuații:

$$
\begin{matrix}
d_1: & y = a_1x + b_1 \\
d_2: & y = a_2x + b_2
\end{matrix}
$$
sunt paralele dacă și numai dacă $ a_1 = a_2 $. Pentru siguranță, merită adăugată
și condiția $ b_1 \neq b_2 $, pentru că altfel, dreptele coincid și, cel mai probabil,
e un caz care nu ne interesează.

Pentru condiția de perpendicularitate, avem un pic mai mult de lucrat.
Pornim tot cu dreptele $ d_1 $ și $ d_2 $ din ecuațiile generale de mai sus,
dar construim sistemul de coordonate *xOy* astfel încât originea să fie chiar
în punctul lor de intersecție. Asta o să simplifice calculele și oricum, sistemul de
coordonate nu este universal fixat. Echivalent, te poți gândi că nu lucrăm cu dreptele
inițiale, ci cu altele două, paralele cu acelea, care se intersectează fix în $ O $.
Din condiția de paralelism, rezultă că cele două noi drepte vor avea aceleași pante
cu $ d_1 $ și $ d_2 $, iar asta e tot ce ne interesează.

Iată, deci, o configurație.

<figure id="fig-drepte-perpendiculare">
<img src="/images/figures/fig8.svg" alt="Drepte perpendiculare"
style="width:75%;">
<figcaption>Drepte perpendiculare, care se intersectează în origine</figcaption>
</figure>

Panta dreptei $ d_1 $ este $ \mathrm{tg}(\alpha) = a_1 $, iar panta dreptei $ d_2 $
este $ \mathrm{tg}(180\degree - \beta) = -\mathrm{tg}(\beta) = a_2 $.

Acum, dacă dreptele sunt perpendiculare, atunci $ \alpha + \beta = 90\degree $,
deci $ \mathrm{tg}(\alpha) = \mathrm{tg}(90\degree - \beta) $. Aici avem nevoie
de o formulă trigonometrică binecunoscută. Cum într-un triunghi dreptunghic
sinusul unui unghi ascuțit este egal cu cosinusul celuilalt unghi ascuțit
(complementul său), rezultă că tangenta unui unghi este egală cu inversa tangentei
(cotangenta) complementarului. Altfel spus:
$$
\mathrm{tg}(A) = \dfrac{1}{\mathrm{tg}(90\degree - A)},
$$
pentru orice unghi ascuțit $ A $. Dar dacă în loc de unghiul $ A $ folosim unghiul
$ \alpha $ care ne interesează, obținem:
$$
\mathrm{tg}(\alpha) = \dfrac{1}{\mathrm{tg}(90\degree - \alpha)} = %
\dfrac{1}{\mathrm{tg}(\beta)} = - \dfrac{1}{\mathrm{tg}(180\degree - \beta)},
$$
iar dacă trecem la pante, rezultă $ a_1 = -\dfrac{1}{a_2} $, care se mai scrie și
$ a_1 \cdot a_2 = -1 $.

Am obținut ce căutam.

{{% important %}}

# Condiția de perpendicularitate a două drepte

Dacă două drepte sunt perpendiculare, atunci produsul pantelor lor este egal cu -1.

{{% /important %}}

## Ecuația dreptei prin două puncte

Până acum, exemplele pe care le-am dat porneau cu ecuații ale dreptelor, pe care puteam
lua oricâte puncte &mdash; aleatoriu, convenabil sau punctele de intersecție cu
axele de coordonate.

Acum ne gândim la problema inversă. Prin orice două puncte trece o dreaptă unică.
Cum îi găsim ecuația? Problema se mai numește *ecuația dreptei prin tăieturi*, iar
unele materiale o calculează direct printr-o formulă. Însă ecuația e foarte ușor
de dedus, pe baza înțelegerii celor doi coeficienți, $ a $ și $ b $, cum i-am notat
până acum.

Iată un exemplu concret. Vrei să afli ecuația dreptei care conține punctele $ A(-1, 2) $
și $ B(3, -1) $. Ești, așadar, în căutarea coeficienților $ a $ și $ b $ din ecuația
$ y = ax + b $, astfel încât cele două puncte să fie pe aceeași dreaptă.

Cum ecuația dreptei dă legătura între perechile de coordonate $ (x, y) $ pentru orice
punct care se găsește pe dreapta respectivă, înseamnă că și punctele $ A $ și $ B $
au coordonatele care respectă ecuația dreptei căutate. Altfel spus, $ y_A = a \cdot x_A + b $
(unde $ x_A = -1 $ și $ y_A = -2 $) și similar pentru punctul $ B $.

Rezultă două ecuații cu două necunoscute:

- Pentru punctul $ A $: $ 2 = -1 \cdot a + b $;
- Pentru punctul $ B $: $-1 = 3 \cdot a + b $.

Rezolvăm sistemul și obținem $ a = -\dfrac{3}{4} $ și $ b = \dfrac{5}{4} $,
deci dreapta căutată este $ y = -\dfrac{3}{4} x + \dfrac{5}{4} $.

Cu această metodă poți să calculezi ecuația oricărei drepte prin două puncte,
fără să folosești formule complicate, ci doar definițiile: cum se scrie în general
ecuația dreptei și ce înseamnă că un punct cu coordonate cunoscute se află pe o dreaptă.

## Lungimea unui segment de dreaptă

Dacă te interesează mai degrabă segmentul de dreaptă dintre două puncte, nu dreapta întreagă,
și vrei să afli lungimea acestui segment, ai o metodă simplă, pentru care trebuie să-ți
amintești doar teorema lui Pitagora.

Dar înainte să poți calcula pentru un segment oarecare, ajută să începem cu două cazuri
mai simple: când segmentele sunt orizontale sau verticale.

De exemplu, un segment vertical este descris de puncte care au aceeași coordonată $ x $,
pentru că se află la aceeași „lățime” (măsurată pe axa orizontală), dar la „înălțimi”
diferite (măsurate pe axa verticală). Deci punctele arată de forma $ A(x_A, y_A) $ și
$ B(x_A, y_B) $. Lungimea segmentului $ [AB] $ este, atunci, diferența celor două
coordonate verticale și, pentru că nu știm care dintre ele este mai mare, vom folosi
modulul. Deci $ AB = | y_A - y_B | $.

Ca să fie și mai clar, te poți gândi că punctele se află direct pe axa *Oy*, deci $ x_A = 0 $.
Așadar, segmentul $ [AB] $ devine o porțiune din axa *Oy*, de lungime $ | y_A - y_B | $.

Similar, pentru segmente orizontale, determinate de puncte care au aceeași coordonată $ y $,
fiindcă se află la aceeași „înălțime”: $ A(x_A, y_A) $ și $ B(x_B, y_A) $. Lungimea
este $ AB = | x_A - x_B | $. Din nou poți particulariza pentru $ y_A = 0 $, caz în care
segmentul $ [AB] $ devine o porțiune din axa *Ox*.

Acum, pentru cazul general, când segmentul este oblic. Îți explic pe un exemplu, aceleași
două puncte pe care le-am mai folosit: $ A(-1, 2) $ și $ B(3, -1) $. Vrei lungimea segmentului
$ [AB] $ sau distanța dintre cele două puncte. Este suficient să le reprezinți într-un sistem
de coordonate și să construiești un triunghi dreptunghic în care $ [AB] $ este ipotenuză.
Vezi figura de mai jos.

<figure id="fig-segment-oblic">
<img src="/images/figures/fig9.svg" alt="Un segment oblic" style="width:95%;">
<figcaption>Distanța dintre două puncte oarecare, calculată cu teorema lui Pitagora</figcaption>
</figure>

Am format triunghiul dreptunghic $ \Delta ABC $, în care ipotenuza este $ AB $, iar catetele
sunt una orizontală și una verticală. Deci știm să le calculăm lungimile, pe baza cazurilor
particulare discutate puțin mai sus. Să mai adaug că știm și coordonatele lui $ C $, din
modul în care a fost obținut: $ C(-1, -1) $, fiindcă se află pe aceeași verticală cu $ A $
și pe aceeași orizontală cu $ B $. Apoi:

$$
\begin{matrix}
AC = |y_A - y_C| = | 2 - (-1) | = 3 \\
BC = |x_B - x_C| = | 3 - (-1) | = 4
\end{matrix}
$$

Cu teorema lui Pitagora, rezultă $ AB = \sqrt{3^2 + 4^2} = 5 $.

Poți reface oricând această metodă, fără să ții minte vreo formulă suplimentară.
Dacă vrei, totuși, să aplici o formulă directă, poți reduce calculele de mai sus la:

$$
AB = \sqrt{ (x_A - x_B)^2 + (y_A - y_B)^2 },
$$

unde nu am mai pus modulul, pentru că, prin ridicare la pătrat, semnul oricum devine irelevant.

## Supliment: Calcule și figuri geometrice

Legătura dintre algebră și geometrie ajută foarte mult ca să vezi același obiect din mai multe
unghiuri. În istoria matematicii, această legătură a venit foarte târziu. Geometria, cu originile
în Grecia antică — ne gândim la Pitagora, Euclid, Arhimede, Thales și alții —, a fost tratată
drept disciplină diferită de algebră până tocmai în secolul al XVII-lea. De fapt, geometria
nici măcar nu se prea ocupa cu măsurători și calcule. Sunt celebre problemele lui Euclid și ale
contemporanilor care se rezolvau prin construcții cu rigla (negradată!) și compasul.
Lungimea unui segment era irelevantă: îl luai în deschizătura compasului și-l mutai sau îl
comparai cu un altul, de exemplu.

Însă, pe parcurs ce s-au dezvoltat algebra și metodele de calcul cu funcții, matematicienii
au încercat să le combine cu componentele vizuale din geometrie. Dar ce legătură are un punct
sau o dreaptă cu un număr sau o funcție? Astăzi, răspunsul vine în anii de gimnaziu, însă
a necesitat creativitatea francezilor René Descartes (1596-1650) și François Viète
(1540-1603), portretizați mai jos, care au clarificat aceste legături.

<figure id="fig-descartes-viete">
<img src="/images/figures/descartes_viete.png" alt="René Descartes și François Viète"
style="width:95%;">
<figcaption>René Descartes (s) și François Viète (d), matematicieni francezi ai secolelor XVI-XVII</figcaption>
</figure>

Descartes este cel care a propus interpretarea punctelor prin coordonatele lor. El a asociat
o pereche de numere reale fiecărui punct din plan, numere care aveau o semnificație pe
cât de simplă, pe atât de ingenioasă. A fost nevoie să fixeze un sistem de referință,
cum l-au numit fizicienii, sau *sistem de coordonate*, în termeni matematici: reperul *xOy*.
Cele două axe sunt drepte, cu sensurile pozitive alese spre dreapta, respectiv în sus, și
o unitate de măsură fixată, astfel încât distanțele să poată fi exprimate prin numere reale.
Când un punct se află pe una dintre axe, coordonatele lui sunt simple: una este zero și cealaltă
arată de câte ori se cuprinde unitatea în distanța dintre punct și origine. Dar pentru puncte
care nu se află pe axe? Atunci Descartes a propus *proiecții* ale punctelor, astfel încât
să se poată vedea „urmele” pe care le lasă punctele față de axele de coordonate.


Astfel, un punct din plan $ A(x_A, y_A) $ îl poți
gândi ca pe o pereche de instrucțiuni: pornești din originea sistemului de coordonate
(fixată), mergi $ x_A $ unități pe axa orizontală (la dreapta dacă $ x_A > 0 $
și la stânga dacă $ x_A < 0 $), apoi $ y_A $ unități pe axa verticală
(în sus dacă $ y_A > 0 $ și în jos dacă $ y_A < 0 $). Astfel, ai pornit
dintr-un punct fixat și ai ajuns în orice punct căruia îi știi coordonatele.
Pașii poți să-i vezi în figura de mai jos.

<figure id="fig-pasi-reprezentare">
<img src="/images/figures/fig10.svg" alt="Pașii pentru reprezentarea grafică a unui punct"
style="width:75%;">
<figcaption>Interpretarea coordonatelor unui punct din plan ca pe doi pași prin care
pornești din origine și ajungi la punctul respectiv</figcaption>
</figure>

În ce privește numerele negative, ele sunt ușor de înțeles dacă ții cont
de faptul că direcția este o convenție. De fapt, acest lucru este adevărat
și în fizică și aproape oriunde apar numere negative: cercetătorii au stabilit
un punct de referință pe care îl consideră zero, precum și direcția pozitivă.

De exemplu, temperaturile mai mici decât pragul de îngheț sunt negative,
sumele cheltuite dintr-un buget inexistent sunt datorii și se înregistrează
cu numere negative, iar în reperul $ xOy $, numerele aflate la stânga sau
în josul originii sunt negative. Însă distanțele sunt calculate, desigur,
prin numere pozitive, care sunt modulele celor negative. Situația e chiar
convenabilă, pentru că, atunci când te gândești la punctul $ B(-1, 3) $,
de exemplu, știi sigur că poți ajunge la el dacă pornești pe axa
orizontală către stânga o unitate, apoi 3 unități în sus. Cu alte cuvinte,
numerele negative vin cu informație suplimentară, cea legată de direcție.

Încă un fapt deosebit este că, în perioada medievală, limba latină era foarte folosită,
mai ales în Europa, astfel că mulți cercetători o foloseau în tratatele și publicațiile lor,
ba chiar își luau și un nume latinesc. De aceea, Viète mai este cunoscut și ca
*Franciscus Vieta*, iar Descartes, drept *Renatus Cartesius*. Atât de
importantă a fost introducerea interpretării algebrice pentru drepte și, în general,
figuri plane încât sistemul de coordonate *xOy* se mai numește *cartezian*
în onoarea lui Descartes.


---

## Exerciții
