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

### Instalace na Windows

 - Stáhni si [instalační soubor](https://gitforwindows.org/) Gitu pro Windows.
 - Spusť si instalátor, a pokud jsi jako většina uživatelů, stačí se proklikat nakonec instalace pomocí tlačítek Next a Finish.
 - Otevři si program Git Bash. Do vyhledávání na tvém počítači stačí zadat Git Bash a zmáčknout Enter.
 - Pomocí následujících příkazů si nastav uživatelské jméno a e-mail. S těmito údaji budou potom asociovány změny v projektu na tvém počítači. Doplň samozřejmě své údaje.
```
$ git config --global user.name "Jméno Příjmení"
$ git config --global user.email "tvuj_email@gmail.com"
```

### Instalace na Linuxu

 - Otevři si příkazový řádek a v závislosti na distribuci proveď následující příkaz:
```
$ sudo apt-get update           # Debian/Ubuntu
$ sudo apt-get install git
```

nebo:
```
$ sudo dnf install git          # Fedora
```
případně:
```
$ sudo yum install git          # Fedora
```
 - Ověř, že instalace proběhla úspěšně:
 ```
$ git --version
git version 2.20.1
```
 - Nastav si uživatelské jméno a e-mail. S těmito údaji budou potom asociovány změny v projektu na tvém počítači. Doplň samozřejmě své údaje.
```
$ git config --global user.name "Jméno Příjmení"
$ git config --global user.email "tvuj_email@gmail.com"
```

### Instalace na MacOs

Existuje více způsobů, jak si nainstalovat Git na MacOS. My si zde ukážeme dva, instalaci pomocí Mac Installeru nebo Homebrew:

#### Mac Installer
 - Stáhni si [instalační soubor](https://sourceforge.net/projects/git-osx-installer/files/) Gitu pro MacOS.
 - Proklikej se instalací.
 - Otevři si terminál a ověř, že instalace proběhla úspěšně:
```
$ git --version
git version 2.20.1
```
 - Nastav si uživatelské jméno a e-mail. S těmito údaji budou potom asociovány změny v projektu na tvém počítači. Doplň samozřejmě své údaje.
```
$ git config --global user.name "Jméno Příjmení"
$ git config --global user.email "tvuj_email@gmail.com"
```

#### Homebrew
 - Otevři si terminál a zadej následující příkaz:
```
$ brew install git
```
 - Ověř si v terminálu, že instalace proběhla úspěšně:
```
$ git --version
git version 2.20.1
```
 - Nastav si uživatelské jméno a e-mail. S těmito údaji budou potom asociovány změny v projektu na tvém počítači. Doplň samozřejmě své údaje.
```
$ git config --global user.name "Jméno Příjmení"
$ git config --global user.email "tvuj_email@gmail.com"
```

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

GitHub je tedy platforma, která může uchovávat naše projekty online, aby byly dostupné i ostatním vývojářům nebo zaměstnavatelům. Jinými slovy jde o místo, kde můžeme uchovávat zdrojový kód ve formě vzdáleného repozitáře (remote repo). Tento repozitář by měl mít určitou strukturu a měli bychom s ním zacházet určitým způsobem. To vše si ukážeme v dalších lekcích.

Než si založíme první repozitář na GitHubu, musíme si založit účet. Pojďme si ukázat, jak na to:

 - Jdi na [github.com](https://github.com/).
 - Registruj se pomocí formuláře.
 - Projdi třídílným procesem registrace.
 - Ověř svůj e-mail (jdi do svého e-mailu a klikni na ověřovací link).
 - Měl by ses objevit na domovské stránce uživatele, kde můžeš začít prozkoumávat GitHub :).
 - Abys získal lepší obecnou představu, o čem vlastně GitHub je, doporučujeme se podívat na krátké edukační video přímo od GitHubu.

## ssh klíč

### Vygenerování ssh klíče

 - Otevřeme si terminál (Linux, MacOS) nebo Git Bash (Windows).
```
$
```
 - Přesuneme se do domovského adresáře.
```
$ cd ~
```
 - Vygenerujeme si SSH klíč.
```
$ ssh-keygen -t rsa
```
 - Po zmáčknutí klávesy Enter budeme dotázáni na místo uložení klíče a heslo. Pokud nechceme měnit navrženou cestu a heslo nepotřebujeme, stačí se proklikat opět pomocí Enter.
```
Generating public/private rsa key pair. 
Enter file in which to save the key (/home/user/.ssh/id_rsa): 
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
```
 - Výstup potom může vypadat nějak takto:
```
Your identification has been saved in /home/user/.ssh/id_rsa.
Your public key has been saved in /home/user/.ssh/id_rsa.pub.
The key fingerprint is:
60:8b:50:1e:0f:bc:5a:2a:13:1e:83:2b:d9:95:38:9e user@localhost
The key's randomart image is:
+---[RSA 2048]----+
|   .+            |
|   o.+           |
|. ...o+          |
|ooo.=o o         |
|.*oB. . S        |
|*.E              |
|.o               |
|                 |
|                 |
+-----------------+
```
 - Přečteme soubor s klíčem a zkopírujeme výstup (Ctrl+c) – musíme se ujistit, že zkopírujeme vše od ssh až pod localdomain bez přebytečných mezer!:
```
$ cat /home/user/.ssh/id_rsa.pub
ssh-rsa AAAAB3N...                      # Kopírujeme tedy od začátku tohoto řádku...
...
... user@localhost.localdomain          # ...po konec tohoto řádku.
```

### Vložení SSH klíče do GitHubu

 - Ve našem repozitáři klikneme na Clone or download a následně na Use SSH.
 - Klikneme na add a new public key.
 - Vložíme a uložíme:
```
jméno svého klíče podle zařízení,
klíč samotný (Ctrl+v).
```

Hotovo! Máme nastavený náš veřejný SSH klíč. Nyní můžeme začít používat SSH URL (kterou najdeme v našem repozitáři) pro klonování repozitáře.

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
