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







---

# Opgave 7 – Markér den aktuelle side i navigationen

Navigationen viser visuelt den aktive side med en CSS-klasse:

```html
<a href="news.html" class="join">Latest news</a>
```

## Forkert

```html
<a href="news.html" class="join">Latest news</a>
```

### Hvorfor er det et problem?

En CSS-klasse fortæller ikke i sig selv hjælpemidler, at dette link repræsenterer den aktuelle side.

## Korrekt princip

```html
<a
    href="news.html"
    class="join"
    aria-current="page"
>
    Latest news
</a>
```

### Hvorfor er dette bedre?

`aria-current="page"` gør det muligt for hjælpemidler at identificere den aktuelle side i navigationen.

Tilføj `aria-current="page"` til det aktive navigationslink på hver side.

Der må kun være én aktuel side i denne navigation ad gangen.

> Brug native semantisk HTML først. Tilføj ARIA, når der er et konkret behov.

---

# Opgave 8 – Gør formularerne tilgængelige

Sitet indeholder formularer på flere sider.

I starterkoden bruges blandt andet `placeholder` som eneste information om feltets formål.

Eksempel:

```html
<input
    type="email"
    name="email"
    placeholder="Type email & hit enter"
    required
>
```

Et `placeholder` er ikke en erstatning for et `<label>`.

## Forkert

```html
<input
    type="email"
    placeholder="Type your email"
>
```

### Hvorfor er det et problem?

Når brugeren begynder at skrive, forsvinder placeholder-teksten. Feltet har heller ikke nødvendigvis et tydeligt og entydigt tilgængeligt navn.

## Korrekt princip

```html
<label for="email">Email address</label>

<input
    type="email"
    id="email"
    name="email"
    autocomplete="email"
    placeholder="name@example.com"
    required
>
```

### Hvorfor er dette bedre?

Et synligt `<label>` gør feltets formål tydeligt og skaber en semantisk relation mellem label og input.

`for` på `<label>` skal matche feltets `id`.

---

## Labels gælder også textarea og datalist-input

Et `<textarea>` bør også have et label.

## Forkert

```html
<textarea
    name="question"
    placeholder="Ask a question..."
></textarea>
```

## Korrekt princip

```html
<label for="question">Your question</label>

<textarea
    id="question"
    name="question"
    placeholder="Ask a question..."
></textarea>
```

Et inputfelt med `list` og `<datalist>` skal også have et label.

## Forkert

```html
<input
    list="countries"
    name="country"
    id="country"
>

<datalist id="countries">
    <option value="Denmark">
    <option value="Sweden">
</datalist>
```

## Korrekt princip

```html
<label for="country">Country</label>

<input
    list="countries"
    name="country"
    id="country"
    autocomplete="country-name"
>

<datalist id="countries">
    <option value="Denmark">
    <option value="Sweden">
</datalist>
```

### Hvorfor er dette bedre?

`<datalist>` giver forslag til feltet, men den fortæller ikke brugeren, hvad feltets formål er. Det gør `<label>`.

---

## Brug `autocomplete` til kendte personoplysninger

`autocomplete` fortæller browseren, hvilken type information et felt forventer.

Eksempel:

```text
First name → autocomplete="given-name"
Last name  → autocomplete="family-name"
Email      → autocomplete="email"
Country    → autocomplete="country-name"
```

Eksempel i HTML:

```html
<label for="firstname">First name</label>
<input
    type="text"
    id="firstname"
    name="fname"
    autocomplete="given-name"
    required
>

<label for="lastname">Last name</label>
<input
    type="text"
    id="lastname"
    name="lname"
    autocomplete="family-name"
    required
>
```

### Vigtigt

`autocomplete` skal ikke nødvendigvis have samme værdi som `id` eller `name`.

De tre attributter har forskellige roller:

```text
id
→ identificerer HTML-elementet og bruges sammen med label

name
→ navnet på den værdi, som formularen sender

autocomplete
→ beskriver hvilken type information browseren forventer
```

### Hvorfor understøtter dette accessibility?

Autofill kan reducere behovet for at skrive de samme personlige oplysninger manuelt igen og igen.

Det kan blandt andet være en hjælp for brugere med motoriske, kognitive eller hukommelsesmæssige udfordringer.

---

## Giv formularen en tydelig submit-handling

På `index.html`, `news.html`, `games.html` og nederst på `contact.html` findes en emailformular, hvor brugeren forventes at forstå instruktionen:

```text
Type email & hit enter
```

Hovedformularen på `contact.html` har allerede en gyldig submit-kontrol:

```html
<input type="submit" value="Get in Touch">
```

Den behøver derfor ikke ændres alene af accessibility-hensyn. Opgaven er at vurdere hver formular og kun ændre de dele, der faktisk har et problem.

## Forkert princip

```html
<form>
    <label for="email">Email address</label>

    <input
        type="email"
        id="email"
        placeholder="Type email & hit enter"
    >
</form>
```

### Hvorfor er det et problem?

