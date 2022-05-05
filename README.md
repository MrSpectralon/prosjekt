# prosjekt


| Gruppe | (bytt med nummer) |
| ------ | -------- |
| Fornavn | Etternavn |
| Fornavn | Etternavn |

---
## Introduksjon
Prosjekt for elever på VGS.

Målet med oppgaven er å lage en database og et program som kan hente ut og sette inn data i denne databasen.

Via prosjektet får enn prøvd seg litt på: 
- Planlegging av datastruktur
- Gruppearbeid via Git
- Praktisk eksempel og bruk av database med relasjoner mellom tabeller.
- SQL queries.



---

## Vurdering

Oppgaven vil bli gitt en total vurdering med poeng opp til 100.
Hver oppgave har en egen verdi av poeng.

---

# Oversikt

## Huskeliste av oppgaver

1. [Lag fork av dette repositoryet](/README.md#fork-prosjektet)
2. [Legg til gruppemedlemmer i repo som utviklere.](/README.md#legge-til-gruppemedlemmer-i-repository)
3. [Sett opp .gitignore for IDE filer.](/README.md#sett-opp-.gitignore-for-IDE-filer)
4. [~~Endre på branch regler - Ikke lov å "pushe" til master branch.~~](/README.md#endre-branch-regler)
5. [Lag plan for database struktur.](/README.md#lag-plan-for-database-struktur) 10p
6. [Lag plan for prosjekt/program struktur.](/README.md#lag-plan-for-prosjektprogram-struktur) 10p

7. [Implementer databasen.](/README.md#database) 20p
8. [Implementer program som kan hente data og sette inn data i databasen.](/README.md#program) 60p

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
**Bakgrunn til oppgaven:**
***Du og din vennegjeng er ekstremt glade i energidrikker, og finner en dag ut at dere skal lage en oversikt over alle energidrikkene dere har prøvd og dokumentere alle sine ratings av dem.***

***For å få dette til kom dere frem til at det greieste hadde hvert å sette opp en database for lagring av data, og en simpel meny laget i terminal for enkel tilgang til styring av databasen.***

- Løsningen trenger da en database som lagrer bruker informasjon og produkt informasjon fra flere produsenter i tillegg til brukernes rating av produktene.
- Databasen skal styres i fra et eksternt program som enkelt kan hente ut og legge inn mer data i databasen.

- Programmet som kommuniserer med databasen skrives i Python.


# TODO(s)


## Fiks git repo (10p)
### Fork prosjektet

**KUN ÉN PERSON PÅ GRUPPA TRENGER Å GJØRE DETTE STEGET.**

For å forke prosjektet så trykker du på **fork** som ligger oppe til høyre på hoved siden til dette repositoryet (root directory).

Sett **Project name** til å være hydro_reviews_[+gruppenavn] (f.ex: hydro_reviews_1337) og sett deretter prosjektet til å være privat.

![Fork repo](readmeImages/fork-project.png)



### Legge til gruppemedlemmer i repository 
- Oppe i venstre hjørne av GitLab finner du **"Members"** under **"Project Information"** kategorien.
- Trykk deretter på **"Invite members"** nær toppen på høyre siden av **"Members"** tabben.

![Gitlab add members](readmeImages/gitlab-add-members.png)

- Inviter gruppemedlemmene som **Maintainer** eller **Developer**, inviter også stian.pedersen1996 som **Reporter**.

![Gitlab add roles](readmeImages/gitlab-member-roles.png)

Etter dette er gjort så legger dere inn alle gruppe medlemmene inn på toppen av denne README.md fila.


### ~~Sett opp .gitignore for IDE filer~~

**Python HAR IKKE EKSTERN COMPILER OG ANDRE IDE SPESIFIKE FILER. DETTE STEGET TRENGS IKKE**

For å hindre at autogenererte filer som er forskjellige for alle på gruppen, er det nødvendig å sette opp et filter som utelokker disse i fra å bli lastet opp på deres repository.

Bildet under viser et resultatet av kommandoen `git status` i et nytt prosjekt der .gitignore filen er tom og IDE'en har generert masse filer som vi ikke ønsker å laste opp til git.

![All files git](/readmeImages/all-files-git.png)

I dette tilfellet er vi kun interessert i å laste opp filene som de andre på gruppen trenger, så vi setter opp **.gitignore** fila til å ignorere de uønskede filene:
```.gitignore
#Merk at alt som slutter med "/" er en mappe, og inneholder mange andre filer og mapper.
#Ved å ekskludere ytterste mappen, ekskluderer du alt innenfor også.
.gradle/
.idea/
gradle/
local.properties
```
**Merk at alle filer som starter med'.' er skjulte og vises derfor ikke normalt sett i deres 'file explorer'**
Etter **.gitignore** fila er satt opp, vil `git status` kun vise de filene vi ønsker å laste opp.

![With Gitignore](readmeImages/files-with-gitignore.png)

### ~~Endre branch regler~~

Kan ikke brukes på gratis versioner av GitLab og GitHub.
Her skulle det settes opp regler som gjør det umulig å laste opp endringer direkte til 'master' branchen. Dette er avnlig å gjøre for å forhindre kresj mellom versjoner fra utviklerene. En annen grunn til at enn ikke skal pushe endringer direkte til master branch - er at det er branchen som alltid skal ha et fungerende produkt.

---

## Planlegging

### Lag plan for database struktur 
Totalt tilgjengelig 10p.

Lag en ERD(Entity Realtionchip Diagram) av tabeller og hvilken data som skal inn i tabellene, sett deretter opp relasjoner imellom tabellene, slik at samme dataen blir lagret minst mulig ganger.

Her anbefaler jeg at dere bruker [Lucid chart](https://www.lucidchart.com/) til å tegne diagrammene, ettersom det et lett å lage en oversiktlig tegning av database strukturen. 

Guide til å sette opp ordentlig ERD tegning:
[ERD part 1: https://www.youtube.com/watch?v=QpdhBUYk7Kk](https://www.youtube.com/watch?v=QpdhBUYk7Kk)

[ERD part 2: https://www.youtube.com/watch?v=-CuY5ADwn24](https://www.youtube.com/watch?v=-CuY5ADwn24)

ERD'en skal lastes opp i repo som bilde eller pdf fil. 

### Lag plan for prosjekt/program struktur
Totalt tilgjengelig 10p.

Strukturen på programmet skal settes opp som om det var et stort prosjekt - altså strukturere programmet slik at det har flere klasser og flere filer som brukes sammen.

Tegn en plan/diagram for hvor mange klasser som skal være i programmet og hvordan de skal kommunisere sammen.
Last planen opp som et bilde eller PDF. Dere kan da tegne planen på papir eller bruke et program for tegningen.

Her er eksempel på klasse strukturen på et større prosjekt:
![Class structure](/readmeImages/projectStructure.png)

---

## Implementasjon

### Database

Selve databasen er ikke anbefalt å laste opp på Git, så dere må eksportere SQL koden som lager databasen som egen SQL fil og laste den opp på git istedet. 
Egen fil med SQL kode for å legge inn test data i databasen er også anbefalt, slik at det er lett å legge inn ny data automatisk dersom databasen skulle ødelegges eller lignende.


### Program

Lite eksempel på inndeling: 
-  **Database.py**: inneholder en klasse, og håndterer alle interaksjoner(queries) med databasen, og ingenting annet.
- **ConsoleNavigation.py**: Håndterer all interaksjon og navigasjon gjort i konsoll.
Eksempel på konsoll interaksjon: 
```py

bool running = False
while (running)
   print("""
      Type one of the following letters to navigate through the menu.

      u : Enter User options
      f : Find reviews
      x : Exits the program
   """)

   choice = input("Action: ")

   match choice.lower():
      case 'u':
         user_option_menu()
      case 'f':
         find_reviews()
      case 'x':
         running = false
      case _:
         print("No such entry.")


```

**Funksjonaliteter som skal implementeres:**

**SIDEN DERE ALLEREDE HAR STARTET PÅ WEBDESIGN, KAN DERE FORTSETTE MED DETTE, MEN FUNKSJONALITETER SKAL OGSÅ VÆRE TILGJENGELIG I KOMMANDO LINJE (SE KODE EKSEMPEL OVENFOR)**

- Det må være mulig for brukere å legge inn nye produsenter og produkter hvis de ikke allerede eksisterer i databasen.

- Brukere skal også ha mulighet til å slette sine reviews av produkter. I tilfeller der brukere sletter sitt review av et produkt - og det ikke er noen andre som har review av produktet, skal også selve produktet slettes fra databasen.

- Som søke filter skal det være mulig å hente ut alle reviews en spesifik bruker har skrevet. (Altså du søker etter en bruker og så vises alle reviews den brukeren har skrevet)

- Det skal være mulig å hente ut alle reviews skrevet om et spesifikt produkt.

- Det skal være mulig å hente ut alle produktene til en spesifik produsent/merke.

- Det skal være mulig å hente ut alle produkter som har fått gjennomsnittlig terningskast X eller høyere.

- Det skal også være en funksjon som lister ut top tre "Bang for the buck" produktene. (Altså pris delt på gjennomsnittlig terningskast)



Programmet kan senere utvides til å bruke webtjeneste istedet for å styre programmet via terminalen. (Dersom vi har tid til det)

---

# Veileding

## Git

### GitLab

#### Issueboard

For å få bedre arbeidsflyt i GitLab, anbefaler jeg å ta i bruk Kanban brettet(issueboard). Dette er et verktøy som enkelt gir gruppa oversikt over hvilke oppgaver som gjenstår, hvem som jobber med hva, og hva som er ferdig.

![Git issueboard](/readmeImages/Git-issueboard.png)

Issueboardet begynner ganske tomt, med bare to kategorier (**Open** og **Closed**), så for å utnytte brettet ordentlig er det viktig å legge til flere kategorier.

For å legge til flere kategorier trykker du på **Issues** -> **List** og deretter på **New issue** på høyre side av nye siden du åpner, som vist på bildet under.

![Label](readmeImages/git-list-new-issue.png)

Etter dette trykker du på **Labels** dropdown menyen som ligger nede til venstre. Trykk deretter på **Create new Label** og skriv inn hva enn du ønsker å navngi den. 

![New label](readmeImages/create-new-label.png)

En god måte å bruke issueboardet på kan vœre å legge inn et issue så fort du kommer på en ting som bør implementeres - men ikke har tid til å gjøre akkurat nå.

#### Notifikasjon via Webhook

For dere som er spesielt interessert, kan det være gøy å få satt opp automatiske notifikasjoner i Discord når det skjer oppdateringer på git.

[Kort tutorial på oppsett her](https://gist.github.com/jagrosh/5b1761213e33fc5b54ec7f6379034a22)

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

git fetch --all # Henter alle branches fra repo og oppdaterer dem.
```
---

## Database

### Composit Primary Key

![Database Model](/readmeImages/physicalModel.png)

```sql
CREATE TABLE `Location` (
  `cat_ID` int,
  `timestamp` TIMESTAMP,
  `pos_X` float,
  `pos_Y` float,
  PRIMARY KEY (`cat_ID`, `timestamp`),
  FOREIGN KEY (`cat_ID`) REFERENCES `Cat`(`cat_ID`)
);

```

### Query
