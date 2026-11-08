+++
title = "Combinatorică"
type = "docs"
slug = "combinatorica"
+++

# Probleme de numărare și combinatorică

{{< material-author >}}
Adrian Manea, `adrianmanea@poligon-edu.ro`
{{< /material-author >}}

<span
style="font-family:'Switzer', 'Arial', 'San Francisco', sans-serif;weight: 600;font-size:1.1rem;letter-spacing:0.01rem;">
<b><a href="/documents/combinatorica.pdf">Descarcă versiunea PDF</a></b>
</span>

Ai 10 prieteni la care ții foarte mult și ai câștigat 3 invitații la concertul
de mâine seară. Cum îi alegi pe cei pe care îi vei invita?
Dacă într-adevăr îi prețuiești în mod egal, înseamnă că poți să alegi pe
oricare 3. Așa că listezi posibilitățile și alegi una la întâmplare
sau să folosești `random.org`.
Dar câte opțiuni ai? În câte moduri poți să alegi 3 persoane din 10?
*Cam multe: 120.*

Echipa clasei vrea să-și facă o uniformă de joc și un blazon. Dar nu vreți
să arate ca un steag, așa că folosiți 6 culori în loc de două sau trei.
În ce ordine să le pui pe steag? În câte moduri poți să aranjezi șase culori
pe un (fel de) steag? *Foarte multe: 720.*

Problemele de numărare răspund la întrebarea
*„În câte moduri poți să...?”* Când ai mai multe opțiuni
din care trebuie să alegi sau vrei să listezi toate posibilitățile,
<span style="color:var(--burgundy) !important;">permutările, aranjamentele</span>
și <span style="color:var(--burgundy) !important;">combinările</span> sunt obiectele matematice
de care ai nevoie.

Așa că studiul problemelor de numărare devine important în mai multe situații.
Dacă vrei să rezolvi o problemă prin încercări, de exemplu, ajută să-ți dai seama
cât de multe posibilități există. Tot cu probleme de numărare poți să înțelegi și
jocurile de cărți sau alte jocuri de noroc. Dacă numeri corect, cu ajutorul
permutărilor sau combinărilor, o să-ți dai seama imediat cât de mică este
probabilitatea de câștig.

*Care este probabilitatea ca, într-un joc de tip „păcănele” (slot machines)
cu 3 rotoare, având fiecare câte 7 simboluri, să nimeresc cel puțin două simboluri la fel?*

Răspunsul este $\dfrac{1}{7}$ sau aproximativ $14\%$ și o să-ți arăt ceva mai încolo cum să-l calculezi.

Mai poți să înțelegi și faptul uimitor că *numărul
amestecurilor unui pachet de 52 de cărți este atât de mare, încât aproape sigur dacă
amesteci acum pachetul, ordinea pe care o obții nu a mai fost obținută niciodată în
istoria omenirii.* Motivul care stă la baza acestui adevăr este că operația
<span style="color:var(--burgundy) !important;">factorial</span> crește foarte repede. Tot factorialului
se datorează și numărul foarte mare de posibilități în care poți să inviți
prietenii la concert sau să aranjezi culorile pe blazon.

În afară de astfel de problemele și întrebări cu oarecare substanță practică sau poate
distractivă, problemele de numărare sunt legate și de concepte avansate de care ai nevoie
în școală, începând cu clasa a zecea. Binomul lui Newton, de exemplu, care îți arată
cum calculezi $ (a + b)^n $, pentru orice număr natural $ n $ sau identități combinatorice
pe care le folosești în informatică, în teoria grafurilor, sunt doar două exemple.

Noțiunile de teorie sunt puține și simple, dar modurile în care le poți aplica se diversifică.
De aceea, o să introduc pe scurt conceptele fundamentale, după care îți voi arăta
prin mai multe exemple de exerciții rezolvate cum să le folosești.

Multe din rezultatele numerice pe care le vom obține pot părea
surprinzătoare. De aceea, prinde bine ca uneori să te gândești puțin la așteptările
pe care le ai și să înțelegi ordinele de mărime ale numerelor implicate.
Un număr ca $ 10! $ poate să nu pară foarte mare, dar în realitate,
are o valoare de aproximativ 3,6 milioane.
De aceea, o să te ajut cu indicații intuitive acolo unde este cazul.

---

## Permutări, aranjamente, combinări

Cea mai mare parte din discuția despre probleme de numărare se leagă de o funcție
pe care cu siguranță ai mai folosit-o: <span style="color:var(--burgundy) !important;">factorialul</span>.

{{% important %}}

# Factorialul unui număr natural

Pentru orice număr natural nenul $ n \in \mathbb{N} $, se definește factorialul
său, notat $ n! $, ca fiind produsul tuturor numerelor naturale de la $ 1 $ la $ n $:

$$
    n! = 1 \cdot 2 \cdot 3 \cdot 4 \cdots (n-1) \cdot n.
$$

Prin convenție, se definește și $ 0! = 1 $, rezultat util în combinatorică.

{{% /important %}}

Poți să vezi factorialul ca pe o funcție
(de forma $ f : \mathbb{N} \to \mathbb{N}, f(n) = n! $, pentru $ n \neq 0 $ și $ f(0) = 1 $)
cu valori care cresc foarte repede. Uite câteva exemple:

$$
\begin{align*}
    0! &= 1 & & &5! &= 120 \\
    1! &= 1 & & &6! &= 720 \\
    2! &= 2 & & &7! &= 5040 \\
    3! &= 6 & & &8! &= 40320 \\
    4! &= 24 & & &9! &= 362880
\end{align*}
$$

Cu ajutorul funcției factorial exprimi <span style="color:var(--burgundy) !important;">permutările</span>.
Prin definiție, o permutare de $ n $ elemente înseamnă o rearanjare a celor $ n $
elemente ale unei mulțimi. Este ceea ce în engleză se numește
<span style="color:var(--burgundy) !important;">*shuffle*</span>. Mai riguros:

{{% important %}}

# Permutări

Orice funcție bijectivă definită pe o mulțime cu $ n $ elemente,

$$
    f : \{ 1, 2, 3, \dots, n \} \to \{ 1, 2, 3, \dots, n \},
$$

se numește *permutare de $ n $ elemente*.

