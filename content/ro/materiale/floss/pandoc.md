+++
title = "Pandoc"
type = "docs"
slug = "pandoc"
bookHidden = true
+++

# Pandoc
## Argument
Filosoful [John MacFarlane](https://johnmacfarlane.net/tools.html) este autorul `pandoc`,
pe care l-a creat în 2006 ca să convertească între mai multe tipuri de formate text.

Eu îl folosesc cel mai des ca să lucrez cu [markdown]({{< relref path="/materiale/floss/markdown.md" lang="ro" >}}),
din care obțin, după nevoi, formate stil Word sau PDF.

Argumentul principal de ce l-ai folosi *tu* este că îți permite să lucrezi 100% offline
și simplu, în felul acesta:
- scrii textul în format markdown, cu toate avantajele lui: te concentrezi pe 
conținut, salvezi într-un fișier *plain text*, totul rapid și fără software complicat;
- convertești sursa markdown în ce format ai nevoie acum. Dacă îți faci un *template*
(document-model), atunci `pandoc` poate să-l folosească și-ți produce automat
toate fișiere să arate la fel. Mâine poți să convertești din nou, același fișier
markdown într-un alt format și așa mai departe. Sursa rămâne aceeași, cât se
poate de simplă și concentrată pe text, în timp ce „înfățișările” sale pot
fi diverse: DOCX, PDF, ODT, HTML și nu numai.

Eu, de exemplu, lucrez așa:
* scriu în markdown și, ca să mă asigur că am formatul corect, mai folosesc
*live preview* uneori (amintește-ți de metoda de 
[transformare cu VSCode]({{< relref path="/materiale/floss/markdown.md#transformă-cu-vscode" lang="ro" >}})
de exemplu);
* după ce termin de scris, convertesc cu `pandoc` în format ODT (echivalentul
open source de la DOCX);
* salvez fișierul ODT local și conținutul îl pot copia direct în Google Docs, dacă
am nevoie să trimit un articol pentru publicare.

O să-ți dau mai multe exemple și variante de lucru, dar în forma cea mai simplă
și directă, `pandoc` se folosește din linia de comandă, cu o sintaxă care arată
la fel, indiferent de sistemul de operare:

```sh
# sintaxa generală, cea mai simplă:
$ pandoc -s fisier_sursa.extensie -o fisier_iesire.extensie

# de exemplu, ca să convertesc markdown în docx (Word):
$ pandoc -s notite.md -o notite.docx

# când am și un document-model, convertesc așa:
$ pandoc -s articol.md -o articol.odt --reference-doc=document_model.odt
```

Flexibilitatea lui este imensă și poți să specifici multe opțiuni care să
controleze fișierul de ieșire, astfel încât să fie gata de imprimare sau publicare.

În plus, dacă nu îți place să lucrezi cu linia de comandă, ai multe opțiuni
cu interfață și editoare care se leagă de `pandoc` pentru conversie directă.

## Testează înainte

Dacă ai curiozitate să probezi direct conversia, înainte să instalezi orice,
`pandoc` are și o versiune web [aici](https://pandoc.org/app/).

Descarcă un fișier-test markdown pe care l-am scris de [aici](/documents/test_markdown.md),
încarcă-l în pagina `pandoc`, alege să fie convertit în PDF (sau ce format dorești),
apoi descarcă rezultatul.

![pandoc_convert_web](/images/pandoc_convert_web.png)

## Ce să instalezi
### Procesorul
Indiferent de metoda cu care vei lucra, ai nevoie de „creierul” care procesează,
adică `pandoc`. Și dacă folosești un editor cu interfață grafică, și dacă apelezi
la linia de comandă, `pandoc` trebuie instalat local.

Procedura e foarte simplă: descarci installer-ul specific sistemului
tău de operare de pe [pagina oficial de GitHub](https://github.com/jgm/pandoc/releases)
a lui MacFarlane. 

![pandoc_releases](/images/pandoc_releases.png)

La data când scriu asta, cel mai probabil te interesează una din opțiunile acestea:
- `pandoc-3.10-windows-x86_64.msi`, dacă ești pe Windows și ai procesor cu arhitectură x86 (Intel, AMD);
- `pandoc-3.10-arm64-macOS.pkg`, dacă ești pe macOS cu procesor Apple Silicon;
- `pandoc-3.10-1.amd64.deb` dacă ești pe Linux din familia Debian (Ubuntu, Linux Mint, Debian etc.) și ai procesor cu
arhitectură x86.

În plus, dacă te descurci cu managere de pachete, vei găsi `pandoc` și în
depozitele respective:

```sh
# pe Windows
winget install pandoc

# pe macOS
$ brew install pandoc

# pe Fedora Linux (cum am eu)
$ sudo dnf install pandoc
```

După ce ai instalat, asigură-te că funcționează.
Deschide linia de comandă (Windows Terminal sau Command Prompt pe Windows sau
aplicația ta preferată de terminal) și scrie:

```
$ pandoc --version

pandoc 3.7.0.2
Features: +server +lua
Scripting engine: Lua 5.4
User data directory: $HOME/.local/share/pandoc
Copyright (C) 2006-2024 John MacFarlane. Web: https://pandoc.org
This is free software; see the source for copying conditions. There is no
warranty, not even for merchantability or fitness for a particular purpose.
```
Dacă totul e în regulă, terminalul ar trebui să răspundă cu un
text similar celui primit de mine mai sus. 

În caz de eroare, citește cu atenție mesajul primit și caută rezolvări.
Pe Windows, una dintre problemele des întâlnite are legătură cu
vizibilitatea programelor noi în [PATH](https://www.architectryan.com/2018/03/17/add-to-the-path-on-windows-10/).

### Un editor cu interfață grafică
Mai departe, dacă vrei să continui cu linia de comandă, nu mai ai nimic de instalat.
Dacă totuși preferi un editor cu interfață grafică și preview markdown, îți recomand
[PanWriter](https://panwriter.com/), pe care îl poți instala gratuit pe orice sistem
de operare.

În exemplele care urmează, eu o să-ți dau comenzile de terminal, totuși.

## Conversii uzuale
### Din Markdown în Rich Text
Când ai un document markdown care te mulțumește și ești gata să-l convertești în format
*rich text*, cum se folosește în Word, Google Docs, LibreOffice și altele,
conversia e cât se poate de simplă.

Deschide linia de comandă (Windows Terminal sau Command Prompt pe Windows sau aplicația
ta preferată de terminal pe alte sisteme de operare). **Asigură-te că ești în directorul
care conține fișierul-sursă**. Dacă l-ai salvat, de exemplu, pe Desktop, pentru siguranță,
introdu în terminal această comandă:

```sh
cd Desktop
```

Ea ar trebui să facă încât directorul curent să fie `Desktop`, iar prompt-ul să înceapă
cam așa:

```
# pe Windows
C:\Users\[numele_tău]\Desktop\> (aici scrii)

# pe macOS și Linux
[numele_tău]@[nume_pc]:~/Desktop$ (aici scrii)
```

Acum ești gata să lansezi conversia. Presupunem că fișierul tău markdown se numește
`fisier_sursa.md`. Dacă nu, adaptează comanda:

```sh
# convertește în DOCX (Word)
pandoc -s fisier_sursa.md -o fisier_iesire.docx

# convertește în ODT (LibreOffice)
pandoc -s fisier_sursa.md -o fisier_iesire.odt
```

Lansează oricare dintre comenzi (sau pe ambele — același fișier-sursă se poate transforma
în mai multe fișiere de ieșire, oricare ai nevoie).

Apoi observă că `fisier_iesire.docx`, de exemplu, a fost creat tot în directorul
curent (să zicem pe `Desktop`). Îl poți deschide cu Word sau ce program folosești
și vei vedea conținutul în format *rich text*.

#### Cu document-model
Problema principală, dacă ții la aspect, este că documentul de ieșire nu arată
grozav. A folosit stilurile implicite, fonturile, culorile și spațierea standard
din Word. Însă le poți personaliza și, mai mult, este suficient să faci asta
o singură dată, iar apoi reutilizezi.

Ca să creezi un document-model, deschide Word sau LibreOffice sau editorul tău
preferat de *rich text* și *nu scrie nimic în el*, dar schimbă toate formatele
care te interesează. Schimbă fontul pentru fiecare stil de paragraf, schimbă
spațierea, culorile, tot ce vrei, după gust. Apoi salvează-l ca *template*
(cu extensia `dotx` în Word sau `ott` în LibreOffice).

Salvează acest model unde vrei (de exemplu, tot pe `Desktop`) și acum revino
la linia de comandă:

```sh
# convertește în DOCX (Word) cu documentul tău model
pandoc -s fisier_sursa.md -o fisier_iesire.docx --reference-doc=document-model.dotx

# convertește în ODT cu documentul tău model
pandoc -s fisier_sursa.md -o fisier_iesire.odt --reference-doc=document-model.ott
```

Încearcă, de exemplu, documentul nostru model `ott` (funcționează doar pentru
conversia către formatul `odt`). Descarcă-l de [aici](/documents/libre_template_poligon.ott),
mută-l pe `Desktop` sau în același director cu fișierul sursă, apoi lansează comanda:

```sh
# convertește în ODT cu documentul nostru model
pandoc -s fisier_sursa.md -o fisier_iesire.odt --reference-doc=libre_template_poligon.ott
```

### Din Markdown în PDF
Conversia în PDF se poate face în mai multe moduri, dar cea mai simplă trece
prin *rich text*. Dacă vrei o conversie directă, mai ales dacă ai și
matematică mai complicată în fișier, este obligatoriu să treci prin
LaTeX, despre care discutăm separat.

Dar, cum majoritatea editoarelor de *rich text*, ca Word, LibreOffice și altele
permit exportul în PDF, îți propun această soluție de compromis,
valabilă în primul rând dacă documentul tău nu are multă matematică:
* convertește în *rich text* ca mai sus, cu sau fără document-model;
* deschide documentul rezultat cu programul specific (Word, LibreOffice etc.);
* exportă-l de acolo în PDF.

După ce detaliez separat și lucrul cu LaTeX, voi completa și aici metoda
cu `pandoc` via LaTeX.

---

Versiunea web a `pandoc` poate să facă această conversie, din markdown în PDF,
cu un program ceva mai nou și mai complex decât LaTeX ([typst](https://typst.app/)).
Dacă ești gata să accepți opțiuni pe care nu le poți personaliza prea detaliat,
poți să încarci documentul markdown în [`pandoc` pe web](https://pandoc.org/app/)
și să alegi rezultatul `pdf (PDF via Typst)` ca format de ieșire.
De altfel, este și exemplul pe care l-am dat [mai sus](#testează-înainte).

## Alte resurse
* [Aici](https://pandoc-templates.org/) găsești diverse documente-model pe care
le poți folosi pentru conversie, cu diverse specificații de format.
* [Aici](https://pandoc.org/demos.html) ai exemple multe din manualul oficial `pandoc` pentru
o parte din funcțiile sale de transformare.
* [Aici](https://pandoc.org/MANUAL.html) este manualul oficial (⚠️ *foarte tehnic* ⚠️).
* [Aici](https://pandoc.org/extras.html) funcțiile sale speciale.
* Întoarce-te la ghidurile noastre 👉 [aici]({{< relref path="/materiale/floss/_index.md" lang="ro" >}}).
