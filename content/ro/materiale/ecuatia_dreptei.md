+++
title = "Ecuația dreptei"
type = "docs"
slug = "ecuatia-dreptei"
+++

# Ecuația dreptei

{{< material-author >}}
Adrian Manea, `adrianmanea@poligon-edu.ro`
{{< /material-author >}}

<span
style="font-family:'Switzer', 'Arial', 'San Francisco', sans-serif;weight: 600;color: var(--teal);font-size:1.1rem;letter-spacing:0.01rem;">
<b><a href="/documents/ecuatia_dreptei.pdf">Descarcă versiunea PDF</a></b>
</span>

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
<img src="/images/figures/fig1.svg" alt="Dreapta de ecuație y = x + 3" style="width:95%;">
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
<img src="/images/figures/fig2.svg" alt="Dreapta de ecuație y = x + 3 și intersecțiile cu axele" style="width:95%;">
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
style="width:95%;">
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
style="width:95%;">
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

## Panta dreptei

Înclinarea unei drepte poate fi măsurată precis. În afară de faptul că este
descrisă de o anumită valoare a lui $ a $ în ecuația dreptei, care este o interpretare
algebrică, există și o metodă geometrică de a o găsi.

Să ne uităm, pentru început, la un caz foarte simplu: cel când $ a = 1 $ și $ b = 0 $,
adică dreapta este $ y = x $, care se mai numește și *prima bisectoare* (dacă nu e clar
de ce, te vei lămuri imediat). Iată desenul.

<figure id="fig-prima-bisectoare">
<img src="/images/figures/fig5.svg" alt="Prima bisectoare" style="width:95%;">
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
style="width:95%;">
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
style="width:95%;">
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

Îți propun în continuare câteva exerciții, unele dintre ele standard, adaptate
din manuale și culegeri, dar și câteva mai deosebite. Las aici doar cerințele
și te încurajez să încerci mai întâi să le rezolvi singur, iar în paginile următoare
îți arăt și rezolvările detaliate. Îți recomand, de asemenea, să folosești
reprezentarea grafică ori de câte ori este nevoie --- poate chiar la fiecare exercițiu.

Mai adaug că, de obicei, în manuale și culegeri pe care le folosești la clasă,
multe calcule se termină cu rezultate numere întregi sau fracții simple ca $ \dfrac{1}{2} $
sau $ -\dfrac{3}{2} $. Poți aproape să fii sigur, dacă obții un rezultat ca $ \dfrac{15}{7} $,
trebuie să fi greșit pe undeva. Însă în exercițiile pe care ți le-am propus, nu toate
calculele dau rezultate „frumoase”. Decizia a fost intenționată, pentru
că e util să te obișnuiești cu metoda, să ai încredere în teoria și procedurile pe
care le folosești, fără această verificare specială, *„dacă nu e număr întreg, am greșit”*.
În plus, în multe situații reale, vei avea un calculator de buzunar la îndemână, astfel
că, atunci când ești sigur pe metodă, calculele, oricât de urâte, le poți face pe un calculator
și nu e nicio problemă.

1. Calculează ecuația și lungimea medianei din $ A $ a triunghiului $ \Delta ABC $,
cu vârfurile în punctele $ A(-2, -1) $, $ B(2, 0) $, $ C(0, 6) $.

2. Calculează ecuația dreptei care conține punctul $ A(6, 0) $ și este
perpendiculară pe dreapta de ecuație $ 2x - 3y + 1 = 0 $.

3. Găsește ecuația dreptei care se obține prin simetria dreptei
de ecuație $ d: 2x - 3y + 1 = 0 $ față de punctul $ A(6, 0) $.

4. Calculează ecuația dreptei care conține punctul $ A(-2, 2) $ și este
paralelă cu dreapta $ CD $, determinată de $ C(2, 1) $ și $ D(-1, -3) $.

5. Calculează ecuația și lungimea înălțimii din $ A $ în triunghiul $ ABC $,
cu vârfurile în punctele $ A(-1, 7) $, $ B(-7, 0) $, $ C(5, -3) $.

6. Verifică dacă punctele $ A(3, -5), B(-2, 6) $ și $ C(8, -16) $ sunt coliniare.

7. Verifică dacă dreptele următoare sunt concurente:

$$
\begin{matrix}
d_1:& 2x - y - 1 = 0 \\
d_2:& 3x + 2y - 5 = 0 \\
d_3:& x + 3y - 4 = 0
\end{matrix}
$$

8. Două orașe se află pe o hartă la coordonatele $ A(-3, -2) $ și $ B(2, 2) $.
Administrația regională vrea să construiască un centru comercial în afara orașelor,
dar astfel încât locuitorii ambelor orașe $ A $ și $ B $ să ajungă la fel de repede,
iar distanțele de la centrul comercial $ C $ și orașele $ A $ și $ B $ să nu depășească
10 unități (să spunem, kilometri). Dă un exemplu de plasare a punctului $ C $ care să verifice condițiile.