Ce se întâmplă este că imaginea funcției creează o rearanjare a celor
$ n $ elemente, care se mai numește și *permutare* a ei.

Numărul tuturor permutărilor de $ n $ elemente (adică al funcțiilor bijective
definite pe mulțimi cu $ n $ elemente) este $ n! $ și se mai notează $ P(n) $.

<span style="color:var(--burgundy) !important;">**Observație:**</span>
Din punctul de vedere al terminologiei, am scris *permutare de $ n $ elemente*,
dar am folosit primele $ n $ numere naturale. Decizia a fost arbitrară și, cumva,
practică. Poți foarte bine să folosești orice mulțime cu $ n $ elemente vrei,
pentru orice $ n $, și definiția rămâne. O funcție bijectivă între două mulțimi
le face să fie, practic, interschimbabile.

{{% /important %}}

Iată un exemplu: $ f : \{ 1, 2, 3 \} \to \{ 1, 2, 3 \} $, definită prin
$ f(1) = 2, f(2) = 1, f(3) = 3 $ creează permutarea $2, 1, 3$,
care a amestecat numerele $1, 2, 3$. În total, există $ P(3) = 3! = 6 $ permutări
de $ 3 $ elemente, deci ai 6 moduri în care poți defini această funcție $ f $. Printre ele se află
și funcția identitate, care nu face nimic: $ f(1) = 1, f(2) = 2, f(3) = 3 $.
Permutarea (funcția) aceasta se mai numește *permutarea identică*.

Numărul total al permutărilor de $ n $ elemente, adică $ P(n) = n! $,
răspunde, deci, la întrebarea
*În câte moduri se pot rearanja $ n $ obiecte?*

Înțelegi acum de ce numărul total de amestecuri ale unui pachet de 52 de
cărți are proporții astronomice și chiar peste: $ 52! $ are ordinul de mărime $ 10^{67} $.

În multe situații practice și exerciții școlare, însă, nu ai pur și simplu
de reordonat niște numere sau obiecte, ci trebuie să extragi din ele câteva
și să le combini pe acelea. De exemplu, răspunsul la întrebarea *În câte
moduri pot să stea 10 elevi pe un rând în sala de spectacole?* este, desigur,
$ 10! $, dar mai des poți să întâlnești întrebări precum *În câte moduri
    pot să aleg un comitet cu 3 reprezentanți ai elevilor dintr-o clasă de 20
de elevi?* Aici, permutările nu te mai ajută, pentru că ai nevoie de o selecție.
Nu vei folosi toate elementele (toți elevii), ci doar câțiva, pe care, eventual,
îi reordonezi.

Pentru astfel de situații există <span style="color:var(--burgundy) !important;">combinările</span> sau
<span style="color:var(--burgundy) !important;">coeficienții binomiali</span>. Este un concept cu o definiție
abstractă, dar pe care o vom putea particulariza imediat.

{{% important %}}

# Combinări (coeficienți binomiali)

Numărul de submulțimi cu $ k $ elemente ale unei mulțimi cu $ n $
elemente (cu $ 0 \leq k \leq n $) se notează $ C_n^k $ și se citește *combinări
de $ n $ luate câte $ k $*.[^1]

Acest coeficient binomial se calculează după formula:

$$
    C_n^k = \dfrac{n!}{k!(n - k)!} = \dfrac{P(n)}{P(k) \cdot P(n - k)}.
$$

{{% /important %}}

În termeni practici, folosești numărul $ C_n^k $ atunci când ai de ales $ k $
obiecte dintr-o mulțime cu $ n $ obiecte *și ordinea nu contează*.
Altfel spus, alegerile în care, printre cele $ k $ obiecte se află obiectele
$ A $ și $ B $ sau obiectele $ B $ și $ A $ sunt, practic, identice.

În exemplul cu comitetul de elevi este clar metoda potrivită. Dacă în comitet
alegi mai întâi pe Ionel și apoi pe Maria ajungi la exact același rezultat ca atunci
când ai fi ales-o mai întâi pe Maria și apoi pe Ionel. Rezultă că numărul
de moduri în care poți face un comitet de $ 3 $ elevi dintr-o clasă de $ 20 $
de elevi este:

$$
    C_{20}^3 = \dfrac{20!}{3! \cdot 17!} = \dfrac{18 \cdot 19 \cdot 20}{2 \cdot 3} = 1140.
$$

Observă că și aici valoarea numerică este, poate, surprinzător de mare. Asta se datorează
faptului că $ 20! $ este un număr foarte mare, dar și faptului că mulțimea celor 20 de elevi
poate fi fragmentată foarte divers în submulțimi de câte 3 elevi.

Tot prin combinări poți să răspunzi și la întrebarea pe care am pus-o la început:
ai $ C_{10}^3 $ moduri în care să alegi cei 3 prieteni invitați la spectacol.
Când calculezi, obții 120.

O altă aplicație imediată a combinărilor este în calculul numărului total de extrageri
posibile la loto 6 din 49. Întrebarea este: *În câte moduri pot alege 6 numere dintr-o mulțime
cu 49?*, iar răspunsul:

$$
    C_{49}^6 = \dfrac{49!}{6! \cdot 43!} = \dfrac{44 \cdot 45 \cdot 46 \cdot 47 \cdot 48 \cdot 49}{720} = 13983816,
$$

adică aproape 14 milioane.

Dar combinările nu te ajută să răspunzi la întrebări precum:

*Câte cuvinte cu $ k $ litere pot forma dintr-un alfabet cu $ n $ litere?*

Motivul este că, de data aceasta, ordinea de alegere contează. Două cuvinte
care au două litere inversate sunt diferite. În română, de exemplu, cuvintele
*mare* și *rame* sunt diferite, chiar dacă ele conțin aceleași litere.
Dacă am fi formulat problema cu *mulțimi de litere*, atunci mulțimea
$ \{ m, a, r, e \} $ și mulțimea $ \{ r, a, m, e \} $ ar fi fost identice și
problema se rezolva cu combinări.

Dacă te uiți cu atenție, însă, poți să deduci în ce fel diferă acest caz.
Când vrei să alegi $ k $ obiecte dintr-o mulțime cu $ n $, fiecare alegere
de câte $ k $ obiecte poate să vină în $ P(k) = k! $ amestecuri. Din punctul
de vedere al combinărilor (adică al coeficienților binomiali), aceste amestecuri
nu contează --- se numără doar o dată. Dar în această nouă problemă, a cuvintelor,
toate aceste amestecuri sunt diferite.

