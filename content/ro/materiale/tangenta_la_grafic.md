+++
title = "Ecuația tangentei la grafic"
type = "docs"
slug = "tangenta-la-grafic"
+++

# Ecuația tangentei la graficul unei funcții

{{< material-author >}}
Adrian Manea, `adrianmanea@poligon-edu.ro`
{{< /material-author >}}

<span
style="font-family:'Switzer', 'Arial', 'San Francisco', sans-serif;weight: 600;font-size:1.1rem;letter-spacing:0.01rem;">
<b><a href="/documents/tangenta_la_grafic.pdf">Descarcă versiunea PDF</a></b>
</span>

Curbele sunt forme naturale, pentru că ai multe exemple în jur care nu sunt
făcute din colțuri și linii drepte. Dar una este să intuiești ce înseamnă o curbă,
să o poți recunoaște vizual și cu totul altceva să o descrii riguros, matematic.

Tehnologia digitală, de exemplu pixelii de pe ecran, te ajută să înțelegi că o curbă se obține,
de fapt, prin bucățele foarte mici, fragmente de dreaptă, practic. Cu cât fragmentele
sunt mai mici și mai multe, cu atât aproximația este mai bună.

<figure id="fig-curba">
{{< svgfig src="tangenta_fig1.svg" alt="Curba asociată unei funcții și puncte diverse luate pe ea, care o aproximează liniar" style="width:80%" >}}
<figcaption>Curba asociată unei funcții și puncte diverse luate pe ea, care o aproximează liniar</figcaption>
</figure>

Și pentru că în matematică
poți să spui că ai *o infinitate* de fragmente, de lungime *infinitezimală*, adică
„infinit de mică”, ajungi la descrierea (aproape) riguroasă a unei curbe.

Dar înțelegerea intuitivă, rudimentară din acele fragmente de dreaptă îți dau o noțiune
foarte importantă și încă relevantă, chiar și după ce ai văzut cum se obține o curbă.
Vechile fragmente pe care le-ai folosit când ai trasat curba sunt *tangente*
la curba respectivă, în puncte intermediare. Cum o dreaptă este reprezentarea grafică
a unei funcții de gradul întâi sau *liniare*, poți să vezi
<span style="color:var(--burgundy) !important;">*tangentele ca aproximații liniare ale curbelor*</span>.
Curba devine, așadar, o „șlefuire la infinit” a unei linii alcătuite din tot mai mici
și mai multe segmente de dreaptă.

Problema ecuației tangentei la o curbă se pune din mai multe motive, nu doar al desenului.
Ideea că o tangentă aproximează o curbă într-o vecinătate suficient de mică a punctului de
intersecție (de tangență) devine și mai folositoare când înțelegi că ea modelează viteza cu care se schimbă mărimea reprezentată de curbă.

---

## Tangenta, derivata și viteza de schimbare

Până în preajma secolelor XVII-XVIII, când au trăit Isaac Newton și Gottfried W. Leibniz,
fizica nu avea o metodă riguroasă și precisă pentru calculul *vitezei instantanee*.
Problema este la baza mecanicii clasice, pe care astăzi o înveți
în clasa a IX-a. Iar fundamentele ei matematice au fost puse tot de Newton, care a arătat cum
poți folosi analiza matematică ca să înțelegi variația unei mărimi. De exemplu,
variația poziției în spațiu a unui corp, care îți arată viteza sau variația vitezei,
care îți arată accelerația.

În general, variația unei mărimi înseamnă pur și simplu diferența dintre valoarea ei la un moment
considerat final și cea de la momentul considerat inițial (sau de referință). Dacă vrei să vezi variația temperaturii într-o zi, de dimineață până la prânz, să spunem, calculezi diferența
dintre temperatura la ora 13.00 și cea de la ora 7.00.

Diferențele de tipul acesta se numesc *variații absolute* și se notează, în fizică, prin $ \Delta $.
Scrii $ \Delta x = x_{\text{final}} - x_{\text{inițial}} $ când vrei să arăți variația poziției
pe orizontală ($ x $).

Numai că variația absolută nu dă nicio indicație despre ce s-a întâmplat pe parcurs.
Dacă, atunci când calculezi variația temperaturii într-o zi, obții doar 2 grade Celsius,
să spunem, vei deduce că temperatura de la ora 13.00 este doar cu 2 grade mai mare decât cea
de la ora 07.00. Dar dacă între timp a plouat? Sau mare parte din timp a fost înnorat, a bătut
vântul și soarele a ieșit doar după ora 11.00? Uitându-te doar la două valori, inițială și finală,
înțelegi doar diferența lor, nu și modul în care s-a ajuns de la prima la a doua, eventuale
creșteri sau descreșteri rapide de pe parcurs, care s-au echilibrat sau modificări bruște,
dar într-un interval foarte scurt.

