# Responsive Design

In de begindagen van webdesign werden pagina's gebouwd om een bepaalde schermgrootte te targeten. Als de gebruiker een groter of kleiner scherm had dan de ontwerper had verwacht, varieerden de resultaten van ongewenste schuifbalken tot te lange lijnlengtes en slecht ruimtegebruik. Naarmate er meer verschillende schermformaten beschikbaar kwamen, verscheen het concept van _responsief webdesign_ (RWD), een reeks praktijken waarmee webpagina's hun lay-out en uiterlijk kunnen aanpassen aan verschillende schermbreedtes, resoluties, enz. Het is een idee dat de manier waarop we ontwerpen voor een web met meerdere apparaten heeft veranderd, en in dit artikel helpen we u de belangrijkste technieken te begrijpen die u moet kennen om het onder de knie te krijgen.

## [Historische website lay-outs](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#historic_website_layouts "Permalink to Historic website layouts")

Op een bepaald moment in de geschiedenis had je twee opties bij het ontwerpen van een website:

- U een _vloeibare_ site maken, die zich uitstrekt om het browservenster te vullen
- of een site _met een vaste breedte,_ die een vaste grootte in pixels zou zijn.

Deze twee benaderingen neigden naar een website die er op zijn best uitzag op het scherm van de persoon die de site ontwierp! De vloeibare plaats resulteerde in een verpletterd ontwerp op kleinere schermen (zoals hieronder te zien) en onleesbaar lange lijnlengtes op grotere.

![A layout with two columns squashed into a mobile size viewport.](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design/mdn-rwd-liquid.png)