Obținem astfel un nou obiect combinatorial, numit *aranjamente de $ n $ luate câte $ k $*.
Formula de calcul arată ce am discutat: sunt de $ k! $ ori mai multe decât combinările
corespunzătoare, tocmai ca să nu mai ignore permutările celor $ k $ obiecte alese.

{{% important %}}

# Aranjamente

Numărul de șiruri ordonate cu $ k $ simboluri care se pot forma dintr-o mulțime cu $ n $
simboluri se notează $ A_n^k $ și se numește *aranjamente de $ n $ luate câte $ k $*.

Formula de calcul este:

$$
    A_n^k = \dfrac{n!}{(n-k)!} = P(k) \cdot C_n^k.
$$

{{% /important %}}

Am formulat această definiție cât se poate de abstract, dar, de fapt, esența am explicat-o
anterior. Am numit „șiruri ordonate cu simboluri” aceste alegeri, în loc de „cuvinte”,
ca să avem o exprimare mai generală, dar este vorba despre același fenomen.

Așadar, diferența între aranjamente și combinări este în răspunsul la întrebarea:

<span style="color:var(--burgundy) !important;">*Două alegeri care folosesc aceleași obiecte, dar diferă prin ordinea lor sunt
alegeri diferite?*</span>

Dacă răspunsul este afirmativ, lucrezi cu aranjamente. Dacă nu, cu combinări.

Îți arăt în continuare cum poți să folosești permutările, combinările și aranjamentele
în identități și probleme de examen. Ca idee generală, vei vedea că de departe
combinările sunt cele mai utile, dar, într-un fel, în calculul lor ai deja incluse
și permutările și aranjamentele. Și, de fapt, toate se bazează pe factorial.

---

## Binomul lui Newton și identități combinatoriale

În afară de răspunsul la întrebări precum *În câte moduri poți să...?*,
combinările sunt utile și pentru dezvoltări binomiale, formule de calcul
algebric pe care le-ai întâlnit începând cu gimnaziul. Este chiar motivul
pentru care se numesc și *coeficienți binomiali*.

Un binom înseamnă o expresie care folosește două nedeterminate (două monoame,
ca să fim mai preciși, de unde și denumirea de *bi*nom),
adică de forma $ a \pm b $. Știi deja să calculezi $ (a \pm b)^2 $ și
$ (a \pm b)^3 $. Dar de ce să ne oprim aici?

Putem calcula inductiv $ (a \pm b)^n $, dacă o luăm treptat. N-ai decât
să înmulțești binomul $ (a \pm b) $ cu el însuși de $ n $ ori.
Dar poți să ajungi și direct la răspuns cu o formulă, descoperită de Isaac
Newton în 1664-1665, deși cazuri particulare erau cunoscute
din Antichitate.

{{% important %}}

# Binomul lui Newton (Formula de dezvoltare binomială)

$$
    (a + b)^n = C_n^0 a^n b^0 + C_n^1 a^{n-1} b^1 + \dots + C_n^{n-1} ab^{n-1} + C_n^n a^0 b^n.
$$

Cu simbolul de sumare $ \Sigma $, putem scrie:

$$
    (a + b)^n = \displaystyle\sum_{k = 0}^n C_n^k a^{n-k} b^k.
$$


{{% /important %}}

Formula pare complicată, dar o poți vedea la lucru deja în dezvoltările cunoscute.

- Pentru $ n = 1 $, $ (a + b)^1 = 1 \cdot a + 1 \cdot b $, ceea ce corespunde la $ C_1^0 = 1 = C_1^1 $.
- Pentru $ n = 2 $, $ (a + b)^2 = 1 \cdot a^2 + 2 \cdot a^1 b^1 + 1 \cdot b^2 $. Și aici, verifici
    imediat coeficienții binomiali: $ C_2^0 = 1, C_2^1 = 2, C_2^2 = 1 $.
- Pentru $ n = 3 $, $ (a + b)^3 = 1 \cdot a^3 + 3 \cdot a^2 b^1 + 3 \cdot a^1 b^2 + 1 \cdot b^3 $.
    Calcule simple arată, conform așteptărilor, că $ C_3^0 = 1 $, $ C_3^1 = C_3^2 = 3 $ și $ C_3^3 = 1 $.

Și așa mai departe. Dar, în loc să calculezi concret, există o metodă vizuală pentru
coeficienții binomiali și, implicit, pentru dezvoltarea binomului $ (a + b)^n $. Ea se numește
<span style="color:var(--burgundy) !important;">triunghiul lui Pascal</span>, denumit după matematicianul francez
Blaise Pascal, care a trăit în secolul al XVII-lea. Mai multe cercetări istorice au arătat,
însă, că și triunghiul acesta era cunoscut încă din Antichitate și în afara Europei.

O să ți-l arăt, mai întâi, în figura de mai jos, apoi îți explic cum
îl poți alcătui și folosi.

<figure id="fig-pascal">
<img src="/images/figures/pascal_triangle.svg" alt="Triunghiul lui Pascal, primele 8 linii" style="width:70%;">
<figcaption>Triunghiul lui Pascal, primele 8 linii</figcaption>
</figure>

Se vede, mai întâi, că pe laturile triunghiului ai numai cifra $ 1 $.
Apoi, începând cu a treia linie, fiecare număr în afara extremităților (egale cu $ 1 $)
se obține ca sumă a numerelor imediat vecine de deasupra. Pe linia a treia, de exemplu,
$ 2 $-ul din mijloc se obține ca suma vecinilor săi de deasupra, $ 1 + 1 $. Pe linia
a patra, cei doi de $ 3 $ sunt obținuți ca sume ale vecinilor de deasupra, $ 1 + 2 $,
respectiv $ 2 + 1 $, de la stânga la dreapta. Și așa mai departe.

Doar că astfel de observații sunt mai degrabă *proprietăți*. Definiția după care
construiești triunghiul lui Pascal se bazează pe coeficienți binomiali. Mai precis,
pe linia corespunzătoarea unui $ n $ ai toți coeficienții binomiali, de la $ C_n^0 $
până la $ C_n^n $,
cu observația că primul $ n $ permis este $ n = 0 $, unde $ C_0^0 = 1 $, care
corespunde la prima linie unde ai doar un 1 în vârf.
Pe linia a patra, de exemplu, (corespunzătoare la $ n = 3 $), ai $ C_3^0 = 1 $,
$ C_3^1 = 3$ , $ C_3^2 = 3 $ și $ C_3^3 = 1 $.