9. Pe harta unui joc ai 3 clădiri, pentru care știi coordonatele:
$ A(1, 1), B(-3, 1), C(2, -4) $.
Ele se aprovizionează de la același rezervor $ R(x_R, y_R) $.
Unde trebuie plasat rezervorul (găsește coordonatele sale) astfel încât jucătorii
din cele 3 clădiri să poată interveni la fel de rapid pentru
reparații ale rezervorului, indiferent din ce clădire ar pleca?

---

## Rezolvări ale exercițiilor

<span style="color:var(--burgundy); font-size:1.3rem;">
1. Ecuația și lungimea medianei din $ A $ în $ \Delta ABC $, cu vârfurile în
$ A(-2, -1) $, $ B(2, 0) $ și $ C(0, 6) $.
</span>

Îți propun să lăsăm reprezentarea grafică pentru la final, ca de verificare.
Poți să rezolvi problema și doar prin calcule.

Mediana unește un vârf cu mijlocul laturii opuse, deci să notăm $ M(x_M, y_M) $ punctul
de mijloc al laturii $ BC $. Dintr-o formulă de calcul simplă (pe care te invit să ți-o
justifici), coordonatele mijlocului unui segment se calculează ca media aritmetică
a coordonatelor capetelor. Adică:

$$
x_M = \frac{x_B + x_C}{2} = 1 \quad \text{și} \quad %
y_M = \frac{y_B + y_C}{2} = 3.
$$

Deci mijlocul lui $ BC $ este $ M(1, 3) $. Acum problema are două părți: lungimea
segmentului $ [AM] $ și ecuația dreptei $ AM $.

Pentru lungimea segmentului, poți să folosești formula de calcul care provine din
teorema lui Pitagora, adică:

$$
AM = \sqrt{(x_A - x_M)^2 + (y_A - y_M)^2} = \sqrt{9 + 16} = \sqrt{25} = 5.
$$

Iar pentru ecuația dreptei, să o notăm cu $ y = ax + b $. Coeficienții $ a $ și $ b $
îi afli din condiția ca punctele $ A $ și $ M $ să aibă coordonate care verifică
ecuația dreptei. Adică:

$$
\begin{matrix}
A \in AM \Rightarrow y_A = a \cdot x_A + b \Rightarrow -1 = -2a + b \\
M \in AM \Rightarrow y_M = a \cdot x_M + b \Rightarrow 3 = a + b
\end{matrix}
$$

Poți scădea cele două relații și obții $ -3a = -4 $, de unde $ a = \dfrac{4}{3} $, iar apoi,
$ b = 3 - a = \dfrac{5}{3} $. În final:

$$
AM: y = \dfrac{4}{3} x + \dfrac{5}{3}.
$$

Așadar, este o dreaptă care are panta $ \dfrac{4}{3} $, deci un pic mai mare decât $ 1 $
și ordonata la origine $ \dfrac{5}{3} $, adică ceva mai mică decât 2. Astfel de estimări
sunt utile în partea de vizualizare.

Acum putem face și desenul, să ne asigurăm că am lucrat corect:

- Desenăm cele trei puncte care dau triunghiul $ \Delta ABC $ și le unim, ca să obținem laturile;
- Plasăm punctul $ M(1, 3) $ și observăm dacă este mijlocul laturii $ BC $;
- Desenăm dreapta de ecuație $ y = \dfrac{4}{3} x + \dfrac{5}{3} $ prin două puncte oarecare
și verificăm (vizual) dacă trece prin $ A $ și $ M $. Cel mai simplu ar fi să folosim
punctele de intersecție cu axele: $ \left( 0, \dfrac{5}{3} \right) $ și
$ \left( -\dfrac{5}{4}, 0 \right) $.

Reprezentarea e în figura de mai jos și confirmă calculele.

<figure id="fig-ex1">
<img src="/images/figures/fig11.svg" style="width:95%" alt="Rezolvarea exercițiului 1">
<figcaption>Reprezentarea grafică pentru soluția exercițiului 1</figcaption>
</figure>

---


<span style="color:var(--burgundy); font-size:1.3rem;">
2. Ecuația dreptei prin $ A(6, 0) $ perpendiculară pe $ d: 2x - 3y + 1 = 0 $.
</span>

Mai întâi, observă că ecuația dreptei $ d $ este dată într-o formă ușor diferită de cum
am lucrat până acum. Dar nu e nicio problemă: o prelucrezi prin separarea lui $ y $ și obții:

$$
2x - 3y + 1 = 0 \Rightarrow 3y = 2x + 1 \Rightarrow y = \dfrac{2}{3} x + \dfrac{1}{3}
$$

Deci e vorba de o dreaptă cu panta $ \dfrac{2}{3} $ și ordonata la origine $ \dfrac{1}{3} $,
adusă acum în forma cu care ne-am obișnuit.

