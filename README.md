# prosjekt


| Gruppe | (bytt med nummer) |
| ------ | -------- |
| Fornavn | Etternavn |
| Fornavn | Etternavn |
| Fornavn | Etternavn |

---
## Introduksjon
Prosjekt for elever på VGS.

Målet med oppgaven er å lage en database og et program som henter ut og setter inn data i denne databasen. 
Strukturen på programmet skal settes opp som om det var et stort prosjekt - altså strukturere programmet slik at det har flere klasser og flere filer som brukes sammen.


Databasen og tabellene skal settes opp slik at den følger kravene til [3NF](https://en.wikipedia.org/wiki/Third_normal_form) standarden.

Programmet som kommuniserer med databasen kan skrives i Python.

Programmet kan senere utvides til å bruke Javascript som frontend og python som backend.(Dersom vi har tid til det)

---

# Oversikt

## Huskeliste av oppgaver

- [ ] [Lag fork av dette repositoryet](/README.md#fork-prosjekt)
- [ ] [Legg til gruppemedlemmer i repo som utviklere.](/README.md#legge-til-gruppemedlemmer-i-repository)
- [ ] [Sett opp .gitignore for IDE filer.](/README.md#sett-opp-.gitignore-for-IDE-filer)
- [ ] [~~Endre på branch regler - Ikke lov å "pushe" til master branch.~~](/README.md#endre-branch-regler)
- [ ] [Lag plan for database struktur.](/README.md#lag-plan-for-database-struktur)
- [ ] [Lag plan for prosjekt/program struktur.](/README.md#lag-plan-for-prosjekt/programm-struktur)

- [ ] [Implementer databasen.]()
- [ ] [Implementer  API som kan hente data og sette inn data i databasen. ]()

### Brukerveileding og hjelp

- [Generellt bruk av Git](/README.md#git)
   - [GitLab](/README.md#gitlab)
      - [Issueboard](/README.md#issueboard)
      - [Notifikasjon via Webhook](/README.md#notifikasjon-via-webhook)
   - [Git Bash](/README.md#git-bash)
      - [Kommandoer](/README.md#gitbash-kommandoer)

- [Database](/README.md#database)

---

## Oppgavetekst

Dere skal lage en tjeneste som lar deg og din vennekrets(venners venner) skrive reviews om diverse produkter. Tjenesten må da lagre informasjon om brukere, produsent/merke, produkt og selvfølgelig reviewene til brukerne.

Det skal være mulig for brukere å legge inn nye produsenter hvis de ikke allerede eksisterer i databasen. Det samme gjelder for produkter. 

Brukere skal også ha mulighet til å slette sine reviews.

Som søke filter skal det være mulig å hente ut alle reviews til hver spesifik bruker.
Det skal være mulig å hente ut alle reviews om et spesifikt produkt.
Det skal være mulig å hente ut alle produktene til en spesifik produsent/merke..



# TODO(s)


## Fiks git repo
### Fork prosjektet

For å forke prosjektet så trykker du på **fork** som ligger oppe til høyre på denne siden (repository root directory).

Sett **Project name** til å være hydro_reviews_[+gruppenummer] (f.ex: hydro_reviews_01) og sett deretter prosjektet til å være privat.

![Fork repo](Images/fork-project.png)



### Legge til gruppemedlemmer i repository 
- Oppe i venstre hjørne av GitLab finner du **"Members"** under **"Project Information"** kategorien.
- Trykk deretter på **"Invite members"** nær toppen på høyre siden av **"Members"** tabben.

![Gitlab add members](Images/gitlab-add-members.png)

- Inviter gruppemedlemmene som **Maintainer** eller **Developer**, inviter også stian.pedersen1996 som **Reporter**.

![Gitlab add roles](Images/gitlab-member-roles.png)

Etter dette er gjort så legger dere inn alle gruppe medlemmene inn på toppen av denne README.md fila.


### Sett opp .gitignore for IDE filer

For å hindre at autogenererte filer som er forskjellige for alle på gruppen, er det nødvendig å sette opp et filter som utelokker disse i fra å bli lastet opp på deres repository.

Bildet under viser et resultatet av kommandoen `git status` i et nytt prosjekt der .gitignore filen er tom og IDE'en har generert masse filer som vi ikke ønsker å laste opp til git.

![All files git](/Images/all-files-git.png)

I dette tilfellet er vi kun interessert i å laste opp filene som de andre på gruppen trenger så vi setter opp **.gitignore** fila til å ignorere de uønskede filene:
```.gitignore
#Merk at alt som slutter med "/" er en mappe, og inneholder mange andre filer og mapper.
#Ved å ekskludere ytterste mappen, ekskluderer du alt innenfor også.
.gradle/
.idea/
gradle/
local.properties
```

Etter **.gitignore** fila er satt opp, vil `git status` kun vise de filene vi ønsker å laste opp>

![With Gitignore](Images/files-with-gitignore.png)

### ~~Endre branch regler~~

Kan ikke brukes på gratis versioner av GitLab og GitHub 

---

## Planlegging

### Lag plan for prosjekt/program struktur

Tegn en plan/diagram for hvor mange klasser som skal være i programmet og hvordan de skal kommunisere sammen.
Last det opp som et bilde eller PDF. Dere kan da tegne planen på papir eller bruke et program for tegningen. 

---

### Lag plan for database struktur

Lag en Conceptual model av tabeller og hvilken data som skal inn i tabellene, sett deretter opp relasjoner imellom tabellene, slik at samme dataen ikke blir lagret minst mulig ganger. 
Her anbefaler jeg at dere bruker [Lucid chart](https://www.lucidchart.com/pages/) til å tegne diagrammene, ettersom det gjør ting oversiktlig og fint.

### Databasen skal inneholde:

Databasen skal ha en oversit over alle brukerne med kontakt informasjonen demmes, dvs: navn, nummer etc...  
 - Bruker: 
    - Bruker ID {PK}
    - Navn
    - Nummer
    - E-Mail
 - Drikke
    - Drikke ID {PK}
    - Merke/produsent
    - Type
    - Pris
    - Sukkerinnhold
    - andre detaljer(optional)
  - Review
    - PPK {Bruker ID, Drikke ID}
    - terningskast
    - Review
    - Forfatter
    - Hva er det/type og merke

---

# Veileding

## Git

### GitLab

#### Issueboard

For å få bedre arbeidsflyt i GitLab, anbefaler jeg å ta i bruk Kanban brettet(issueboard). Dette er et verktøy som enkelt gir gruppa oversikt over hvilke oppgaver som gjenstår, hvem som jobber med hva, og hva som er ferdig.

![Git issueboard](/Images/Git-issueboard.png)

Issueboardet begynner ganske tomt, med bare to kategorier (**Open** og **Closed**), så for å utnytte brettet ordentlig er det viktig å legge til flere kategorier.

For å legge til flere kategorier trykker du på **Issues** -> **List** og deretter på **New issue** på høyre side av nye siden du åpner, som vist på bildet under.

![Label](Images/git-list-new-issue.png)

Etter dette trykker du på **Labels** dropdown menyen som ligger nede til venstre. Trykk deretter på **Create new Label** og skriv inn hva enn du ønsker å navngi den. 

![New label](Images/create-new-label.png)

En god måte å bruke issueboardet på kan vœre å legge inn et issue så fort du kommer på en ting som bør implementeres - men ikke har tid til å gjøre akkurat nå.

#### Notifikasjon via Webhook

For dere som er spesielt interessert, kan der være gøy å få satt opp automatiske notifikasjoner i Discord når noen på gruppa gjør endringer på git.

Oppsett av Webhook er


### Git Bash

#### GitBash kommandoer

Standard kommandoer som brukes mesteparten av tiden.

```bash
git status # Gir deg oversikt over alle filer som er endret eller nye.

git add  # brukes for å legge til endrede filer i neste commit. 
         # Du kan enten manuellt legge til alle filnavnene, eller bruke . 
         # for å legge til alle filene som er merket med rødt i 
         # 'git status' kommandoen.

git commit -m 'message' # Klargjør filene som skal pushes opp til repo.

git push # Pusher endringer opp til git repo(hvis mulig).

git pull # Henter endringer fra git repo og legger det inn på dine lokale filer.

```

Ekstra Kommandoer for når flere branches er i bruk.

```bash

git switch <branch navn> # Går fra nåværende branch og inn på den 
                            # branchen du skrev inn hvis den eksisterer.

git switch -c <branch navn> # Gjør det samme som kommandoen over, bare denne 
                               # lager en ny branch med navnet du skrev

git push --set-upstream origin <branch navn> # Må gjøres første gang du skal 
                                             # bruke push på en ny branch.
                                             # Terminalen vil også gi beskjed 
                                             # om dette om du glemmer det.

git rebase origin <branch navn> # Dette er en funksjon som setter en branch som
                                # "base". Den brukes når din branch ligger en 
                                # del versjoner bak den branchen du ønsker å
                                # "merge" med, og gjør slik at din versjon av 
                                # alle filene på branchen er lik den du skal 
                                # bruke merge med + de endringene du har jobbet 
                                # med.



```
---

## Database

### Query