Tocmai de aceea, este necesar să poți calcula și *variația instantanee*, adică ce se întâmplă
acum, într-un interval de timp foarte mic, atât de mic încât nu e potrivit să calculezi cu $ \Delta $,
fiindcă ai obține (aproape) zero.

De exemplu, pentru graficul funcției $ f(x) = \sin x $ (figura de mai jos), dacă te uiți
pe un interval de forma $ [0, \pi] $, pare că nu se întâmplă nimic, fiindcă $ f(0) = f(\pi) $,
deci valoarea inițială este egală cu cea finală. Un astfel de calcul surprinde două momente doar
și, dacă nu sunt bine alese, nu afli nimic despre *comportamentul intermediar*.

<figure id="fig-sinus">
{{< svgfig src="tangenta_fig2.svg" alt="Graficul funcției f(x) = sin x, cu valorile egale marcate f(0) = f(π) = 0" style="width:80%" >}}
<figcaption>Graficul funcției f(x) = sin x, cu valorile egale marcate f(0) = f(π) = 0</figcaption>
</figure>

Pentru calcule instantanee, la fizică ți s-a explicat că e nevoie să calculezi o limită, în care intervalul
de timp este aproape zero. De exemplu, fiindcă viteza este calculată ca variația poziției
în timp, un calcul precum:
$$
    v_m = \dfrac{\Delta x}{\Delta t}
$$
îți arată doar *viteza medie*, pentru că folosește variații absolute și nu îți poate
arăta ce s-a întâmplat pe parcurs, ci doar diferența dintre momentul final și cel inițial.

Așa că profesorul de fizică îți poate explica despre necesitatea lucrului cu un interval
de timp aproape de zero, iar raportul acesta devine un calcul la limită:
$$
    v = \displaystyle\lim_{\Delta t \to 0} \dfrac{\Delta x}{\Delta t},
$$
metodă cu care calculezi *viteza instantanee*. Iar dacă îți amintești că poziția $ x $
este dată de o lege de mișcare sub forma unei funcții $ x(t) $, poți să scrii:
$$
    v = \displaystyle\lim_{t \to t_0} \dfrac{x(t) - x(t_0)}{t - t_0}.
$$
Și fiindcă această limită se poate calcula oricând ai fixat un moment $ t_0 $ la care te raportezi,
rezultă că ea returnează o *funcție de $ t $*, pe care ai notat-o cu $ v^\prime(t) $.
A fost, probabil, prima întâlnire cu noțiunea de *derivată a unei funcții*, cu mult înainte
de studiul riguros de la matematică.

Construcția asta e fix ce-ți trebuie ca să înțelegi motivația practică, fizică, a funcțiilor derivate.
Metoda matematică vine în completare, pe baza reprezentării grafice.

Definiția funcției derivate, așa cum este introdusă la matematică, se bazează pe limita
de mai sus, din cazul vitezei, doar că într-un context mai abstract.[^1]

Începem, deci, cu o funcție reală, $ f : D \subseteq \mathbb{R} \to \mathbb{R} $. Pentru un punct
arbitrar $ x_0 \in D $, se definește derivata funcției $ f $ în $ x_0 $, notată $ f^\prime(x_0) $
prin:[^2]
$$
    f'(x_0) = \lim_{x \to x_0} \dfrac{f(x) - f(x_0)}{x - x_0}.
$$

Această limită își arată adevărata față atunci când o interpretezi cu ajutorul reprezentării grafice.

<figure id="fig-secanta">
{{< svgfig src="tangenta_fig3.svg" alt="Tangenta la grafic și o secantă" style="width:80%" >}}
<figcaption>Tangenta la grafic și o secantă</figcaption>
</figure>

Să zicem că ai graficul funcției în figura de mai sus și trasezi o secantă la grafic, astfel încât
punctul $ x_0 $ fixat arbitrar[^3] să fie între punctele de intersecție dintre secantă
și grafic.

Dacă duci paralele la axele de coordonate prin punctele de intersecție dintre secantă și
graficul funcției, obții un triunghi dreptunghic, care are drept ipotenuză segmentul
determinat de intersecția secantei cu graficul. Să zicem că abscisele celor două puncte
de intersecție sunt $ x = a $ și $ x = b $, iar ordonatele, $ f(a) $ și $ f(b) $.
Să ne uităm la ce calculează un raport precum cel din definiția derivatei:
$$
    \dfrac{f(b) - f(a)}{b - a} = \mathrm{tg}\alpha,