Dreapta pe care o căutăm are și ea o ecuație de aceeași formă, să zicem $ y = ax + b $.

Din proprietățile pe care le-am discutat, produsul pantelor a două drepte perpendiculare
este $ -1 $, deci:

$$
a \cdot \dfrac{2}{3} = -1 \Rightarrow a = -\dfrac{3}{2}.
$$

Avem, deocamdată, $ y = -\dfrac{3}{2} x + b $ pentru ecuația dreptei căutate.

Mai rămâne să folosim și punctul $ A $ de pe dreaptă: coordonatele sale verifică ecuația
dreptei, când $ x = 6 $, $ y $ trebuie să fie $ 0 $, adică:

$$
0 = -\dfrac{3}{2} \cdot 6 + b \Rightarrow b = 9.
$$

În final, $ y = -\dfrac{3}{2} x + 9 $ este ecuația dreptei căutate.

Din nou, ajută să facem o reprezentare grafică, să avem măcar o verificare vizuală.
O găsești în figura de mai jos.

<figure id="fig-ex2">
<img src="/images/figures/fig12.svg" alt="Reprezentarea pentru exercițiul 2"
style="width:95%">
<figcaption>Reprezentarea grafică pentru soluția exercițiului 2</figcaption>
</figure>

Dreapta dată are panta $ \dfrac{2}{3} $, deci urcă spre dreapta, dar nu foarte abrupt.
Iar dreapta calculată are panta $ -\dfrac{3}{2} $, deci urcă spre stânga, ceva mai abrupt
decât cealaltă.

Ambele drepte le vom desena prin două puncte ajutătoare, care să fie chiar intersecțiile cu axele.
Pentru prima dreaptă, avem $ \left(0, \dfrac{1}{3} \right) $ și $ \left(-\dfrac{1}{2}, 0 \right) $,
iar pentru cealaltă, punctele $ (0, 9) $ și $ (6, 0) $.


<br />
<span style="font-family:'Switzer', 'Arial', 'San Francisco', sans-serif;font-weight:800;font-size: 1.3rem;">
Supliment
</span>

Cele două drepte par perpendiculare pe figură și le poți reprezenta cu atenție, cu
instrumente geometrice. Dar putem și să ne asigurăm, prin calcule. Alegem unul dintre cele
două triunghiuri formate la intersecția lor și verificăm prin reciproca teoremei lui Pitagora.

Mai întâi, punctul de intersecție. O să-l notăm cu $ P(x_P, y_P) $.
Îi vom calcula coordonatele, ținând cont că se găsește pe ambele drepte,
deci $ x_P $ și $ y_P $ satisfac ambele ecuații:

$$
\begin{matrix}
y_P &= \dfrac{2}{3} x_P + \dfrac{1}{3} \\
y_P &= -\dfrac{3}{2} x_P + 9
\end{matrix}
$$

Scazi cele două relații și obții:
$$
x_P \left( \dfrac{2}{3} + \dfrac{3}{2} \right) + \dfrac{1}{3} - 9 = 0 %
\Rightarrow x_P \cdot \dfrac{13}{6} - \dfrac{26}{3} = 0 \Rightarrow x_P = \dfrac{26}{3} \cdot \dfrac{6}{13} = 4.
$$

Apoi înlocuiești în oricare dintre ecuații și obții:
$$
y_P = \dfrac{2}{3} \cdot 4 + \dfrac{1}{3} = 3.
$$

Acum să încercăm teorema lui Pitagora în triunghiul $ \Delta PQR $, unde $ P(4, 3) $
este punctul calculat, $ Q(0, 9) $ este punctul de intersecție a dreptei calculate
cu axa $ Oy $, iar $ R\left(0, \dfrac{1}{3} \right) $ este punctul de intersecție
a dreptei date cu axa $ Oy $.

Lungimile laturilor le putem calcula direct la pătrat, fiindcă oricum le vom folosi
în teorema lui Pitagora.

$$
\begin{matrix}
    PQ^2 =& 4^2 + 6^2 = 16 + 36 = 52 = \dfrac{468}{9} \\
    QR^2 =& \left( 9 - \dfrac{1}{3} \right)^2 = \left( \dfrac{26}{3} \right)^2 = \dfrac{676}{9} \\
    RP^2 =& 4^2 + \left( 3 - \dfrac{1}{3} \right)^2 = 16 + \dfrac{64}{9} = \dfrac{208}{9}.
\end{matrix}
$$

Calculele confirmă acum că $ PQ^2 + RP^2 = QR^2 $, deci triunghiul este dreptunghic în $ P $,
adică dreptele sunt perpendiculare.

---

<span style="color:var(--burgundy); font-size:1.3rem;">
3. Simetrica dreptei $ d: 2x - 3y + 1 = 0 $ față de punctul $ A(6, 0) $.
</span>

