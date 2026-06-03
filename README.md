# Site-ul Poligon Educational
Refacere a [site-ului vechi](https://poligon-edu.ro),
folosind [Hugo](https://gohugo.io/), tema [Book](https://book.alxs.dev/docs/getting-started/introduction/).

## Instalare și test local
- instalează `hugo`;
- clonează repository-ul: `git clone https://github.com/Poligon-Edu/poligon-hugo.git`;
- din directorul proiectului (`cd poligon-hugo`), lansează `hugo server`;
- deschide în browser `http://localhost:1313`.

**Important:** La schimbări majore (e.g. conținutul folderelor sau numele
fișierelor), serverul trebuie relansat. În rest, modificările de conținut
și de aspect se sincronizează în timp real.

## Fișiere și directoare importante
- `hugo.toml`: fișierul de descriere și configurare principală;
- `assets/_custom.scss`: fișierul principal de configurare a aspectului;
- `layouts/partials/docs/inject/{head,menu-after}.html`: conținut HTML de injectat (**modificarea lor necesită repornirea serverului**);

## Aranjarea fișierelor și meniu
- `content/{en,ro}/docs`: conținutul separat pe limbi;
- fiecare director care conține cîte un `_index.md` va deveni element de meniu. 
Exemplu: `content/ro/docs/cursuri/_index.md` apare în meniu (sidebar) prin titlul dat în fișier.
- elementele din subdirectorul respectiv vor deveni elemente din sub-meniu, cu titlurile din fișiere.
Exemplu: `content/ro/docs/cursuri/muzica.md` apare la `Cursuri > Muzică`;
- ordinea din meniu (sidebar) se poate face manual, folosind `weight` în fișiere.
Un `weight` mai mic apare mai sus. Două `weight`-uri egale sînt aranjate alfabetic.
Exemplu:

```md
---
title: Cursuri personalizate
weight: 2
---
```
- imaginile se găsesc în `static/images` și se folosesc cu `/images/imagine.png`;
- referințele interne se găsesc cu `ref`, comandă specială care caută în tot proiectul.
Exemplu și sintaxă: `[link la cursuri.md]({{< ref "cursuri.md" >}})`.
Pentru dezambiguizare, se poate folosi orice șir de caractere care este unic.
De exemplu, dacă vreau să leg `_index.md` din directorul `cursuri`,
pot folosi `[link la cursuri/index]({{< ref "cursuri/_index.md" >}})`.
Calea relativă nu contează, fiindcă `ref` _caută_, deci sintaxa `cursuri/_index.md`
îl ajută să caute, dar căutarea pornește de la top-level al proiectului.

## Progres
- [x] structura paginilor din meniu în română;
- [x] butoane de toggle la limbă și temă;
- [x] structura paginilor din meniu în engleză;
- [x] pus pe GitHub Organization;
- [x] pus Google Analytics tag;
    - [ ] de schimbat?
- [ ] de revăzut/curățat paginile de Cookies și Privacy Policy;
- [ ] curățat HTML din fișierele `.md` și trecut la Hugo nativ;
- [ ] conținut la landing page;
    - [ ] scris whitepaper;
    - [ ] scris o descriere generală;
- [ ] pagină de „postări”/idei random (?);
- [ ] conținut la Adrian;
- [ ] conținut la Răzvan (de schimbat/extins);
- [ ] conținut la Maria (de schimbat/extins);
- [ ] conținut la Joshua (de schimbat/extins);
- [ ] conținut la cursuri;
- [ ] editat tot (textele);
- [ ] rafinat vizual, inclusiv tema întunecată;
    - [ ] de pus logo undeva?
- [ ] publicat pe domeniu. **DEADLINE: AUGUST 2026**
