+++
title = "Ce este dx?"
type = "docs"
slug = "infinitezimal"
+++

# Ce este dx? Despre infinitul mic

{{< material-author >}}
Adrian Manea, `adrianmanea@poligon-edu.ro`
{{< /material-author >}}

<span
style="font-family:'Switzer', 'Arial', 'San Francisco', sans-serif;weight: 600;font-size:1.1rem;letter-spacing:0.01rem;">
<b><a href="/documents/ce_este_dx.pdf">Descarcă versiunea PDF</a></b>
</span>

La începutul lecțiilor de analiză din clasa a douăsprezecea, ai aflat despre
operația inversă derivării: integrarea. Ca să găsești primitiva unei funcții
reale $ f $, te întrebi *„Ce funcție trebuie să derivez ca să obțin pe $ f $?”*.
De exemplu, dacă derivezi funcția $ f(x) = x^2 $, obții $ f^\prime(x) = 2x $,
așa că, invers, în termeni de primitive,
ai $ \displaystyle\int 2x dx = x^2 + \mathcal{C} $.

În scrierea și calculul primitivelor, sunt două detalii care par neobișnuite,
mai ales la prima vedere.

<span style="color:var(--burgundy) !important;">

- *Ce rol are constanta care se adaugă la final de fiecare dată?*
- *De ce trebuie să scriu ceva suplimentar, acel $ dx $, care nici nu e clar ce este,
    dacă eu calculez primitiva funcției $ 2x $?*

</span>

Prima întrebare are un răspuns simplu, care vine din regulile de derivare.
$ \mathcal{C} $-ul de la final înseamnă, de fapt, *orice (funcție) constantă* sau
*mulțimea funcțiilor constante*, pentru că orice două primitive ale aceleiași
funcții pot să difere printr-o constantă.

De exemplu, fie că derivezi funcția
$ f_1(x) = x^2 $ sau funcția $ f_2(x) = x^2 + \pi $ sau funcția $ f_3(x) = x^2 - 1 $,
obții același lucru de fiecare dată: $ 2x $. Rezultă că toate cele trei funcții,
$ f_1, f_2, f_3 $ sunt primitive pentru $ 2x $. Și atunci, pe care o alegi?
Nu ai niciun motiv să dai o prioritate sau alta, așa că *toate trei sunt la fel de bune*.
Sau, altfel spus: oricare dintre ele și multe altele, toate sub forma $ 2x \ + $ orice constantă.
De aceea, ca să cuprinzi toate răspunsurile posibile, se scrie
$ \displaystyle\int 2x dx = x^2 + \mathcal{C} $.

Dacă nu apar specificații suplimentare,
cum ar fi să se ceară primitiva $ F $ a funcției $ f $ care are proprietatea că $ F(1) = 1 $,
atunci păstrezi răspunsul general: orice constantă e la fel de bună, iar calculul
returnează, de fapt, *mulțimea primitivelor funcției $ f $*. Pentru cazul când
ai o valoare particulară, ca $ F(1) = 1 $, găsești precis *primitiva*:
$ F(1) = 1^2 + \mathcal{C} = 1 \Rightarrow \mathcal{C} = 0 $, deci $ F(x) = x^2 $ și atât.
O singură primitivă în loc de mulțimea primitivelor.

Pentru întrebarea a doua, însă, facem o excursie istorică, filosofică și
științifică spre una dintre cele mai importante noțiuni din matematică, științe
și filosofie: <span style="color:var(--burgundy) !important;">infinitul</span>.

---

## Mai multe tipuri de infinit

La baza calculului primitivelor unei funcții și chiar
când calculezi integrala definită, cu interpretarea ei ca arie, nu te-ai aștepta
să găsești o discuție milenară despre infinit, nu? Mai ales dacă te gândești
la interpretarea geometrică a integralei definite, cu aplicațiile sale în
calculul ariei sau al volumului, rezultatul pare cât se poate de finit.

Surpriza vine chiar din modul în care înțelegi acest concept. În istoria gândirii,
cu mult înainte de apariția științei riguroase, oamenii s-au raportat la infinit
ca la o imensitate fără margini. Ceea ce este complet natural, pentru că dacă te
întrebi ce imagine îți vine în minte atunci când spui „infinit”, cel mai
probabil faci aceleași asocieri pe care le-au făcut și oamenii antichității:
universul (cerul), timpul sau Dumnezeu.