Simetrica unei drepte față de un punct înseamnă o dreaptă paralelă cu cea
inițială și astfel încât distanța de la punctul fixat la ambele drepte să
fie aceeași.

În manuale găsești formule care-ți dau direct ecuația dreptei simetrice,
însă cred că este mai ajutător să o construim din aproape în aproape,
pe baza interpretării pe care am dat-o și cu cât mai puține formule
suplimentare.

Mai întâi, observă că e aceeași dreaptă cu cea de la exercițiul anterior,
deci putem să o rescriem în forma cu care suntem obișnuiți:
$$
d: y = \dfrac{2}{3} x + \dfrac{1}{3}.
$$

Propun să procedăm așa:
- Găsim ecuația dreptei perpendiculare pe $ d $, care trece prin $ A $.
- Calculăm punctul de intersecție dintre perpendiculara respectivă și $ d $.
- Calculăm distanța de la $ A $ la acest punct.
- Luăm o paralelă la $ d $, pe care o intersectăm cu aceeași perpendiculară
(care va fi perpendiculară comună).
- Punem condiția ca punctul de intersecție dintre această paralelă și
perpendiculara comună să se afle la aceeași distanță față de $ A $ cât
era distanța de la $ A $ la $ d $.

Cum spuneam, sunt mai mulți pași decât rezolvarea printr-o simplă formulă,
dar fiecare etapă folosește doar lucruri pe care le știm deja.

Fie, deci, $ d^\prime \perp d $, cu $ d^\prime: y = a^\prime x + b^\prime $.
Din perpendicularitate, rezultă că $ a^\prime = -\dfrac{3}{2} $.

Apoi, din faptul că $ A \in d^\prime $ rezultă că $ 0 = -\dfrac{3}{2} \cdot 6 + b^\prime $,
de unde $ b^\prime = 9 $.

Deci $ d^\prime: y = -\dfrac{3}{2} x + 9 $ este perpendiculara pe $ d $
care trece prin $ A $ și am rezolvat primul punct din planul propus. (Este, de fapt,
calculul pe care l-am făcut la exercițiul anterior.)

Acum, punctul de intersecție dintre $ d^\prime $ și $ d $ să-l notăm cu $ M(x_M, y_M) $.
El verifică ecuațiile ambelor drepte, deci:
$$
\begin{matrix}
y_M = \dfrac{2}{3} x_M + \dfrac{1}{3} \\
      y_M = -\dfrac{3}{2} x_M + 9
      \end{matrix}
$$

Le scădem și obținem:
$$
0 = x_M \left( \dfrac{2}{3} + \dfrac{3}{2} \right) + \dfrac{1}{3} - 9 \Rightarrow %
x_M = \dfrac{26}{3} \cdot \dfrac{6}{13} = 4.
$$

Apoi, $ y_M = \dfrac{2}{3} \cdot 4 + \dfrac{1}{3} = 3 $, deci $ M(4, 3) $ (din nou, calculul
pe care l-am făcut și mai devreme, pentru punctul $ P $.)

Distanța de la $ A $ la acest $ M $ este:
$$
AM = \sqrt{ (6 - 4)^2 + (0 - 3)^2 } = \sqrt{4 + 9} = \sqrt{13}.
$$

Acum, orice paralelă la dreapta $ d $ are aceeași pantă cu ea. Deci, dacă dreapta $ f $
este paralelă cu dreapta $ d $, atunci $ f: y = \dfrac{2}{3} x + b $, pentru un $ b $
oarecare, care să fie diferit de $ \dfrac{1}{3} $ (altfel, coincide cu dreapta $ d $).

Intersectăm pe $ f $ cu $ d^\prime $ acum, să zicem într-un punct $ B(x_B, y_B) $.
El are proprietățile:
$$
\begin{matrix}
    B \in d^\prime &\Rightarrow y_B = -\dfrac{3}{2} x_B + 9 \\
    B \in f &\Rightarrow y_B = \dfrac{2}{3} x_B + b.
\end{matrix}
$$

Scădem cele două relații ca să dispară $ y_B $ și obținem:
$$
0 = x_B \left( -\dfrac{3}{2} - \dfrac{2}{3} \right) + 9 - b %
\Rightarrow x_B \cdot \dfrac{13}{6} = b - 9 \Rightarrow %
x_B = \dfrac{13(b - 9)}{6}.
$$

Acum calculăm $ y_B $ corespunzător, tot în funcție de $ b $:
$$
    y_B = \dfrac{2}{3} x_B + b = \dfrac{2}{3} \cdot \dfrac{13(b - 9)}{6} - \dfrac{9b}{9} %
    \Rightarrow y_B = \dfrac{4b - 117}{9}.
$$

