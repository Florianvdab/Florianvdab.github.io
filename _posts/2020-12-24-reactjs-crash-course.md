---
layout: single
title: "React JS Crash Course 2021"
date: 2020-10-24
---

Hallo daar beste blog lezers, vandaag zal ik even bloggen over een React JS Course. Toen ik deze cursus volgde was er enkel een 2020 editie beschikbaar maar sinds is er een nieuwere versie verschenen op YouTube. Vandaar de de mogelijkse verwarring in datums.

![image-20210515100021635](https://florianvdab.github.io/assets/images/image-20210515100021635.png)

[React JS Crash Course Link](https://www.youtube.com/watch?v=w7ejDZ8SWv8)

# Hoe, Wat, Waar & Wanneer?

> **Wanneer**: 24 Oktober
>
> **Hoe lang**: Video van een uur en half
>
> **Waar**: YouTube

De React JS Crash Course is een grote snelcursus voor het leren werken in React JS. Eén van mijn opdrachten voor school was toen een app ontwikkelen in React Native. Maar aangezien de React basis daar wordt behouden moest ik eerst een kijkje nemen in de wereld van de standaard React. 

Sinds het volgen van deze crash course en het bewerken van de notities is er een nieuwe YouTube versie verschenen en daarom verwijs ik naar die video als referentie.

Laten we er aan beginnen!

# Intro

React is een library voor het bouwen van user interfaces. React draait op de client als een SPA (Single Page App), maar kan gemakkelijk een full stack app zijn als het communiceert met een server of API. 

React is vaak vergeleken met een front-end "framework" omdat het vergelijkbaar is met Angular & Vue. 

## Prerequisites

Het is belangrijk dat er een standaard begrip is van JavaScript. Het is ten strengste af te raden om React te leren zonder kennis van JavaScript. 

De onderdelen die je best kent voor je aan React begint zijn: 

- Data types, variables, functions, loops etc
- Promises & Async programming
- Array Methods like forEach() & Map()
- Fetch API & Making HTTP Requests

## UI Components

Als je React gebruikt zie je uw UI best als een hoop componenten. Een voorbeeld hier van zit u hieronder. 

![image-20210515101043198](https://florianvdab.github.io/assets/images/image-20210515101043198.png)

### Components: Functions vs. Classes

Om componenten weer te geven zijn er 2 mogelijkheden. Functies en Classes, de huidige manier van werken is het gebruiken van een functie. (Links op de foto)

![image-20210515101220464](https://florianvdab.github.io/assets/images/image-20210515101220464.png)

## State

React pagina's zijn **NIET** statisch, deze pagina's hebben een state, deze state bepaald hoe een object moet renderen en werken. Een "App" of "global" state refereert naar een state dat beschikbaar is voor de volledige UI en niet één specifiek component. Om het nog wat meer te verduidelijken wat een state precies is, als men data wil meegeven aan een component zal deze data onderdeel uitmaken van de state. 

## React Hooks

React Hooks zijn functies die het toelaat om te hooken in een react state en lifecycle features van een functie component. Voorbeelden hier van zijn:

- useState - Returns a stateful value and a function to update it
- useEffect - Perform side effects in function components
- useContext, useReducer, useRef (komen niet aan bod in deze course)

Deze laatste onderdelen kunnen nogal lastig zijn zonder voorbeelden maar geen zorgen, deze komen later aan bod in de course! 😅

# Create a React app

De eerste stap is het installeren van [Node.JS](https://nodejs.org/en/). Wat ook handig is, is het installeren van de React Developer Tools. Dit geeft veel voordelen bij het aanmaken van de applicaties omdat ze handige info geven over je state enz...

Als alles geïnstalleerd is kunnen we overgaan naar het aanmaken van de applicatie. Dit doe je via het onderstaande commando in een terminal (waar x de naam is, spaties moeten "-" zijn):

```
npx create-react-app x
```

Als laatste moeten we deze applicatie open doen in onze text editor, in mijn geval was dit Visual Studio Code maar je bent natuurlijk vrij te kiezen wat je wilt! 

# Files & Folders

In het volgende onderdeel overloopt de presentator alle standaard files die komen bij je installatie. Waar alles terecht komt en wat er aanwezig is in de package.json. Deze package.json bevat heel wat informatie zoals bijvoorbeeld de scripts die ervoor zorgen dat we de app kunnen starten, maar ook de dependencies. 

In dit onderdeel werd als laatste ook getoond hoe we deze React app al meteen kunnen uitvoeren. Dit kan je doen door in de terminal van VS Code het onderstaande commando uit te voeren. 

```
npm start
```

De applicatie zal er uitzien als volgt: 

![image-20210515102801899](https://florianvdab.github.io/assets/images/image-20210515102801899.png)

# App Components & JSX

Het is erg belangrijk om deze informatie goed op te nemen en mee te volgen. Het is erg veel maar legt de volledige basis uit van alle files. Als dit allemaal goed opgenomen is in je brein kan je meteen al wat dingen testen zoals bv. de titel van de bovenstaande foto aanpassen. 

Enkele kern punten van dit onderdeel staan in de onderstaande foto. Deze App.js is trouwens de code achter bovenstaande foto van het vorige topic. Maar dus, je kan er enkele dingen uit afleiden: 

- Er word een logo geïmporteerd die aanwezig is in de source map "./logo.svg"
- Er wordt een CSS file geïmporteerd die alle opmaakt verzorgt. 
- Het geen dat word weergegeven is een functie en geen klasse
- Er is een div met een image, een p en een a. En er is iets aanwezig dat staat tussen {} brackets (wat dit is komt zo meteen aan bod)

![image-20210515103427951](https://florianvdab.github.io/assets/images/image-20210515103427951.png)

## Expressions

Om JavaScript te schrijven in de UI kan je dit doen door de code tussen brackets te plaatsen zoals in bovenstaande foto met het logo. Maar je kan veel meer doen dan enkel dat, je kan bijvoorbeeld een if statement maken, of een constante aanspreken. Zie onderstaande foto voor verduidelijking. 

Moest men {name} gebruiken zou er Brad in de UI staan, als men de code die op de foto staat gebruikt {x ? 'Yes' : 'No'} zal hij de constante x waarde bekijken als het een true of false is. 

![image-20210515103750314](https://florianvdab.github.io/assets/images/image-20210515103750314.png)

# Creating a component

Het is aangeraden om in de src map een map te maken met als naam "components" daar in maken we een javascript file die header.js noemt. Hier zal er een header aangemaakt worden. 

Dit is geen erg ingewikkeld proces, het is als het ware gewoon een functie de we zullen exporteren.  De uiteindelijke code die aangemaakt werd in dit onderdeel staat hieronder.

![image-20210515104042187](https://florianvdab.github.io/assets/images/image-20210515104042187.png)

## Props

In dit onderdeel worden props uitgelegd, in de context van de applicatie is dit met een titel voor de pagina. Het is niet erg ingewikkeld maar wat we doen is als het ware een waarde meegeven met onze header die dan kan gebruikt worden in de app.js file waar al onze components samen komen. 

![image-20210515104313873](https://florianvdab.github.io/assets/images/image-20210515104313873.png)

![image-20210515104332745](https://florianvdab.github.io/assets/images/image-20210515104332745.png)

Het is wel belangrijk om te vermelden dat wanneer er een title zou meegegeven worden in de laatste foto na de header tag op lijn 6 dat hij het default zal overschrijven. Anders zal hij gebruik maken van de header default title. 

### PropTypes

Het is mogelijk om een package te importeren die proptypes mogelijk maakt, zo kan je de Header.propTypes gelijkstellen aan brackets en daar de titel bijvoorbeeld definiëren als een string! Dit zal er dan voor zorgen dat je code wat robuuster is. Zo kan je bijvoorbeeld geen titel die gelijk is aan nummers. 

# Styling

Dit onderdeel is puur CSS. Indien dit niet gekend is zal er daar zeker moeten een les over gevolgd worden. Het enige echte belangrijke is dat de file word geïmporteerd en dat is het. Alhoewel dit erg simpel is zorgt deze file natuurlijk voor alle uiterlijke styling. 

# Button Component

Zoals eerder gezegd zie je best alles als een component. In dit onderdeel toonde hij hoe je een button ook als component kan maken. Dit hoeft natuurlijk niet meer is wel heel erg handig omdat we natuurlijk gebruik kunnen maken van props zoals bijvoorbeeld voor de tekst en kleur van de button. Een onderstaande foto toont deze button component.

![image-20210515105039761](https://florianvdab.github.io/assets/images/image-20210515105039761.png)

# Events

Een button die niets doet is natuurlijk niet erg handig, in dit onderdeel word er aangeleerd hoe we een event meegeven. Dit kan je doen door een onClick te zetten op de button die gelijkstaat aan een functie. Zie foto hieronder. (Ook hier is click event embedded in de header.)

![image-20210515110206974](https://florianvdab.github.io/assets/images/image-20210515110206974.png)

# Tasks

Vanaf dit punt gaat de course de richting uit van zijn applicatie, in veel gevallen is dit niet altijd even nuttig maar zo komen wel veel topics  perfect aan bod. In deze Tasks topic zal hij een file aanmaken in zijn components en daar een lijst maken van zijn tasks. 

Hij begint door een component aan te maken en vervolgens creëert hij een array met een hele hoop tasks. Vervolgens zal hij deze functie mappen en voor iedere task een h3 tag maken met de tekst van de task. Zie code hieronder voor verduidelijking. Dit is niet moeilijk en geeft meteen al een sterk punt van React weer. 

![image-20210515110554283](https://florianvdab.github.io/assets/images/image-20210515110554283.png)



# State - useState

Stateful werken is erg ingewikkeld en daarom kan ik enkel aanraden om dit te proberen. Zelf was de video niet genoeg uitleg voor mij en ben ik zelf eens aan het werk gegaan. Het belangrijkste om te weten is dat we de state moeten meegeven met de functie. Vanaf dan is hij beschikbaar. De state kan je zetten, in mijn voorbeeld heb ik dit gebruikt om een specifieke task weer te geven in een detail pagina. De state bevatte toen de index van de array. Het is ook belangrijk dat de state top level is, dus in de App.js. Daar geven we de task mee aan het task component en daar lijst hij hem uiteindelijk. 

# React-Icons

Dit is niet erg belangrijk maar eens leuk om mee te delen, je kan react-icons installeren, dit zal dan in je package.json terecht komen en vanaf dan kan je het simpelweg importeren en gebruik maken van de veel react-icons. Tipje: de dev server moet herstart worden dus npm stop en dan weer start. Screenshot hieronder van een kruis icoontje. 

![image-20210515111308643](https://florianvdab.github.io/assets/images/image-20210515111308643.png)

# Other topics

In de vele volgende topics maakt hij zijn applicatie stukje per stukje. Er komt niet meteen iets nieuws aan bod en hij gaat wat meer in-depth over de verschillende onderdelen. Omdat het andere een heel erg lange blog word sla ik deze onderdelen over en ga ik over naar de nieuwe content.  Als laatste komt er een stuk aan bod over een JSON-server, omdat dit niet meteen van toepassing was voor mijn applicatie heb ik dit niet gevolgd en beschreven. Het is zeker wel de moeite waard maar dit onderdeel specifiek is mij aangeleerd door een mede student en dus moeilijk te documenteren als blog! 

# Reflectie

Deze crashcourse was erg belangrijk voor mij omdat ik later ook een presentatie heb moeten geven over React Native. Het heeft me de basis getoond maar uiteindelijk heb ik wel zelf alles eens moeten testen. Het was erg lastig om constant druk bezig te zijn met deze video want er zijn natuurlijk geen pauzes of leuke anekdotes tussenin. Een 2 tal uur erg goed opletten is niet niets maar het was de moeite waard! 

Moesten er vragen zijn over react-native of react contacteer me zeker en hopelijk kan ik jullie vragen beantwoorden. Bedankt voor het lezen!





