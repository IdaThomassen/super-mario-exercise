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

Performance:

Før: 73

Efter: 93

Accessibility:

Efter: 96

--- 
1. Hvilke ændringer gav den største performanceforbedring?
Billeder: fra jpg til WebP

2. Hvilke accessibility-problemer fandt du?
Heading-strukturen, manglende labels i formularerne og manglende autocomplete-værdier.

3. Hvilke problemer kunne Lighthouse finde?
Farvekontrast, billedoptimering og semantisk HTML.

4. Hvilke problemer fandt WAVE?
Ingen fejl ud over kontrast og lange alt-tekster.

5. Hvilke problemer krævede HeadingsMap eller manuel kontrol?
Selve strukturen og hierarki.

6. Hvad har du lært om sammenhængen mellem performance og accessibility?
Begge områder påvirker brugerens oplevelse af hjemmesiden.
En hurtigere hjemmeside gør det lettere for brugeren at komme til indholdet.
Accessibility sikrer at flere brugere kan forstå og anvende hjemmesiden.