Mai avem doar să punem condiția ca distanța de la $ A $ la această dreaptă să fie tot $ \sqrt{13} $,
adică lungimea $ AB $ să fie $ \sqrt{13} $. Vom lucra mai simplu cu pătratul acestei lungimi,
care vrem să fie $ 13 $:
$$
    AB^2 = \left( 6 - \dfrac{13(b - 9)}{6} \right)^2 + \left(\dfrac{4b - 117}{9}\right)^2 = 13.
$$

Rezultă o ecuație de gradul al doilea pentru $ b $:
$$
    \left(\dfrac{153 - 13b}{6}\right)^2 + \left(\dfrac{4b - 117}{9} \right)^2 = 13 %
    \Rightarrow b = -\dfrac{25}{3}.
$$

Când înlocuiești pentru punctul $ B $, obții simplu $ B(8, -3) $.

În concluzie, dreapta căutată este $ f : y = \dfrac{2}{3} x - \dfrac{25}{3} $,
care mai poate fi scrisă și sub forma:
$$
    f: 2x - 3y - 25 = 0.
$$

Reprezentarea grafică de mai jos îți arată pașii pe care i-am parcurs.

<figure id="fig-ex-3">
<img src="/images/figures/fig13.svg" alt="Reprezentarea grafică pentru exercițiul 3"
style="width:95%">
<figcaption>Reprezentarea grafică pentru exercițiul 3</figcaption>
</figure>

---

<span style="color:var(--burgundy); font-size:1.3rem;">
4. Ecuația dreptei prin $ A(-2, 2) $, paralelă cu $ CD $, unde $ C(2, 1) $ și $ D(-1, -3) $.
</span>

Pas cu pas: căutăm o dreaptă, deci o expresie de forma $ d: y = ax + b $.
Dreapta conține punctul $ A $, deci $ 2 = -2a + b $.

Apoi, ca să folosim condiția de paralelism, trebuie să găsim ecuația dreptei $ CD $.
Fie ea $ CD: y = mx + n $. Avem, pe rând:

$$
\begin{matrix}
    C \in CD &\Rightarrow 1 = 2m + n \\
    D \in CD &\Rightarrow -3 = -m + n
\end{matrix}
$$

Scădem cele două relații și găsim $ 4 = 3m $, deci $ m = \dfrac{4}{3} $. Apoi
$ n = -3 + m = \dfrac{-5}{3} $.

Deci $ CD: y = \dfrac{4}{3} x - \dfrac{5}{3} $.

Cum $ d \parallel CD $, rezultă că $ a = \dfrac{4}{3} $.
Acum ne întoarcem la relația anterioară:
$$
    2 = -2 \cdot \dfrac{4}{3} + b \Rightarrow b = 2 + \dfrac{8}{3} = \dfrac{14}{3}.
$$
În concluzie, dreapta căutată are ecuația $ y = \dfrac{4}{3} x + \dfrac{14}{3} $.
Într-o formă fără fracții, poți elimina numitorii și obții $ -4x + 3y - 14 = 0 $.

Verificarea prin desen este în figura de mai jos.

<figure id="fig-ex4">
<img src="/images/figures/fig14.svg" alt="Reprezentarea grafică pentru exercițiul 4"
style="width:95%">
<figcaption>Reprezentarea grafică pentru exercițiul 4</figcaption>
</figure>

---

<span style="color:var(--burgundy); font-size:1.3rem;">
5. Ecuația și lungimea înălțimii din $ A $ în $ \Delta ABC $, cu vârfurile în punctele
$ A(-1, -7) $, $ B(-7, 0) $ și $ C(5, -3) $.
</span>

Problema este echivalentă cu a cere distanță de la punctul $ A $
la dreapta $ BC $ și ecuația perpendicularei din $ A $ pe $ BC $.

Mai întâi, găsim ecuația dreptei $ BC $. Fie ea $ BC: y = ax + b $
pentru început. Apoi:
$$
\begin{matrix}
    B \in BC \Rightarrow 0 &= -7a + b \\
    C \in BC \Rightarrow -3 &= 5a + b
\end{matrix}
$$

Scădem relațiile și găsim $ 3 = -12a $, deci $ a = -\dfrac{1}{4} $.
Apoi:
$$
b = -3 - 5a = -3 + \dfrac{5}{4} = \dfrac{7}{4}. %
\Rightarrow BC: y = -\dfrac{1}{4} x - \dfrac{7}{4}
$$

Acum vrem o perpendiculară din vârful $ A $ pe dreapta $ BC $. Să-i notăm ecuația
generic $ d: y = mx + n $. Cum $ d \perp BC $, rezultă
$ m \cdot \dfrac{-1}{4} = -1 $, deci $ m = 4 $.

Apoi, $ A \in d $, deci $ 7 = -4 + n $, de unde $ n = 11 $,
adică $ d: y = 4x + 11 $.