În consecință, poți să folosești liniile triunghiului lui Pascal ca să scrii dezvoltarea
binomului $ (a + b)^n $: mergi pe linia $ n $ a triunghiului, pornind de la $ n = 0 $,
iar numerele pe care le găsești sunt coeficienții dezvoltării. Mai trebuie doar să ții
minte că acești coeficienți, conform binomului lui Newton, se înmulțesc cu produse
de forma $ a^{n-k} \cdot b^k $, unde puterea lui $ a $ scade de la $ n $ la $ 0 $
și puterea lui $ b $ crește de la $ 0 $ la $ n $.

De exemplu, dacă vrei să scrii direct dezvoltarea $ (a + b)^5 $, mergi pe linia cu $ n = 5 $
(adică a șasea, fiindcă începem cu $ n = 0 $), iei coeficienții ($ 1, 5, 10, 10, 5, 1 $)
și scrii:

$$
    (a + b)^5 = a^5 + 5a^4b + 10a^3b^2 + 10a^2b^3 + 5 ab^4 + b^5.
$$

Pe baza triunghiului lui Pascal, dar și cu alte raționamente care pornesc de la definiția
coeficienților binomiali, poți să demonstrezi câteva identități.

De exemplu, triunghiul lui Pascal are numerele simetrice față de un fel de „mediană”.
Ceea ce duce cu gândul la următoarea identitate generală, care se mai numește și
<span style="color:var(--burgundy) !important;">formula combinărilor complementare</span>:

$$
    C_n^k = C_n^{n-k}.
$$

Îți arăt justificarea acestei identități, pentru că este un exemplu excelent de demonstrație
prin explicație. Evident că poți demonstra direct algebric, cu formulele de calcul:

$$
    \dfrac{n!}{k! \cdot (n - k)!} = \dfrac{n!}{(n - k)! \cdot (n - (n - k))!},
$$

ceea ce este evident. Dar mai memorabil este să te gândești așa:

*Atunci când aleg $ k $ obiecte din $ n $ pe care vreau să le păstrez,
este exact același lucru ca și cum aș alege $ n - k $ obiecte pe care nu le vreau.*

Practic, dacă ai 10 colegi și vrei să inviți la o petrecere doar pe 4 dintre ei,
poți să-i numești fie pe cei 4 invitați, fie pe cei 6 pe care nu îi vrei; este
exact același lucru. În consecință, numărul de alegeri „pozitive”
(colegii pe care îi vrei) este egal cu numărul de alegeri „negative”
(cei pe care nu îi vrei). Ambele numere de alegeri se calculează cu combinările
corespunzătoare: $ C_n^k $ înseamnă să alegi cele $ k $ obiecte păstrate, iar $ C_n^{n-k} $
înseamnă să alegi restul de $ n - k $ obiecte pe care nu le vrei.

O altă identitate pe care o poți observa din triunghiul lui Pascal este aceasta:
dacă faci suma tuturor numerelor de pe o linie (orizontală), obții $ 1, 2, 4, 8, 16 $
și așa mai departe, adică puteri ale lui 2. Mai precis, obții
$ 2^n $, unde $ n $ este numărul liniei (începând cu $ 0 $).

În termeni algebrici, asta se scrie așa:

$$
    C_n^0 + C_n^1 + C_n^2 + \dots + C_n^{n-1} + C_n^n = \displaystyle\sum_{k=0}^n C_n^k = 2^n.
$$

O demonstrație simplă și ingenioasă spune să folosești binomul lui Newton pentru
valorile $ a = b = 1 $.
Atunci orice putere a lui $ a $ sau $ b $ și orice produs între puterile lor vor fi egale cu $ 1 $,
deci din formula binomială rămân doar coeficienții, adică combinările. Rezultă:

$$
    (1 + 1)^n = \displaystyle\sum_{k = 0}^n C_n^k \cdot 1^{n-k} \cdot 1^k = \displaystyle\sum_{k = 0}^n C_n^k = 2^n.
$$

Ajută să înțelegi această identitate și prin interpretarea combinărilor conform definiției.
Am văzut că $ C_n^k $ înseamnă numărul de submulțimi cu $ k $ elemente ale unei mulțimi
cu $ n $ elemente, cu $ 0 \leq k \leq n $. Asta înseamnă că suma tuturor combinărilor
de mai sus îți arată numărul total de submulțimi ale unei mulțimi cu $ n $ elemente,
inclusiv mulțimea vidă (cu $ 0 $ elemente, pentru $ k = 0 $) și mulțimea însăși
(cu $ n $ elemente, pentru $ k = n $). Am obținut un rezultat important,
care merită remarcat separat.

{{% important %}}

# Mulțimea părților unei mulțimi

Dacă $ A $ este o mulțime oarecare, se notează cu $ \mathcal{P}(A) $
mulțimea tuturor submulțimilor sale (inclusiv $ \emptyset $, inclusiv $ A $)
și se numește *mulțimea părților lui $ A $*.

Cum există $ C_n^k $ submulțimi cu $ k $ elemente ale unei mulțimi cu $ n $
elemente, suma combinărilor de mai sus arată că, dacă mulțimea $ A $
are $ n $ elemente, atunci mulțimea $ \mathcal{P}(A) $ are $ 2^n $ elemente.

{{% /important %}}

Dacă vrei un exemplu, ia $ A = \{ 1, 2, 3 \} $. Conform teoriei, există
$ 2^3 = 8 $ submulțimi ale lui $ A $, inclusiv mulțimea vidă
și $ A $ însăși. Iată-le:

$$
\begin{align*}
    &\emptyset & &\{1,2\} \\
    &\{1\} & &\{1,3\} \\
    &\{2\} & &\{2, 3\} \\
    &\{3\} & &\{1, 2, 3\}
\end{align*}
$$

Trucul de particularizare a lui $ a $ și $ b $ în binomul lui Newton
de mai devreme îl poți folosi și pentru o identitate mai subtilă.
Dacă iei $ a = 1 $ și $ b = -1 $, obții:

