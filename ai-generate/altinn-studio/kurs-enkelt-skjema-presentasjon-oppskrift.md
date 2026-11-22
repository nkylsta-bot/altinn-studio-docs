# Oppskrift: Presentasjon av kurset «Lage et enkelt skjema» med Slidev

Denne oppskriften beskriver hvordan du lager presentasjonsutgaven av kurset «Lage et enkelt skjema». Presentasjonen
bygges med [Slidev](https://sli.dev) og erstatter Marp.

Presentasjonen er en egen markdown-fil. Den lages fra den gjeldende kursartikkelen og skjermbildene som allerede ligger
sammen med kurset. Det skal ikke tas nye skjermbilder for presentasjonen.

Oppskriften hører sammen med [playbooken for kurset](kurs-enkelt-skjema-playbook.md). Playbooken beskriver caset og
innholdet. Denne oppskriften beskriver bare hvordan kursartikkelen gjøres om til lysbilder.

De tekniske reglene i kapittel 4 er testet med Slidev 53.1.0 og Hugo 0.162.0, som er versjonen CI bruker.

---

## 1. Inndata og utdata

| Hva                | Hvor                                                                                   |
|--------------------|----------------------------------------------------------------------------------------|
| Kursartikkel       | `content/altinn-studio/v9/getting-started/development/basic-form/_index.nb.md`         |
| Skjermbilder       | `.png`-filene i samme mappe som kursartikkelen                                          |
| Case og læringsmål | `ai-generate/altinn-studio/kurs-enkelt-skjema-playbook.md`                             |
| **Presentasjon**   | `content/altinn-studio/v9/getting-started/development/basic-form/slides.md`            |

Presentasjonen skal ligge i samme mappe som kursartikkelen. Slidev nekter å hente bilder utenfor mappen der
presentasjonen ligger, også via symbolske lenker. Når filen ligger ved siden av skjermbildene, kan den bruke dem direkte.
Da trengs ingen kopier.

Kursartikkelen er kilden. Presentasjonen skal ikke inneholde noe som ikke står i kursartikkelen eller playbooken.

---

## 2. Hva presentasjonen skal være

Presentasjonen brukes av en kursholder i et kurs med fysisk eller digitalt oppmøte. Deltakerne følger med på
lysbildene og gjør oppgavene i Altinn Studio underveis.

- **Lysbildene viser hva som skal gjøres.** Hver oppgave vises med korte steg og skjermbildet fra kurset.
- **Talernotatene forklarer.** Lengre forklaringer fra kursartikkelen flyttes til talernotater, ikke til lysbildet.
- **Rekkefølgen følger kursartikkelen.** Ikke flytt deler eller slå dem sammen.
- **Ett budskap per lysbilde.** Et lysbilde har enten et konsept, en oppgave eller et skjermbilde.

---

## 3. Struktur

### Fra kursartikkel til lysbilder

| I kursartikkelen                              | I presentasjonen                                                                 |
|-----------------------------------------------|----------------------------------------------------------------------------------|
| Tittel og beskrivelse i front matter          | Forside med layout `cover`                                                       |
| Læringsmålene i innledningen                  | Lysbildet «Dette lærer du»                                                       |
| «Dette skal du lage»                          | Ett lysbilde om caset                                                            |
| Overskrift på nivå 3 (`###`)                  | Seksjonslysbilde med layout `section`                                            |
| Konseptforklaring                             | Ett lysbilde med 3 til 5 punkter. Resten av teksten blir talernotat.              |
| Nummererte steg under nivå 4 (`####`)         | Ett lysbilde med stegene forkortet til én linje hver, og med UI-navn i **fet**     |
| Skjermbilde                                   | Eget lysbilde med skjermbildet, eller høyre kolonne ved siden av stegene         |
| Tabell, for eksempel komponentene i skjemaet  | Tabellen beholdes, uten forklarende tekst rundt                                   |
| Merknad i sitat (`>`)                         | Talernotat, eller en kort linje nederst på lysbildet hvis den er viktig            |
| Sammenleggbar fordypning (`expandlarge`)      | Ett valgfritt lysbilde med kode, merket som fordypning                            |
| Lenker med `relref`                           | Full URL til docs.altinn.studio, eller fjernes                                     |
| Oppsummeringen til slutt                      | Ett lysbilde med layout `default` med det deltakeren har laget                    |
| (finnes ikke)                                 | Siste lysbilde med layout `end`, med bare navnet på neste kurs                    |

### Forventet lysbildeplan for dagens kurs

Planen bruker alle de 24 skjermbildene i mappen én gang. Filen `kommune-logo.png` er ikke et skjermbilde, men logoen
deltakerne lenker til fra Studio. Den skal ikke brukes i presentasjonen. Hvis kursartikkelen har endret seg, følger du
kursartikkelen og oppdaterer planen.

| #  | Del                        | Lysbilde                                   | Layout     | Skjermbilde                    |
|----|----------------------------|--------------------------------------------|------------|--------------------------------|
| 1  |                            | Lage et enkelt skjema                      | `cover`    |                                |
| 2  |                            | Dette lærer du                             | `default`  |                                |
| 3  |                            | Dette skal du lage                         | `default`  |                                |
| 4  | Opprett en ny app          | Seksjon                                    | `section`  |                                |
| 5  |                            | Opprett en ny app                          | `two-cols` | `opprett-app.png`              |
| 6  | Endre informasjonen        | Seksjon                                    | `section`  |                                |
| 7  |                            | Oversiktssiden                             | `default`  | `oversikt.png`                 |
| 8  |                            | Se hva som mangler                         | `two-cols` | `valideringsfeil.png`          |
| 9  |                            | Legg inn navn, beskrivelse og kontaktinformasjon | `default` |                         |
| 10 |                            | Om appen                                   | `default`  | `innstillinger.png`            |
| 11 |                            | Ny tittel på oversiktssiden                | `default`  | `oversikt-med-tittel.png`      |
| 12 | Lagre og dele endringer    | Seksjon                                    | `section`  |                                |
| 13 |                            | To områder                                 | `default`  | `lagre-og-dele.png`            |
| 14 |                            | Del endringene                             | `two-cols` | `del-endringer.png`            |
| 15 | Lage velkomstsiden         | Seksjon                                    | `section`  |                                |
| 16 |                            | Åpne Utforming                             | `default`  | `utforming-oppgaver.png`       |
| 17 |                            | Slik er Utforming bygd opp                 | `default`  | `utforming.png`                |
| 18 |                            | Legg til et bilde                          | `two-cols` | `legg-til-komponent.png`       |
| 19 |                            | Velg komponent                             | `default`  | `vis-alle-bilde.png`           |
| 20 |                            | Lim inn adressen                           | `two-cols` | `bilde-url.png`                |
| 21 |                            | Legg til et avsnitt                        | `two-cols` | `ny-komponent-pluss.png`       |
| 22 |                            | Skriv velkomstteksten                      | `two-cols` | `avsnitt.png`                  |
| 23 |                            | Den ferdige velkomstsiden                  | `default`  | `infoside-resultat.png`        |
| 24 | Sette opp datamodellen     | Seksjon                                    | `section`  |                                |
| 25 |                            | Hva er en datamodell?                      | `default`  |                                |
| 26 |                            | Krav fra kommunen                          | `default`  |                                |
| 27 |                            | Datamodellen du skal lage                  | `default`  |                                |
| 28 |                            | Åpne datamodellen                          | `default`  | `datamodell.png`               |
| 29 |                            | Slett eksempelfeltene                      | `default`  | `datamodell-slett.png`         |
| 30 |                            | Lag den første gruppen                     | `default`  | `datamodell-legg-til-felt.png` |
| 31 |                            | Gjør ferdig datamodellen                   | `default`  | `datamodell-ferdig.png`        |
| 32 |                            | Del endringene                             | `default`  |                                |
| 33 | Utforme skjemasiden        | Seksjon                                    | `section`  |                                |
| 34 |                            | Lag en ny side                             | `two-cols` | `ny-side.png`                  |
| 35 |                            | Legg til det første skjemafeltet           | `default`  | `legg-til-tekstfelt.png`       |
| 36 |                            | Tekster og tekst-ID-er                     | `default`  |                                |
| 37 |                            | Legg inn ledeteksten                       | `two-cols` | `ledetekst.png`                |
| 38 |                            | Knytt feltet til datamodellen              | `two-cols` | `datamodellfelt.png`           |
| 39 |                            | Fordypning: navnefeltet i filene til appen | `default`  |                                |
| 40 |                            | Legg til resten av skjemafeltene           | `default`  |                                |
| 41 |                            | Komponentene etter «Fullt navn»            | `default`  |                                |
| 42 |                            | Den ferdige skjemasiden                    | `default`  | `resten-av-skjemaet.png`       |
| 43 | Teste skjemaet             | Teste skjemaet                             | `default`  |                                |
| 44 | Dele endringene            | Del endringene                             | `default`  |                                |
| 45 |                            | Du har laget en app med                    | `default`  |                                |
| 46 |                            | Neste kurs: Publiser og test en tjeneste   | `end`      |                                |

---

## 4. Tekniske regler

### Headmatter

Presentasjonen starter med denne headmatteren. Blokken `build` er obligatorisk. Den hindrer Hugo i å publisere
presentasjonen som en side i dokumentasjonen.

```yaml
---
theme: default
title: Lage et enkelt skjema
info: Altinn Studio – kom i gang
routerMode: hash
exportFilename: altinn-studio-lage-et-enkelt-skjema
fonts:
  sans: Inter
build:
  render: never
  list: never
  publishResources: false
layout: cover
---

# Lage et enkelt skjema

Altinn Studio – kom i gang

<style>
:global(.slidev-layout:not(.end)) {
  color: #212B3B;
}
</style>
```

Headmatteren er også frontmatter for forsiden. Derfor står `layout: cover` her, og forsidens innhold kommer rett etter.

Alle presentasjonene bruker fonten Inter og tekstfargen `#212B3B`:

- **Fonten** setter du med `fonts` i headmatteren. Slidev henter Inter fra Google Fonts, så nettleseren må ha
  nettilgang når presentasjonen vises.
- **Tekstfargen** setter du med `<style>`-blokken på forsiden. `:global` gjør at den gjelder alle lysbildene, også når
  presentasjonen åpnes direkte på et senere lysbilde. Layouten `end` beholder sin lyse tekst på mørk bakgrunn.
- **Ikke bruk `style.css`.** Filen måtte ligget i kursmappen, og da publiserer Hugo den sammen med kursartikkelen.

`routerMode: hash` gjør at den bygde presentasjonen fungerer uansett hvilken mappe den publiseres i.

### Hvert lysbilde skal ha egen frontmatter

Start hvert lysbilde med en frontmatter-blokk, også når det bare bruker standardlayouten:

```md
---
layout: default
---

# Overskrift

Innhold
```

Slidev leser innholdet mellom to `---` som frontmatter hvis det kan tolkes som YAML. Et lysbilde med bare en overskrift
og et bilde blir da borte uten feilmelding.

### Layouter

Bruk bare innebygde layouter fra standardtemaet:

| Layout     | Brukes til                                         |
|------------|----------------------------------------------------|
| `cover`    | Forsiden                                           |
| `section`  | Seksjonslysbilde for hver del                      |
| `default`  | Konsepter, steg, tabeller og store skjermbilder     |
| `two-cols` | Steg til venstre og skjermbilde til høyre, med `::right::` |
| `end`      | Siste lysbilde, med bare en kort tittel            |

Layouten `end` har mørk bakgrunn. Inline-kode blir hvite bokser, og punktlister står skjevt. Bruk den bare til en
kort tittel, og legg oppsummeringen på et eget lysbilde med `default`.

Ikke bruk `image`, `image-right` eller `image-left` med relative stier i `image:`. Bildet blir pakket med, men vises ikke
på lysbildet. Bruk `two-cols` i stedet.

### Skjermbilder

- **Bruk relative stier** som starter med `./`, for eksempel `./ny-side.png`.
- **Mellomrom i filnavn** skrives som `%20`, for eksempel `./mitt%20bilde.png`. Ikke endre navnet på filene, fordi
  kursartikkelen bruker dem.
- **Store skjermbilder** settes inn med `<img>` og en høydegrense, ellers blir de kuttet nederst:

  ```html
  <img src="./ny-side.png" class="max-h-96 mx-auto" alt="Lag en ny side" />
  ```

  Disse høydene passer:

  - `max-h-96` for et skjermbilde alene under overskriften
  - `max-h-112` i høyre kolonne i `two-cols`
  - `max-h-56` til `max-h-72` for et bredt skjermbilde under steg eller punkter

  Bruk `two-cols` bare for høye eller kvadratiske skjermbilder. Brede skjermbilder blir for små i en kolonne, så legg
  dem under stegene med layouten `default`. Hold overskriften kort, ellers går den inn i bildet i høyre kolonne.
- **Skriv alt-tekst** som sier hva bildet viser.
- **Fjern Marp-direktiver** fra alt-teksten, som `bg right:60% contain`, `h:620px` og `?width=300`.

### Talernotater

Talernotater skrives som en HTML-kommentar til slutt i lysbildet:

```md
<!--
Navnet må være unikt i organisasjonen. Det blir også en del av URL-en til tjenesten.
-->
```

### Ikke ta med

- Hugo-shortcodes, som `{{< relref >}}`, `{{% expandlarge %}}` og `{{< code-title >}}`
- Marp-innstillinger og Marp-direktiver
- Front matter fra kursartikkelen, bortsett fra tittelen

---

## 5. Språk

- Skriv på bokmål, med samme ord og UI-navn som i kursartikkelen.
- Overskriftene har stor forbokstav bare i første ord, og ingen punktum.
- Stegene er korte setninger i imperativ, for eksempel «Klikk på **Opprett app**.»
- Punkter er korte fraser uten punktum.

---

## 6. Bygg og kontroll

Repoet har ingen avhengigheter til Slidev. Kjør Slidev med `npx` fra en mappe utenfor repoet:

```sh
# Forhåndsvisning i nettleseren
npx -y -p @slidev/cli -p @slidev/theme-default slidev \
  <repo>/content/altinn-studio/v9/getting-started/development/basic-form/slides.md

# Statisk bygg
npx -y -p @slidev/cli -p @slidev/theme-default slidev build \
  <repo>/content/altinn-studio/v9/getting-started/development/basic-form/slides.md --out <ut-mappe>
```

Sjekk dette før du leverer:

1. **Bygget går uten feil.** Feilen `resolves outside of Vite server.fs.allow` betyr at en sti peker ut av mappen.
2. **Alle skjermbildene er med.** Antall `.png`-filer i `assets/` i den bygde presentasjonen skal være én mer enn
   antallet skjermbilder du har brukt. Den ekstra filen er logoen til Slidev, `logo-<hash>.png`.
3. **Ingen lysbilder mangler.** Antallet lysbilder skal stemme med lysbildeplanen.
4. **Ingen bilder er kuttet.** Se gjennom alle lysbildene i forhåndsvisningen.
5. **Hugo publiserer ikke presentasjonen.** Etter `hugo` skal ingen fil i `public/` inneholde tekst som bare finnes i
   presentasjonen. Hugo-bygget kan endre `assets/jsconfig.json`. Den endringen skal ikke committes.

---

## 7. Bestilling til KI

> Lag presentasjonsutgaven av kurset «Lage et enkelt skjema» med Slidev. Følg oppskriften i
> `ai-generate/altinn-studio/kurs-enkelt-skjema-presentasjon-oppskrift.md`.
>
> Bruk den gjeldende kursartikkelen i
> `content/altinn-studio/v9/getting-started/development/basic-form/_index.nb.md` som eneste kilde for innhold. Bruk
> skjermbildene som allerede ligger i samme mappe, og ikke lag nye. Skriv presentasjonen til `slides.md` i samme mappe.
>
> Bygg presentasjonen og gå gjennom kontrollene i kapittel 6. Rapporter avvik fra lysbildeplanen og eventuelle
> skjermbilder i mappen som ikke er brukt.