Acum vrem distanța de la punctul $ A $ la dreapta $ BC $. Mai întâi, să aflăm
punctul de intersecție între dreapta-înălțime și latura $ BC $.
Fie acesta $ M(x_M, y_M) $, deci:
$$
\begin{matrix}
    M \in BC &\Rightarrow y_M = -\dfrac{1}{4} x_M - \dfrac{7}{4} \\
    M \in d &\Rightarrow y_M = 4 x_M + 11.
\end{matrix}
$$

Prin scădere rezultă $ x_M \left( -\dfrac{1}{4} - 4 \right) - \dfrac{7}{4} - 11 = 0 $,
adică $ x_M = -3 $. Înlocuim și obținem $ y_M = 4 \cdot (-3) + 11 = -1 $.

În fine, $ M(-3, -1) $ și mai rămâne de calculat doar lungimea $ AM $:
$$
    AM = \sqrt{ (-1 + 3)^2 + (7 + 1)^2 } = \sqrt{4 + 64} = 2 \sqrt{17}.
$$

<br />
<span style="font-family:'Switzer', 'Arial', 'San Francisco', sans-serif;font-weight:800;font-size: 1.3rem;">
Supliment
</span>

În unele manuale găsești o formulă directă care calculează distanța
de la un punct la o dreaptă, deci nu mai e nevoie de găsit punctul $ M $.
Pentru asta, trebuie să rescriem ecuația $ BC $ sub forma:
$$
BC: x + 4y + 7 = 0
$$
și distanță de la $ A $ la $ BC $ este:
$$
\mathrm{dist}(A, BC) = \dfrac{|x_A + 4y_A + 7|}{\sqrt{1^2 + 4^2}} = 2 \sqrt{17}.
$$
Dar am preferat o construcție pas cu pas, care nu folosește formule noi de memorat.

Verificarea prin desen, măcar orientativ, în figura de mai jos.

<figure id="fig-ex5">
<img src="/images/figures/fig15.svg" alt="Reprezentarea grafică pentru exercițiul 5"
style="width:95%">
<figcaption>Reprezentarea grafică pentru exercițiul 5</figcaption>
</figure>

---

<span style="color:var(--burgundy); font-size:1.3rem;">
6. Coliniaritatea punctelor $ A(3, -5), B(-2, 6), C(8, -16) $.
</span>

La nivelul clasei a unsprezecea, există o metodă elegantă și directă
de verificare, cu ajutorul matricelor. Dar, în spiritul de până acum,
o să ne uităm la o soluție care nu folosește nimic nou, ci doar
noțiunile simple legate de ecuația dreptei pe care le-am întâlnit deja.

Planul este să găsim ecuația dreptei determinate de două dintre cele
trei puncte și să vedem dacă și coordonatele celui de-al treilea punct
verifică acea ecuație. Dacă da, punctele sunt coliniare, fiindcă toate
au coordonate care verifică o aceeași ecuație a dreptei.

Să găsim ecuația dreptei $ AB $, de exemplu, pe care o notăm, în general,
$ AB: y = ax + b $. Apoi, pe rând:
$$
\begin{matrix}
    &A \in AB \Rightarrow -5 = 3a + b \\
    &B \in AB \Rightarrow 6 = -2a + b
\end{matrix}
$$
Prin scădere: $ -11 = 5a $, deci $ a = -\dfrac{11}{5} $ și
$ b = 6 + 2a = 6 - \dfrac{22}{5} = \dfrac{8}{5} $.

Deci $ AB: y = -\dfrac{11}{5} x + \dfrac{8}{5} $ sau
$ AB: 11x + 5y - 8 = 0 $.

Mai rămâne doar să vedem dacă și coordonatele lui $ C $ verifică această
ecuație:
$$
11 \cdot 8 + 5 \cdot (-16) - 8 = 88 - 80 - 8 = 0,
$$
ceea ce este adevărat, deci punctele sunt coliniare și se află toate pe dreapta $ AB $.

Le poți vedea în figura de mai jos.

<figure id="fig-ex6">
<img src="/images/figures/fig16.svg" alt="Reprezentarea grafică pentru exercițiul 6"
style="width:95%">
<figcaption>Reprezentarea grafică pentru exercițiul 6</figcaption>
</figure>

---

<span style="color:var(--burgundy); font-size:1.3rem;">
7. Drepte concurente:
$$
\begin{matrix}
d_1 :& 2x - y = 1 = 0 \\
d_2 :& 3x + 2y - 5 = 0 \\
d_3 :& x + 3y - 4 = 0
\end{matrix}
$$
</span>

Vom găsi punctul de intersecție al primelor două drepte și verificăm
dacă punctul respectiv se găsește și pe dreapta a treia. În clasa a unsprezecea,
problema se poate formula ca un sistem de trei ecuații și două necunoscute.

Să luăm, deci, sistemul alcătuit din primele două ecuații. Putem
să-l rezolvăm prin metoda substituției, adică din prima ecuație scoatem
$ y = 2x - 1 $ și înlocuim în a doua:
$$
    3x + 2( 2x - 1) - 5 = 3x + 4x - 2 - 5 = 7x - 7 = 0 \Rightarrow x = 1.
