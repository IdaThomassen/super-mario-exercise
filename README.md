# Super Mario Fanclub
# Webtilgængelighed og web performance-optimering

# Opgave 1 – Lighthouse-baseline

### Index:
Performance score: 73

### Games
Performance score: 73

### Contact
Performance score: 73

### News
Performance score: 73

---
# Opgave 2 – Billede optimering 

### Banner
- Konverteret fra jpg(1.8 MB)  til WebP(238 kB)
- Kvaliteten er stadig fin
- Beholdt størrelsen

### Drmario
- Kan slettes da jeg ikke kan finde den

### Favicon
- Kan ikke optimers da det er en emoji

### Thumb-1
- Konverteret fra jpg(233 kB)  til WebP(68,8 kB)
- Kvaliteten er det samme
- Beholdt størrelsen

### Thumb-2
- Konverteret fra jpg(336 kB)  til WebP(72,9 kB)
- Kvaliteten er det samme
- Beholdt størrelsen

### Thumb-3
- Konverteret fra jpg(246 kB)  til WebP(166 kB)
- Kvaliteten er det samme
- Beholdt størrelsen

### Thumb-4
- Konverteringen gjorde den større. Den gik fra 313 til 369 kB.
- Kvaliteten er det samme
- Beholdt størrelsen
- Valgte ikke at ændre den til den nye

### Thumb-5
- Konverteringen gjorde den større. Den gik fra 175 til 209 kB.
- Kvaliteten er det samme
- Beholdt størrelsen
- Valgte ikke at ændre den til den nye

### Thumb-6
- Konverteringen gjorde den større. Den gik fra 121 til 134 kB.
- Kvaliteten er det samme
- Beholdt størrelsen
- Valgte ikke at ændre den til den nye

---
# Opgave 3 – Kontrollér billedkvaliteten

Jeg tjekkede alle billeder igennem, også dem der blev større ved at blive til WebP.
Jeg oplevede ikke at kvaliteten ændret sig, hverken da de blev mindre eller større. 


---

# Opgave 4 – Opdatering af billedreferencer og lazy loading 

### Opdatering
Opdatering af billedereference: alle nødvendige opdateringer er fortaget


### Lazy loading

Lazy loading er blivet tilføjet på siden games.html 
Dette er gjort da der kommer 6 billeder efter hinanden, så brugeren skal scrolle ned for at se. 
Jeg har tilføjet det til de sidste 4 billeder på siden.

---

# Opgave 5 – Gennemgå billedernes alt-tekster

### Nye alt tekster:
#### Banner
Banner med guld baggrund med Mario ikoner, Mario figuren er i højre side og holder en klods med spørgsmåls tegn på.

#### Thumb-1
Mario og Yoshi hopper efter mønter.

#### Thumb-2
Mario svømmer efter mønter under vandet og prøver at undgå fisk med pikke.

#### Thumb-3
Info billede af Super Mario, viser Mario, Super Mario logoet og lidt af Super Mario verden.

#### Thumb-4
Super Mario, Luigi, Daisy og andre Mario karakter kommer løbende. Baggrunden viser Super Mario verden.

#### Thumb-5
Mario og Luigi bygger deres egen Super Mario verden.

#### Thumb-6
Mario kart start linje, med Mario i front. Luigi er bag ved Mario på hans højre side. På venstre side bag Mario er Daisy og Bowser. Daisy er foran Bowser.

---

# Opgave 6 – Undersøg sidernes headingstruktur med HeadingsMap

Jeg har forbedr headingstrukturen og semantik.
Jeg har fået hjælp af ChatGPT til at forstår hvordan det kunne struktureres. 


---

# Opgave 7 – Markér den aktuelle side i navigationen

Jeg har tilføjet aria-current, så brugeren ved hvor de er selvom de ikke kan se hvor de er.

---

# Opgave 8 – Gør formularerne tilgængelige

Jeg har forbedret formularernes tilgængelighed ved at tilføje labels og autocomplete.


---

# Opgave 9 – Kontrollér og optimér dokumentets `<head>`


Viewport var allerede korrekt angivet, og stylesheetet var også korrekt sat ind. Der manglede en charset-angivelse, og <html>-elementet manglede en lang-attribut. Derudover havde alle fire sider samme generiske <title>, som blev ændret beskrivende titler.