$$
    (1 - 1)^n = 0 = \displaystyle\sum_{k = 0}^n C_n^k \cdot 1^{n-k} \cdot (-1)^k.
$$

Observă că $ 1^{n-k} $ nu contează în produs, dar $ (-1)^k $ va schimba semnul combinărilor
cu $ k $ impar și numai acelora. Rezultă că suma din membrul drept va conține
combinările cu $ k $ par cu semnul plus și cele cu $ k $ impar cu semnul minus.
Toată suma dă $ 0 $, deci dacă le muți pe cele cu $ k $ impar în membrul stâng,
obții:

$$
    \displaystyle\sum_{k = 1, \ k \text{ impar}}^n C_n^k = \displaystyle\sum_{k = 0, \ k \text{ par}}^n C_n^k.
$$

---

## Probleme de numărare directă și alte exerciții

Calculul coeficienților binomiali pe baza unor exerciții care se referă la dezvoltări
ca în binomul lui Newton sau la numărul de submulțimi înseamnă doar un tip restrâns
de probleme. Sunt multe altele pe care le poți rezolva cu ajutorul lor, după ce
interpretezi enunțul unei probleme de numărare. Alteori, poți pur și simplu să
numeri fără să folosești explicit permutări, aranjamente sau combinări.

Îți arăt aici câteva exemple de exerciții rezolvate, majoritatea preluate sau
adaptate din modelele de bacalaureat. Pe unele le vom rezolva ca aplicații ale
permutărilor, aranjamentelor sau combinărilor, iar pe altele, direct, prin numărare
în urma unui raționament.

O să-ți las mai întâi lista exercițiilor, ca să le încerci, iar apoi îți arăt rezolvările
propuse de mine.

---

## Exerciții propuse

1. Determină numărul funcțiilor $ f : \{ 1, 2, 3, 4 \} \to \{ 1, 2, 3, 4 \} $
    cu proprietatea $ f(1) = f(4) $.
2. Determină numărul funcțiilor pare $ f : A \to A $, unde $ A = \{ -2, -1, 0, 1, 2 \} $.
3. Determină numărul funcțiilor strict crescătoare $ f : A \to B $,
    unde domeniul și codomeniul sunt, respectiv,
    $ A = \{ 1, 2, 3, 4 \} $ și $ B = \{ 1, 2, 3, 4, 5, 6 \} $.
4. Câte funcții $ f: A \to B $ strict descrescătoare și cu
    $ f(3) = 1 $ se pot defini, dacă $ A = \{ 1, 2, 3 \} $ și $ B = \{ 1, 2, 3, 4, 5 \} $?
5. Care este termenul care nu-l conține pe $ x $ în dezvoltarea
    $ \left( \sqrt[3]{x} + \dfrac{2}{\sqrt{x}} \right)^{200}, x > 0 $?
6. Care este probabilitatea ca, alegând o funcție $ f: A \to B $,
    unde $ A = \{ 1, 2, 3 \} $ și $ B = \{ 4, 5, 6 \} $, aceasta să fie injectivă?
7. *Generalizare a problemei anterioare:* Care este probabilitatea
    ca o funcție $ f : A \to B $, cu $ A = \{ a_1, a_2, \dots, a_k \} $ și
    $ B = \{ b_1, b_2, \dots, b_t \} $, să fie injectivă? Dar surjectivă? Dar bijectivă?
8. Câte diagonale are un poligon convex cu $ n $ laturi?

---

## Soluții la exerciții

<span style="color:var(--burgundy); font-size:1.3rem;">

Determină numărul funcțiilor $ f : \{ 1, 2, 3, 4 \} \to \{ 1, 2, 3, 4 \} $
cu proprietatea $ f(1) = f(4) $.

</span>

*Soluție:* O funcție se determină fie prin enumerarea valorilor (adică atunci când
știi explicit cât este $ f(x) $, pentru orice $ x $ din domeniul de definiție), fie prin
una sau mai multe formule generale.

Aici, pentru că domeniul de definiție și codomeniul
sunt mulțimi finite (și chiar mici), cel mai ușor este să știm cât fac $ f(1) $, $ f(2) $,
$ f(3) $ și $ f(4) $. Cu alte cuvinte, a defini o funcție ca în cerință înseamnă
a ști imaginea sa. De aceea, problema se reformulează așa:

*În câte moduri pot să asociez elementele mulțimii $ \{ 1, 2, 3, 4 \} $ cu ele înseși,
dar astfel încât $ 1 $ și $ 4 $ să fie asociate la fel?*

Dacă ai înțeles întrebarea așa, e clar că devine o problemă de numărare. În loc să
ne gândim la permutări, combinări sau aranjamente, putem pur și simplu să numărăm:

- $ f(1) $ poate lua oricare dintre cele 4 valori, nu avem nicio restricție asupra proprietăților
    funcției în afară de $ f(1) = f(4) $. Deci pentru $ f(1) $ avem 4 cazuri.
- $ f(2) $ poate lua tot oricare dintre cele 4 valori, din aceleași motive.
- La fel și $ f(3) $.
- Pentru $ f(4) $ suntem obligați să alegem aceeași valoare ca și pentru $ f(1) $, oricare
    ar fi fost aceea. Deci pentru $ f(4) $ rămâne o singură posibilitate: cea pentru $ f(1) $.

Alegerile celor patru valori sunt *independente* (mai puțin ultima). Asta înseamnă că pentru
fiecare dintre cele 4 alegeri ale lui $ f(1) $ avem toate cele 4 alegeri ale lui $ f(2) $
și toate cele 4 alegeri ale lui $ f(3) $.

În concluzie, numărul total al posibilităților se obține prin înmulțirea numerelor de alegeri:
$ 4 \cdot 4 \cdot 4 \cdot 1 = 4^3 = 64 $.

---

<span style="color:var(--burgundy); font-size:1.3rem;">

Determină numărul funcțiilor pare $ f : A \to A $, unde $ A = \{ -2, -1, 0, 1, 2 \} $.

</span>

*Soluție:* O funcție pară are proprietatea că $ f(-x) = f(x) $, pentru orice $ x $ din domeniul
de definiție. Asta înseamnă că alegerile vor fi limitate: când alegi valoarea lui $ f(x) $, automat
ai ales aceeași valoare și pentru $ f(-x) $.