Problema infinitului era, într-un fel,
legată automat de cea a continuității și a existenței atomilor. Dacă acceptăm
că există atomi (nu neapărat în sensul fizic de astăzi, ci cu înțelesul de
unități indivizibile, care există fizic sau doar conceptual), atunci avem o
imagine concretă a infinitului ca totalitatea atomilor din univers. Nu mai e nevoie
să spunem că universul este infinit, ci precizăm că numărul total de atomi
din univers este infinit.

În secolul al patrulea înaintea erei noastre, Aristotel propune, însă,
*două tipuri de infinit*. Ideea că universul sau timpul ar fi infinite,
de exemplu, poate fi înțeleasă în două moduri. Dacă accepți că există atomi,
atunci totalitatea unităților (atomilor) care alcătuiesc spațiul sau timpul
sunt nenumărate, „în număr infinit”. Însă dacă atomii nu există,
înseamnă că orice fragment poate fi făcut și mai mic, și mai mic, și mai mic...
Adică poate fi micșorat sau divizat *la infinit*. De aici, ideea lui
Aristotel că infinitul se prezintă sub două variante:

<span style="color:var(--burgundy) !important;">

- *infinitul în adunare*, când poți să adaugi fără sfârșit,
    cum este cazul numerelor naturale: la oricare dintre ele ai vrea
    să te oprești, mai poți adăuga 1 și obții tot un număr natural;
- *infinitul în diviziune*, când poți să fragmentezi fără
    sfârșit, cum este cazul unui interval de numere reale: între
    oricare două numere reale se află încă unul.

</span>

Pentru că primul tip de infinit se leagă direct de mulțimea numerelor naturale,
el stă la baza principiului inducției. O mulțime se numește *inductivă*
dacă, oricând conține un element, conține și pe succesorul său, definit
specific. De exemplu, pentru numere naturale, succesorul
înseamnă următorul, adică numărul obținut prin adunarea cu 1.

Mulțimea numerelor naturale este o mulțime inductivă, fiindcă este suficient
să pornești cu $ 0 $ și cu funcția succesor $ S(x) = x + 1 $. Construcția
care rezultă este întreaga mulțime a numerelor naturale, care este infinită
sau, în sensul lui Aristotel, *infinită în adunare*.

Dar pentru scopurile de aici, ne interesează mai mult infinitul în diviziune,
legat direct de numerele reale. Faptul că între orice două numere reale
poți să mai găsești încă un număr real se numește proprietatea de *densitate*
a mulțimii numerelor reale. În particular, ea îți permite să faci un interval $ (a,b) $
oricât de mic din punctul de vedere al lungimii, adică al diferenței $ b - a $.
Celebrul $ \varepsilon $ pe care l-ai întâlnit în definițiile din clasa a unsprezecea
era înțeles în acest sens: *oricât de mic*, adică mai mic decât orice număr
real ai putea fixa.

Așadar, mulțimea numerelor naturale este infinită în adunare, în sensul că
orice număr ai alege, *oricât de mare*, tot mai găsești pe succesorul său
în mulțime. Iar numerele reale sunt cadrul potrivit pentru infinitul în diviziune,
pentru că orice interval $ (a, b) $ ai alege, cu diferența $ b - a $ *oricât de mică*,
încă mai există un număr real $ c \in (a, b) $.

---

## Infinitezimalul

Infinitul în diviziune este conceptul care conduce la „infinitul mic”,
numit și *infinitezimal*. Când spun că putem face intervalul $ (a, b) $
oricât de mic, de fapt mă refer la o limită de forma:
$$
    \lim_{a \to b} (b - a).
$$

Însăși definiția conceptului de limită se bazează pe asta: diferența $ b - a $
este *arbitrar de mică* atunci când $ a $ tinde către $ b $.

Pentru o astfel de situație, în jurul secolului al XVII-lea, Gottfried W.\ Leibniz
și Isaac Newton au propus o notație aparte, pentru că apare foarte des, atât
în calculul derivatelor, cât și al integralelor — practic, în toată analiza matematică,
la care amândoi au contribuit enorm. Au introdus *notația diferențială*,
prin care $ d M $ înseamnă o variație oricât de mică a mărimii $ M $.
Cum ar fi $ dx = \displaystyle\lim_{x \to x_0} (x - x_0) $.