$$
unde $ \alpha $ este unghiul pe care îl face ipotenuza-secantă cu cateta paralelă la axa $ Ox $.
Dar, din geometria de bază, acest unghi este congruent cu unghiul pe care îl face
*dreapta secantă cu axa $ Ox $*, ca unghiuri corespondente (date de paralela la axa $ Ox $,
axa $ Ox $ și secanta la grafic, care devine secantă și pentru această pereche de drepte paralele).

Însă tangenta unghiului pe care îl face o dreaptă cu axa $ Ox $ este panta acestei drepte.
Rezultă, deci, că raportul sus-menționat calculează *panta secantei la grafic*.

De menționat că ar fi fost posibil ca secanta să fie o dreaptă cu pantă negativă,
caz în care ar fi determinat un unghi obtuz cu axa $ Ox $, și atunci, raportul de mai sus
nu mai calculează chiar $ \mathrm{tg}(\alpha) $, cu $ \mathrm{tg}(\pi - \alpha) $,
care este egal cu $ -\mathrm{tg}(\alpha) $. Dar această situație este convenabilă, pentru
că, în cazul respectiv, $ f(b) < f(a) $, deci raportul are valoare negativă oricum, egală
în modul cu cazul celălalt.

Definiția derivatei mai implică și o limită. Dacă ne gândim acum că $ x_0 = b $
și pornim de la $ x = a $ către $ x_0 $, secanta ajunge să determine un triunghi dreptunghic
cu o ipotenuză cât mai mică, până când, la limită, $ x = x_0 $ și ipotenuza este redusă
la un punct. Atunci, *secanta devine tangentă*, iar ipotenuza, punctul de tangență.
Situația, pas cu pas, când o secantă tinde să devină tangentă, este ilustrată în figura de mai jos.

<figure id="fig-sec-tg">
{{< svgfig src="tangenta_fig4.svg" alt="Tangenta la grafic, obținută prin rafinarea secantei" style="width:80%" >}}
<figcaption>Tangenta la grafic, obținută prin rafinarea secantei</figcaption>
</figure>

Raportul respectiv calculează tot panta acestei drepte, însă, fiindcă expresia nu s-a schimbat.
Rezultă, deci, că la limită, când $ x \to x_0 $, limita respectivă, adică $ f^\prime(x_0) $
ajunge să calculeze panta tangentei la graficul funcției în punctul $ x_0 $.

Aici este rezultatul-cheie, așa că merită evidențiat separat.

{{% important %}}

# Derivata într-un punct este panta tangentei

Pentru o funcție $ f : D \subseteq \mathbb{R} \to \mathbb{R} $ și un punct arbitrar $ x_0 \in D $,
valoarea funcției derivate în punctul $ x_0 $, adică $ f^\prime(x_0) $, este panta dreptei
tangente la graficul funcției în punctul respectiv.

{{% /important %}}

Odată înțeles acest lucru, problema pe care ne-am propus-o la început, cea de găsirea ecuației
tangentei la graficul funcției, este mai mult de jumătate rezolvată.

Iată un exemplu.

<span style="color:var(--burgundy); font-size:1.3rem;">

Fie funcția $ f : \mathbb{R} \to \mathbb{R}, f(x) = x^3 - 5x + 1 $. Să găsim ecuația tangentei
la graficul funcției în punctul $ x_0 = -1 $.

</span>

Orice tangentă este o dreaptă, deci trebuie să aibă o ecuație generală de forma $ y = ax + b $.
Ca să determinăm dreapta, trebuie să găsim $ a $ și $ b $.

Dar $ a $ este chiar panta dreptei tangente, deci, în baza observațiilor anterioare, $ a = f^\prime(-1) $.
Calculăm derivata în general și apoi:
$$
    f^\prime(x) = 3x^2 - 5 \Rightarrow f^\prime(-1) = -2 = a.
$$
Pentru valoarea lui $ b $, să ne amintim că rezolvăm, de fapt, o problemă de intersecție între
două curbe: graficul funcției $ f $ și dreapta tangentă. Punctul lor de intersecție este
punctul de tangență, despre care știm că are abscisa $ x_0 = -1 $. Atunci ordonata lui
se poate calcula atât prin funcția $ f $, cât și prin ecuația dreptei tangente, căci punctul
se află pe amândouă. Deci $ f(x_0) = f(-1) = 5 $, adică punctul de tangență este $ T(-1, 5) $.