Pentru problema de față, asta înseamnă că:

- $ f(-2) $ poate fi ales în 5 moduri (oricare dintre elementele mulțimii $ A $), fiindcă
    nu avem vreo restricție.
- $ f(-1) $ la fel.
- $ f(0) $ la fel.
- $ f(1) $ este obligatoriu egal cu $ f(-1) $, deci avem o singură posibilitate.
- La fel și $ f(-2) $, care trebuie să fie egal cu $ f(2) $.

Pentru $ f(-2), f(-1) $ și $ f(0) $, alegerile sunt independente, deci
răspunsul se obține din nou ca produs: $ 5 \cdot 5 \cdot 5 \cdot 1 \cdot 1 = 5^3 = 125 $.

---

<span style="color:var(--burgundy); font-size:1.3rem;">

Determină numărul funcțiilor strict crescătoare $ f : A \to B $,
unde $ A = \{ 1, 2, 3, 4 \} $ și $ B = \{ 1, 2, 3, 4, 5, 6 \} $.

</span>

*Soluție:* Te poți gândi, în primă fază, la definiția funcțiilor strict crescătoare.
Ea spune că, dacă $ x < y $ din domeniul de definiție, atunci $ f(x) < f(y) $ din codomeniu.
Se mai spune că funcțiile strict crescătoare păstrează ordinea, pentru că ordinea numerelor din
domeniu este aceeași cu ordinea imaginilor lor în codomeniu.

Pentru problema de față, deoarece $ 1 < 2 < 3 < 4 $, rezultă că $ f(1) < f(2) < f(3) < f(4) $.
Poți să pornești de aici, dar te mai poți gândi așa: practic, ai de creat un șir crescător
de numere din mulțimea $ B $ (corespunzătoare valorilor $ f(1), f(2), f(3), f(4) $,
în această ordine). Atunci e mai ușor să pornim de aici și reformulăm problema:

*În câte moduri poți crea un șir (strict) crescător de 4 numere din mulțimea $ B $?*

Răspunsul la această întrebare este, de fapt, răspunsul problemei, pentru că, după
ce ai creat șirul respectiv, îl ordonezi și asociezi: cea mai mică valoare este $ f(1) $,
următoarea este $ f(2) $, următoarea, $ f(3) $ și următoarea, $ f(4) $.

Așa că răspunsul este pur și simplu $ C_6^4 $, adică numărul submulțimilor cu 4 elemente
ale unei mulțimi ($B$) cu 6 elemente. Cele 4 elemente alcătuiesc imaginea funcției.

Uite, de exemplu: să zicem că ai ales submulțimea $ \{ 2, 6, 4, 3 \} $. Este o alegere
validă, pentru că o sortezi: $ \{ 2, 3, 4, 6 \} $ și acum pui $ f(1) = 2 $, $ f(2) = 3 $,
$ f(3) = 4 $ și $ f(4) = 6 $. Rezultă că orice astfel de alegere va fi bună, deci
numărul total, $ C_6^4 = 15 $ este cel corect.

Alternativ, dacă folosești formula combinărilor complementare, poți să spui că,
în loc să alegi cele 4 elemente ale imaginii funcției, le alegi pe cele 2 care
*nu* vor fi valori pentru $ f(x \in A) $ și obții $ C_6^2 $, care,
desigur, este egal cu $ C_6^4 $, adică 15.

Mai adaug că un avantaj al folosirii combinărilor în această problemă este acela că,
fiind definite de submulțimi, nu permit valori repetate. O funcție poate să repete
valori, am văzut asta în exercițiile anterioare. Dar dacă avem nevoie de monotonie
strictă, atunci valorile trebuie să fie distincte. Ceea ce corespunde perfect
oricărei (sub)mulțimi: un element nu poate apărea de două ori.

---

<span style="color:var(--burgundy); font-size:1.3rem;">

Câte funcții $ f: A \to B $ strict descrescătoare și cu
$ f(3) = 1 $ se pot defini, dacă $ A = \{ 1, 2, 3 \} $ și $ B = \{ 1, 2, 3, 4, 5 \} $?

</span>

*Soluție:* Funcțiile strict descrescătoare inversează ordinea. Deci, fiindcă
$ 1 < 2 < 3 $, rezultă că $ f(1) > f(2) > f(3) $, adică $ f(3) $ este minimul dintre
cele trei valori alese. Dar asta nu e nicio problemă, pentru că ipoteza impune
$ f(3) = 1 $, care este oricum cea mai mică valoare din mulțimea $ B $.

Așa că ne rămâne doar să definim $ f(1) $ și $ f(2) $, ambele (automat) mai mari
decât $ f(3) $. Mai trebuie și să fie diferite între ele. Deci avem de ales
doar două valori din mulțimea $ B $, cu condiția să fie diferite între ele
și diferite de 1.

Rezultă că putem răspunde ca în problema anterioară: numărăm submulțimile
cu două elemente ale unei mulțimi cu 4 elemente (anume $ B \setminus \{ 1 \} $)
și, când alegem o astfel de submulțime, punem $ f(1) $ ca fiind valoarea
cea mai mare și $ f(2) $ pe cealaltă.

De exemplu, dacă am ales $ \{ 3, 5 \} $, funcția va fi: $ f(1) = 5 $,
$ f(2) = 3 $ și $ f(3) = 1 $. Este descrescătoare și verifică ipoteza.

Concluzia este că numărul total de astfel de funcții este $ C_4^2 = 6 $.

---

<span style="color:var(--burgundy); font-size:1.3rem;">

Care este termenul care nu-l conține pe $ x $ în dezvoltarea
$ \left( \sqrt[3]{x} + \dfrac{2}{\sqrt{x}} \right)^{200}, x > 0 $?

</span>

*Soluție:* De data asta, e o problemă în care avem nevoie de binomul lui Newton.
Pentru binomul de față:

$$
    \left( \sqrt[3]{x} + \dfrac{2}{\sqrt{x}} \right)^{200} = \displaystyle\sum_{k=0}^{200} C_{200}^k \sqrt[3]{x}^{200-k} \left( \dfrac{2}{\sqrt{x}} \right)^k.
$$

