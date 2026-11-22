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
| Skjermbilder       | `.jpg`-filene i samme mappe som kursartikkelen                                          |
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
| (finnes ikke)                                 | Agenda med delene i kurset, og ett lysbilde om caset med kravene fra kommunen     |
| Overskrift på nivå 3 (`###`)                  | Seksjonslysbilde med layout `section`                                            |
| Konseptforklaring                             | Ett lysbilde med 3 til 5 punkter. Resten av teksten blir talernotat.              |
| Nummererte steg under nivå 4 (`####`)         | Ett lysbilde med stegene forkortet til én linje hver, og med UI-navn i **fet**     |
| Skjermbilde                                   | Eget lysbilde med skjermbildet, eller høyre kolonne ved siden av stegene         |
| Tabell, for eksempel komponentene i skjemaet  | Tabellen beholdes, uten forklarende tekst rundt                                   |
| Merknad i sitat (`>`)                         | Talernotat, eller en kort linje nederst på lysbildet hvis den er viktig            |
| Sammenleggbar fordypning (`expandlarge`)      | Ett valgfritt lysbilde med kode, merket som fordypning                            |
| Lenker med `relref`                           | Full URL til docs.altinn.studio, eller fjernes                                     |
| (finnes ikke)                                 | Avslutning med oppsummering av hva deltakeren har laget, og hva neste modul er      |

### Forventet lysbildeplan for dagens kurs

Planen bruker alle de 21 skjermbildene i mappen én gang. Hvis kursartikkelen har endret seg, følger du kursartikkelen og
oppdaterer planen.

| #  | Del                     | Innhold                                              | Skjermbilde                                             |
|----|-------------------------|------------------------------------------------------|---------------------------------------------------------|
| 1  |                         | Forside                                              |                                                         |
| 2  |                         | Agenda                                               |                                                         |
| 3  |                         | Caset: Sogndal kommune og kravene                    |                                                         |
| 4  | Opprett en ny app       | Seksjon                                              |                                                         |
| 5  |                         | Steg for å opprette app                              | `Kurs-skjermbilder-Oppgave-Lag-ny-app.jpg`              |
| 6  | Redigere informasjon    | Seksjon                                              |                                                         |
| 7  |                         | Oversiktssiden og hva den viser                      | `Kurs-skjermbilder-Konsept-Oversikt-i-appen.jpg`        |
| 8  |                         | Steg for å endre tittel og beskrivelse               | `Kurs-skjermbilder-Oppgave-Endre-tittel-på-appen.jpg`   |
| 9  |                         | Tittel på bokmål og nynorsk, oppdatert oversikt       | `Kurs-skjermbilder-Konsept-Oversikt-i-appen-med-tittel.jpg` |
| 10 | Lagre og dele endringer | Seksjon                                              |                                                         |
| 11 |                         | Eget område og sentralt område                       | `Kurs-skjermbilder-Konsept-Endringer-og-lagring.jpg`    |
| 12 |                         | Steg for å dele endringer                            | `Kurs-skjermbilder-Oppgave-Del-endringer.jpg`           |
| 13 | Lage en informasjonsside| Seksjon                                              |                                                         |
| 14 |                         | Slik er Utforming bygd opp                           | `Kurs-skjermbilder-Konsept-Utforming.jpg`               |
| 15 |                         | Steg for å legge til bilde                           | `Kurs-skjermbilder-Oppgave-infoside-bilde-leggtil.jpg`  |
| 16 |                         | Steg for å legge til avsnitt                         | `Kurs-skjermbilder-Oppgave-infoside-avsnitt-leggtil.jpg`|
| 17 |                         | Resultat                                             | `Kurs-skjermbilder-Oppgave-infoside-resultat.jpg`       |
| 18 | Sette opp datamodellen  | Seksjon                                              |                                                         |
| 19 |                         | Hva en datamodell er                                 | `Kurs-skjermbilder-Konsept-Datamodell.jpg`              |
| 20 |                         | Krav fra kommunen                                    |                                                         |
| 21 |                         | Steg for å lage datamodellen                         | `Kurs-skjermbilder - Oppgave-Datamodell.jpg`            |
| 22 |                         | Ferdig datamodell                                    | `Kurs-skjermbilder - Oppgave-Datamodell-2-resultat.jpg` |
| 23 |                         | Generere modeller                                    | `Kurs-skjermbilder - Oppgave-Datamodell-generer-modeller.jpg` |
| 24 |                         | Dele endringene                                      | `Kurs-skjermbilder - Oppgave-Del-endringer-basic.jpg`   |
| 25 | Utforme skjemaet        | Seksjon                                              |                                                         |
| 26 |                         | Lag en ny side                                       | `Kurs-skjermbilder-Oppgave-Ny-side.jpg`                 |
| 27 |                         | Legg til den første komponenten                      | `Kurs-skjermbilder-Oppgave-Legg-til-komponent.jpg`      |
| 28 |                         | Ledetekst og tekstressurser                          | `Kurs-skjermbilder-Oppgave-Ledetekst.jpg`               |
| 29 |                         | Knytt feltet til datamodellen                        | `Kurs-skjermbilder-Oppgave-Datamodellfelt.jpg`          |
| 30 |                         | Fordypning: slik ser feltet ut i filene (valgfri)     |                                                         |
| 31 |                         | Tabell med resten av komponentene                    | `Kurs-skjermbilder-Oppgave-Resten-av-skjemaet.jpg`      |
| 32 |                         | Forhåndsvis skjemaet                                 | `Kurs-skjermbilder-Oppgave-Forhandsvis-skjema.jpg`      |
| 33 |                         | Del endringene                                       |                                                         |
| 34 |                         | Avslutning og neste modul                            |                                                         |

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
build:
  render: never
  list: never
  publishResources: false
layout: cover
---

# Lage et enkelt skjema
```

Headmatteren er også frontmatter for forsiden. Derfor står `layout: cover` her, og forsidens innhold kommer rett etter.

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
| `end`      | Siste lysbilde                                     |

Ikke bruk `image`, `image-right` eller `image-left` med relative stier i `image:`. Bildet blir pakket med, men vises ikke
på lysbildet. Bruk `two-cols` i stedet.

### Skjermbilder

- **Bruk relative stier** som starter med `./`, for eksempel `./Kurs-skjermbilder-Oppgave-Ny-side.jpg`.
- **Mellomrom i filnavn** skrives som `%20`, for eksempel `./Kurs-skjermbilder%20-%20Oppgave-Datamodell.jpg`. Ikke
  endre navnet på filene, fordi kursartikkelen bruker dem.
- **Store skjermbilder** settes inn med `<img>` og en høydegrense, ellers blir de kuttet nederst:

  ```html
  <img src="./Kurs-skjermbilder-Oppgave-Ny-side.jpg" class="max-h-100 mx-auto" alt="Lag en ny side" />
  ```

  Bruk vanlig markdown-bilde bare i en kolonne i `two-cols`, der bildet blir skalert etter bredden.
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
2. **Alle skjermbildene er med.** Antall `.jpg`-filer i `assets/` i den bygde presentasjonen skal være likt antallet
   skjermbilder du har brukt.
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