El se găsește și pe dreapta tangentă, deci:
$$
    5 = (-2) \cdot (-1) + b \Rightarrow b = 3.
$$

Rezultă că ecuația tangentei este $ y = -2x + 3 $.

Vizual, figura de mai jos arată graficul funcției și tangenta calculată.

<figure id="fig-tangenta-ex1">
{{< svgfig src="tangenta_fig5.svg" alt="Tangenta la graficul funcției din exemplu" style="width:80%" >}}
<figcaption>Tangenta la graficul funcției din exemplu</figcaption>
</figure>

---

Dacă înțelegi ecuația dreptei tangente pe componente și în special rolul pantei
acesteia, poți să rezolvi și exerciții mai sofisticate, ca acesta.

<span style="color:var(--burgundy); font-size:1.3rem;">

Fie funcția $ f : (0, \infty) \to \mathbb{R}, f(x) = x + \ln^2 x - x \ln x $.

Găsiți abscisele punctelor situate pe graficul funcției $ f $ în care tangenta la graficul
funcției este paralelă cu axa $ Ox $. (Model MEN 2025)

</span>

Axa $ Ox $ este o dreaptă orizontală, deci are panta $ 0 $. Așadar, problema cere
abscisele (adică valorile lui $ x $) corespunzătoare punctelor unde panta tangentei
la grafic ar fi orizontală. Însă panta tangentei într-un punct este dată de valoarea
funcției derivate în punctul respectiv. Cu alte cuvinte, problema cere să găsim $ x $
astfel încât $ f^\prime(x) = 0 $, ceea ce se poate rezolva algebric, de îndată ce
interpretarea este clară.

Derivata este: $ f^\prime(x) = 1 + 2 \ln x \cdot \dfrac{1}{x} - \ln x - 1 = \ln x \left( \dfrac{2}{x} - 1 \right) $.

Ca să anulăm derivata, trebuie fie ca $ \ln x = 0 $, fie $ \dfrac{2}{x} - 1 = 0 $.
Din primul caz obținem $ x = 1 $, iar din al doilea, $ x = 2 $. Acestea sunt abscisele
punctelor în care tangenta la graficul funcției ar fi orizontală, deci paralelă cu axa $ Ox $.

---

Tot pe baza noțiunilor despre ecuația dreptei, în cazul particular când este vorba
despre dreapta tangentă la graficul unei funcții se rezolvă și exercițiul următor.

<span style="color:var(--burgundy); font-size:1.3rem;">

Fie funcția $ f : \mathbb{R} \to \mathbb{R}, f(x) = \sqrt{x^2 + 3} - \ln\left( x + \sqrt{x^2 + 3} \right) $.

Arătați că tangenta la graficul funcției în punctul $ \left( -1, f(-1) \right) $ este
perpendiculară pe dreapta de ecuație $ x - y + 2 = 0 $. (Simulare Covasna 2025)

</span>

Ordonata punctului de tangență nu este importantă, deci nu este nevoie să calculăm $ f(-1) $.
Avem în vedere două lucruri: știm abscisa punctului de tangență, $ x = - 1 $, deci vom
putea calcula panta tangentei acolo, iar aceasta este singura informație utilă, căci
condiția de perpendicularitate a două drepte se scrie doar cu ajutorul pantelor.

Așadar, panta tangentei în $ x = - 1 $ este $ f^\prime(-1) $ și, în general:
$$
    f^\prime(x) = \dfrac{x}{\sqrt{x^2 + 3}} - \dfrac{1 + \dfrac{x}{\sqrt{x^2 + 3}}}{x + \sqrt{x^2 + 3}}.
$$

Nu este nevoie să prelucrăm mai mult, pentru că, înlocuind $ x = - 1 $, calculele se vor ușura.
Deci:
$$
    f^\prime(-1) = \dfrac{-1}{\sqrt{4}} - \dfrac{1 + \dfrac{-1}{\sqrt{4}}}{-1 + \sqrt{4}}
    = \dfrac{-1}{2} - \dfrac{1}{2} = -1.
$$

Panta tangentei la graficul funcției în punctul $ \left( -1, f(-1) \right) $ este $ -1 $.

Cealaltă dreaptă dată trebuie prelucrată puțin, ca să-i găsim panta:
$$
    x - y + 2 = 0 \Longleftrightarrow y = x + 2,
$$
deci are panta 1. Condiția de perpendicularitate a două drepte este ca produsul pantelor
lor să fie $ -1 $, ceea ce în cazul nostru se verifică și am terminat.