În liceu, noțiunea apare mai întâi la fizică, atunci când vrei să calculezi
variații instantanee. De exemplu, viteza medie a unui corp o calculezi
prin raportul $ v_m = \dfrac{\Delta x}{\Delta t} $, unde $ \Delta M $, pentru
o mărime $ M $, arată o simplă diferență între valoarea finală și valoarea inițială,
între două momente de referință. Însă un astfel de calcul arată doar o variație
de ansamblu, nu-ți permite să afli ce se întâmplă momentan. În cazul cel mai rău,
când ai o mărime care variază periodic, se poate să nimerești valori egale
și la început, și la finalul intervalului și atunci, pare că variația este nulă,
deși pe parcurs s-ar fi putut întâmpla multe.

De aceea, calculul instantaneu înseamnă să presupui că momentele inițial și final
sunt aproape identice sau altfel spus, că $ \Delta t \to 0 $, adică
$ t_\text{inițial} \to t_\text{final} $. Însă asta înseamnă tocmai infinitezimalul
despre care am vorbit, adică:
$$
    \lim_{t_{\text{inițial}} \to t_{\text{final}}} \left( t_{\text{final}} - t_{\text{inițial}} \right) = dt.
$$

Corespunzător, pentru un astfel de interval de timp infinitezimal, și variația poziției
o să fie infinitezimală, adică $ \Delta x \to dx $. Rezultă că raportul care calcula
viteza medie acum calculează o viteză instantanee, pe care o notez simplu cu $ v $:
$$
    v = \dfrac{dx}{dt}.
$$

Dar asta este chiar definiția pentru derivata funcției $ x(t) $, sub o altă notație, pentru că:
$$
    x^\prime(t) = \lim_{t \to t_0} \dfrac{x(t) - x(t_0)}{t - t_0} = \dfrac{dx(t)}{dt}.
$$

Situația nu este o coincidență, pentru că, mai ales în fizică, întâlnești adesea
derivatele notate ca raport de diferențiale. Este, într-un fel, notația mai explicită,
pentru că îți arată că derivata înseamnă, concret, un raport de variații infinit de mici.
Astfel, $ f^\prime(x) = \dfrac{df}{dx} $, unde nu mai este neapărat necesar să pui și argumentul
lui $ f $ în notația diferențială ($ df(x) $), pentru că el se deduce din numitorul raportului.

Acum, cu aceste preliminarii, să-ți arăt rolul lui $ dx $ într-o integrală. Suplimentar,
o să înțelegi mai bine și metoda schimbării de variabilă pentru calculul integralelor definite.

---

## dx-ul din integrale

Poate ai auzit una dintre explicațiile pragmatice, că $ dx $-ul de la
integrală îți arată unde se termină integrala sau că îți arată care este
variabila în raport cu care integrezi, în cazul în care ai o funcție
care conține parametri.

Prima „explicație” este aproape o glumă, pentru că unii fizicieni
(și nu numai) pun diferențiala la începutul integralei, adică scriu
$ \displaystyle\int dx \ x^2 + 5 $, de exemplu. Oricât ți s-a explicat
la clasă că diferențiala trebuie scrisă
la final, argumentele riguroase nu sunt de acord. O notație de forma
$ \displaystyle\int f(x) \ dx $ înseamnă, concret, integrală din $ f(x) $
*înmulțit cu* $ dx $. Și, cum înmulțirea este comutativă, este la
fel de corect să scrii și $ \displaystyle\int dx \ f(x) $.

A doua „explicație” merită luată în seamă, totuși, pentru că,
într-adevăr, poți avea de calculat primitiva unei funcții cu parametri,
de forma $ f_m(x) = mx^2 + 2x + 3 $. Dacă integrezi în raport cu $ x $,
adică scrii $ \displaystyle \int f_m(x) \ dx $, obții un rezultat,
care este diferit de integrarea în raport cu $ m $, adică de
$ \displaystyle \int f_m(x) \ dm $.
$$
\begin{align*}
    \int mx^2 + 2x + 3 dx &= \dfrac{mx^3}{3} + x^2 + 3x + \mathcal{C} \\
    \int mx^2 + 2x + 3 dm &= \dfrac{m^2x^2}{2} + 2mx + 3m + \mathcal{C}.