Brugeren skal selv vide, at Enter sender formularen, og instruktionen i placeholderen forsvinder, når der skrives i feltet.

## Korrekt princip

```html
<form>
    <label for="email">Email address</label>

    <input
        type="email"
        id="email"
        name="email"
        autocomplete="email"
        required
    >

    <button type="submit">Join the club</button>
</form>
```

### Hvorfor er dette bedre?

Formularfeltets formål og handlingen for at sende formularen er begge tydeligt angivet.

### `button` eller `input type="submit"`?

Begge dele er gyldige:

```html
<input type="submit" value="Get in Touch">
```

og:

```html
<button type="submit">Get in Touch</button>
```

`<button type="submit">` anvendes i eksemplerne, fordi det er et fleksibelt og tydeligt moderne valg.

Det betyder ikke, at `<input type="submit">` er en accessibility-fejl.

---

## Gennemgå alle formularer

Kontrollér formularerne i:

```text
index.html
news.html
games.html
contact.html
```

Vær især opmærksom på `contact.html`.

Kontrollér:

- Har hvert relevant felt et synligt og forståeligt label?
- Matcher `for` og `id`?
- Er alle `id`-værdier unikke?
- Har textarea et label?
- Har datalist-input et label?
- Er relevante `autocomplete`-værdier anvendt?
- Er formularens submit-handling tydelig?

---

# Opgave 9 – Kontrollér og optimér dokumentets `<head>`

Undersøg `<head>` i alle fire HTML-filer.

Formålet er ikke kun at finde fejl, men også at kunne genkende det, der allerede er korrekt, og vurdere, hvad der bør forbedres.

Kontrollér blandt andet:

- om dokumentets tegnsæt er angivet med `<meta charset="utf-8">`
- om `viewport` er angivet korrekt
- om hver side har en unik og beskrivende `<title>`
- om favicon og stylesheet er indlæst korrekt
- om elementerne i `<head>` er organiseret i en logisk og læsbar rækkefølge

## Stilladsering – tænk i denne rækkefølge

En vejledende struktur kan være:

```html
<head>
    <!-- tegnsæt -->

    <!-- viewport -->

    <!-- unik og beskrivende title -->

    <!-- favicon -->

    <!-- stylesheet -->
</head>
```

Du skal selv undersøge den eksisterende kode og afgøre, hvilke elementer der allerede er korrekte, hvilke der mangler, og hvilke der bør flyttes eller ændres.

En mulig færdig struktur kan eksempelvis ende sådan:

```html
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Marioclub - Contact</title>

    <link rel="shortcut icon" href="img/favicon.ico" type="image/x-icon">
    <link rel="stylesheet" href="css/style.css">
</head>
```

> Rækkefølgen af alle elementerne i `<head>` er ikke i sig selv et WCAG-krav. Det vigtigste er, at de nødvendige oplysninger er korrekte. `meta charset` bør dog placeres tidligt i `<head>`.

---

## Kontrollér dokumentets tegnsæt

Undersøg, om hver HTML-fil indeholder:

```html
<meta charset="utf-8">
```

Hvis den mangler, skal den tilføjes.

### Hvorfor er dette vigtigt?

`charset` fortæller browseren, hvilket tegnsæt dokumentet anvender.

Det hjælper browseren med at fortolke tekst og specialtegn korrekt.

---

## Kontrollér dokumentets sprog

Kontrollér også selve `<html>`-elementet.

Hvis starterfilen eksempelvis begynder sådan:

```html
<html>
```

skal du overveje, hvilket sprog siden er skrevet på.

Siderne i Marioclub-projektet er skrevet på engelsk.

### Korrekt princip

```html
<html lang="en">
```

### Hvorfor er dette bedre?

`lang`-attributten gør det muligt for browseren og hjælpemidler at identificere sidens primære sprog.

Det kan blandt andet have betydning for, hvordan skærmlæsere udtaler indholdet.

---

## Gør sidernes `<title>` unikke og beskrivende

Hvis flere sider bruger den samme generiske titel:

```html
<title>Marioclub</title>
```

bliver det vanskeligere at skelne siderne fra hinanden.

### Korrekt princip

Hver side skal have en kort, unik og beskrivende `<title>`, som både identificerer websitet og den aktuelle side.

Eksempel:

```html
<title>Marioclub - Home</title>
<title>Marioclub - News</title>
<title>Marioclub - Games</title>
<title>Marioclub - Contact</title>
```

### Hvorfor er dette bedre?

En beskrivende `<title>` hjælper brugeren med hurtigt at forstå, hvilken side der er åben, og gør det lettere at skelne mellem flere sider i blandt andet:

- browserfaner
- browserhistorik
- bogmærker
- hjælpemidler, som annoncerer sidens titel

Kontrollér og optimér `<title>` på alle fire HTML-sider.

---

# Opgave 10 – Test webtilgængelighed med WAVE og tastatur

Automatiske værktøjer kan finde mange accessibility-problemer, men ikke alle.

Du skal derfor kombinere **WAVE Evaluation Tool** med manuel tastaturtest.

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
