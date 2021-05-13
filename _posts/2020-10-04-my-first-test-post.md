---
layout: single
title: "Welcome to my blog. Made in Jekyll!"
date: 2020-10-04
---

## Welcome

**Hello world**, this is my first Jekyll post. In mijn aller eerste post zal ik uitleggen hoe je Jekyll installeert, een thema op Jekyll plaatst, hoe je blogposts aanpast, wat basic configuratie aanpast en op het einde nog wat leuke tips om te werken in Markdown. 

# Installatie

1. [Jekyll](https://jekyllrb.com/docs/)
2. [Minimal Mistakes](https://mademistakes.com/work/minimal-mistakes-jekyll-theme/)

Eerst en vooral moet Jekyll geïnstalleerd worden, want Minimal Mistakes is een thema voor Jekyll. Jekyll kan je gratis trouwens gratis hosten op GitHub Pages. Om Jekyll te installeren heb ik simpelweg de DOCS gevolgd van Jekyll. 

## Prerequisites

https://jekyllrb.com/docs/installation/

Voor je aan het werk kan met Jekyll moeten er enkele dingen geïnstalleerd worden, zoals Ruby. Ruby is een programmeertaal die het mogelijk maakt om gems te installeren. Dit komt aan bod bij het installeren van Jekyll dus zeker belangrijk!

## Instructions

Om Jekyll te installeren zijn er 6 stappen. De eerste was al het installeren van de "prerequisites" van het bovenstaande hoofdstukje. De volgende 6 stappen zijn als volgt:

- Install all prerequisites
- Install the jekyll and bundler gems

```
gem install jekyll bundler
```

- Create a new Jekyll site at ./myblog.

```
jekyll new myblog
```

- Change into your new directory

```
cd myblog
```

- Build the site and make it available on a local server

```
bundle exec jekyll serve
```

- Browse to http://localhost:4000

Het proces van het installeren is erg simpel en gemakkelijk. Het hosten is ook een makkie dankzij GitHub Pages. Het enige wat er dan echt nog moet gebeuren is enkele kleine aanpassingen. Als dat klaar is kunnen we aan de slag met het maken van de markdown blog posts. 

Maar voor we overgaan naar die stappen! Wat is "GitHub Pages" nu precies? Het zorgt ervoor dat er een statische website kan gehost worden via een Git Repository. Alles wat ik dus moest doen om het werkende te krijgen was een GitHub Pages repo aanmaken en daar in de content van mijn zojuist gemaakte Jekyll te plaatsen. 

## Thema installeren

Om me niet te moeten bezighouden met de lay-out van de website ben ik opzoek gegaan naar een gepast thema. Daar kwam ik Minimal Mistakes tegen. Ondertussen had ik Jekyll al geïnstalleerd maar was dit proces een beetje overbodig. Ik kon simpelweg de GitHub van Minimal Mistakes te forken en zo hem meteen te hosten zonder dat echt iets moest geïnstalleerd worden. 

Dit proces is erg simpel maar voor de zekerheid zal ik de link meegeven die ik heb gebruikt.  https://github.com/mmistakes/minimal-mistakes

## Configuratie

De meeste configuratie heb ik gedaan in de _config.yml file. Deze file bevat  de belangrijkste opties zoals links, bio, avatar,... Om wat te verduidelijken kan je een voorbeeld zien hiervan hieronder. 

![image-20210513111842823](C:\Users\Flori\Documents\Github\Florianvdab.github.io\florianvdab.github.io\assets\images\image-20210513111842823.png)

## Een pagina aanmaken

[Creating a page - Jekyll DOCS](https://jekyllrb.com/docs/pages/)

Voor ik aan de slag ging met het aanmaken van posts heb ik snel eens de guidelines geraadpleegd. Het is belangrijk dat er een bepaalde werkwijze wordt gehanteerd, ook al is er een thema aanwezig. Daar vond ik onder andere dat men pagina's kan aanmaken. Aangezien ik graag een pagina had gemaakt waar ik al mijn verwezenlijkingen op kon plaatsen ben ik hier dus mee aan de slag gegaan. Het is een simpel proces en kan ook gedaan worden met markdown. Hoe je het precies doet is een .html of .md file aanmaken in de _pages folder. Voor wat meer duidelijkheid verwijs ik jullie graag ook door naar de guide (zie URL onder titel). Een voorbeeld van de markdown file die ik heb aangemaakt voor mijn Projects pagina staat hieronder. 

![image-20210513105101641](C:\Users\Flori\Documents\Github\Florianvdab.github.io\florianvdab.github.io\assets\images\image-20210513105101641.png)

## Een blogpost aanmaken

[Creating a post - Jekyll DOCS](https://jekyllrb.com/docs/posts/)

Om een blogpost te maken maakt u gewoon een markdown bestand aan in de map \_posts en dat is het. (natuurlijk met inachtneming van het formaat: JAAR-MAAND-DAG-titel.MARKUP -> 2011-12-31-nieuw-jaar-is-awesome.md)

Alles wat je hoeft te doen is wat markdown toevoegen voor de lay-out en titel en je bent klaar! Jekyll heeft een zeer gemakkelijke manier van werken en aangezien ik niet echt de moeite heb genomen met een CMS kan ik gewoon notities in markdown opschrijven en later al mijn notities omzetten naar een volledige blog post.

Dit is waarschijnlijk niet de beste manier van werken aangezien een CMS beter is voor bloggen. Maar ik moet toegeven dat deze manier veel cooler is dan het occasionele CMS zoals WordPress.

## Editing in a decent environment.

Werken in een fatsoenlijke omgeving is een noodzaak. Ik wil niet telkens lastig gevallen worden om een wijziging te zien.
Gelukkig kun je dit doen via Jekyll serve. Maar omdat dit thema een gemfile gebruikt is het nodig voor mij om een commando over bundel te draaien. Om dit te doen gebruik ik het onderstaande commando: 

```
bundle exec jekyll serve
```

## Handige links

- [Typora](https://typora.io/)

Typora is een erg handige markdown editor. Ik gebruik dit in plaats van Word of het gewone kladblok.

- [Markdown-Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

Natuurlijk is markdown makkelijk, maar ik weet niet alles uit mijn hoofd. Dus dit kwam ook goed van pas.
