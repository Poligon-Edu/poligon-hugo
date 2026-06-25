+++
title = "LaTeX"
type = "docs"
slug = "latex"
bookHidden = true
+++

# LaTeX
TeX și varianta sa actualizată, LaTeX, au o istorie de peste o jumătate de secol.
În anii 70, americanul Donald Knuth, care lucra la o carte, devenită între timp
biblia analizei algoritmilor (*The Art of Computer Programming*), a fost nemulțumit
de sistemele de tehnoredactare ale vremii.

Așa a ajuns să creeze propriul limbaj de programare, TeX, și, odată cu el,
o nouă paradigmă de programare: *programarea literară*. Conform acesteia,
nu există diferență între documentație și cod; limbajele de programare
trebuie să fie clare și ușor de citit și pentru oameni și, în același timp,
structurile algoritmice să fie documentate cât mai detaliat.

Conaționalul lui Knuth, Leslie Lamport, i-a preluat ideile, pe care
le-a modernizat în sistemul pe care îl folosim astăzi, LaTeX. Lizibilitatea
s-a păstrat, astfel încât multe comenzi și cuvinte-cheie sunt, de fapt,
cuvinte obișnuite în engleză. De exemplu:
- `\rightarrow` desenează o săgeată în dreapta, $\rightarrow$;
- `\longrightarrow` desenează o săgeată similară, dar mai lungă, $\longrightarrow$;
- `\frac{a}{b}` este fracția $\frac{a}{b}$;
- literele grecești sunt scrise ca în transliterarea obișnuită: `\alpha` ($\alpha$),
`\beta` ($\beta$), `\gamma` ($\gamma$) și așa mai departe.