Termenul care nu-l conține pe $ x $ înseamnă că îl conține la puterea 0, care se poate obține,
pentru că ambii sumanzi din binom pot fi scriși cu baza $ x $. Mai precis, $ \sqrt[3]{x} = x^{\frac{1}{3}} $
și $ \dfrac{2}{\sqrt{x}} = 2x^{-\frac{1}{2}} $. Rezultă că putem face înmulțirea:

$$
    \sqrt[3]{x}^{200-k} \cdot \left( \dfrac{2}{\sqrt{x}} \right)^k = x^{\frac{200-k}{3}} \cdot 2^k \cdot x^{-\frac{k}{2}} = 2^k \cdot x^{\frac{200-k}{3} - \frac{k}{2}}.
$$

Dacă ne interesează termenul care-l conține pe $ x^0 $ înseamnă că trebuie să avem:

$$
    \frac{200 - k}{3} - \frac{k}{2} = \frac{400 - 2k - 3k}{6} = 0 \Rightarrow 400 - 5k = 0 \Longrightarrow k = 80.
$$

Așadar, termenul respectiv este $ C_{200}^{80} 2^{80} $ și, pentru că suma
începe la $ k = 0 $, înseamnă că este al $81$-lea din sumă.

---

<span style="color:var(--burgundy); font-size:1.3rem;">

Suma coeficienților binomiali din dezvoltarea $ \left( 2x^2 - 5y \right)^n $
este 32. Care este al patrulea termen?

</span>

*Soluție:* Aici trebuie, mai întâi, să fie clară o chestiune de terminologie.
*Coeficienții* sunt cei care conțin combinări. Chiar dacă primul termen al binomului
este $ 2x^2 $, nu spunem că $ 2 $ este un coeficient. În ansamblu, *coeficient binomial*
înseamnă termen de forma $ C_n^k $.

Apoi, în orice dezvoltare a unui binom, conform lui Newton, avem toate combinările
de forma $ C_n^k $, de la $ k = 0 $ și până la $ k = n $. Deci ce spune ipoteza este că:

$$
    \displaystyle\sum_{k=0}^n C_n^k = 32.
$$

Dar știm că suma combinărilor este $ 2^n $, dintr-o identitate demonstrată anterior.
Deci $ 2^n = 32 $, de unde $ n = 5 $.

În fine, al patrulea termen este cel care conține $ k = 3 $, pentru că primul are
$ k = 0 $. Mai precis, este:

$$
    C_5^3 \left( 2x^2 \right)^{5 - 3} \cdot (-5y)^3 = 10 \cdot 4 \cdot x^4 \cdot (-125) y^3 = -5000 x^4 y^3.
$$

---

<span style="color:var(--burgundy); font-size:1.3rem;">

Care este probabilitatea ca, alegând o funcție $ f: A \to B $,
unde $ A = \{ 1, 2, 3 \} $ și $ B = \{ 4, 5, 6 \} $, aceasta să fie injectivă?

</span>

*Soluție:* Aici sunt mai multe lucruri de înțeles. Pentru început,
există un rezultat care spune că orice funcție monotonă este injectivă.
Cu alte cuvinte, dacă ne asigurăm că avem o funcție monotonă (fie ea crescătoare
sau descrescătoare), știm sigur că este injectivă. Numai că problema cere ca funcția
să fie injectivă și asta nu implică obligatoriu monotonia (te poți gândi la un contraexemplu?).

Apoi, un alt rezultat ușor de văzut este acesta:

{{% important %}}

# Funcții injective definite pe mulțimi finite

Dacă $ A $ este o mulțime finită, atunci $ f : A \to A $ este o funcție injectivă
dacă și numai dacă este surjectivă dacă și numai dacă este bijectivă.

Cu alte cuvinte, este suficient să verifici oricare dintre cele trei proprietăți
(injectivitate, surjectivitate, bijectivitate) și rezultă automat și celelalte două.

{{% /important %}}

Justificarea e ușor de văzut, măcar intuitiv: o funcție injectivă este una care nu repetă
valorile, deci dacă $ x \neq y $, rezultă $ f(x) \neq f(y) $. Asta înseamnă că toate
elementele din imagine vor fi diferite și, cum ai de definit $ \# A = \mathrm{card}(A) $
valori, înseamnă că vor fi toate elemente lui $ A $ în imagine. Deci este și surjectivă.

Revenind la problemă, înseamnă că trebuie să alegem o funcție bijectivă, de exemplu.
Dar o funcție bijectivă definită pe o mulțime cu 3 elemente este o permutare de 3 elemente,
deci avem în total $ P(3) = 3! = 6 $ cazuri favorabile de funcții bijective.

Cât privește cazurile posibile, fiecare dintre valorile $ f(1) $, $ f(2) $ și $ f(3) $
pot lua oricare dintre cele trei valori din codomeniu, fără restricție, fiindcă ne întrebăm
despre toate funcțiile. Alegerile sunt și independente, deci cazurile posibile sunt în număr
de $ 3^3 = 27 $.

Ceea ce ne duce la probabilitatea $ p = \dfrac{6}{27} = \dfrac{2}{9} \simeq 22 \% $.

---

<span style="color:var(--burgundy); font-size:1.3rem;">

*Generalizare a problemei anterioare:* Care este probabilitatea
    ca o funcție $ f : A \to B $, cu $ A = \{ a_1, a_2, \dots, a_k \} $ și
$ B = \{ b_1, b_2, \dots, b_t \} $, să fie injectivă? Dar surjectivă? Dar bijectivă?

</span>

*Soluție:* Să lămurim mai întâi cazurile posibile, fiindcă sunt comune în toate
cele trei răspunsuri care se cer. $ \# A = k $ și $ \# B = t $. A defini o funcție
$ f : A \to B $ înseamnă să asociem fiecăruia dintre cele $ k $ elemente ale lui $ A $
câte un singur element din cele $ t $ ale lui $ B $. Mai mult, alegerile sunt independente,
dar altă restricție nu avem. Deci numărul total de funcții este $ t^k $. Este și motivul
pentru care uneori mulțimea funcțiilor $ f : A \to B $ se mai notează $ B^A $.

Apoi, pentru funcții injective: rezultatele de care am discutat în problema anterioară
nu ne ajută, pentru că, în general, $ A \neq B $, chiar dacă ambele sunt mulțimi finite.
În orice caz, putem folosi definiția: o funcție injectivă nu repetă valori, deci fiecare
dintre $ f(a_1), f(a_2), \dots, f(a_k) $ trebuie să fie diferite și se află printre
$ b_1, b_2, \dots, b_t $.