$$
Apoi $ y = 2 \cdot 1 - 1 = 1 $.

Deci $ d_1 \cap d_2 = \left\{ A(1, 1) \right\} $, adică primele două drepte
se intersectează în punctul $ A(1, 1) $.

Acum rămâne doar să vedem dacă acest punct se găsește și pe a treia dreaptă:
$$
    1 + 3 \cdot 1 - 4 = 0,
$$
care este adevărat, deci într-adevăr, toate cele trei drepte se intersectează în $ A(1, 1) $.

Reprezentarea o găsești în figura de mai jos.

<figure id="fig-ex7">
<img src="/images/figures/fig17.svg" alt="Reprezentarea grafică pentru exercițiul 7"
style="width:95%">
<figcaption>Reprezentarea grafică pentru exercițiul 7</figcaption>
</figure>

---

<span style="color:var(--burgundy); font-size:1.3rem;">
8. Coordonatele unui punct $ C $, egal depărtat de $ A(-3, -2) $ și $ B(2, 2) $
și astfel încât $ AC < 10 $, $ BC < 10 $.
</span>

O metodă simplă de a plasa un punct egal depărtat de două puncte fixate
$ A $ și $ B $ este să fie pe mediatoarea segmentului $ AB $.
Asta pentru că se formează un triunghi isoscel $ \Delta ABC $, cu $ AC = BC $,
fiindcă din vârful $ C $ ai dus o mediană, care este și înălțime (mediatoarea).

Deci avem de aflat ecuația perpendicularei pe mijlocul segmentului $ AB $
mai întâi.

Dacă $ M(x_M, y_M) $ este mijlocul acestui segment, atunci:
$$
    x_M = \dfrac{-3 + 2}{2} = -\dfrac{1}{2}, \quad %
    y_M = \dfrac{-2 + 2}{2} = 0 \Rightarrow M\left( -\dfrac{1}{2}, 0 \right).
$$

Vrem o perpendiculară pe $ AB $ care să treacă prin $ M $. Mai întâi,
ecuația dreptei, notată generic $ AB: y = ax + b $:
$$
\begin{matrix}
    &A \in AB \Rightarrow -2 = -3a + b \\
    &B \in AB \Rightarrow 2 = 2a + b
\end{matrix}
$$

Rezultă $ -4 = -5a $, deci $ a = \dfrac{4}{5} $ și $ b = 2 - 2a = \dfrac{2}{5} $.
Deci $ AB: y = \dfrac{4}{5} x + \dfrac{2}{5} $.

Acum fie perpendiculara căutată $ d: y = mx + n $. Știm că
$ m \cdot \dfrac{4}{5} = -1 $, deci $ m = -\dfrac{5}{4} $.

Cum $ M \in d $, rezultă $ 0 = -\dfrac{1}{2} \cdot \left( -\dfrac{5}{4} \right) + n $,
deci $ n = -\dfrac{5}{8} $.

Așadar, mediatoarea segmentului $ AB $ are ecuația:
$$
    d: y = -\dfrac{5}{4} x - \dfrac{5}{8} \Leftrightarrow 10x + 8y + 5 = 0.
$$

Orice punct $ C $ care se găsește pe această dreaptă are coordonatele
care verifică ecuația de mai sus și este automat egal depărtat de $ A $ și $ B $.
Mai rămâne doar să alegem unul astfel încât distanța să nu depășească 10 kilometri.

Fie, deci, $ C(x_C, y_C) \in d $, adică $ 10x_C + 8y_C + 5 = 0 $.

Distanța $ AB $ de exemplu este:
$$
    AB = \sqrt{(-3 - x_C)^2 + (-2 - y_C)^2}
$$
și $ AB < 10 $ este echivalent cu $ AB^2 < 100 $

Ca să lucrăm cât mai simplu și pentru că avem nevoie de un exemplu, încercăm
să luăm $ x_C = 0 $. Atunci $ y_C = -\dfrac{5}{8} $, iar ca distanță:
$$
    AB^2 = (-3 - 0)^2 + \left( -2 + \dfrac{5}{8} \right)^2 = 9 + \dfrac{121}{64} = \dfrac{697}{64} < 100,
$$
deci este o alegere bună. Rămâne $ C \left( 0, \dfrac{-5}{8} \right) $.

Iată și reprezentarea grafică, în figura de mai jos.

<figure id="fig-ex8">
<img src="/images/figures/fig18.svg" alt="Reprezentarea grafică pentru exercițiul 8"
style="width:95%">
<figcaption>Reprezentarea grafică pentru exercițiul 8</figcaption>
</figure>

> Suplimentar, te poți gândi la o metodă prin care să găsești cea mai îndepărtată
> poziție a punctului $ C $, dar tot astfel încât distanța să nu depășească 10 kilometri?

