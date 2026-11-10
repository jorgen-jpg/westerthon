# Westerthon

Nettsiden westerthon.no. Hele siden er én fil: `index.html`. GitHub Pages publiserer automatisk fra roten av `main`, så en endring er ute på westerthon.no et par minutter etter at den er lagret her.

Repoet er offentlig. Alt som ligger her, kan leses av alle.

## Slik endrer du siden

1. Åpne `index.html` her på GitHub og trykk på blyanten («Edit this file»).
2. Søk etter `const CONFIG` (Cmd/Ctrl + F). Alt innhold står i den lista.
3. Endre bare det som står mellom anførselstegnene, eller tallene. La resten stå.
4. Trykk «Commit changes». Siden oppdateres av seg selv.

## Regler som må holdes

- Tekst står i anførselstegn: `tittel: "Badekaret"`.
- Tall står uten anførselstegn og uten mellomrom: `antall: 1800`.
- Det er komma etter hver linje i en liste, også når du legger til en ny.
- Ikke slett klammer `{ }` og `[ ]`.

**Ble siden blank eller rar?** Da mangler det et komma, et anførselstegn eller en klamme. Angre siste endring (Cmd/Ctrl + Z), lagre og prøv igjen.

## Det dere oftest endrer

- **Sub-tallet:** `subs: { antall: 1800 }`.
- **Sub goals (`goals`):** én linje per mål: `{ subs: 6000, tittel: "Noe gøy", type: "stunt" },`. Type er `"giveaway"`, `"stunt"` eller `"chat"`. Skriv `hemmelig: true` for å skjule tittelen til målet er nådd.
- **Det store målet (`rekord`):** vises midt på siden, i bunnlinja og nederst i stigen. Endre `subs`, `etikett` og `tittel`. Under streamen viser det også hvor mange subs som gjenstår. Skriv `rekord: null` for å fjerne det.
- **Tomme lister skjules eller viser «kommer»:** `goals: []` viser «Sub goals kommer», `program: []` viser «Program kommer», og `gjester: []` skjuler hele gjesteseksjonen.
- **Flere mål på vei (`flereKommer`):** `flereKommer: true` viser raden «Flere mål avsløres underveis» nederst i stigen, og «Nye mål kommer» når alle målene i fila er nådd. Sett `false` når hele stigen er lagt ut.
- **Avsløre nye mål:** lim inn en ny linje i `goals` og lagre. Mål som står i fila kan leses i kildekoden, også når de er skjult med `visTil`. Hold derfor hemmelige mål utenfor fila, og utenfor dette repoet, til de skal ut.
- **Program (`program`):** `program: []` viser «Program kommer». Legg inn én blokk per dag med `dato: "2026-11-16"`. Hvert punkt: `{ tid: "20:00", slutt: "21:00", tittel: "…", notat: "…" },`. `slutt` og `notat` er valgfrie. Uten klokkeslett: `tid: ""`. Da står punktet som «Senere».
- **Gjester (`gjester`):** `{ navn: "Navn", rolle: "Dagens gjest", dato: "2026-11-15" },`. Bare bekreftede navn.
- **Kofferten (`koffert`):** `pott: 25000` viser beløpet (`null` skjuler det). Lås opp et hint ved å bytte `{ tekst: null }` med `{ tekst: "Hinttekst" }`. Bilde fra viltkameraet: `bilde: "viltkamera.jpg"`.
- **Tekstbåndet (`band`):** tekstene som ruller over siden.
- **Partnere (`partner` og `partnere`):** `partner` er hovedpartneren, `partnere` er lista under. `lenke: "https://…"` gjør navnet klikkbart, og `logo: "assets/partnere/filnavn.webp"` viser logoen rett på den mørke flaten. Bruk en versjon laget for mørk bakgrunn (lys skrift, gjennomsiktig bakgrunn). Logofilene ligger i `assets/partnere/`. Bytter du ut en logo, gi den nye fila et nytt navn, ellers viser nettlesere den gamle en stund. Legg til eller fjern en linje i `partnere` for å endre lista.
- **Spørsmål (`faq`):** `{ q: "Spørsmål?", a: "Svar." },`.
- **Lenker (`lenker`):** fyll inn adressen til TikTok, Instagram og YouTube. Tomme felt vises ikke.
- **Modus:** `"auto"` går live av seg selv kl. 15:00 den 14.11. Skriv `"ferdig"` når det er over.

**Bilder** (viltkamera, partnerlogo, delingsbilde) lastes opp i mappa `assets/`, og så skriver du `assets/filnavn.jpg` i feltet. Westerthon-logoen ligger allerede inni fila. Ikke rør den lange blokka nederst.

## Twitch-spilleren

Spilleren og chatten virker bare når siden åpnes fra westerthon.no (eller et annet domene med HTTPS). Åpner du fila rett fra maskinen, er spilleren grå. Det er normalt.

## For utviklere

- Testbrytere i adressen: `?now=2026-11-15T12:00:00+01:00` (tiden står stille), `?subs=1800`, `?modus=nedtelling|live|ferdig`.
- Ingen byggesteg og ingen avhengigheter. CSS, JavaScript og logoen ligger inline i `index.html`.
