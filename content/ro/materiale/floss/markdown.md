+++
title = "Markdown"
type = "docs"
slug = "markdown"
bookHidden = true
+++

# Markdown
## Ce este și cum a apărut?
Textele de pe internet, ca toate paginile, de altfel, se bazează pe un
limbaj de programare specific, inventat la CERN în 1993, de către
Tim Berners-Lee: HTML.

Riguros vorbind, nu este un limbaj *de programare*, ci unul pentru
*„marcaj”*, care controlează conținutul și aspectul, dar nu poate să
calculeze, de exemplu, sau să exprime algoritmi, cum o fac limbajele
de programare. Acronimul HTML o arată clar: *HyperText Markup Language*,
adică un limbaj care marchează ceva mai mult decât text, un fel de hiper-text.

În timp, programatorii au început să automatizeze aceste marcaje și să
le separe, în cea mai mare parte, de textul propriu-zis. Unul dintre
motive este claritatea. Dacă tot scriem text, ca acest articol, am vrea
să fie lizibil pentru ochiul uman, nu doar pentru computer.

De exemplu, formatul HTML putea să arate cam așa:

```html
<!DOCTYPE html>
<head></head>
<body>
<h1>Markdown</h1>
<p>Textele de pe internet, ca toate paginile, de altfel, se bazează
pe un <i>limbaj de programare specific</i>.</p>
<br/>
<br/>
<p>Riguros vorbind...</p>
</body>
</html>
```

Pentru un exemplu simplu, nu e greu de citit, dar când documentele
deveneau complicate, etichetele închise și deschise (acele `<tag>` și `</tag>`)
pentru fiecare instrucțiune încarcă vizual.

Așa a apărut un format mult simplificat, care a prins rapid în special
printre scriitori, publiciști, bloggeri și programatorii care aveau 
de scris documentație: Markdown. Inventat de jurnalistul John Gruber
în 2004, Markdown a devenit rapid limbajul cel mai folosit de cei care
publică în primul rând pe internet. Asta pentru că „sursa” Markdown
se bazează tot pe „etichete”, doar că mai puține și mai clare, pe care
un program separat le convertește în HTML.

De exemplu, etichetele de la început nu mai sunt necesare, pentru că
oricum se adaugă fiecărui document, așa că pot fi automatizate,
iar textul ajunge să arate foarte curat. Aceleași paragrafe de mai sus
se scriu cu Markdown așa simplu și direct:

```md
# Markdown

Textele de pe internet, ca toate paginile, de altfel, se bazează
pe un *limbaj de programare specific*.

Riguros vorbind...
```