\end{align*}
$$

Iar când vei ajunge să studiezi
funcții de mai multe variabile, devine chiar esențial să știi care
este variabila de integrare. De pildă, $ \displaystyle\int x + y \ dx $
și $ \displaystyle \int x + y \ dy $ sunt două integrale complet diferite
și ambele au sens, pentru scopuri diferite.

Acum pentru rolul exact al lui $ dx $. O să-ți explic atât în cazul primitivelor
(integralelor nedefinite), cât și pentru integrale definite (Riemann).
Prima situație este o formalitate, a doua are o interpretare grafică.

### În primitive

Cel mai important lucru de reținut aici este că operația de integrare
este inversa operației de derivare. Altfel spus, integrala unei funcții derivate
este egală cu derivarea unei funcții integrate și ambele sunt egale cu funcția
respectivă. În simboluri:
$$
    \int f^\prime(x) \ dx = \left( \int f(x) \ dx \right)^\prime = f(x), \forall x.
$$

Însă mai sus ți-am arătat că o altă notație pentru $ f^\prime(x) $ este
raportul $ \dfrac{df}{dx} $. Dacă înlocuiești scrierea asta în primul membru
al egalității anterioare ai:
$$
    \int \dfrac{df(x)}{dx} \ dx = \int df(x) = f(x), \forall x,
$$
ceea ce arată exact mecanismul anunțat. Operația de integrare inversează
efectul operației de derivare.

Observă că în deducerea acestui fapt, am folosit că $ \dfrac{df(x)}{dx} $
este un simplu raport, așa că am putut simplifica $ dx $.

Acum, în general, când vrei să calculezi $ \displaystyle \int f(x) \ dx $,
adică primitiva funcției $ f $, îți răspunzi la întrebarea *Ce funcție
derivată produce $ f(x) $?* Altfel spus, dacă $ F $ este o primitivă a funcției $ f $,
atunci $ \displaystyle \int f(x) \ dx = F(x) + \mathcal{C} $ și $ F^\prime(x) = f(x), \forall x $.

Și această ultimă egalitate poate fi scrisă cu notația diferențială, adică
$ \dfrac{dF(x)}{dx} = f(x), \forall x $. Când înlocuiești în integrală, ai:
$$
    \int \dfrac{dF(x)}{dx} \ dx = \int dF(x) = F(x) + \mathcal{C},
$$
pentru că rolul integralei este ca operația de *undo* aplicată derivării.

Concluzia este că nu contează dacă pui diferențiala ($ dx $ sau $ dt $ sau orice
altă variabilă de integrare ai) la începutul sau la finalul integralei,
dar ea trebuie obligatoriu scrisă. În lipsa ei, integrala pur și simplu nu are
sens, pentru că este o operație de inversare a diferențierii aplicată unui
obiect matematic care *nu este o diferențială*, ci un raport.

### În integrale definite

Știi deja că integrala definită, de la $ a $ la $ b $, a unei funcții
$ f : [a, b] \to \mathbb{R} $ calculează aria suprafeței delimitate
de graficul funcției $ f $, axele de coordonate și verticalele $ x = a $
și $ x = b $. Dar de ce și cum intervine $ dx $ în explicația asta?

Construcția care explică legătura se datorează matematicianului german
Bernhard Riemann (1826-1866). Este un exemplu excelent
de formulare riguroasă a unei construcții, de altfel, intuitive
și care a ajuns să fie foarte importantă în inginerie și informatică,
unde calculele aproximative sunt singura șansă când lucrezi cu numere
și funcții reale.

O curbă o poți gândi ca fiind alcătuită din fragmente de segment,
cu cât mai mici și mai multe, cu atât aproximația este mai bună.
Asta înseamnă că aria suprafeței care are una dintre laturi o curbă
și celelalte trei laturi drepte se poate aproxima cu o sumă a unor arii
de dreptunghiuri sau trapeze — la fel, cu cât mai multe și mai mici,
cu atât aproximația este mai bună.