Rezultă o condiție esențială: problema nu are soluție (adică nu putem defini o funcție
injectivă) decât dacă $ k \leq t $. Altfel, nu putem avea valori diferite: dacă, de exemplu,
$ k = 5 $ și $ t = 3 $, nu putem asocia 5 numere diferite din doar 3 posibilități.

Așadar, cu ipoteza $ k \leq t $, este acum ușor de văzut: nu avem decât să alegem $ k $
obiecte din cele $ t $ și să le punem într-o mulțime. Astfel, ne asigurăm că sunt diferite,
fiindcă o mulțime nu permite repetiții. Rezultă că o reformulare a întrebării este:

*În câte moduri putem forma submulțimi cu $ k $ elemente dintr-o mulțime cu $ t $ elemente?*

Răspunsul este cunoscut: $ C_t^k $. Acesta este numărul de funcții injective.
Probabilitatea cerută, atunci, este $ p_i = \dfrac{C_t^k}{t^k} $.

Pentru funcții surjective, avem nevoie să se acopere întreg codomeniul. Deci cele $ k $
valori din imaginea funcției ($ f(a_1), \dots, f(a_k) $) trebuie să epuizeze mulțimea $ B = \{ b_1, \dots, b_t \} $.
Rezultă imediat și aici o condiție esențială: $ k \geq t $.

Acum, pentru numărul funcțiilor surjective, ai putea fi tentat să spui că sunt $ C_k^t $,
pentru că ai de definit $ t $ valori, anume imaginile elementelor din $ A $. Numai că
e mult mai complicat decât atât. Dacă $ k > t $, atunci funcția $ f : A \to B $ nu va fi
injectivă, deci va avea valori repetate, în număr de $ k - t $. Dar care sunt cele repetate
contează.

Iată un exemplu: $ k = 5, t = 3 $, deci să luăm $ A = \{ 1, 2, 3, 4, 5 \} $ și
$ B = \{ 1, 2, 3 \} $. Să spunem că definești o funcție astfel încât $ f(1) $, $ f(2) $
și $ f(3) $ acoperă pe $ B $ (de exemplu, $ f(1) = 3 $, $ f(2) = 2 $ și $ f(3) = 1 $).
Dar apoi mai ai de definit $ f(4) $ și $ f(5) $, care vor repeta elementele lui $ B $, evident.
Însă dacă pui $ f(4) = f(5) = 1 $ sau $ f(4) = 1 $ și $ f(5) = 2 $ obții funcții diferite.
Deci trebuie numărate cu maximă atenție.

Ce preluăm din acest exemplu simplu este faptul că putem da deoparte $ t $ elemente
pe care funcția $ f $ să nu le repete (cum am avut aici pe primele 3) și apoi, cele $ k - t $
care vor avea valori repetate.

Cu alte cuvinte, dacă te gândești la restricția lui $ f $ pe o submulțime a lui $ A $
care conține doar $ t $ elemente, o faci bijectivă, deci ai $ t! $ posibilități de a o defini.
Dar valorile care se repetă apoi, cele $ k - t $, pot fi alese într-un număr foarte mare de moduri.
Și nu doar atât, ci numărul respectiv este unul care se calculează greu în general.
Se numește <span style="color:var(--burgundy) !important;">*numărul de partiții Stirling*</span> și se notează,
în cazul nostru, $ S(k, t) $, adică numărul de partiții cu $ t $ elemente ale unei mulțimi cu $ k $ elemente.

Valorile sunt, de obicei, tabelate, pentru că au o formulă complicată de calcul, iar discuția
mai amănunțită depășește scopurile acestui material (și programei de liceu, de altfel):

$$
    S(k, t) = \dfrac{1}{t!} \cdot \displaystyle\sum_{i = 0}^t (-1)^{t-i} \cdot C_t^i \cdot i^n.
$$

Revenind la întrebare, numărul de funcții surjective de pe o mulțime cu $ k $ elemente către
o mulțime cu $ t $ elemente (cu $ k \geq t $ obligatoriu) este $ t! \cdot S(k, t) $.
Răspunsul ca probabilitate este, atunci: $ p_s = \dfrac{t! \cdot S(k, t)}{t^k} $.

În fine, pentru funcții bijective, este necesar $ k = t $ și atunci este vorba despre permutări
ale unei mulțimi cu $ k = t $ elemente.

Deci numărul de funcții bijective este $ P(k) = P(t) = k! = t! $, iar ca probabilitate,
$ p_b = \dfrac{t!}{t^t} $.

---

<span style="color:var(--burgundy); font-size:1.3rem;">

Câte diagonale are un poligon convex cu $ n $ laturi?

</span>

*Soluție:* Te poți gândi în două moduri. Mai întâi, o diagonală este definită
de două vârfuri, dar care nu sunt consecutive, fiindcă altfel este latură. Ai $ n $
laturi, deci și $ n $ vârfuri în poligon. Numărul de moduri în care poți alege 2 dintre ele
(capetele diagonalei) este $ C_n^2 $. Numai că aici nu am prevăzut și situația când sunt
laturi, fiindcă vârfurile alese pot fi consecutive. Deci din $ C_n^2 $ scădem numărul
laturilor și obținem:

$$
    C_n^2 - n = \dfrac{n!}{2! (n-2)!} - n = \dfrac{n(n-3)}{2}.
$$

O altă soluție este să te gândești, concret, cum formezi o diagonală, ca algoritm:
unești fiecare dintre cele $ n $ vârfuri cu oricare alt vârf, mai puțin cu: el însuși,
vârful anterior și vârful următor. Deci pentru fiecare dintre cele $ n $ vârfuri ai de
trasat $ n - 3 $ segmente. Doar că astfel ai numărat diagonalele de câte două ori:
o dată când a fost trasată dintr-un vârf și din nou când ai ajuns la vârful celălalt.
Așadar, răspunsul este jumătate din cât ai calculat: $ \dfrac{n(n-3)}{2} $.

---

[^1]: Același coeficient binomial are, în materialele anglo-saxone,
denumirea *$ n $ choose $ k $* și notația $\binom{n}{k}$.
