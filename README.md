<p align="center">
  <img src="https://engeto.cz/wp-content/uploads/2019/01/engeto-square.png" width="200" height="200">
</p>

# Java - 6. lekce

## Co bychom měli mít hotové

## Co nás čeká

- [Verzovací systémy](#verzovací-systémy)

- [GIT](#git)

- [Instalace GITu](#instalace-gitu)

- [Repozitář](#repozitář)

- [Hostingové služby](#hostingové-služby)

- [Účet na githubu](#účet-na-githubu)

- [ssh klíč](#ssh-klíč)

- [IDE vs terminál](#ide-vs-terminál)

- [Příkazy](#příkazy)

## Verzovací systémy

Jak už název naznačuje, verzovací systém (anglicky VSC – Version Control System) odkazuje na systém, který spravuje různé verze našeho projektu. Jinými slovy, zaznamenává změny v souborech. Verzovací systémy výrazně zjednodušují správu jak skupinových, tak individuálních projektů. Jednou z přidaných hodnot je, že předchází potenciálním lidským chybám, jako je třeba postupná degradace nebo ztráta zdrojového kódu.

Dobrý verzovací systém funguje na jakémkoli operačním systému (Linux, Windows, MacOS a podobně) a můžeme ho použít pro projekt v jakémkoli programovacím jazyce – v Pythonu, C# nebo třeba v Javě.

Hlavní výhody verzovacích systémů jsou:

 - Uchovávají kompletní historii všech souborů v rámci projektu – to znamená, že máme k dispozici informace o vytvoření, smazání, změnách, autorovi, datu a další.
 - Schopnost větvit a slučovat (anglicky branching & merging) – když na projektu pracuje více lidí, verzovací systém se stará o to, aby mohli pracovat na stejné věci současně tím, že umožňuje vytvářet nové „větve“ (anglicky branches) projektu a zase je zpátky slučovat dohromady.
 - Umožňuje snadné zpětné dohledávání změn v naší historii – při zaznamenávání změn nám verzovací systém umožňuje veškeré změny dokumentovat.

## GIT

Git je open source verzovací systém, který je zdarma. Jinak řečeno, je to program, který nám pomáhá uchovávat historii projektu. Projekt uchováváme v takzvaném repozitáři (zkráceně repo) – datovém úložišti.

Git je distribuovaný verzovací systém. Co to znamená? Každý člen vývojářského týmu má u sebe kopii repozitáře s jeho celou historií – tomu říkáme klon repozitáře (kopie repozitáře + historie). Tím se liší od centralizovaných verzovacích systémů, kde každý člen uchovává pouze poslední verzi repozitáře.

Změny v repozitáři (na projektu) provádí vývojáři na klonu ve svém počítači (lokální repozitář – local repo). Každý klon je napojený na sdílený vzdálený repozitář (remote repo). Ten je umístěn na jedné z Git webových služeb.

Úloha Gitu je tedy koordinovat práci několika vývojářů a jejich individuálních historií, kterou mají u sebe na počítači. Například eviduje, kdo, kdy a kde udělal jaké změny. Všechny změny je možné díky této evidenci vzít zpět.

V dnešní době je Git nejrozšířenějším verzovacím systémem a neoddělitelnou součástí při práci vývojáře. Není jediný verzovací systém a také se nedá říct, že by byl tím nejlepším. Existují i jiné verzovací (ať už centralizované nebo decentralizované) systémy, které mají své zastánce.

## Instalace GITu

## Repozitář

Git pracuje s takzvanými repozitáři, zkráceně repo. Jedná se o místo, kde uchováváme náš kód. V rámci Gitu máme dva druhy:

<b>Vzdálený repozitář</b> – jedná se o místo na serveru (na internetu) jedné z Git hosting služby (GitHub, GitLab, Bitbucked), kde uchováváme kód sdílený s ostatními vývojáři.

<b>Lokální repozitář</b> – jedná se kopii vzdáleného repozitáře, kterou uchováváme u sebe na počítači.

Repozitáře většinou následují tento proces:

 - Vytvoří se vzdálený repozitář na Git hosting službě.
 - Každý vývojář si k sobě stáhne kopii vzdáleného repozitáře.
 - Každý vývojář pracuje na projektu v rámci svého lokálního repozitáře.
 - Každý vývojář synchronizuje svůj lokální repozitář s repozitářem vzdáleným.
 - Kroky 3 a 4 se neustále opakují. Z popisu vyplývá, že změny, které provedeme na lokálním repozitáři, se promítnout do vzdáleného repozitáře (ten sdílíme s ostatními) až po synchornizaci.

## Hostingové služby

Aby mohli vývojáři mezi sebou kdykoliv sdílet projekt, na kterém spolupracují, potřebují místo na webu, kde budou uchovávat svůj zdrojový kód. Toto místo poskytují právě takzvané Git webové služby. Jedná se o webové aplikace, které využívají Git ke správě repozitářů. Mezi nejznámější patří [GitHub](https://github.com/), [GitLab](https://about.gitlab.com/), [Bitbucket](https://bitbucket.org/), ale existuje jich mnohem víc.

Stejně jako Git, každá z těchto webových služeb má své zastánce. Z důvodu zachování jednoduchosti budeme pracovat pouze s tou nejznámější – GitHub.

## Účet na GitHubu

## ssh klíč

## IDE vs terminál

#### Vývojové prostředí (IDE)

Pokud se chceš věnovat vývoji softwaru, budeš určitě potřebovat vývojové prostředí. Práce s Gitem je ve vývojových prostředích většinou automatizovaná. To často urychluje a zjednodušuje práci.

#### Příkazový řádek

Možná si říkáš: Proč mi budete ukazovat Git v příkazovém řádku, když je to ve vývojovém prostředí jednodušší a efektivnější?

Protože pokud jsi s Gitem (nebo jiným verzovacím systémem) nikdy nepracoval, je dobré vidět, co se děje na pozadí. Nehledě na to, že každý vývojář by měl znát aspoň základní příkazy pro práci s příkazovým řádkem – přesouvání se mezi složkami, vytváření, úprava, čtení nebo odstranění souborů a podobně.

Pokud máš Windows, budeš používat Git Bash, který přichází s instalací Gitu. Na Linuxu nebo Mac OS budeš používat terminál, jenž je součástí systému.

## Příkazy

### git config

### git init

### git clone

### git add

### git commit

### git push

### git pull

### git status

### git diff

### git status

### git log

### git tag

### git blame
