---
layout: single
title: "Hack The Future, my first Hackaton"
date: 2020-11-24

---

Hoi beste bloglezers, in deze blog zal ik jullie wat vertellen over Hack The Future. Voor Hack The Future had ik nog nooit echt meegewerkt aan een hackaton. Ik moet toegeven dat ik aangenaam verrast was over wat een hackaton precies was. Vroeger dacht ik dat het ook effectief te maken had met inbreken zonder effectieve toegang te hebben, maar door deze hackaton heb ik geleerd dat het eigenlijk gezamenlijk een project creëren is. 

Hack The Future werkte dus ook met teams, omdat ik Anton Plancke al jaren ken was het een erg logische keuze om dit samen met hem te doen. We zijn beiden goed vertrouwt met elkaar, en elkaars manier van werken dus alles verliep erg vlot tussen ons. Als groepsnaam kozen we "Prinsesjes", beetje humor kan nooit kwaad!

![](https://hackthefuture.be/uploads/_1200x675_crop_center-center_none/HTF-Home-Fold-Copy-2.png)

# Hoe, Wat, Waar & Wanneer?

> **Wanneer**: 24 november 2020
>
> **Hoe lang**: Volledige werkdag
>
> **Waar**: @ Home

Hack The Future nam plaats op 24 november. Gelukkig hadden we deze dag vrij in ons lesrooster en hoefden we ons geen zorgen te maken. Aangezien Anton en ik beide grote interesse hebben in Javascript hebben we ons daar voor ingeschreven in de hoop wat nieuws te leren. 

Door COVID-19 vond deze editie van Hack The Future online plaats. Aangezien ik nog nooit eerder een hackaton had gevolgd was dit dus niet erg voor mij, ik kon genieten van de warmte en rust van mijn eigen huis. 

Hack The Future had een online platform voorzien voor ons dat wat meehad van de befaamde Lord of The Rings serie. Je kreeg een unieke link met de mogelijkheid om een character te creëren en met dat character in de verschillende ruimtes te gaan. Anton en ik gingen dus eerst naar de verzamelruimte om de introductie mee te volgen en later naar de JavaScript ruimte om te luisteren wat onze opdracht precies inhield. 

# De opdracht

De context van de opdracht heb ik nog voor jullie dus deze plaats ik hier even: "We desperately need the best JavaScript hackers around the world to save us from a world-wide blackout! All Google servers are infected and are exponentially throwing more errors. We can't shutdown all servers at once. We need you to visualise the servers to find the super spreaders and put them in lockdown!"

- 🔐  Identify
- 🔍  Visualise
- ⚡  Isolate
- 🔥 Bonus: Fix JS errors

## 🔐 Identify

Even wat korte context: We're not writing our world saving application for any fool to access it! Secure your webpages!

You can get your JSON Web Token (JWT) by requesting one with your credentials at `/login`.

Use this token in the request header for all subsequent calls!

Steps of difficulty:

- Hard-coded login ⭐
- Login dialog ⭐⭐
- Login page ⭐⭐⭐

Informatie die we meekregen: 

```json
{
  "Authorization": "Bearer your.jwt.token"
}

```

De eerste stap was het aanmelden op de /login pagina van een API. Om dit op te lossen moesten we enkele stappen doorgaan. Eerst en vooral moesten we posten naar de API om een Bearer token te krijgen. Aangezien er moest onthouden worden of iemand ingelogd is hebben wij ervoor gekozen om een cookie aan te maken die de JWT Token onthoud. Vervolgens haalden we de token uit de cookie om een request te sturen naar de API. Dit gebeurt simpelweg door bovenstaande Authorization-value in te vullen en mee te sturen in de body. Hieronder geef ik een klein voorbeeld van de code:

```javascript
const requestOptions = {
    method: "POST",
    headers: {
        "Content-Type": "application/json",
        "Access-Control-Allow-Origin": "*",
    },
    body: JSON.stringify({
        username: user,
        password: pass
    }),
};
const token = await fetch(
    `${baseURL}/auth/login`,
    requestOptions
).then((response) => response.json());

setCookie("token", JSON.stringify(token), token.expires_in);

window.location.reload();

function setCookie(name, value, ttl) {
    let d = new Date();
    d.setTime(d.getTime() + ttl);
    document.cookie = `${name}=${value};expires=${d.toLocaleString()};path=/`;
}
```

## 🔍  Visualise

Even weer een korte context: Once you're logged in, you have access to the following data:

- Datacenters
- Errors per datacenter

Visualise the data returned by the `/datacenters` and `/datacenters/{id}/errors` endpoints. The goal is that users can easily find the datacenters with the most errors. Think of the necessary functionality to accomplish this!

Steps of difficulty:

1. Data grid ⭐
2. Charts ⭐⭐
3. Map ⭐⭐⭐

Op deze stap is het voor ons een beetje misgelopen. We waren heel positief over onze eerste stap en dachten we dat we deze ook wel snel zouden kunnen oplossen. Niets was minder waar! Maar dus, we zijn gestart met de tool leaflet.js. Deze tool maakt het mogelijk op mappen te maken met zelf aangemaakte aangeduide locaties. Onze bedoeling was om de data op te vragen en ze daarna toe te voegen in de leaflet map. Uiteindelijk is ons dit dan wel gelukt maar maar wegens het gebruik maken van een nieuwe framework die we beiden nog niet uitbundig hadden gebruikt was er niet erg veel tijd meer over. 

Hier is een klein voorbeeldje van hoe we dit gedaan hebben... Voor meer uitleg bekijk zeker eens [LeafletJS](https://leafletjs.com/).

```javascript
render() {
    const {
        error,
        isLoaded,
        items
    } = this.state;
    if (error) {
        return <div > Error: {
            error.message
        } < /div>;
    } else if (!isLoaded) {
        return <div > Loading... < /div>;
    } else {
        return ( <
            MapContainer center = {
                [51.505, -0.09]
            }
            zoom = {
                3
            }
            scrollWheelZoom = {
                true
            } >
            <
            TileLayer attribution = '&copy; <a href="http://osm.org/copyright">OpenStreetMap</a> contributors'
            url = "https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png" /
            >

            {
                items.map((item) => ( <
                    Marker key = {
                        item.id
                    }
                    position = {
                        [item.location.lat, item.location.lng]
                    } >
                    <
                    Popup >
                    Id: {
                        item.id
                    } - Name: {
                        item.name
                    } < br / >
                    Longtitude: {
                        item.location.lng
                    } <
                    br / >
                    Latitude: {
                        item.location.lat
                    } <
                    br / >
                    Provider: {
                        item.provider
                    } <
                    br / >
                    In isolation: {
                        item.inIsolation ? "true" : "false"
                    } <
                    br / >
                    <
                    /Popup> <
                    /Marker>
                ))
            } <
            /MapContainer>
        );
    }
}
```

## ⚡  Isolate

Plug the power of the datacenter throwing the most errors!

This can be accomplished by POSTing to `/datacenters/{id}/isolate`.

Steps of difficulty:

You can increase difficulty by letting the UI suggest to the user which datacenters should be isolated

Aangezien Anton en ik al zoveel tijd hadden verloren bij de vorige 2 topics zaten we vol met stress en zijn we hier niet in geslaagd. Maar dat wil niet zeggen dat we het niet geprobeerd hebben, het was uiteindelijk wel mogelijk om alles werkende te krijgen via POSTMAN, maar net toen we begonnen aan het implementeren van een mogelijkheid in de UI was de tijd op! Erg jammer! Wel nog even ons plan voor jullie: het was de bedoeling om te werken met een button in de pop-up van een locatie.  (Zie foto voor meer duidelijkheid)

![image-20210404103012579](..\assets\images\image-20210404103012579.png)

# Reflectie

Zowel Anton en ik vonden het een geweldige belevenis en hebben ons geamuseerd op deze dag. We hebben beiden veel bijgeleerd over React.js & API's. Het was zeker de moeite waard en ik zou met veel plezier nog eens meedoen aan de volgende editie, maar deze keer misschien een ander topic. Ondanks we niet op een erg hoge plaats belandden ben ik erg tevreden over ons werk. 

Dit evenement is natuurlijk erg technisch maar ik raad het zeker iedereen aan die geïnteresseerd is in 1 van hun tientallen topics waar je uit kan kiezen. Alhoewel wij merkten dat we er maar los werden ingegooid zijn we er zeker van overtuigd dat waar er een wil is, een weg is. Documentatie van de talen die je zal gebruiken is dan ook je beste vriend tijdens dit evenement. 

Iets dat ik wel erg negatief vond was dat door COVID het strikt thuiswerken was in een groepje. Er was nooit echt een mogelijkheid om met andere mensen een praatje te maken, eens samen een koffie te drinken en wat dingen te bespreken en dergelijke. Dit nadeel/probleem ligt natuurlijk zeker niet bij Hack The Future want ze hebben zeker geprobeerd om dit zo goed mogelijk te maken maar ik wou het toch nog even aankaarten. We leven in bizarre en eenzame tijden. Zelf vind ik het ook veel aangenamer om in het echt een praatje te maken dan voor een laptop. Het is zeker niet hetzelfde en deze connecties vollen niet altijd hetzelfde. 

Hack The Future was dus zeker de moeite waard, bedankt aan iedereen die het mogelijk heeft gemaakt! 

**Later komt er nog een pitch over dit onderwerp maar nog even geduld!**