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

 - [git config](#git-config)
 
 - [git init](#git-init)
  
 - [git clone](#git-clone)
   
 - [git add](#git-add)
    
 - [git commit](#git-commit)
     
 - [git push](#git-push)
      
 - [git pull](#git-pull)
       
 - [git config](#git-status)
        
 - [git config](#git-diff)
 
 - [git config](#git-log)
 
 - [git config](#git-tag)
 
 - [git config](#git-blame)
 
 - [git config](#git-checkout)
 
 - [git config](#git-merge)

### git config

Slouží k nastavovaní gitu. My jsme si pomocí něj v předchozích krocích nastavovali uživatelské jméno a email, který bude spojený s našimi úpravami.

### git init

Při inicializaci lokálního repozitáře, a to příkazem git init, vzniká repozitář nejdříve u nás na počítači. Složka, ve které tento příkaz spustíme, se stane Git repozitářem. Náš systém pozná, že jde o Git repozitář, protože příkaz git init vytvoří složku .git, která obsahuje konfigurační informace Git repozitáře. Nemusíme vědět, co přesně se v této složce nachází, protože s ní nebudeme přímo pracovat. Jen si zapamatujme, že díky ní víme, že se jedná o Git repozitář.

 - Vytvoříme si na svém počítači složku, která bude reprezentovat náš první repozitář (například s názvem my_first_repo). Později budeme mít v této složce náš zdrojový kód. Pokud používáme Linuxu nebo MacOS, otevřeme si terminál. Pokud Windows, spustíme si Git Bash.
```
$
```
 - Přemístíme se do složky repozitáře.
```
$ cd /cesta/k/tvemu/repozitari/my_first_repo        # Příkaz 'cd' nás dostane do dané složky.
```
 - Inicializujeme lokální git repozitář (je možné, že dostaneme hlášení o jeho vytvoření).
```
git init                                            # Příkaz 'git init' inicializuje Git repozitář.
Initialized empty Git repository in /cesta/k/tvemu/repozitari/my_first_repo/.git/
```
 - Ověříme, že se složky .git nachází v našem lokálním git repozitáři.
```
$ ls -a                                            # Příkaz 'ls -a' vypíše rozšířený seznam všechny souborů.
.git
```

### git clone

Klonování vzdáleného repozitáře znamená, že k sobě kopírujeme již existující vzdálený repozitář (například z GitHubu) i se složkou .git. To je klíčový rozdíl mezi stažením a klonováním repozitáře. Složka .git totiž obsahuje veškerou historii repozitáře. Když si tedy k sobě naklonujeme repozitář, můžeme se dívat na jeho různé verze právě díky složce .git.

Složka může být skrytá. Nezapomeň si tedy ve svém správci souborů odkrýt skryté složky.

Zde můžeme vidět výhodu distribuované verzovacího systému oproti centralizovanému. Po naklonování repozitáře u sebe máme repozitář s jeho celou historií. To znamená, že kdyby došlo k poruše disku na serveru (například GitHubu), můžeme použít libovolný klon k obnovení serveru do stavu, ve kterém byl v okamžiku klonování.

 - Půjdeme do našeho repozitáře na GitHubu a zkopírujeme si SSH URL.
 - Otevřeme si terminál (Linux, MacOS) nebo Git Bash (Windows).
```
$
```
 - Přesuneme se do adresáře, kde si budeme chtít naklonovat náš repozitář.
```
$ cd /cesta/k/tve/slozce
```
 - Naklonujeme si repozitář.
```
$ git clone git@github.com:user/my-github-repo.git
Cloning into 'my-github-repo'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
Receiving objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
```
 - Náš adresář by měl obsahovat README.md soubor, jehož obsah si můžeme přečíst a tím se přesvědčit, že vše proběhlo úspěšně.
```
$ cat my-github-repo/README.md 
# my-github-repo
I will test my Git knowledge on this repo.
```
 - Nastavíme si konfigurační atributy pro tento repozitář. (tento krok není nutný, pokud máte již nastavenou globální konfiguraci gitu a nechcete pro tento repozitář nějakou speciální)
```
$ git config --local user.name "Jméno Příjmení"         # Nastavení Git jména pro tento repozitář.
$ git config --local user.email "tvuj_email@gmail.com"  # Nastavení Git e-mailu pro tento repozitář
```

### git add

Nově vytvořené a již existující změněné soubory můžeme připravit k zápisu (stage) pomocí příkazu git add, který přesouvá soubory z pracovního adresáře (anglicky working directory) do prostoru připravených změn (anglicky staging area).

```
$ git add script.py 
$ git add README.md
```

Tento zápis bychom mohli zkrátit buď takto:

```
$ git add script.py README.md       # Cesty ke každému souboru uvedeme za samotný příkaz.
```

Nebo takto:

```
$ git add -A                        # Tento přepínač přidá všechny sledované i nesledované soubory.
```

### git commit

„Uložit soubor“ běžně znamená přepsat stávající soubor na základě změn, které proběhly od posledního uložení. My už víme, že Git je verzovací systém, tudíž místo toho, abychom přepisovali jeden soubor, spíše ukládáme novou verzi souborů.

Uložení aktuální verze nazýváme commit, který provádíme lokálně. To znamená, že při každém commitu se ještě nic neposílá do vzdáleného repozitáře (na GitHubu). K tomu se ale brzy dostaneme. Všechny naše dosavadní verze (commity) jsou nám tedy vždy dostupné i bez internetu a můžeme se k nim vrátit.

Commit provádíme pomocí příkazu git commit. Správně by každý commit měl mít zprávu, která jednou větou dokumentuje provedené změny. Můžeme ji specifikovat pomocí přepínače -m:

$ git commit -m "Created MyFirstClass.java, Added new line to README.md"
Příkaz git commit automaticky ukládá vše, co bylo přepraveno k zápisu (MyFirstClass.java, README.md). Není tedy potřeba specifikovat, které soubory chceme uložit.

Všimněme si, že zpráva dokumentuje dva různé soubory, což není nejlepší způsob. V našem případě by tedy bylo lepší pomocí git add přidat každý soubor zvlášť a pomocí git commit je uložit.

Takže pro README.md:
```
$ git add README.md
$ git commit -m 'Added new line to README.md'
```
a MyFirstClass.java:
```
$ git add MyFirstClass.java
$ git commit -m 'Created MyFirstClass.java'
```
V praxi samozřejmě budeme provádět změny, které budou ve více na sobě závislých souborech. Například se budou všechny týkat určité funkcionality naší aplikace.

Pro ověření se podívejme na aktuální stav repozitáře:
```
$ git status
On branch master
Your branch is ahead of 'origin/master' by 2 commits.
  (use "git push" to publish your local commits)
nothing to commit, working tree clean               # Nemáme nic k zápisu.
```

### git push

Příkaz git push slouží k tomu, abychom nahráli změny (anglicky push) na vzdálený repozitář na GitHubu. Z anglického názvu vyplývá název příkazu – git push.
```
$ git push
Username for 'https://github.com': <username>           # Zde zadej své GitHub uživatelské jméno nebo e-mail.
Password for 'https://username@github.com': <password>  # Své heslo z GitHubu.
Enumerating objects: 11, done.
Counting objects: 100% (11/11), done.
Delta compression using up to 4 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (9/9), 846 bytes | 282.00 KiB/s, done.
Total 9 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), done.
To https://github.com/username/my-github-repo.git
   33a5639..a85d116  master -> master
```

### git pull

Pro úplnost ještě přidáme příkaz pro stažení poslední verze ze vzdáleného repozitáře na GitHubu. K tomu používáme příkaz git pull.

Pokud jsme jediní, kdo přispívá do repozitáře, dostaneme tento výstup:
```
$ git pull
Already up to date.
```

### git status

Příkaz git status nám uhazuje stav skoro všech souborů – nesledované, změněné a připravené k zapsání. Výjimkou jsou nezměněné soubory (jsou součástí posledního commitu).

Příkaz nám tedy umožňuje vidět pouze soubory, které spadají do dvou ze tří stromů Gitu – Working Directory (pracovní adresář) a Index (Staging Area – prostor připravených změn). Nezobrazí Historii commitů (k tomu slouží [git log](#git-log)).

Aktuální výstup příkazu by měl vypadal nějak takto:

```
$ git status
On branch master
Your branch is ahead of 'origin/master' by 2 commits.
  (use "git push" to publish your local commits)
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)
    modified:   README.md
Untracked files:
  (use "git add <file>..." to include in what will be committed)
    .gitignore
no changes added to commit (use "git add" and/or "git commit -a")
```

Zkrácený výstup tohoto příkazu můžeme vytisknout pomocí přepínače -s (z anglického short).
```
$ git status -s
 M README.md
?? .gitignore
```

Kdybychom chtěli vidět i soubory, které jsou ignorovány, mohli bychom přidat volbu --ignored:
```
$ git status -s --ignored
 M README.md
?? .gitignore
!! .idea/
```
Obecný formát výstupu je XY cesta/k/souboru. Písmena XY reprezentují aktuální stav daného souboru, který může nabývat různých hodnot. V našem případě vidíme tento výstup:

README.md (M) – na pozici Y máme písmeno M, což znamená, že soubor byl upraven, ale nepřidán do indexu.
.gitignore (??) – na obou pozicích máme otazníky, což znamená, že soubor není sledován.
.idea/ (!!) – soubor je ignorován.
Podrobný výpis možných stavů a jejich kombinací můžeme najít v dokumentaci příkazu git status:

```
$ git status --help
...
      X          Y     Meaning
    -------------------------------------------------
               [AMD]   not updated
      M        [ MD]   updated in index
      A        [ MD]   added to index
...
```

### git diff

### git log

### git tag

### git blame

### git checkout

### git merge
