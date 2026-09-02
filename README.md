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

## 10.1 – Test alle sider med WAVE

Installér **WAVE Evaluation Tool** som Chrome Extension.

Kør WAVE på:

```text
index.html
news.html
games.html
contact.html
```

Undersøg især kategorierne:

```text
Errors
Contrast Errors
Alerts
Features
Structure
ARIA
```

Du skal ikke blot forsøge at få alle markeringer til at forsvinde.

Undersøg først:

1. Hvad fortæller WAVE?
2. Hvilket HTML- eller CSS-element handler markeringen om?
3. Hvorfor er det et problem?
4. Kræver det faktisk en ændring?
5. Hvordan kan problemet løses uden at ødelægge sidens funktion eller design?

> WAVE er et analyseværktøj – ikke en automatisk facitliste.

---

## 10.2 – Undersøg Errors

Hvis WAVE finder fejl, skal du undersøge dem og rette relevante problemer.

Det kan eksempelvis være:

```text
Missing form label
Language missing or invalid
```

Brug WAVE til at lokalisere det konkrete element, og undersøg derefter HTML-koden i VS Code.

Når du har rettet problemet, skal du køre WAVE igen.

---

## 10.3 – Undersøg Contrast Errors

WAVE kan identificere tekst, hvor kontrasten mellem tekstfarve og baggrund er utilstrækkelig.

Hvis WAVE finder en kontrastfejl:

1. Find det relevante element.
2. Undersøg de anvendte farver i `css/style.css`.
3. Tilpas tekstfarve eller baggrundsfarve.
4. Bevar så vidt muligt sidens visuelle udtryk.
5. Kør WAVE igen og kontrollér, om problemet er løst.

Du skal ikke ændre farver tilfældigt. Brug værktøjets information til at finde den konkrete CSS-regel, der giver problemet.

---

## 10.4 – Undersøg Alerts

Et **Alert** i WAVE er ikke nødvendigvis en accessibility-fejl.

Hvis WAVE viser et alert, skal du:

- undersøge hvorfor elementet markeres
- vurdere om koden faktisk bør ændres
- kunne forklare din beslutning

Det er vigtigt at kunne skelne mellem:

```text
automatisk fundet fejl
og
noget der kræver menneskelig vurdering
```

---

## 10.5 – Test også med tastatur

Efter WAVE-testen skal du teste alle sider uden mus.

Brug:

```text
Tab
Shift + Tab
Enter
```

Kontrollér:

- Kan du nå alle links?
- Kan du nå alle formularfelter?
- Kan du nå submit-knapper?
- Kan navigationen bruges med tastaturet?
- Følger fokus en logisk rækkefølge?
- Kan du tydeligt se, hvilket element der har fokus?

Starterprojektets CSS indeholder allerede egne fokusregler.

Eksempel:

```css
form input:focus {
    border: 4px dashed #4B4B4B;
    outline: none;
}
```

`outline: none` er ikke automatisk en accessibility-fejl, hvis browserens standardfokus erstattes af en tydelig fokusindikator.

Din opgave er derfor at **teste fokusmarkeringen**, ikke blot at fjerne eller erstatte CSS-reglen mekanisk.

Hvis fokus ikke er tydeligt nok, skal du forbedre CSS'en og teste igen.

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