---

<span style="color:var(--burgundy); font-size:1.3rem;">
9. De plasat punctul $ R(x_R, y_R) $ egal depărtat de punctele $ A(1, 1) $, $ B(-3, 1) $
și $ C(2, -4) $.
</span>


Inspirat și din problema anterioară, e clar că $ R $ ar trebui să se afle
pe mediatoarele tuturor segmentelor $ AB, AC $ și $ BC $. Altfel spus,
să fie intersecția mediatoarelor acestora. Echivalent, $ R $ este centrul
cercului circumscris triunghiului $ \Delta ABC $ și atunci, distanțele
$ RA, RB, RC $ devin raze ale acestui cerc.

Există formule care-ți dau direct ecuația cercului prin trei puncte,
dar noi vom proceda pas cu pas, ca mai devreme, pe baza mediatoarelor.

Mai întâi, mijlocul $ M $ al lui $ AB $ este $ M(-1, 1) $, mijlocul $ N $
al lui $ AC $ este $ N \left( \dfrac{3}{2}, -\dfrac{3}{2} \right) $,
iar mijlocul $ P $ al lui $ BC $ este $ P \left( -\dfrac{1}{2}, -\dfrac{3}{2} \right) $.

Cele trei mediatoare sigur sunt concurente, deci este suficient
să determinăm două dintre ecuații și punctul lor comun, fiindcă
acel punct se va găsi și pe cea de-a treia.

Fie, deci, $ m_{BC} : y = ax + b $ mediatoarea pe $ BC $.

Mai întâi, însă, ecuația $ BC: y = mx + n $:
$$
\begin{matrix}
    &B \in BC \Rightarrow 1 = -3m + n \\
    &C \in BC \Rightarrow -4 = 2m + n,
\end{matrix}
$$
de unde $ -5m = 5 $, adică $ m = -1 $ și apoi $ n = -4 - 2m = -2 $.
Deci $ BC: y = -x - 2 $.

Din $ m_{BC} \perp BC $, rezultă $ a = 1 $
și din $ P \in m_{BC} $ obținem $ -\dfrac{3}{2} = -\dfrac{1}{2} + b $, adică $ b = -1 $.
În fine, $ m_{BC}: y = x - 1 $.

Mai departe, $ m_{AC} $ mediatoarea pe $ AC $. Mai întâi,
$ AC: y = ax + b $:
$$
\begin{matrix}
    &A \in AC \Rightarrow 1 = a + b \\
    &C \in AC \Rightarrow -4 = 2a + b,
\end{matrix}
$$
de unde $ -a = 5 $, adică $ a = -5 $ și $ b = 1 - a = 6 $.
Rezultă $ AC: y = -5x + 6 $ și, dacă $ m_{AC}: y = mx + n $,
rezultă $ m = \dfrac{1}{5} $. În fine:
$$
    N \in m_{AC} \Rightarrow -\dfrac{3}{2} = \dfrac{1}{5} \cdot {3}{2} + n \Rightarrow %
    n = -\dfrac{3}{2} - \dfrac{3}{10} = -\dfrac{9}{5}.
$$
adică $ m_{AC}: y = \dfrac{1}{5} x - \dfrac{9}{5} $.

Avem cele două mediatoare, acum să le găsim punctul de intersecție:
$$
\begin{matrix}
    y &= \dfrac{1}{5} x - \dfrac{9}{5} \\
    y &= x - 1,
\end{matrix}
$$
de unde $ 0 = \left( \dfrac{1}{5} - 1 \right)x - \dfrac{9}{5} + 1 \Rightarrow x = -1 $
și $ y = x - 1 = -2 $.
Deci $ R (-1, -2) $.

Putem verifica, pentru siguranță, că acest punct se găsește și pe mediatoarea
$ m_{AB} $. Echivalent, verificăm dacă sunt egale distanțele $ AR = BR = CR $
și ar fi mai simplu așa:
$$
\begin{matrix}
    AR &= \sqrt{ 2^2  + 3^2 } = \sqrt{13} \\
    BR &= \sqrt{ (-2)^2 + 3^2 } = \sqrt{13} \\
    CR &= \sqrt{ (3^2 + (-3)^2 } = \sqrt{13}.
\end{matrix}
$$

Reprezentarea, cu ajutorul celor două mediatoare, o găsești în figura de mai jos.

<figure id="fig-ex9">
<img src="/images/figures/fig19.svg" alt="Reprezentarea grafică pentru exercițiul 9"
style="width:95%">
<figcaption>Reprezentarea grafică pentru exercițiul 9</figcaption>
</figure>

<span
style="font-family:'Switzer', 'Arial', 'San Francisco', sans-serif;weight: 600;color: var(--teal);font-size:1.1rem;letter-spacing:0.01rem;">
<b><a href="/documents/ecuatia_dreptei.pdf">Descarcă versiunea PDF</a></b>
</span>