---
# Opgave 10 – Test webtilgængelighed med WAVE og tastatur

## 10.1 – Test alle sider med WAVE

WAVE blev kørt på alle fire sider. Der blev ikke fundet nogen Errors, men WAVE fandt nogle enkelte Contrast Errors. Jeg gennemgik dem for at vurdere, hvilke HTML- og CSS-elementer der skulle ændres. Jeg gennemgik også Alerts, Features, Structure og ARIA for at vurdere, om der var elementer, der krævede manuel kontrol.

index.html: 0 fejl
news.html: 0 fejl
games.html: 0 fejl
contact.html: 0 fejl

---

## 10.2 – Undersøg Errors

Da der ikke blev fundet fejl, var der ikke noget at rette.

---

## 10.3 – Undersøg Contrast Errors

### Kontrast fejl fundet af WAVE:

index.html: 4 fejl
news.html: 4 fejl
games.html: 4 fejl
contact.html: 4 fejl

Alle fejl er ens. Problemerne er logo i toppen (hvid/rød), tekst på banner (hvid/gul) og tekst i bunden (hvid/rød)
Løsning:
Logo i toppen: Gik fra F63232 til c82929, den blev mere nedtonet.
Tekst på banner: Denne valgte jeg ikke at ændre. Gul er meget svær at ændre for at kontrasten er god. Man skal næsten over i brun før den er ok.
Tekst i bunden: Gik fra F63232 til c82929, den blev mere nedtonet.

Nu har alle sider kun 2 fejl, men de er bevidste. 

---

## 10.4 – Undersøg Alerts

Alerts:
For lange alt-tekster 
Et link der sender til forsiden

