# Yrkesfaglig-fordypning-3IMI-omar

Matoppskrifter

Om prosjektet

Matoppskrifter er et tidligere skoleprosjekt jeg utviklet i VG2. Det er en webapplikasjon der brukere kan registrere seg, logge inn og dele matoppskrifter med hverandre.

Prosjektet ble opprinnelig laget med Python og Flask som backend, MySQL som database og HTML/CSS som frontend. Databasen kjørte på en Raspberry Pi som fungerte som en lokal server.

I VG3 skal jeg bruke prosjektet videre i faget yrkesfaglig fordypning (YFF). Målet er å forbedre den eksisterende løsningen ved å fokusere på IT-sikkerhet. Jeg skal gå gjennom hvordan applikasjonen er bygget opp, identifisere sikkerhetsutfordringer og implementere tiltak som gjør løsningen tryggere.

Jeg skal også tilpasse serveroppsettet slik at prosjektet kan kjøres på Debian.

Eksisterende funksjonalitet

Brukerregistrering og innlogging

Brukere kan opprette en konto med brukernavn og passord og deretter logge inn for å bruke applikasjonen. Etter innlogging opprettes en sesjon som holder brukeren innlogget mens de navigerer på nettsiden.

Legge til oppskrifter

Innloggede brukere kan legge til oppskrifter ved å fylle ut et skjema med navn, ingredienser, fremgangsmåte, koketid og antall porsjoner. Oppskriften lagres i databasen og vises på hovedsiden.

Se alle oppskrifter

På hovedsiden vises oppskriftene som er lagt til i applikasjonen. Brukerne kan se informasjon om hver oppskrift, blant annet ingredienser, fremgangsmåte, koketid og antall porsjoner.

Slette oppskrifter

Brukere kan slette oppskrifter fra applikasjonen. Når en oppskrift slettes, skal den også fjernes fra brukernes lagrede oppskrifter.

Lagre favorittoppskrifter

Brukere kan lagre oppskrifter som favoritter. Disse vises på en egen side, der brukeren kan se og fjerne sine lagrede oppskrifter.

FAQ

Applikasjonen skal ha en FAQ-side der brukerne kan finne svar på vanlige spørsmål. Det skal også være mulig å sende inn egne spørsmål gjennom et skjema.

Planlagt arbeid i VG3 YFF

Hovedmålet med prosjektet er å videreutvikle Matoppskrifter med fokus på sikkerhet. Jeg skal undersøke den eksisterende løsningen og implementere flere sikkerhetstiltak.

1. Bruke .env for konfigurasjon

Jeg skal opprette en .env-fil for å lagre sensitiv konfigurasjon, for eksempel databasebrukernavn, databasepassord og Flask sin hemmelige nøkkel.

Dette gjør at sensitiv informasjon ikke trenger å ligge direkte i kildekoden. Jeg skal også sørge for at .env legges til i .gitignore, slik at filen ikke lastes opp til GitHub.

2. Implementere passordhashing

Jeg skal implementere sikker hashing av passord ved hjelp av funksjoner som generate_password_hash() og check_password_hash() fra Werkzeug.

Passord skal ikke lagres i klartekst i databasen. I stedet skal applikasjonen lagre en hash som brukes til å kontrollere passordet når brukeren logger inn.

Jeg skal også kontrollere at eksisterende registrering og innlogging fungerer med den nye løsningen.

3. Begrense nettverkstilgang med porter og brannmur

Jeg skal konfigurere Debian-serveren slik at applikasjonen bare er tilgjengelig fra det lokale nettverket jeg bruker til prosjektet.

Dette innebærer å undersøke hvilke porter som er åpne, og konfigurere brannmuren slik at bare nødvendige tilkoblinger tillates. Jeg skal unngå å eksponere applikasjonen direkte mot internett.

Målet er at andre enheter på det godkjente lokale nettverket skal kunne nå nettsiden, mens tilkoblinger utenfra skal blokkeres.

Jeg skal også kontrollere at databasen ikke er tilgjengelig direkte fra andre maskiner dersom den bare trenger å brukes av applikasjonen lokalt på serveren.

4. Begrense antall mislykkede innloggingsforsøk

Jeg skal implementere en begrensning på hvor mange ganger en bruker kan forsøke å logge inn med feil passord.

Etter et bestemt antall mislykkede forsøk skal nye innloggingsforsøk blokkeres midlertidig. Dette skal redusere risikoen for at noen prøver mange forskjellige passord for å få tilgang til en konto.

Jeg skal undersøke hvordan dette kan implementeres i Flask, og sørge for at begrensningen fungerer på en kontrollert måte. Det skal også være mulig å logge inn igjen når sperreperioden er over.

5. Tilpasse prosjektet til Debian

Det opprinnelige prosjektet brukte en Raspberry Pi som server. I VG3 skal jeg sette opp prosjektet på Debian.

Jeg skal installere nødvendige pakker, konfigurere databasen og tilpasse oppsettet slik at applikasjonen kan kjøres på det nye systemet.

Målet er å få den eksisterende funksjonaliteten til å fungere på Debian før jeg begynner å teste de nye sikkerhetstiltakene.

Testing og dokumentasjon

Underveis skal jeg teste at både eksisterende funksjoner og nye sikkerhetstiltak fungerer som forventet.

Jeg skal blant annet teste:

At brukere kan registrere seg og logge inn.

At passord ikke lagres i klartekst.

At databaseopplysninger og hemmelige nøkler ikke ligger direkte i kildekoden.

At applikasjonen bare er tilgjengelig fra det tillatte lokale nettverket.

At innlogging sperres midlertidig etter for mange mislykkede forsøk.

At oppskrifter kan legges til, vises, lagres som favoritter og slettes.

At applikasjonen fungerer på Debian.

Jeg skal dokumentere arbeidet og resultatene av testingen, slik at det blir mulig å se hvilke sikkerhetstiltak som er implementert, og hvordan de fungerer.

Mål for prosjektet

Målet med dette YFF-prosjektet er å videreutvikle et tidligere VG2-prosjekt og bruke kunnskapen min innen programmering, serveradministrasjon og IT-sikkerhet i praksis.

Ved å forbedre sikkerheten i en eksisterende applikasjon skal jeg få erfaring med å identifisere sårbarheter, implementere sikkerhetstiltak og teste at en løsning fungerer som forventet.

Prosjektet skal ende opp som en fungerende webapplikasjon på Debian med bedre beskyttelse av brukerkontoer, konfigurasjon og nettverkstilgang.
