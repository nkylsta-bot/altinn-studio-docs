# Playbook: Kurset «Lage et enkelt skjema» i Altinn Studio

Kilde: `content/altinn-studio/v9/getting-started/development/basic-form/_index.nb.md` i
[altinn-studio-docs](https://github.com/Altinn/altinn-studio-docs).

Denne playbooken beskriver **caset** og **hva** deltakeren skal gjøre i kurset. Den beskriver ikke **hvordan** det gjøres
i grensesnittet. Navn på knapper, menyer og paneler endrer seg over tid. Når kurset skal skrives på nytt, skal den som
skriver det finne riktig fremgangsmåte i den gjeldende versjonen av Altinn Studio, og bruke denne playbooken som fasit for
innhold, rekkefølge og resultat.

---

## 1. Formål og målgruppe

**Målgruppe:** Tjenesteeiere og utviklere som ikke har brukt Altinn Studio før. Kurset forutsetter ingen
programmeringskunnskap.

**Formål:** Deltakeren skal lage sin første app i Altinn Studio, fra tom app til et enkelt skjema med to sider som kan
forhåndsvises. Kurset er første modul i serien «Lag en app». Senere moduler bygger videre på appen fra dette kurset
(tilgangskontroll, publisering og testing, grener).

**Læringsmål.** Etter kurset skal deltakeren kunne

1. opprette en app i en organisasjon
2. finne frem i appens oversikt og endre informasjon om appen
3. forklare forskjellen på eget arbeidsområde og appens sentrale område, og dele endringer
4. bygge en side med informasjonskomponenter
5. forklare hva en datamodell er, og lage en enkel datamodell med grupper og felter
6. bygge en skjemaside med inndatafelter, ledetekster og kobling til datamodellen
7. forklare at tekster lagres separat med egne ID-er
8. forhåndsvise skjemaet slik brukeren vil se det

---

## 2. Caset

**Sogndal kommune** vil ønske nye innbyggere velkommen og samtidig samle inn noen opplysninger om dem. Når noen melder
flytting til kommunen, skal de få tilgang til et enkelt skjema i Altinn.

Skjemaet har to sider:

1. **En velkomstside** med kommunens logo og en kort velkomsttekst.
2. **En side med opplysninger om innflytteren**, der innflytteren fyller ut personinformasjon, adresse og
   kontaktinformasjon, og sender inn skjemaet.

Deltakeren spiller rollen som tjenesteutvikler i kommunen. Kravene fra kommunen presenteres som en bestilling som
deltakeren skal oversette til datamodell og skjema.

### Krav fra kommunen

Kommunen vil i første omgang samle inn disse opplysningene om innflyttere:

- **Personinformasjon:** fullt navn, alder
- **Adresse:** gateadresse, postnummer, poststed
- **Kontaktinformasjon:** e-postadresse, telefon

---

## 3. Faste verdier i caset

Disse verdiene skal være like i alle versjoner av kurset, med mindre noen bevisst bestemmer noe annet. De gjør at
skjermbilder, senere moduler og eksempler i dokumentasjonen henger sammen.

### App

| Egenskap         | Verdi                                                                 |
|------------------|-----------------------------------------------------------------------|
| Eier             | Deltakerens organisasjon. Egen bruker går også, men gir ingen miljøer. |
| Appnavn          | Valgfritt for deltakeren. Må være unikt i organisasjonen.             |
| Tittel           | Beskrivende tittel, på både bokmål og nynorsk                         |
| Beskrivelse      | Hvem skal bruke appen, og hva skal de bruke den til                   |
| Oppgave/prosess  | Standardprosessen appen får ved opprettelse. Den første oppgaven er utfyllingsoppgaven. |

### Velkomstsiden

| Element      | Verdi                                                                                       |
|--------------|---------------------------------------------------------------------------------------------|
| Side         | Den første siden appen får ved opprettelse                                                   |
| Bilde        | Kommunelogo hentet fra URL. Bruk logoen som ligger i dokumentasjonen (`kommune-logo.png`).   |
| Avsnitt      | «Vi har registrert at du har meldt flytting til Sogndal kommune - velkommen til oss!»       |

### Datamodell

Deltakeren tømmer standardmodellen (`model`) og bygger denne strukturen:

| Gruppe (objekt) | Felt          | Type    |
|-----------------|---------------|---------|
| `person`        | `fullt_navn`  | Tekst   |
| `person`        | `alder`       | Heltall |
| `adresse`       | `gateadresse` | Tekst   |
| `adresse`       | `postnummer`  | Tekst   |
| `adresse`       | `poststed`    | Tekst   |
| `kontaktinfo`   | `epost`       | Tekst   |
| `kontaktinfo`   | `telefon`     | Tekst   |

Postnummer og telefon er tekst med vilje. Kurset tar ikke opp validering eller formatering.

### Skjemasiden

| Egenskap     | Verdi           |
|--------------|-----------------|
| Side-ID      | `om-innflytter` |
| Visningsnavn | Om innflytter   |

Komponenter, i denne rekkefølgen:

| Ledetekst     | Komponenttype        | Datamodellfelt          |
|---------------|----------------------|-------------------------|
| Fullt navn    | Tekstfelt, én linje  | `person.fullt_navn`     |
| Alder         | Tekstfelt, én linje  | `person.alder`          |
| Gateadresse   | Tekstfelt, én linje  | `adresse.gateadresse`   |
| Postnummer    | Tekstfelt, én linje  | `adresse.postnummer`    |
| Poststed      | Tekstfelt, én linje  | `adresse.poststed`      |
| E-postadresse | Tekstfelt, én linje  | `kontaktinfo.epost`     |
| Telefon       | Tekstfelt, én linje  | `kontaktinfo.telefon`   |
| Send inn      | Knapp for innsending | Ingen                   |

Bruk komponentnavnene slik de heter i grensesnittet når kurset skrives. I dagens versjon heter tekstfeltet
«Lite tekstfelt» og knappen «Knapp».

Kurset skal bruke det nye grensesnittet for å legge til komponenter. Deltakeren skrur det på med bryteren
**Prøv nytt design** øverst til høyre i Utforming. Ikke beskriv dra og slipp fra komponentlisten i det gamle designet.
Når det nye designet blir standard og bryteren forsvinner, fjerner du steget som skrur den på.

Navigasjon mellom sidene (Neste/Forrige) skal finnes. Hvis Studio ikke legger den til automatisk, skal deltakeren legge
den til.

---

## 4. Kursforløpet

Kurset består av åtte deler. Hver del har et mål, det deltakeren gjør, konseptene som skal forklares og et resultat
deltakeren kan sjekke mot. Rekkefølgen er pedagogisk begrunnet og bør beholdes.

### Del 1: Opprett appen

- **Mål:** Deltakeren har en app å jobbe i.
- **Deltakeren gjør:** Oppretter en ny app, velger organisasjonen som eier og gir appen et navn.
- **Forklar:** At navnet må være unikt i organisasjonen, og at det blir en del av URL-en til tjenesten.
- **Resultat:** Appen er opprettet, og deltakeren står på oversiktssiden.

### Del 2: Bli kjent med appen og endre informasjon om den

- **Mål:** Deltakeren kjenner hovedområdene i Studio og har gitt appen tittel og beskrivelse.
- **Deltakeren gjør:**
  1. Ser på oversiktssiden.
  2. Åpner innstillingene for appen og legger inn tittel på bokmål og nynorsk, og en beskrivelse.
  3. Går tilbake til oversikten og ser at tittelen er oppdatert.
- **Forklar:** Hva som finnes på oversiktssiden, for eksempel navigasjon til verktøyene, appens tittel, tilgjengelige
  miljøer (vanligvis TT02 og produksjon), lenke til dokumentasjonen og nyheter. Hvor brukeren ser tittelen: inne i appen og
  i innboksen i Altinn. At apper laget på egen bruker ikke har miljøer.
- **Resultat:** Oversikten viser den nye tittelen.

### Del 3: Lagre og dele endringer

- **Mål:** Deltakeren forstår lagringsmodellen og har delt sin første endring.
- **Deltakeren gjør:** Ser gjennom endringene sine, skriver en beskrivelse og deler endringene.
- **Forklar:** Forskjellen på
  - *eget område*, der Studio lagrer alt automatisk og bare deltakeren ser endringene, og
  - *appens sentrale område*, som alle ser og som publisering tar utgangspunkt i.
  Endringer må deles før de kan publiseres. Unngå Git-terminologi i hovedteksten.
- **Resultat:** Tittelendringen er delt.

### Del 4: Lag velkomstsiden

- **Mål:** Deltakeren har bygget en side med informasjonskomponenter.
- **Deltakeren gjør:**
  1. Åpner verktøyet for å utforme skjemaet, for utfyllingsoppgaven.
  2. Skrur på det nye grensesnittet for å legge til komponenter, med bryteren **Prøv nytt design** øverst til høyre.
  3. Åpner den første siden og legger til et bilde med kommunelogoen fra URL.
  4. Legger til et avsnitt med velkomstteksten.
- **Forklar:** Hvordan utformingsverktøyet er bygd opp, for eksempel sideoppsett, innstillinger for valgt element og
  forhåndsvisning. Beskriv panelene slik de er i gjeldende versjon, med det nye designet slått på. Vis hvordan man finner
  en komponent man ikke ser med en gang.
- **Resultat:** Forhåndsvisningen viser logo og velkomsttekst.

### Del 5: Lag datamodellen

- **Mål:** Deltakeren har en datamodell som dekker kravene fra kommunen.
- **Deltakeren gjør:**
  1. Åpner datamodellverktøyet og fjerner eksempelfeltene i standardmodellen.
  2. Lager tre grupper med felter etter tabellen i kapittel 3. Kurset viser første gruppe og første felt steg for steg.
     Deltakeren lager resten selv.
  3. Genererer modellfilene.
  4. Deler endringene.
- **Forklar:** At datamodellen er en slags innholdsfortegnelse for skjemaet. Den bestemmer *hva* som samles inn og
  *hvordan* dataene ser ut. For enkle skjemaer er det ofte ett skjemafelt per felt i datamodellen. For avanserte
  skjemaer kan de være ganske forskjellige. Lenk til veiledningen om datamodellering.
- **Resultat:** Modellen har tre grupper og sju felter, og modellfilene er generert. Vis et skjermbilde av ferdig modell
  som deltakeren kan sammenligne med.

### Del 6: Bygg skjemasiden

Dette er kjernen i kurset. Første komponent gjennomgås grundig med forklaring av konseptene. Resten legger deltakeren til
selv etter tabellen.

- **Mål:** Deltakeren har en skjemaside der alle felter har ledetekst og er koblet til datamodellen.
- **Deltakeren gjør:**
  1. Lager en ny side med side-ID og visningsnavn fra kapittel 3.
  2. Legger til et tekstfelt på én linje for fullt navn.
  3. Gir feltet ledeteksten «Fullt navn».
  4. Kobler feltet til `person.fullt_navn`.
  5. Legger til resten av komponentene etter tabellen i kapittel 3, inkludert innsendingsknappen.
- **Forklar:**
  - At Studio legger til navigasjon mellom sidene, hvis det fortsatt gjelder.
  - Hvorfor forhåndsvisningen viser en feil før feltet er koblet til datamodellen, hvis det fortsatt gjelder.
  - *Ledetekst:* teksten over feltet som forteller brukeren hva de skal fylle inn.
  - *Tekstressurser:* tekstene ligger i en egen tekstfil, og hver tekst har en ID. Komponenten peker på ID-en. Derfor kan
    samme tekst brukes flere steder, endres uten å endre komponenten og oversettes til nynorsk og engelsk. Vis at man
    kan gjenbruke en eksisterende tekst.
  - *Datamodellkobling:* hvert skjemafelt kobles til et felt i datamodellen, slik at svaret havner på riktig sted.
  - At innsendingsknappen ikke trenger kobling til datamodellen.
- **Fordypning (valgfri, sammenleggbar):** Vis hvordan navnefeltet ser ut i appens filer. Vis komponenten i
  layoutfilen for siden, med tekstkobling og datamodellkobling, og den tilhørende teksten i tekstfilen for bokmål. Hent
  eksemplet fra en app laget med gjeldende versjon, og si at ID-ene inneholder tilfeldige tegn.
- **Resultat:** Siden «Om innflytter» viser sju felter med riktige ledetekster og en innsendingsknapp, uten feilmeldinger.

### Del 7: Forhåndsvis skjemaet

- **Mål:** Deltakeren ser skjemaet slik brukeren vil oppleve det.
- **Deltakeren gjør:** Åpner forhåndsvisningen, starter på velkomstsiden, går videre til skjemasiden og prøver å fylle
  ut feltene. Går tilbake til utformingen.
- **Forklar:** Hva forhåndsvisningen kan og ikke kan. I dag kan man ikke sende inn fra forhåndsvisningen. For å teste
  hele flyten må appen publiseres til et testmiljø. Det kommer i en senere modul.
- **Resultat:** Begge sidene vises, og navigasjonen fungerer.

### Del 8: Del endringene

- **Mål:** Alt arbeidet ligger i appens sentrale område, klart for publisering i neste modul.
- **Deltakeren gjør:** Deler endringene med en beskrivelse.
- **Forklar:** Ingenting nytt. Henvis til del 3. Avslutt med lenke til oversikten over komponenter.
- **Resultat:** Ingen udelte endringer.

---

## 5. Sluttresultat

Kurset er vellykket når deltakeren har en app som

- har tittel på bokmål og nynorsk, og en beskrivelse
- har en velkomstside med kommunelogo og velkomsttekst
- har en datamodell med gruppene `person`, `adresse` og `kontaktinfo` og feltene i kapittel 3, med genererte modellfiler
- har siden `om-innflytter` med sju koblede tekstfelter og en innsendingsknapp
- kan forhåndsvises fra velkomstsiden til skjemasiden
- har alle endringer delt til appens sentrale område

---

## 6. Utenfor kurset

Disse temaene hører hjemme i senere moduler eller i referansedokumentasjonen. Nevn dem bare som pekere:

- publisering og testing i testmiljø
- tilgangsregler
- grener
- validering, obligatoriske felter og formatering av felter
- dynamikk, betingede felter og uttrykk
- oversettelse av alle tekster
- prosessendringer, for eksempel signering eller betaling
- lokal utvikling og kode

---

## 7. Føringer for kursteksten

- **Språk:** Bokmål, klarspråk, du-form. Følg skrivereglene i altinn-studio-docs.
- **Struktur:** Hver del har en kort forklaring av konseptet først og deretter nummererte steg. Navn på knapper, menyer og
  felter i grensesnittet skrives i **fet** skrift og nøyaktig slik de står i Studio.
- **Presentasjon:** Presentasjonen lages som en egen fil med Slidev, etter
  [oppskriften for presentasjonen](kurs-enkelt-skjema-presentasjon-oppskrift.md). Kursartikkelen trenger derfor ikke
  Marp-innstillinger. Skjermbildene brukes både i artikkelen og i presentasjonen.
- **Skjermbilder:** Ett skjermbilde per vesentlig steg eller resultat, minst disse:
  1. opprett ny app
  2. oversiktssiden, før og etter ny tittel
  3. innstillinger med tittel
  4. konseptbilde av eget og sentralt område
  5. dele endringer
  6. utformingsverktøyet med panelene markert
  7. legge til bilde, legge til avsnitt, ferdig velkomstside
  8. datamodellverktøyet, første gruppe og felt, ferdig modell, generere modeller
  9. ny side, legge til komponent, ledetekst, datamodellkobling, ferdig skjemaside
  10. forhåndsvisning av ferdig skjema
  Markeringer i skjermbildene skal peke på elementet steget handler om. Bruk filnavn uten mellomrom.
- **Lenker:** Bruk Hugo `relref` til dokumentasjonen for v9, ikke absolutte lenker til eldre versjoner.

---

## 8. Kjente svakheter i dagens versjon

Rett opp disse neste gang kurset skrives:

- **Lenke til eldre versjon:** Bilde-URL-en peker til dokumentasjonen for v8. Logoen bør ligge sammen med kurset i v9.
- **Nynorsk mangler fremgangsmåte:** Kurset ber deltakeren legge inn tittel på nynorsk, men forklarer ikke hvordan.
- **Tom seksjon:** Delingen etter datamodellen har bare et skjermbilde og ingen tekst.
- **Uklart om navngiving:** Kravene sier «Kontaktinformasjon», mens datamodellen bruker `kontaktinfo`. Feltnavnene for
  adresse og kontaktinformasjon står først i komponenttabellen, etter at modellen skal være laget. Vis hele
  datamodelltabellen i del 5.
- **Mellomrom i filnavn:** Noen skjermbilder har mellomrom i filnavnet og må URL-kodes.

---

## 9. Slik bruker du playbooken med KI

Gi en KI-agent denne playbooken, den gjeldende kursteksten og tilgang til Altinn Studio, med en bestilling som denne:

> Skriv en ny versjon av kurset «Lage et enkelt skjema» i
> `content/altinn-studio/v9/getting-started/development/basic-form/_index.nb.md`.
>
> Bruk playbooken som fasit for case, faste verdier, rekkefølge, læringsmål og resultat. Gå gjennom caset selv i den
> gjeldende versjonen av Altinn Studio, og beskriv fremgangsmåten slik grensesnittet fungerer nå. Bruk de nøyaktige
> navnene på knapper og menyer fra grensesnittet. Ta nye skjermbilder underveis etter listen i kapittel 7.
>
> Hvis grensesnittet gjør et steg overflødig eller umulig, skal du tilpasse fremgangsmåten og beholde målet for delen.
> Skriv en liste over avvik fra playbooken, slik at playbooken kan oppdateres. Rett opp svakhetene i kapittel 8.

Oppdater playbooken når kommunens case, de faste verdiene eller kursets omfang endres. Endringer som bare gjelder
grensesnittet hører hjemme i kursteksten, ikke her.