## Elemente de sintaxă
Markdown este limitat intenționat la elementele de sintaxă care ar folosi
majorității bloggerilor. Poți formata titlul, subtitlul, titluri de secțiuni
și subsecțiuni, text înclinat (italic) sau îngroșat (bold), tabele, poți
include imagini, link-uri, surse de cod, paragrafe cu citate, liste și...
[cam atât](https://www.markdownguide.org/basic-syntax/).

Dar, pentru că Markdown se transformă automat în HTML, se poate îmbogăți
direct cu codul specific. Dacă vrei să adaugi o proprietate care nu este
inclusă în Markdown, cum ar fi textul colorat, poți să o codifici
direct cu HTML-ul corespunzător. Scrii

```html
<span style="color:red;">text roșu</span>
```

și ai obținut <span style="color:red;">text roșu</span>.

Markdown în sine nu a evoluat foarte mult de la introducerea din 2004.
S-a schimbat, de exemplu, modul în care marchezi textul înclinat (italic).
În forma inițială, trebuia să folosești *underscore*, adică `_așa_`,
în timp ce astăzi, se preferă steluțele, adică `*așa*`. Totuși, ambele
variante încă sunt suportate, de aceea le vei vedea pe amândouă.

Ce s-a schimbat cel mai mult este modul în care este procesat. Astfel, diverse
platforme online includ scripturi care procesează și mai multe elemente
decât conține Markdown, dar tot fără să fie nevoie să scrii HTML-ul complicat.
Asta pentru că

> Filosofia de bază a Markdown este să separi conținutul (textul) de aspect.

Acest website, de exemplu, se bazează pe platforma [Hugo](https://gohugo.io/),
iar textul pe care îl citești acum este scris cu Markdown, dar într-o variantă
îmbogățită față de cea propusă de Gruber. În continuare 
[sursa este lizibilă](https://github.com/Poligon-Edu/poligon-hugo/blob/main/content/ro/materiale/floss/markdown.md)
dar pot adăuga și matematică:

$$
\int_a^b f(x) dx = F(x) \mid_a^b = F(b) - F(a).
$$

$$
\begin{vmatrix}
a & b \\
c & d
\end{vmatrix}
= ad - bc, \forall a, b, c, d \in \mathbb{C}.
$$

## La ce-mi trebuie?
De mai mulți ani, Markdown este *lingua franca* a internetului și a 
aplicațiilor web. Este suportat în WhatsApp, GMail, Discord, GitHub
și multe alte platforme care se bazează pe unelte web.

![whatsapp_markdown](/images/whatsapp_markdown.png#center)

Dar ți-l propun ca *unealtă educațională*, pentru că nu trebuie
să fii blogger ca să beneficiezi de ajutorul lui.

De exemplu, ChatGPT, Gemini, Claude și toate LLM-urile răspund
în format Markdown. Când copiezi textul unui răspuns într-un
fișier text simplu, care nu suportă text formatat (adică `.txt`,
creat cu Notepad în Windows, de pildă, nu `.odt` sau `.docx`),
vei vedea sursa Markdown. Ca în imaginea de mai jos, unde în
partea stângă vezi răspunsul lui Gemini la o problema de matematică
în format Markdown (îmbogățit cu matematică), iar în partea dreaptă
vezi textul procesat, cum ar arăta dacă l-ai încărca pe o platformă
online care suportă Markdown sau pe propriul blog.

![adrian_vscode](/images/adrian_vscode.png)

Însă poți să folosești Markdown și dacă nu intenționezi să publici sau să
trimiți nicăieri documentul. Principalul avantaj este că, atunci când creezi
un fișier specific (cu extensia `.md`), el se salvează exact ca un fișier
text simplu. De aceea, poate fi deschis cu absolut orice program, pe orice
sistem de operare, fără să depindă de formatare și procesare cum aplică
Word sau derivatele lui.

La fel este și cazul LaTeX, pe care ți-l prezint ceva mai încolo, dar
dacă ai folosit Word de mai bine de zece ani, ai văzut cum formatul
s-a tot îmbogățit (sau, mai bine zis, s-a „îngrășat”) cu caracteristici
care fac încât fișierul `.docx` să fie un pachet tot mai mare. Afișajul perfect,
așa cum l-ai scris, este asigurat doar dacă îl deschizi fix cu aceeași versiune
de Word cu care a fost creat și chiar și atunci, poți avea surprize ca unele
fonturi, culori, aranjare în pagină să fie corupte. Nu mai vorbim de formatul
mai vechi `.doc`, cu care încă lucrează multă lume, inclusiv instituțiile
statului român.

Nici Google Docs nu o duce mult mai bine, dacă te uiți cu atenție la funcțiile lui.

Prin comparație, fișierele Markdown sunt text simplu. Se concentrează pe conținut,
pe care îl separă de formatare și aranjare în pagină. Tocmai de aceea, când folosești
Markdown, nu are sens să te gândești la marginile paginilor, mărimea alineatului,
fontul folosit, mărimea textului chiar. *Pur și simplu scrii. Toate celelalte lucruri
sunt rezolvate separat.*

În plus, pentru că celelalte sarcini sunt separate și uniforme (ai vrea, probabil, ca
toate documentele pe care le scrii să arate la fel), ele pot fi automatizate. Este suficient
să petreci timp cât să aranjezi procesorul pentru un document și apoi, doar îl aplici
și celorlalte — o metodă mai complicată la început, dar mai eficientă ulterior decât
crearea unor *template*-uri în Word.

## Încearcă și tu
### Un editor online
Poți să nu descarci nimic și doar să testezi un editor online.
Îți recomand [Dilinger](https://dillinger.io/).

### Lucrează local
Dacă vrei să lucrezi local și offline, vestea bună este că *nu ai nevoie de niciun editor*.
Pe Windows, poți pur și simplu să creezi un fișier nou în Notepad și să-l salvezi cu extensia `.md`
în loc de `.txt`. La fel și pe celelalte sisteme de operare: folosește ce program vrei (TextEdit pe macOS,
editorul tău preferat pe Linux sau BSD) și creează un fișier, de exemplu, `test.md`. Scrie în el
ce vrei sau copiază din sursa acestui fișier:

```md
## Încearcă și tu
### Un editor online
Poți să nu descarci nimic și doar să testezi un editor online.
Îți recomand [Dilinger](https://dillinger.io/).

### Lucrează local
Dacă vrei să lucrezi local și offline, vestea bună este 
că *nu ai nevoie de niciun editor*.
Pe Windows, poți pur și simplu să creezi un fișier 
nou în Notepad și să-l salvezi cu extensia `.md`
în loc de `.txt`. La fel și pe celelalte sisteme de 
operare: folosește ce program vrei (TextEdit pe macOS,
editorul tău preferat pe Linux sau BSD) și creează 
un fișier, de exemplu, `test.md`. Scrie în el ce vrei.
```

### Transformă cu VSCode
Fișierul salvat, `test.md`, nu va arăta diferit, decât dacă folosești un editor
care conține unelte de procesare Markdown. Un exemplu, disponibil gratuit pe toate
sistemele de operare, este [VSCode](https://code.visualstudio.com/). 
După ce îl instalezi, ai nevoie de o extensie specifică, pe care o descarci
gratuit [de aici](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one).

Apoi, deschide fișierul cu el, apoi apasă `ctrl-shift-p` și alege opțiunea 
`Markdown: Open preview to the side`.
Ecranul se va împărți în două și în partea dreaptă vei vedea textul transformat.

![vscode_md_preview](/images/vscode_md_preview.png)

### Exportă și salvează
Totuși, textul transformat pe care ți-l arată VSCode nu este salvat.
El este afișat doar cât timp ai și sursa `md` deschisă. Când vrei să și salvezi
varianta transformată, o poți face în mai multe moduri.

Dacă ai ales să scrii cu Dilinger, meniul lui conține deja opțiuni de export.
La fel și dacă ai scris local, poți să copiezi textul în Dillinger și să-i
folosești doar opțiunea de export.

![dillinger_export](/images/dillinger_export.png#center)

În funcție de nevoi, poți exporta în HTML (alege opțiunea *Styled HTML* dacă
vrei să arate fix așa cum îl vezi) sau PDF, dacă vrei un document cu un format
cu care te-ai obișnuit.

Pentru o soluție locală și ultraperformantă, care nu te limitează la HTML și PDF
și produce chiar și documente Word, îți recomand [`pandoc`](https://pandoc.org/), 
despre care îți spun mai multe într-un [articol separat]({{< relref path="materiale/floss/pandoc.md" lang="ro" >}}).
