+++
title = "Xournal++"
type = "docs"
bookHidden = true
slug = "xournalpp"
+++

# Xournal++

## Pledoarie pentru tablete grafice
Mulți profesori și elevi folosesc tablete, ca dispozitive mobile, pentru
scris și citit digital. Dar există și variante care, deși nu sunt la fel
de portabile, oferă mai multă flexibilitate și cu un preț mai mic.
Este vorba despre tablete grafice, care se pot conecta la orice computer
sau laptop și au o suprafață de scris mai mare și mai sensibilă decât multe
ecrane ale tabletelor Android sau iPad. 

Durează până te obișnuiești să scrii pe suprafața tabletei, în timp ce
privești la ecran, dar există și tablete grafice care au propriu ecran.

Nu o să transform textul acesta într-unul despre tablete grafice, însă
dacă ai un laptop sau un PC pe care le folosești zilnic, conectarea
unei tablete grafice la el cred că este o opțiune mai flexibilă și mai puternică
decât o tabletă mobilă, separată. Sunt mai multe motive tehnice, în care nu o
să intru, dar cel mai important mi se pare că lucrezi cu un sistem de 
operare și de fișiere cu care ești obișnuit. Ai totul la îndemână, navigarea
e simplă și fișierele sunt exact acolo unde le-ai lăsat.

Mai adaug că tableta pe care o folosesc eu este cea din imagine, 
*Huion Inspiroy Keydial KD200*. Nu am niciun interes comercial
să o prezint, dar sunt mulțumit de ea și o ofer ca exemplu.
Se poate conecta și prin USB, și prin Bluetooth, iar mica tastatură pe
care o are este numai bună pentru scurtăturile uzuale.

![tableta_huion](/images/tableta_huion.png)

Dacă lucrezi frecvent cu documente digitale, pe care ai nevoie să le
studiezi sau să le adnotezi, sau dacă ești artist, o tabletă grafică
este neprețuită. Deschizi un PDF, subliniezi, adnotezi, corectezi.
La fel și cu o imagine sau cu un document scanat. Cu atât mai mult
dacă ești profesor și ai ținut ore sau meditații online.

![notite_clasa11](/images/notite_clasa11.png)

## Software pentru scris
Lista programelor în care poți să scrii în format digital, cu o tabletă
grafică, este foarte mare și include:
- Microsoft Whiteboard;
- Microsoft OneNote;
- software-ul cu care vine tableta ta;
- software gândit mai degrabă pentru desen, ca Adobe Photoshop, Krita, Clip Studio Paint etc.;
- Inkodo (pe Windows);
- Goodnotes (pe macOS);
- Drawboard PDF.

Dar seria aceasta de articole este în primul rând despre unelte open source
și, dacă se poate, gratuite, așa că voi recomanda și detalia 
[Xournal++](https://xournalpp.github.io/). Se numește așa pentru că
este o versiune îmbunătățită a unui program mai vechi, Xournal.
Din motive tehnice, în unele documente sau pachete de instalare îl
poți găsi și cu numele `Xournalpp`.

Am început să-l folosesc în perioada pandemiei de COVID-19, când țineam
seminarii de matematici la Politehnică și am simțit de la început că are
exact ce-mi trebuie și chiar mai mult, dar fără să fie supracomplicat
sau greoi.

Este disponibil pe toate sistemele de operare (dar pe Linux are performanța
cea mai bună) și îl poți folosi atât pentru notițe, ca o tablă digitală, cât
și pentru adnotat PDF-uri.

![xournalpp_1](/images/xournalpp_1.png)

Interfața grafică e destul de simplă și ai toate uneltele la îndemână.
Poți să scrii (cu creionul), să ștergi, să subliniezi (cu markerul),
dar și să desenezi figuri geometrice, să măsori unghiuri, distanțe
și nu numai.

Paginile pot fi personalizate, încât să alegi fundal de dictando, de 
matematică, simplu sau cu diverse formate. O parte dintre opțiunile
cele mai utile se văd în imaginea de mai jos.

![xournalpp_2](/images/xournalpp_2.png)

Xournal++ funcționează foarte bine și cu documente de sute de pagini. Când lucrez cu elevi
pe parcursul unui întreg semestru, creez un singur „caiet” pentru toată perioada,
astfel încât să pot căuta și face referiri la pagini cu lecții anterioare.
Creez un singur fișier `.xopp` (sau două, pentru clasele a XI-a și a XII-a, unde
separ algebra de analiză) și, după fiecare lecție, export conținutul în format PDF,
pe care îl transmit elevului și-l păstrez și eu, pentru arhivare.
Documentul tot crește, încât nu de puține ori, la finalul semestrului, are peste
500 de pagini. Cu toate astea, Xournal++ se descurcă foarte bine și derulez
ușor printre pagini atunci când vreau să caut o lecție din urmă.

Dacă deschizi un PDF cu Xournal++, ai toate opțiunile la dispoziție, încât
poți să adnotezi, să subliniezi și chiar să decupezi porțiuni pe care să
le adaugi în caietul tău `.xopp`. Odată deschis documentul, funcționează
ca un fișier obișnuit `xopp`, doar că are deja conținut în fundal. De aceea,
poți să adaugi pagini, să ștergi sau să scrii peste.

![xournalpp_3](/images/xournalpp_3.png)

Bonus: Când ai de explicat noțiuni de teorie, poți să combini scrisul de mână
cu cel de la tastatură și chiar cu [LaTeX]({{< relref path="materiale/floss/latex.md" lang="ro" >}}),
pe care îl vezi transformat în timp real, înainte să-l adaugi în document.

![xournalpp_4](/images/xournalpp_4.png)

## Mențiune specială: Rnote
Am aflat recent de o altă aplicație pe care vreau să o recomand: [Rnote](https://rnote.flxzt.net/).
Este, ca și Xournal++, gratuită, open source, și disponibilă pe toate sistemele de operare.

Rnote este mai nouă, deci nu la fel de optimizată și de plină de unelte precum Xournal++,
dar se folosește de accelerația grafică hardware (placa video) pentru performanță.
Din același motiv, este scrisă în limbajul de programare Rust, cunoscut pentru viteză
și are deja câteva opțiuni prin care diferă și, într-un fel, este mai bun decât Xournal++.

De exemplu, poți să deschizi mai multe fișiere odată în Rnote, în tab-uri, în timp ce
în Xournal++ poți lucra doar cu un singur fișier odată.

O a doua opțiune este formatarea ca „tablă infinită”, delimitată în pagini.
Când deschizi Rnote, spațiul de lucru implicit este format dintr-o suprafață
infinită, care se întinde în toate direcțiile, delimitată cu linii subțiri
în pagini A4. În felul acesta, poți să deschizi un fișier PDF pe una dintre
pagini și să iei notițe pe alta, deasupra, dedesubtul sau în lateralul ei,
în timp ce le vezi pe toate (dacă ai un monitor suficient de mare). Uite
o imagine edificatoare, de pe site-ul Rnote.

![rnote](/images/rnote.png)

Deocamdată, Rnote nu are toate tipurile de unelte pe care le are Xournal++,
nici nu suportă cod LaTeX, de exemplu, dar, pentru o experiență modernă
de scris și adnotat, merită luat în calcul.

---

Întoarce-te la ghidurile noastre 👉 [aici]({{< relref path="/materiale/floss/_index.md" lang="ro" >}}).
