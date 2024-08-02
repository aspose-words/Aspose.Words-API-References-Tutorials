---
title: Verticaal anker
linktitle: Verticaal anker
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u verticale ankerposities instelt voor tekstvakken in Word-documenten met Aspose.Words voor .NET. Gemakkelijke stap-voor-stap handleiding inbegrepen.
type: docs
weight: 10
url: /nl/net/programming-with-shapes/vertical-anchor/
---
## Invoering

Heeft u ooit de behoefte gehad om precies te bepalen waar tekst in een tekstvak in een Word-document verschijnt? Misschien wilt u dat uw tekst aan de boven-, midden- of onderkant van het tekstvak wordt verankerd? Dan ben je hier aan het juiste adres! In deze zelfstudie onderzoeken we hoe u Aspose.Words voor .NET kunt gebruiken om het verticale anker van tekstvakken in Word-documenten in te stellen. Beschouw verticale verankering als de toverstaf die uw tekst precies op de gewenste plek in de container plaatst. Klaar om erin te duiken? Laten we beginnen!

## Vereisten

Voordat we ingaan op de moeren en bouten van verticale verankering, moet je een paar dingen op hun plaats hebben:

1.  Aspose.Words voor .NET: Zorg ervoor dat de Aspose.Words voor .NET-bibliotheek is geïnstalleerd. Als je hem nog niet hebt, dan kan dat[download het hier](https://releases.aspose.com/words/net/).
2. Visual Studio: In deze tutorial wordt ervan uitgegaan dat u Visual Studio of een andere .NET IDE gebruikt voor codering.
3. Basiskennis van C#: Bekendheid met C# en .NET zal u helpen dit probleemloos te volgen.

## Naamruimten importeren

Om aan de slag te gaan, moet u de benodigde naamruimten in uw C#-code importeren. Hier vertelt u uw toepassing waar de klassen en methoden kunnen worden gevonden die u gaat gebruiken. Hier leest u hoe u het moet doen:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

Deze naamruimten bieden de klassen die u nodig hebt om met documenten en vormen te werken.

## Stap 1: Initialiseer het document

Allereerst moet u een nieuw Word-document maken. Zie dit als het opzetten van je canvas voordat je begint met schilderen.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Hier,`Document` is je lege canvas, en`DocumentBuilder` is uw penseel, waarmee u vormen en tekst kunt toevoegen.

## Stap 2: Voeg een tekstvakvorm in

Laten we nu een tekstvak aan ons document toevoegen. Dit is waar uw tekst zal leven. 

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

 In dit voorbeeld`ShapeType.TextBox` specificeert de gewenste vorm, en`200, 200` zijn de breedte en hoogte van het tekstvak in punten.

## Stap 3: Stel het verticale anker in

Hier gebeurt de magie! U kunt de verticale uitlijning van de tekst in het tekstvak instellen. Dit bepaalt of de tekst aan de boven-, midden- of onderkant van het tekstvak is verankerd.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

 In dit geval,`TextBoxAnchor.Bottom`zorgt ervoor dat de tekst aan de onderkant van het tekstvak wordt verankerd. Als je het gecentreerd of uitgelijnd wilt hebben met de bovenkant, zou je het gebruiken`TextBoxAnchor.Center` of`TextBoxAnchor.Top`respectievelijk.

## Stap 4: Voeg tekst toe aan het tekstvak

Nu is het tijd om wat inhoud aan uw tekstvak toe te voegen. Zie het als het invullen van je canvas met de laatste hand.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

 Hier,`MoveTo` zorgt ervoor dat de tekst in het tekstvak wordt ingevoegd, en`Write` voegt de daadwerkelijke tekst toe.

## Stap 5: Sla het document op

De laatste stap is het opslaan van uw document. Dit is alsof je je voltooide schilderij in een lijst plaatst.

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

## Conclusie

En daar heb je het! U hebt zojuist geleerd hoe u de verticale uitlijning van tekst in een tekstvak in een Word-document kunt regelen met behulp van Aspose.Words voor .NET. Of u tekst nu bovenaan, in het midden of onderaan verankert, deze functie geeft u nauwkeurige controle over de lay-out van uw document. Dus de volgende keer dat u de tekstplaatsing van uw document moet aanpassen, weet u precies wat u moet doen!

## Veelgestelde vragen

### Wat is verticale verankering in een Word-document?
Verticale verankeringsregelaars waar de tekst in een tekstvak wordt geplaatst, zoals uitlijning boven, midden of onder.

### Kan ik naast tekstvakken ook andere vormen gebruiken?
Ja, u kunt verticale verankering gebruiken met andere vormen, hoewel tekstvakken het meest voorkomende gebruik zijn.

### Hoe wijzig ik het ankerpunt nadat ik het tekstvak heb gemaakt?
 U kunt het ankerpunt wijzigen door de`VerticalAnchor` eigenschap van het tekstvakvormobject.

### Is het mogelijk om tekst in het midden van het tekstvak te verankeren?
 Absoluut! Gebruik gewoon`TextBoxAnchor.Center` om de tekst verticaal in het tekstvak te centreren.

### Waar kan ik meer informatie vinden over Aspose.Words voor .NET?
 Bekijk de[Aspose.Words-documentatie](https://reference.aspose.com/words/net/) voor meer details en handleidingen.