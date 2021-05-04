# Opdracht: Video als achtergrond

Een goeie manier om je site er iets dynamischer er uit te laten zien en de aandacht te trekken van je gebruiker is een video als achtergrond plaatsen.

## Vereisten

- zet je voornaam in de voorgrond in het GROOT & gecentreerd (je kan hier bv. text-align: center voor gebruiken)
- zet een video naar keuze in achtergrond (het is best één van .mp4 formaat - gebruik een andere dan die dat gebruikt wordt in onderstaande tutorial)
- zorg ook dat die valid is volgens W3 regels (dus geen speciale tekens of spaties in de bestandsnamen)
- vooraleer je het zipt, zorg dat je je opdracht eens controleert op fouten en ziet of het werkt

## Indienen

Dien in als .zip bestand in de daartoe betreffende Uploadzone in de module Website Animatie 2; je mag die natuurlijk ook online zetten en de link delen met mij in de Uploadzone.

## Meer Info

Uitleg met video:

<video width="600" controls>
<source src="video-background-vb.mkv">
</video>

[Download hier het voorbeeld](video-background.zip)

## Voorbeeld uitleg

Het belangrijkste dat je moet gebruiken om dit voorbeeld te bekomen is het volgende;

In je CSS plaats je deze klasses:

```CSS
.fullscreen-bg {
            position: fixed;
            top: 0;
            right: 0;
            bottom: 0;
            left: 0;
            overflow: hidden;
            z-index: -100;
        }

        .fullscreen-bg__video {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }
```

in je HTML dit stukje code

```HTML
   <div class="fullscreen-bg">
        <video loop muted autoplay class="fullscreen-bg__video">
            <source src="bboy.mp4" type="video/mp4">
        </video>
    </div>
```

Belangrijk: 

- in `src` komt de url naar de video (die moet dus ook in je website staan - zorg dat die niet te groot is) - in dit geval `bboy.mp4`

- `type` moet overeenkomen met het video type dat je gebruikt; in dit geval `video/mp4`