O listă lungă, dar nu completă, a unor simboluri găsești [aici](https://oeis.org/wiki/List_of_LaTeX_mathematical_symbols).

Spre deosebire de [Markdown]({{< relref path="/materiale/floss/markdown.md" lang="ro" >}}),
însă, LaTeX este gândit în primul rând pentru print, adică pentru PDF.
Este formatul pe care îl produce cel mai simplu, dar, din fericire, sintaxa a fost
preluată și de sisteme web, astfel încât astăzi îl găsești integrat în Markdown.

O să-ți arăt, în continuare, o scurtă introducere în LaTeX pentru PDF, așa cum
a fost el gândit, iar apoi, cum îl poți folosi în Markdown, cu sau fără 
[pandoc]({{< relref path="/materiale/floss/pandoc.md" lang="ro" >}}).

## Utilizare locală ⇒ PDF
Cel mai simplu (dar nu și cel mai rapid) mod ca să începi să folosești
LaTeX este să instalezi un compilator local. Practic, este vorba despre
„creierul” care convertește codul tău în PDF, la o simplă comandă.

O alternativă este să folosești direct servicii online, ca [Overleaf](https://www.overleaf.com/),
dar acelea vin cu propriile dezavantaje, așa că te las să le explorezi
individual dacă vrei.

### Compilatoare

Compilatorul de LaTeX este gratuit, open source, și disponibil pe toate
sistemele de operare, doar că se instalează diferit:
- pentru Windows, trebuie să instalezi [MikTeX](https://miktex.org/);
- pentru macOS, ai [MacTeX](https://tug.org/mactex/mactex-download.html);
- pentru Linux, varianta completă este [texlive](https://tug.org/texlive/).

Dacă vrei varianta completă, cu absolut toate opțiunile posibile, așteaptă-te 
la un download de aproximativ 10 GB.
Pentru sistemele Linux de tip Fedora, poți instala tot pachetul cu comanda:
```sh
sudo dnf install *texlive*
```

MikTeX vine deja cu destul de multe pachete, dar va instala suplimentar, din mers,
ce are nevoie. Iar MacTeX vine deja echipat cu majoritatea pachetelor, deci
e vorba de o instalare de 6-8 GB.

După instalare, reține că acum ai disponibil doar „transformatorul”, mașinăria
care convertește un fișier-sursă în PDF. Dar pe acesta din urmă
trebuie să-l creezi separat, cu ajutorul unui editor.

### Editoare
Dacă nu vrei să instalezi nimic, poți să continui cu Notepad (Windows),
TextEdit (macOS), Vim sau orice editor ai deja instalat. Câștigi
simplitate, dar pentru un utilizator începător, dacă nu știi ce cum să
introduci unele simboluri, interfața este complet goală.

Așa că, la început, îți recomand să începi cu unul dintre următoarele editoare gratuite:
- [VSCode](https://code.visualstudio.com/), disponibil pe toate sistemele de operare.
Îți mai recomand să instalezi și extensia 
[LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop), 
care adaugă multe îmbunătățiri interfeței vizuale;
- [TeXnicCenter](https://www.texniccenter.org/), disponibil pe Windows;
- [TeXMaker](https://www.xm1math.net/texmaker/), disponibil pe toate sistemele de operare;
- [TeXStudio](https://www.texstudio.org/#download), disponibil pe toate sistemele de operare.


### Exemple (MWE)
Odată instalat editorul, deschide-l și creează un fișier nou, cu extensia `.tex`.
Apoi copiază în el codul de mai jos (sau descarcă direct fișierul de [aici](/documents/mwe.tex)):

```tex
\documentclass[a4paper]{article}

\usepackage{amsmath,amssymb,amsthm}

\begin{document}

\begin{center}
    {\Huge \textbf{Primul meu document} \LaTeX}
\end{center}

\vspace{1cm}

Aceasta este formula de rezolvare a ecuației de gradul al doilea,
care are forma canonică $ ax^2 + bx + c = 0, a, b, c \in \mathbb{R}, a \neq 0 $:

\[
    x_{1,2} = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
\]

\end{document}
```

Astfel de exemple se numesc, în terminologia pe care o vei găsi
pe forumurile de discuții specifice MWE, sau *minimal working examples*,
adică exemple de conținut, dar care au inclus tot ce le trebuie încât
să funcționeze. Nu se obișnuiește postarea fragmentelor din fișiere, pentru
că o eventuală problemă poate să se datoreze unei porțiuni din sursă
care se află în altă parte.

Dacă te uiți cu atenție la codul-sursă, cred că poți intui imediat cum funcționează
diverse elemente de sintaxă:
- `\documentclass` declară tipul de document pe care îl vom scrie, în cazul acesta, un articol (`article`),
iar opțiunea dintre paranteze pătrate nu este obligatorie. I-am specificat să formateze pentru o pagină A4.
- `\usepackage` cheamă pachetele strict necesare. Cele trei incluse de mine sunt folosite
în aproape orice document vrei să incluzi niște matematică. Sunt create pe modelul
Societății Americane de Matematică (AMS), de aceea sunt precedate de `ams`.
- Orice document începe cu `\begin{document}` și se încheie cu `\end{document}`. Tot conținutul
de dinainte de `\begin{document}` se numește *preambul*.
- Am creat un titlu, scris centrat, prin `\begin{center} ... \end{center}`.
- Textul titlului a fost scris mare, prin comanda `\Huge`. Există și alte dimensiuni,
ca `\large, \Large, \huge, \big, \Big` și nu numai. Le poți testa pe fiecare.
- Textul este îngroșat, cu comanda `\textbf`, de la *text bold font*. Dacă-l vrei
înclinat, poți folosi `\textit` (de la *text italic*) sau `\emph` (de la *emphasized*).
- Am adăugat spațiu vertical de 1cm, cu `\vspace{1cm}`.
- Textul propriu-zis se scrie normal, iar când vrei să incluzi matematică, o delimitezi prin `$...$`.
- Dacă vrei matematică scrisă separat, pe un rând și centrată, o delimitezi prin `\[ ... \]`.
- Simbolurile din formulă ar trebui să fie clare: `\frac` scrie o fracție, `\pm` scrie $\pm$, 
`\neq` scrie $\neq$, iar `\sqrt` scrie un radical.
- Observă că delimitările se fac prin acolade, nu paranteze sau alte simboluri. Când vrei să izolezi
conținutul, îl incluzi între acolade. La titlu, de exemplu, dacă nu-l delimitam între acolade,
opțiunile `\Huge` și `\textbf` se aplicau întregului document.

### Compilează și prelucrează
Transformarea codului-sursă din fișierul `mwe.tex` într-un PDF se numește *compilare*.
Fiecare editor dintre cele menționate are câte un buton sau opțiunea de compilare,
dar diferă de la o interfață la alta.

De exemplu, în VSCode, ai scurtătura de tastatură `shift + ctrl + b`.
În TeXMaker, ai comanda din meniu Quick Build.

Dar, dacă vrei să lucrezi independent de editoare, poți să invoci compilatorul
instalat direct din terminal, cum am lucrat și cu [pandoc]({{< relref path="/materiale/floss/pandoc.md" lang="ro" >}}).

Deschide Command Prompt sau Windows Terminal sau aplicația ta preferată
de terminal, navighează în directorul unde ai salvat fișierul `.tex` și
cheamă compilatorul direct:

```sh
$ pdflatex mwe.tex
```

Vei primi multe mesaje care îți arată cum lucrează compilatorul, iar la final
(după nici o secundă), vei avea un fișier `mwe.pdf` în același director,
care conține o foaie A4 cu textul introdus de tine în cod.

![mwe-latex](/images/mwe_latex.png)

Dacă ai greșit ceva sau vrei să modifici, deschizi din nou fișierul-sursă `mwe.tex`
și modifici în el, apoi îl compilezi din nou și PDF-ul se va actualiza.

Există moduri diverse de lucru care îmbunătățesc situația și în care
nu e nevoie să tot sari de la `.tex` la terminal, la `.pdf` și înapoi.
Îți vorbesc pe scurt despre ele [mai jos](#alte-resurse).

## Integrare în Markdown și Pandoc
LaTeX este atât de popular, încât a fost integrat în Markdown și Pandoc
și nu e nevoie să lucrezi mereu cu toate uneltele anterioare.

Multe motoare web au inclus biblioteci specifice care să-ți permită să
scrii LaTeX direct în sursa Markdown, iar [Dillinger](https://dillinger.io/), de exemplu,
este un editor care are suport și pentru matematică.

Astfel, poți să scrii într-un fișier Markdown fragmente cu cod LaTeX pentru text
matematic. Delimitează cu `$...$` pentru matematica în rând cu textul obișnuit
sau cu `\[...\]` pentru matematică scrisă separat.

De exemplu, documentul `.tex` de mai sus se poate scrie (aproximativ) la fel
în Markdown așa:

```md
# Primul meu document $\LaTeX$

Aceasta este formula de rezolvare a ecuației de gradul al doilea,
care are forma canonică $ax^2 + bx + c = 0, a, b, c \in \mathbb{R}, a \neq 0$:

\[
    x_{1,2} = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
\]
```

Observă că, spre deosebire de fișierele `.tex`, în Markdown *nu* trebuie
să pui spații după și înainte de `$` în textul matematic. Altfel, vei avea erori.

Dacă primești alte erori sau documentul nu arată la fel în Dillinger, este
pentru că această metodă nu-ți dă acces la preambul și la alte fragmente
de cod cu care ai putea să personalizezi aspectul, fonturile sau bibliotecile
necesare.

De aceea, dacă vrei să folosești această metodă, depinzi de implementarea
LaTeX a celor care au făcut motorul web (o bibliotecă Javascript, de fapt),
pe care o poți personaliza, mai greu sau mai ușor, dacă știi limbajul specific.

[Pandoc]({{< relref path="/materiale/floss/pandoc.md" lang="ro" >}}), dacă l-ai
instalat, folosește compilatorul local de LaTeX (trebuie să-l fi instalat și pe acela,
vezi [mai sus](#compilatoare)).

Așa că poți scrie într-un fișier `.md`, îl salvezi local, apoi chemi `pandoc`
să ți-l convertească în PDF:

```sh
$ pandoc -s mwe.md -o mwe.pdf
```

Flexibilitatea Pandoc este imensă, mai ales că lucrează cu opțiunile
și compilatorul local. Poți să specifici un fișier de preambul, poți
să adaugi oricâte opțiuni dorești, încât, practic, refaci sau chiar
îmbunătățești modul de lucru cu fișierul `.tex` direct.

## Alte resurse
- Overleaf are un [ghid LaTeX în 30 minute](https://www.overleaf.com/learn/latex/Learn_LaTeX_in_30_minutes);
- Indiferent de editorul folosit, există un motor de sincronizare a codului sursă cu PDF-ul.
Se numește SyncTeX și găsești mai multe informații de exemplu [aici](https://tex.stackexchange.com/questions/118489/what-exactly-is-synctex) sau dacă vei căuta numele editorului tău + SyncTeX (exemplu: "TeXMaker SyncTex").
- Poți specifica foarte multe opțiuni de preambul cu Pandoc. De exemplu:

```sh
$ pandoc -N --variable "geometry=margin=1.2cm" \
--variable mainfont="Times New Roman" \
--variable sansfont="Calibri" --variable fontsize=12pt \
--include-in-header fancyheaders.tex \
--toc -s mwe.tex -o mwe.pdf`
```

Mai multe în [documentația pandoc](https://pandoc.org/demos.html).

---

Întoarce-te la ghidurile noastre 👉 [aici]({{< relref path="/materiale/floss/_index.md" lang="ro" >}}).