**Opmerking**: Zie deze eenvoudige vloeibare lay-out: [voorbeeld](https://mdn.github.io/css-examples/learn/rwd/liquid-width.html), [broncode](https://github.com/mdn/css-examples/blob/master/learn/rwd/liquid-width.html). Wanneer u het voorbeeld bekijkt, sleept u uw browservenster in en uit om te zien hoe dit naar verschillende groottes kijkt.

De site met vaste breedte riskeerde een horizontale schuifbalk op schermen die kleiner zijn dan de sitebreedte (zoals hieronder te zien is) en veel witruimte aan de randen van het ontwerp op grotere schermen.

![A layout with a horizontal scrollbar in a mobile viewport.](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design/mdn-rwd-fixed.png)

**Opmerking**: Zie deze eenvoudige lay-out met vaste breedte: [voorbeeld](https://mdn.github.io/css-examples/learn/rwd/fixed-width.html), [broncode](https://github.com/mdn/css-examples/blob/master/learn/rwd/fixed-width.html). Nogmaals, observeer het resultaat wanneer u de grootte van het browservenster wijzigt.

**Opmerking:**De bovenstaande schermafbeeldingen worden gemaakt met behulp van de [responsieve ontwerpmodus](https://developer.mozilla.org/en-US/docs/Tools/Responsive_Design_Mode) in Firefox DevTools.

Toen het mobiele web werkelijkheid begon te worden met de eerste feature phones, zouden bedrijven die mobiel wilden omarmen over het algemeen een speciale mobiele versie van hun site maken, met een andere URL (vaak zoiets als _m.example.com_, of _example.mobi_). Dit betekende dat twee afzonderlijke versies van de site moesten worden ontwikkeld en up-to-date moesten worden gehouden.

Bovendien boden deze mobiele sites vaak een zeer beperkte ervaring. Naarmate mobiele apparaten krachtiger werden en volledige websites konden weergeven, was dit frustrerend voor mobiele gebruikers die vast kwamen te zitten in de mobiele versie van de site en geen toegang hadden tot informatie waarvan ze wisten dat ze zich op de volledig uitgeruste desktopversie van de site bevonden.

## [Flexibele lay-out vóór responsief ontwerp](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#flexible_layout_before_responsive_design "Permalink to Flexible layout before responsive design")

Een aantal benaderingen werden ontwikkeld om te proberen de nadelen van de vloeibare of vaste breedte methoden van het bouwen van websites op te lossen. In 2004 schreef Cameron Adams een post getiteld [Resolution dependent layout](http://www.themaninblue.com/writing/perspective/2004/09/21/), waarin hij een methode beschreef om een ontwerp te maken dat zich kon aanpassen aan verschillende schermresoluties. Deze aanpak vereiste JavaScript om de schermresolutie te detecteren en de juiste CSS te laden.

Zoe Mickley Gillenwater speelde een belangrijke rol in [haar werk](http://zomigi.com/blog/voices-that-matter-slides-available/) om de verschillende manieren te beschrijven en te formaliseren waarop flexibele sites konden worden gecreëerd, in een poging om een gelukkig medium te vinden tussen het vullen van het scherm of volledig vast in grootte.

## [Responsief ontwerp](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#responsive_design "Permalink to Responsive design")

De term responsive design werd [in 2010 bedacht door Ethan Marcotte](https://alistapart.com/article/responsive-web-design/) en beschreef het gebruik van drie technieken in combinatie.

1. De eerste was het idee van fluid grids, iets dat al werd onderzocht door Gillenwater, en kan worden gelezen in Marcotte's artikel, [Fluid Grids](https://alistapart.com/article/fluidgrids/) (gepubliceerd in 2009 op A List Apart).
2. De tweede techniek was het idee van [vloeiende beelden](http://unstoppablerobotninja.com/entry/fluid-images). Met behulp van een zeer eenvoudige techniek om de eigenschap in te stellen op , zouden afbeeldingen kleiner worden als hun kolom smaller zou worden dan de intrinsieke grootte van de afbeelding, maar nooit groter worden. Hierdoor kan een afbeelding worden verkleind om in een kolom van flexibele grootte te passen, in plaats van deze over te lopen, maar niet groter te worden en gepixeld te worden als de kolom breder wordt dan de afbeelding.`max-width``100%`
3. Het derde belangrijke onderdeel was de [mediaquery](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries). Mediaquery's maken het type lay-outschakelaar mogelijk dat Cameron Adams eerder had verkend met JavaScript, met alleen CSS. In plaats van één lay-out voor alle schermformaten, kan de lay-out worden gewijzigd. Zijbalken kunnen worden verplaatst voor het kleinere scherm of alternatieve navigatie kan worden weergegeven.

Het is belangrijk om te begrijpen dat **responsief webdesign geen afzonderlijke technologie is** - het is een term die wordt gebruikt om een benadering van webdesign of een reeks best practices te beschrijven, die wordt gebruikt om een lay-out te maken die kan reageren _op_ het apparaat dat wordt gebruikt om de inhoud te bekijken. In marcotte's oorspronkelijke verkenning betekende dit flexibele rasters (met behulp van vlotters) en mediaquery's, maar in de bijna 10 jaar sinds dat artikel werd geschreven, is responsief werken de standaard geworden. Moderne CSS-lay-outmethoden zijn inherent responsief en we hebben nieuwe dingen ingebouwd in het webplatform om het ontwerpen van responsieve sites gemakkelijker te maken.

De rest van dit artikel wijst u naar de verschillende webplatformfuncties die u mogelijk wilt gebruiken bij het maken van een responsieve site.

## [Mediaquery's](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#media_queries "Permalink to Media Queries")

Responsief ontwerp kon alleen naar voren komen vanwege de mediaquery. De specificatie mediaquery's niveau 3 werd een kandidaat-aanbeveling in 2009, wat betekent dat het klaar werd geacht voor implementatie in browsers. Mediaquery's stellen ons in staat om een reeks tests uit te voeren (bijvoorbeeld of het scherm van de gebruiker groter is dan een bepaalde breedte of een bepaalde resolutie) en CSS selectief toe te passen om de pagina op de juiste manier te stylen voor de behoeften van de gebruiker.

Met de volgende mediaquery wordt bijvoorbeeld getest of de huidige webpagina wordt weergegeven als schermmedia (dus geen afgedrukt document) en is het venster ten minste 800 pixels breed. De CSS voor de selector wordt alleen toegepast als deze twee dingen waar zijn.`.container`

```
@media screen and (min-width: 800px) {
  .container {
    margin: 1em 2em;
  }
}
```

U meerdere mediaquery's toevoegen in een stylesheet, waarbij u uw hele lay-out of delen ervan aanpast aan de verschillende schermformaten. De punten waarop een mediaquery wordt geïntroduceerd en de lay-out wordt gewijzigd, worden _breekpunten ._

Een veelgebruikte aanpak bij het gebruik van mediaquery's is het maken van een eenvoudige lay-out met één kolom voor apparaten met een smal scherm (bijv. mobiele telefoons), vervolgens controleren op grotere schermen en een lay-out met meerdere kolommen implementeren wanneer u weet dat u voldoende schermbreedte hebt om deze te verwerken. Dit wordt vaak omschreven als **mobile first** design.

Meer informatie vindt u in de MDN-documentatie voor [mediaquery's](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries).

## [Flexibele rasters](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#flexible_grids "Permalink to Flexible grids")

Responsieve sites veranderen niet alleen hun lay-out tussen breekpunten, ze zijn gebouwd op flexibele rasters. Een flexibel raster betekent dat u niet elke mogelijke apparaatgrootte hoeft te targeten die er is en er een perfecte pixellay-out voor hoeft te maken. Die aanpak zou onmogelijk zijn gezien het enorme aantal apparaten van verschillende grootte dat bestaat, en het feit dat mensen op desktop in ieder geval niet altijd hun browservenster hebben gemaximaliseerd.

Door een flexibel raster te gebruiken, hoeft u alleen maar een breekpunt toe te voegen en het ontwerp te wijzigen op het punt waar de inhoud er slecht uit begint te zien. Als de lijnlengten bijvoorbeeld onleesbaar lang worden naarmate de schermgrootte toeneemt, of als een vak wordt verpletterd met twee woorden op elke regel terwijl deze smaller wordt.

In de begindagen van responsief ontwerp was onze enige optie voor het uitvoeren van lay-out het gebruik van [drijvers.](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Floats) Flexibele zwevende lay-outs werden bereikt door elk element een procentuele breedte te geven en ervoor te zorgen dat over de lay-out de totalen niet meer dan 100% bedroegen. In zijn originele stuk over vloeiende rasters beschreef Marcotte een formule voor het maken van een lay-out die is ontworpen met behulp van pixels en deze om te zetten in percentages.

```
target / context = result 
```

Als onze doelkolomgrootte bijvoorbeeld 60 pixels is en de context (of container) waarin deze zich bevindt 960 pixels is, delen we 60 bij 960 om een waarde te krijgen die we in ons CSS kunnen gebruiken, nadat we het decimaalteken twee plaatsen naar rechts hebben verplaatst.

```
.col {
  width: 6.25%; /* 60 / 960 = 0.0625 */
}
```

Deze aanpak zal vandaag op veel plaatsen op het web te vinden zijn en wordt hier gedocumenteerd in de lay-outsectie van ons artikel [Over oudere lay-outmethoden.](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Legacy_Layout_Methods) Het is waarschijnlijk dat u websites tegenkomt die deze aanpak in uw werk gebruiken, dus het is de moeite waard om het te begrijpen, ook al zou u geen moderne site bouwen met behulp van een op float gebaseerd flexibel raster.

In het volgende voorbeeld wordt een eenvoudig responsief ontwerp gedemonst gedemonibilitair ontwerp weergegeven met behulp van mediaquery's en een flexibel raster. Op smalle schermen geeft de lay-out de vakken weer die op elkaar zijn gestapeld:

![A mobile view of the layout with boxes stacked on top of each other vertically.](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design/mdn-rwd-mobile.png)

Op bredere schermen gaan ze naar twee kolommen:

![A desktop view of a layout with two columns.](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design/mdn-rwd-desktop.png)

**Opmerking**: U het [live voorbeeld](https://mdn.github.io/css-examples/learn/rwd/float-based-rwd.html) en de [broncode](https://github.com/mdn/css-examples/blob/master/learn/rwd/float-based-rwd.html) voor dit voorbeeld vinden op GitHub.

## [Moderne lay-outtechnologieën](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#modern_layout_technologies "Permalink to Modern layout technologies")

Moderne lay-outmethoden zoals [indeling met meerdere kolommen,](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout) [Flexbox](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox)en [Raster](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids) reageren standaard. Ze gaan er allemaal van uit dat u probeert een flexibel raster te maken en u gemakkelijkere manieren te geven om dit te doen.

### [Multicol](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#multicol "Permalink to Multicol")

De oudste van deze lay-outmethoden is multicol - wanneer u een opgeeft, geeft dit aan in hoeveel kolommen u uw inhoud wilt splitsen. De browser werkt vervolgens de grootte hiervan uit, een grootte die zal veranderen afhankelijk van de schermgrootte.`column-count`

```
.container {
  column-count: 3;
}
```

Als u in plaats daarvan een opgeeft, geeft u een _minimale_ breedte op. De browser maakt zoveel kolommen van die breedte als comfortabel in de container past en deelt vervolgens de resterende ruimte tussen alle kolommen. Daarom verandert het aantal kolommen afhankelijk van hoeveel ruimte er is.`column-width`

```
.container {
  column-width: 10em;
}
```

### [Flexbox](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#flexbox "Permalink to Flexbox")

In Flexbox verkleinen en verdelen flex-items de ruimte tussen de items op basis van de ruimte in hun container, als hun aanvankelijke gedrag. Door de waarden voor te wijzigen en u aangeven hoe u wilt dat de items zich gedragen wanneer ze meer of minder ruimte om hen heen tegenkomen.`flex-grow``flex-shrink`

In het onderstaande voorbeeld nemen de flexitems elk evenveel ruimte in de flexcontainer in beslag, met behulp van de afkorting van zoals beschreven in het lay-outonderwerp [Flexbox: Flexibele grootte van flexitems](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox#flexible_sizing_of_flex_items).`flex: 1`

```
.container {
  display: flex;
}

.item {
  flex: 1;
}
```

**Opmerking:**Als voorbeeld hebben we de eenvoudige responsieve lay-out hierboven opnieuw opgebouwd, dit keer met flexbox. U zien hoe we geen vreemde percentagewaarden meer hoeven te gebruiken om de grootte van de kolommen te berekenen: [voorbeeld](https://mdn.github.io/css-examples/learn/rwd/flex-based-rwd.html), [broncode](https://github.com/mdn/css-examples/blob/master/learn/rwd/flex-based-rwd.html).

### [CSS-raster](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#css_grid "Permalink to CSS grid")

In CSS Grid Layout maakt het apparaat de verdeling van de beschikbare ruimte over rastersporen mogelijk. In het volgende voorbeeld wordt een rastercontainer gemaakt met de grootte van drie tracks op . Hierdoor worden drie kolom tracks gemaakt, die elk een deel van de beschikbare ruimte in de container in beslag nemen. U meer te weten komen over deze aanpak om een raster te maken in het onderwerp Lay-outrasters leren, onder [Flexibele rasters met de fr-eenheid](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids#flexible_grids_with_the_fr_unit).`fr``1fr`

```
.container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
}
```

**Opmerking**: De versie van de rasterlay-out is nog eenvoudiger omdat we de kolommen op de .wrapper kunnen definiëren: [voorbeeld](https://mdn.github.io/css-examples/learn/rwd/grid-based-rwd.html), [broncode](https://github.com/mdn/css-examples/blob/master/learn/rwd/grid-based-rwd.html).

## [Responsieve afbeeldingen](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#responsive_images "Permalink to Responsive images")

De eenvoudigste benadering van responsieve afbeeldingen was zoals beschreven in Marcotte's vroege artikelen over responsief ontwerp. Kortom, je zou een afbeelding maken die het grootste formaat had dat nodig zou kunnen zijn, en deze verkleinen. Dit is nog steeds een aanpak die vandaag de dag wordt gebruikt, en in de meeste stylesheets vindt u de volgende CSS ergens:

```
img {
  max-width: 100%;
}
```

Er zijn duidelijke nadelen aan deze aanpak. De afbeelding kan een stuk kleiner worden weergegeven dan de intrinsieke grootte, wat een verspilling van bandbreedte is - een mobiele gebruiker kan een afbeelding downloaden die meerdere keren zo groot is als wat ze daadwerkelijk in het browservenster zien. Bovendien wilt u mogelijk niet dezelfde beeldverhouding op mobiel als op het bureaublad. Het kan bijvoorbeeld leuk zijn om een vierkante afbeelding voor mobiel te hebben, maar dezelfde scène weer te geven als een liggende afbeelding op het bureaublad. Of, als u de kleinere grootte van een afbeelding op mobiel erkent, wilt u misschien helemaal een ander beeld weergeven, een beeld dat gemakkelijker te begrijpen is bij een klein schermformaat. Deze dingen kunnen niet worden bereikt door een afbeelding af te schalen.

Responsieve afbeeldingen, met behulp van het element [`<picture>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/picture) en de [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) en kenmerken lossen beide problemen op. U meerdere formaten opgeven, samen met hints (metagegevens die de schermgrootte en resolutie beschrijven waarvoor de afbeelding het meest geschikt is), en de browser kiest de meest geschikte afbeelding voor elk apparaat, zodat een gebruiker een afbeeldingsgrootte downloadt die geschikt is voor het apparaat dat ze gebruiken.`srcset``sizes`

U ook directe afbeeldingen _maken_ die op verschillende formaten worden gebruikt, waardoor een ander bijsnijden of volledig ander beeld wordt geboden dan verschillende schermformaten.

U een gedetailleerde [handleiding voor responsieve afbeeldingen](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images) vinden in de sectie HTML leren hier op MDN.

## [Responsieve typografie](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#responsive_typography "Permalink to Responsive typography")

Een element van responsief ontwerp dat niet in eerder werk werd behandeld, was het idee van responsieve typografie. In wezen beschrijft dit het wijzigen van tekengrootten binnen mediaquery's om kleinere of grotere hoeveelheden schermvastgoed weer te geven.

In dit voorbeeld willen we onze kop van niveau 1 instellen op , wat betekent dat deze vier keer onze basislettertypegrootte zal zijn. Dat is echt een grote kop! We willen deze jumbo-kop alleen op grotere schermformaten, daarom maken we eerst een kleinere kop en gebruiken we mediaquery's om deze te overschrijven met het grotere formaat als we weten dat de gebruiker een schermgrootte van ten minste .`4rem``1200px`

```
html {
  font-size: 1em;
}

h1 {
  font-size: 2rem;
}

@media (min-width: 1200px) {
  h1 {
    font-size: 4rem;
  }
}
```

We hebben ons voorbeeld van een responsief raster hierboven bewerkt om ook responsief type op te nemen met behulp van de beschreven methode. U zien hoe de kop van grootte wisselt terwijl de lay-out naar de versie met twee kolommen gaat.

Op mobiel is de kop kleiner:

![A stacked layout with a small heading size.](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design/mdn-rwd-font-mobile.png)

Op desktop zien we echter de grotere kopgrootte:

![A two column layout with a large heading.](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design/mdn-rwd-font-desktop.png)

**Opmerking**: Zie dit voorbeeld in actie: [voorbeeld](https://mdn.github.io/css-examples/learn/rwd/type-rwd.html), [broncode](https://github.com/mdn/css-examples/blob/master/learn/rwd/type-rwd.html).

Zoals deze benadering van typografie laat zien, hoeft u mediaquery's niet te beperken tot het alleen wijzigen van de lay-out van de pagina. Ze kunnen worden gebruikt om elk element aan te passen om het bruikbaarder of aantrekkelijker te maken bij alternatieve schermformaten.

### [Venstereenheden gebruiken voor responsieve typografie](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#using_viewport_units_for_responsive_typography "Permalink to Using viewport units for responsive typography")

Een interessante aanpak is om de viewport-eenheid te gebruiken om responsieve typografie mogelijk te maken. is gelijk aan één procent van de breedte van het venster, wat betekent dat als u uw tekengrootte instelt met , deze altijd betrekking heeft op de grootte van het venster.`vw``1vw``vw`

```
h1 {
  font-size: 6vw;
}
```

Het probleem met het bovenstaande is dat de gebruiker de mogelijkheid verliest om in te zoomen op elke tekst die is ingesteld met behulp van het apparaat, omdat die tekst altijd gerelateerd is aan de grootte van het venster. **Daarom moet u nooit tekst instellen met alleen venstereenheden**.`vw`

Er is een oplossing, en het gaat om het gebruik van . Als u het apparaat toevoegt aan een waardenset met een vaste grootte zoals s of s, is de tekst nog steeds zoombaar. In wezen voegt het apparaat bovenop die ingezoomde waarde toe:`[calc()](https://developer.mozilla.org/en-US/docs/Web/CSS/calc())``vw``em``rem``vw`

```
h1 {
  font-size: calc(1.5rem + 3vw);
}
```

Dit betekent dat we de tekengrootte voor de kop slechts één keer hoeven op te geven, in plaats van deze in te stellen voor mobiel en opnieuw te definiëren in de mediaquery's. Het lettertype neemt dan geleidelijk toe naarmate u de grootte van het venster vergroot.

Zie een voorbeeld hiervan in actie: [voorbeeld](https://mdn.github.io/css-examples/learn/rwd/type-vw.html), [broncode](https://github.com/mdn/css-examples/blob/master/learn/rwd/type-vw.html).

## [De metatag van het venster](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#the_viewport_meta_tag "Permalink to The viewport meta tag")

Als u naar de HTML-bron van een responsieve pagina kijkt, ziet u meestal de volgende [`tag <meta>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta) in de van het document.`<head>`

```
<meta name="viewport" content="width=device-width,initial-scale=1">
```

Deze metatag vertelt mobiele browsers dat ze de breedte van het venster moeten instellen op de breedte van het apparaat en het document moeten schalen naar 100% van de beoogde grootte, wat het document weergeeft op de voor mobiel geoptimaliseerde grootte die u hebt bedoeld.

Waarom is dit nodig? Omdat mobiele browsers de neiging hebben om te liegen over hun vensterbreedte.

Deze metatag bestaat omdat toen de originele iPhone werd gelanceerd en mensen websites op een klein telefoonscherm begonnen te bekijken, de meeste sites niet mobiel geoptimaliseerd waren. De mobiele browser stelt daarom de breedte van het venster in op 960 pixels, geeft de pagina op die breedte weer en toont het resultaat als een uitgezoomde versie van de bureaubladlay-out. Andere mobiele browsers (bijv. op Google Android) deden hetzelfde. Gebruikers konden inzoomen en rond de website pannen om de stukjes te bekijken waarin ze geïnteresseerd waren, maar het zag er slecht uit. Je zult dit vandaag nog steeds zien als je het ongeluk hebt om een site tegen te komen die geen responsief ontwerp heeft.

Het probleem is dat uw responsieve ontwerp met breekpunten en mediaquery's niet werkt zoals bedoeld in mobiele browsers. Als je een smalle schermlay-out hebt die begint met een breedte van het venster van 480 px of minder en het venster is ingesteld op 960px, zie je je smalle schermindeling nooit op mobiel. Door in te stellen, overschrijft u de standaardinstelling van Apple met de werkelijke breedte van het apparaat, zodat uw mediaquery's werken zoals bedoeld.`width=device-width``width=960px`

**U moet dus _altijd_ de bovenstaande html-regel in het hoofd van uw documenten opnemen.**

Er zijn andere instellingen die u gebruiken met de viewport-metatag, maar over het algemeen is de bovenstaande regel wat u wilt gebruiken.

- `initial-scale`: Hiermee stelt u de beginzoom van de pagina in, die we op 1 hebben ingesteld.
- `height`: Hiermee stelt u een specifieke hoogte in voor het venster.
- `minimum-scale`: Hiermee stelt u het minimale zoomniveau in.
- `maximum-scale`: Hiermee stelt u het maximale zoomniveau in.
- `user-scalable`: Voorkomt zoomen als deze is ingesteld op .`no`

U moet het gebruik van , en in het bijzonder de instelling voor . Gebruikers moeten zoveel of zo weinig kunnen zoomen als nodig is; voorkomen dat dit toegankelijkheidsproblemen veroorzaakt.`minimum-scale``maximum-scale``user-scalable``no`

**Opmerking:**Er is een CSS @-regel die is ontworpen om de viewport-metatag te vervangen - [@viewport](https://developer.mozilla.org/en-US/docs/Web/CSS/@viewport) - maar deze heeft slechte browserondersteuning. Wanneer beide worden gebruikt, overschrijft de metatag @viewport.

## [Samenvatting](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#summary "Permalink to Summary")

Responsief ontwerp verwijst naar een site- of toepassingsontwerp dat reageert op de omgeving waarin het wordt bekeken. Het omvat een aantal CSS- en HTML-functies en -technieken en is nu in wezen precies hoe we standaard websites bouwen. Overweeg de sites die u op uw telefoon bezoekt - het is waarschijnlijk vrij ongebruikelijk om een site tegen te komen die de desktopversie is die is afgeschaald, of waar u zijwaarts moet scrollen om dingen te vinden. Dit komt omdat het web is overgestapt op deze benadering van responsief ontwerpen.

Het is ook veel gemakkelijker geworden om responsieve ontwerpen te bereiken met behulp van de lay-outmethoden die u in deze lessen hebt geleerd. Als u vandaag de dag nieuw bent in webontwikkeling, heeft u veel meer tools tot uw beschikking dan in de begindagen van responsief ontwerp. Het is daarom de moeite waard om de leeftijd te controleren van alle materialen waar u naar verwijst. Hoewel de historische artikelen nog steeds nuttig zijn, maakt modern gebruik van CSS en HTML het veel gemakkelijker om elegante en nuttige ontwerpen te maken, ongeacht met welk apparaat uw bezoeker de site bekijkt.