<figure id="fig-riemann">
{{< svgfig src="dx_fig1.svg" alt="Construcția integralei definite ca arie: dreptunghiuri sub graficul unei funcții, cu punctele intermediare ξₖ și valorile f(ξₖ) marcate" style="width:90%" >}}
<figcaption>Construcția integralei definite ca arie</figcaption>
</figure>

Un exemplu de construcție ai în figura de mai sus, dar sunt și alte elemente
care trebuie explicate. Toate în încercarea de a face ca suma ariilor dreptunghiurilor
să aproximeze cât mai bine aria suprafeței cu o latură curbă.

Îți explic elementele tehnice, cu referire la desenul din figură.
Să zicem că ai de calculat $ \displaystyle\int_a^b f(x) \ dx $, deci
aria suprafeței delimitate de graficul unei funcții $ f $, axele de
coordonate (axa $ Ox $ în cazul acesta) și verticalele $ x = a $
și $ x = b $.

Ca să împarți suprafața în dreptunghiuri, ai nevoie de o *diviziune*
a intervalului $ [a, b] $, care în manuale se notează cu $ \Delta $.
Practic, $ \Delta $ este o mulțime de puncte alese în intervalul
$ [a, b] $, astfel încât să înceapă cu $ x_0 = a $ și să se termine cu $ x_n = b $,
unde $ n + 1 $ este numărul total de puncte. Cu cât ai mai multe puncte,
cu atât mai bine.

Aceste puncte pot fi luate arbitrar, nu este necesar să fie uniform distribuite,
adică distanțele între două puncte consecutive pot fi oricât. Tocmai de aceea,
se definește *norma* diviziunii $ \Delta $, notată $ ||\Delta|| $,
ca fiind cea mai mare distanță dintre două puncte consecutive:
$$
    || \Delta || = \max(x_{k + 1} - x_k), \quad k \in \{ 0, 1, 2, \dots, n - 1 \}.
$$

Dreptunghiurile care se formează au toate una dintre laturi de lungime calculată
sub forma
$ x_{k + 1} - x_k $, cu $ k \in \{ 0, 1, 2, \dots, n - 1 \} $.
Cealaltă latură poți să o iei pur și simplu $ f(x_k) $ sau $ f(x_{k + 1}) $,
dar dacă funcția are variații mari, e posibil să conteze foarte mult
ce alegere faci. Tocmai de aceea, se alege încă un punct între $ x_k $
și $ x_{k + 1} $. Mai precis, se alege un *sistem de puncte intermediare*,
$$
    \left\{ \xi_1 \in (x_0, x_1), \xi_2 \in (x_1, x_2), \dots, \xi_n \in (x_{n - 1}, x_n) \right\},
$$
care pot să fie la mijloc sau tot arbitrar.

Ariile dreptunghiurilor se aproximează acum prin produse de tipul $ \left( x_{k + 1} - x_k \right) \cdot f(\xi_{k + 1}) $.

Dacă calculezi suma tuturor, obții aproximația dorită pentru aria de sub grafic, pe care o notez cu $ \mathcal{A} $:
$$
    \mathcal{A} = \displaystyle\sum_{i = 0}^{n - 1} \left( x_{i + 1} - x_i \right) \cdot f(\xi_{i + 1}).
$$

Aria exactă o obții prin trecere la limită, adică atunci când presupui că
unele lucruri de aici sunt infinite la număr sau infinit de mici. Mai precis:

- $ n \to \infty $, bineînțeles, ca să fii sigur că iei cât de multe puncte e posibil;
- $ || \Delta || \to 0 $, astfel încât și în cel mai rău caz, tot ai o latură de tipul
    $ x_k x_{k + 1} $ foarte mică.

În aceste ipoteze, suma de mai sus, prin trecere la limită, devine integrala definită,
în sens Riemann:
$$
    \int_a^b f(x) \ dx = \lim_{n \to \infty, || \Delta || \to 0}
    \displaystyle\sum_{i = 0}^{n - 1} \left( x_{i + 1} - x_i \right) \cdot f(\xi_{i + 1}).
$$

Din punctul de vedere al notației, de altfel, semnul de integrală nu este
decât un S alungit, care notează o sumă. Iar când $ \xi_i $ parcurg toate
intervalele din diviziunea $ \Delta $, e clar că aproximează parcursul lui
$ x $ în intervalul $ [a = x_0, b = x_n ] $.