---

Închei cu un exercițiu care depășește nivelul clasei a XI-a, însă a fost dat la simularea
pentru bacalaureat din 2026 și, cel puțin printre elevii cu care am discutat, a stârnit
nedumeriri.

<span style="color:var(--burgundy); font-size:1.3rem;">

Fie funcția $ f : (0, \infty) \to \mathbb{R}, f(x) = \left( 4x + \dfrac{6}{x^2} \right) \cdot \ln x $.

Determinați primitiva $ F : (0, \infty) \to \mathbb{R} $ a funcției $ f $ pentru care
axa $ Ox $ este tangentă la graficul funcției $ F $.

</span>

Putem începe cu informațiile despre tangentă: faptul că axa $ Ox $ este tangentă la graficul
funcției $ F $ înseamnă că în punctul sau punctele de tangență, derivata lui $ F $ este nulă.
Dar, din faptul că $ F $ este primitiva (numită și *antiderivata*) lui $ f $ rezultă că
$ F'(x) = f(x) $, deci înseamnă că $ f(x) $ se anulează în punctele de tangență.

Atunci rezultă că fie $ \ln x = 0 $, adică $ x = 1 $, fie $ 4x + \dfrac{6}{x^2} = 0 $, adică
$ 4x^3 + 6 = 0 $, de unde am obține o soluții negative, care nu se găsesc în domeniul de definiție.
Rămâne că punctul de tangență este $ x = 1 $ și deci $ F'(1) = f(1) = 0 $.

Însă această informație nu este utilă când vrem să determinăm funcția $ F $.
Pentru asta, trebuie să folosim punctul de tangență, $ (1, 0) $, care se găsește
pe graficul lui $ F $, adică $ F(1) = 0 $. Abia această relație va fi utilă în calculul lui $ F $.

Acum integrăm, cu metoda integrării prin părți:
$$
\begin{align*}
    F(x) &= \displaystyle\int f(x) dx \\
    \phantom{F(x)} &= \displaystyle\int 4x \ln x dx + \displaystyle\int \dfrac{6}{x^2} \ln x dx \\
    \phantom{F(x)} &= 2x^2 \ln x - \displaystyle\int 2x dx - \dfrac{6}{x} \ln x + \displaystyle\int \dfrac{6}{x^2} dx \\
    \phantom{F(x)} &= 2x^2 \ln x - x^2 - \dfrac{6}{x} \ln x - \dfrac{6}{x} + \mathcal{C},
\end{align*}
$$

Din condiția $ F(1) = 0 $, rezultă $ F(1) = -1 -6 + \mathcal{C} = 0 $, adică $ \mathcal{C} = 7 $.

Concluzie: $ F(x) = x^2 \left( 2\ln x - 1\right) - \dfrac{6}{x}\left( \ln x - 1 \right) + 7. $

---

<span
style="font-family:'Switzer', 'Arial', 'San Francisco', sans-serif;weight: 600;font-size:1.1rem;letter-spacing:0.01rem;">
<b><a href="/documents/tangenta_la_grafic.pdf">Descarcă versiunea PDF</a></b>
</span>

[^1]: Analiza matematică de clasa a XI-a începe cu un context mult mai riguros decât
    voi expune aici. Punctele de acumulare, șiruri de numere reale, noțiunea de limită,
    șiruri convergente, criterii de caracterizare a convergenței și altele sunt noțiuni
    pe care se bazează construcția limitei unei funcții într-un punct. Dar, pe de o parte,
    le voi presupune cunoscute pentru ce avem nevoie aici și, pe de alta, cred că toate noțiunile
    cuprinse aici pot fi înțelese și în lipsa unei parcurgeri riguroase a primei părți din materia
    de analiză de clasa a XI-a.

[^2]: Aici ar trebui să presupunem că funcția are anumite proprietăți convenabile, care
    să asigure că limita aceasta este finită sau altfel, să lucrăm cu limite laterale.
    Însă pentru scopul pe care mi l-am propus aici, voi insista doar pe cazurile care nu necesită
    astfel de precauții, adică funcția nu prezintă anomalii care să conducă la derivate infinite
    sau inexistente. Pentru asta, este suficient să presupunem că toate funcțiile pe care le vom discuta
    sunt *continue* pe întreg domeniul de definiție.

[^3]: Fixarea arbitrară a unui punct sau număr înseamnă că îl alegem arbitrar, adică
    „la întâmplare”, fără vreo condiție anume sau metodă, însă, odată ales, el rămâne
    fixat pe parcursul întregii discuții.