Jeg har valgt ikke at ændre disse. 
Alt-teksterne bruges til at beskrive billederne, så det er svært, at gøre beskrivelse kortere uden at miste hvad billedet viser.
Link ved jeg ikke hvor den ellers ville skulle sende brugeren hen.
```

---

## 10.5 – Test også med tastatur

Efter tjek af alle sider, var der især to der var svære at se. 
form button:focus
form input:focus

Begge havde en stiblet linje om sig. 
Det blev ændret til:

border: 4px solid rgb(37, 211, 74);

Resten brugte den automatiske focus der allerede findes på siden.


---

# Opgave 11 – Kør Lighthouse igen

Når du har gennemført optimeringerne, skal du køre Lighthouse igen.

Brug samme indstillinger som i din første test.

Sammenlign:

```text
Før optimering
vs.
Efter optimering
```

Dit mål er en **Performance-score på 90 eller højere**.

Kør også Lighthouse-kategorien **Accessibility**.

Lighthouse kan hjælpe med at finde en række accessibility-problemer, men en høj Lighthouse-score er ikke i sig selv bevis på, at en side er fuldt tilgængelig.

Du skal derfor kombinere Lighthouse med:

- WAVE
- HeadingsMap
- manuel tastaturtest
- kontrol af formularlabels
- kontrol af `autocomplete`
- kontrol af alt-tekster
- HTML-validering

---

# Dokumentér dine resultater

Notér resultaterne før og efter optimering.

Du kan eksempelvis bruge denne tabel:

| Side | Performance før | Performance efter | Accessibility efter |
|---|---:|---:|---:|
| `index.html` |  |  |  |
| `news.html` |  |  |  |
| `games.html` |  |  |  |
| `contact.html` |  |  |  |

Skriv derefter kort:

1. Hvilke ændringer gav den største performanceforbedring?
2. Hvilke accessibility-problemer fandt du?
3. Hvilke problemer kunne Lighthouse finde?
4. Hvilke problemer fandt WAVE?
5. Hvilke problemer krævede HeadingsMap eller manuel kontrol?
6. Hvad har du lært om sammenhængen mellem performance og accessibility?

---

# Kontrol af din løsning

Inden du afslutter opgaven, skal du kontrollere:

- [ ] Lighthouse er kørt før ændringerne.
- [ ] Performance-resultaterne før optimering er dokumenteret.
- [ ] Relevante billeder er konverteret til WebP.
- [ ] HTML-filerne anvender de nye WebP-filer.
- [ ] Billedkvaliteten er kontrolleret.
- [ ] Relevante billeder længere nede på siden bruger `loading="lazy"`.
- [ ] Vigtige billeder øverst på siden er ikke lazy-loadet uden grund.
- [ ] Alt-teksterne er gennemgået.
- [ ] Dekorative billeder er vurderet i forhold til `alt=""`.
- [ ] Headingstrukturen er kontrolleret med HeadingsMap både før og efter ændringer.
- [ ] Den aktuelle navigationsside anvender `aria-current="page"`.
- [ ] Formularfelter har relevante labels.
- [ ] `for` og `id` matcher.
- [ ] `textarea` har et label.
- [ ] `datalist`-input har et label.
- [ ] Relevante `autocomplete`-værdier er anvendt.
- [ ] Formularer har en tydelig submit-handling.
- [ ] Eksisterende gyldige submit-kontroller er vurderet, før de eventuelt ændres.
- [ ] Dokumentets tegnsæt er kontrolleret og er korrekt angivet med `<meta charset="utf-8">`.
- [ ] `<head>` er organiseret i en logisk og læsbar rækkefølge.
- [ ] Dokumentets primære sprog er angivet med `lang="en"` på `<html>`.
- [ ] Alle fire sider har en unik og beskrivende `<title>`.
- [ ] CSS er kontrolleret efter ændringer i HTML-strukturen.
- [ ] Alle fire sider er testet med WAVE.
- [ ] Relevante WAVE Errors er undersøgt og udbedret.
- [ ] WAVE Contrast Errors er undersøgt og udbedret, hvor det var nødvendigt.
- [ ] WAVE Alerts er undersøgt og vurderet.
- [ ] Alle interaktive elementer har en tydelig synlig fokusmarkering.
- [ ] Siderne er testet med tastatur.
- [ ] HTML-koden er valideret.
- [ ] Lighthouse er kørt igen efter optimering.
- [ ] Performance-score er 90 eller højere.
- [ ] Resultater før og efter er sammenlignet.

---

# Værktøjer i opgaven

| Værktøj | Anvendelse |
|---|---|
| **Lighthouse** | Performance og overordnet accessibility-audit før og efter optimering |
| **WAVE** | Accessibility-fejl, kontrast, alerts, struktur og ARIA |
| **HeadingsMap** | Visualisering og analyse af headinghierarki |
| **Chrome DevTools** | Network, responsive test og undersøgelse af HTML/CSS |
| **W3C Validator** | Validering af HTML-koden |
| **Tastatur** | Manuel test af navigation, formularer og fokus |

---

# Useful Links / Nyttige links

## Chrome DevTools

[Chrome DevTools](https://developer.chrome.com/docs/devtools/)

## Lighthouse

[Lighthouse](https://developer.chrome.com/docs/lighthouse/)

[Lighthouse i Chrome DevTools](https://developer.chrome.com/docs/devtools/lighthouse/)

## WebP

[Google WebP](https://developers.google.com/speed/webp/)

## Billedværktøjer

[GIMP](https://www.gimp.org/)

[GIMP – Export Image as WebP](https://docs.gimp.org/3.0/en/file-webp-export.html)

[XnConvert](https://www.xnview.com/en/xnconvert/)

[ImageMagick](https://imagemagick.org/)

## Accessibility-værktøjer

- WAVE Evaluation Tool – Chrome Extension
- HeadingsMap – Chrome Extension

## HTML og accessibility

[MDN – Heading elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/Heading_Elements)

[MDN – label](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/label)

[MDN – placeholder](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Attributes/placeholder)

[MDN – autocomplete](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/autocomplete)

[MDN – button](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/button)

[MDN – datalist](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/datalist)

[MDN – aria-current](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Reference/Attributes/aria-current)

[W3C – Understanding Identify Input Purpose](https://www.w3.org/WAI/WCAG22/Understanding/identify-input-purpose.html)

[W3C HTML Validator](https://validator.w3.org/)

---

## Afsluttende note

> Udviklet til studerende på **3. semester**. Ingen AI-værktøjer er nødvendige — opgaven kan løses med en browser, en teksteditor, et tastatur og et simpelt billedværktøj.