De unde vine dx? Păi, dacă $ || \Delta || \to 0 $,
asta înseamnă că și cea mai mare diferență, de forma $ x_{i + 1} - x_i $ tinde la zero,
adică toate $ x_i \to x_{i + 1} $, ceea ce este întocmai definiția diferențialei:
diferența dintre două valori care tind una către cealaltă.

### Bonus: Schimbarea de variabilă

Acum pentru rolul diferențialei în metoda de integrare prin
schimbare de variabilă, voi folosi un exemplu:
$$
    \int \dfrac{\ln x}{x} \ dx.
$$

Calculul este foarte simplu, îmi propun doar o explicație tehnică.

Când faci schimbarea de variabilă $ t = \ln x $, de fapt introduci
o *funcție*, $ t(x) = \ln x $. Dacă ai înlocui-o direct așa
în primitivă, ai obține:
$$
    \int \dfrac{t(x)}{x} \ dx,
$$
care e același lucru. Ai făcut doar o notație, ca o scurtătură de tastatură.

Ca să devină o substituție pe care să o și poți folosi, ai nevoie să
schimbi și diferențiala, pentru că noua integrală ai vrea să calculeze
primitiva funcției $ t $. Trebuie, de aceea, să apară undeva în noua
integrală și diferențiala $ dt $.

Tehnica cere să calculezi derivata noii funcții, adică
$ t^\prime(x) = \dfrac{1}{x} $, ceea ce se poate scrie
cu notația diferențială ca $ \dfrac{dt}{dx} = \dfrac{1}{x} $.
Cum asta este o simplă egalitate de *fracții*, poți să obții pe $ dt $
de aici, $ dt = \dfrac{dx}{x} $. Acum:
$$
    \int \dfrac{\ln x}{x} \ dx = \int \ln x \cdot \dfrac{dx}{x} \to \int t \cdot dt.
$$

Aici intervine un detaliu tehnic mai dificil, care o să-ți explice și de ce mai sus
nu mai avem egalitate, ci o transformare (pe care am notat-o generic prin $ \to $).

Singurul mod în care poți evalua această integrală, în care are sens, este să
cauți să scrii pe $ t $ ca fiind derivata *unei funcții de $ t $, nu de $ x $*,
de aceea nu l-am mai scris pe $ x $ în $ t(x) $ și nici nu s-a mai păstrat egalitatea.
Cu alte cuvinte, trebuie să te gândești ce funcție *de $ t $* dă, prin derivare,
$ t $, iar răspunsul este $ \dfrac{t^2}{2} + \mathcal{C} $.

Riguros, ar trebui să presupunem că există o primitivă a lui $ t $, pe care o notăm cu $ T $,
astfel încât $ \dfrac{dT(t)}{dt} = t $ și atunci integrala de calculat devine:
$$
    \int t \cdot dt = \int \dfrac{dT}{dt} \cdot dt = \int dT = T(t) + \mathcal{C}.
$$

Observă că, în final, am ajuns să calculăm primitiva altei funcții față de cea
cu care am plecat. Funcția *de $ t $* care prin derivare dă $ t $ nu este același lucru
cu funcția *de $ x $* care prin derivare dă $ \dfrac{\ln x}{x} $.
Asta pentru că litera pe care o folosești pentru variabilă este irelevantă, deci, de fapt,
comparăm primitiva lui $ x $ cu primitiva lui $ \dfrac{\ln x}{x} $, care, evident, diferă.

Numai că procedura de schimbare de variabilă are un as în mânecă. Putem face substituția
înapoi *ca funcție*. Cu alte cuvinte, $ \dfrac{t^2}{2} $ înseamnă, ca funcție,
$ \dfrac{\ln^2 x}{2} $, care este, într-adevăr, o primitivă pentru $ \dfrac{\ln x}{x} $.

---

<span
style="font-family:'Switzer', 'Arial', 'San Francisco', sans-serif;weight: 600;font-size:1.1rem;letter-spacing:0.01rem;">
<b><a href="/documents/ce_este_dx.pdf">Descarcă versiunea PDF</a></b>
</span>
