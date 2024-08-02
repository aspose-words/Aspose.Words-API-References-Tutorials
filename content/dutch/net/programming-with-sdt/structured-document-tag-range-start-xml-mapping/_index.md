---
title: Gestructureerd documenttagbereik Start XML-toewijzing
linktitle: Gestructureerd documenttagbereik Start XML-toewijzing
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u XML-gegevens dynamisch kunt binden aan gestructureerde documenttags in Word met behulp van Aspose.Words voor .NET. Volg onze stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---
## Invoering

Heeft u ooit XML-gegevens dynamisch in een Word-document willen invoegen? Nou, je hebt geluk! Aspose.Words voor .NET maakt deze taak een fluitje van een cent. In deze zelfstudie duiken we diep in de XML-toewijzing van het gestructureerde documenttagbereik. Met deze functie kunt u aangepaste XML-onderdelen koppelen aan inhoudsbesturingselementen, zodat de inhoud van uw document naadloos wordt bijgewerkt met uw XML-gegevens. Klaar om uw documenten om te zetten in dynamische meesterwerken.

## Vereisten

Voordat we ingaan op het codeergedeelte, zorgen we ervoor dat je alles hebt wat je nodig hebt:

1.  Aspose.Words voor .NET Library: Zorg ervoor dat u over de nieuwste versie beschikt. Je kunt het downloaden[hier](https://releases.aspose.com/words/net/).
2. Ontwikkelomgeving: Visual Studio of een andere IDE die C# ondersteunt.
3. Basiskennis van C#: Bekendheid met programmeren in C# is een must.
4. Word-document: een voorbeeld van een Word-document om mee te werken.

## Naamruimten importeren

Laten we eerst de benodigde naamruimten importeren. Dit zorgt ervoor dat we toegang hebben tot alle vereiste klassen en methoden in Aspose.Words voor .NET.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Markup;
using System.Text;
```

## Stap 1: Stel uw documentenmap in

Elk project heeft een basis nodig, toch? Hier stellen we het pad naar uw documentmap in.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Laad het Word-document

Vervolgens laden we het Word-document. Dit is het document waarin we onze XML-gegevens zullen invoegen.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
```

## Stap 3: Voeg een aangepast XML-onderdeel toe

We moeten een XML-gedeelte construeren dat de gegevens bevat die we willen invoegen en dit toevoegen aan de CustomXmlPart-collectie van het document. Dit aangepaste XML-gedeelte zal dienen als gegevensbron voor onze gestructureerde documenttags.

### Een XML-onderdeel maken

Genereer eerst een unieke ID voor het XML-onderdeel en definieer de inhoud ervan.

```csharp
// Construeer een XML-onderdeel dat gegevens bevat en voeg dit toe aan de CustomXmlPart-verzameling van het document.
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

### Controleer de inhoud van het XML-onderdeel

Om ervoor te zorgen dat het XML-gedeelte correct wordt toegevoegd, drukken we de inhoud ervan af.

```csharp
Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
```

## Stap 4: Maak een gestructureerde documenttag

Een Structured Document Tag (SDT) is een inhoudscontrole die aan een XML-onderdeel kan worden gekoppeld. Hier maken we een SDT die de inhoud van ons aangepaste XML-gedeelte weergeeft.

Zoek eerst het begin van het SDT-bereik in het document.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
```

## Stap 5: Stel XML-toewijzing in voor de SDT

Nu is het tijd om ons XML-gedeelte aan de SDT te binden. Door een XML-mapping in te stellen, specificeren we welk deel van de XML-gegevens in de SDT moet worden weergegeven.

 De XPath verwijst naar het specifieke element in het XML-gedeelte dat we willen weergeven. Hier wijzen we op de tweede`<text>` onderdeel binnen de`<root>` element.

```csharp
// Stel een mapping in voor onze StructuredDocumentTag
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## Stap 6: Sla het document op

Sla ten slotte het document op om de wijzigingen in actie te zien. De SDT in het Word-document geeft nu de opgegeven XML-inhoud weer.

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

## Conclusie

En daar heb je het! U hebt met succes een XML-onderdeel toegewezen aan een gestructureerde documenttag in een Word-document met behulp van Aspose.Words voor .NET. Met deze krachtige functie kunt u moeiteloos dynamische en gegevensgestuurde documenten maken. Of u nu rapporten, facturen of een ander documenttype genereert, XML-toewijzing kan uw workflow aanzienlijk stroomlijnen.

## Veelgestelde vragen

### Wat is een gestructureerde documenttag in Word?
Gestructureerde documenttags, ook wel inhoudsbesturingselementen genoemd, zijn containers voor specifieke typen inhoud in Word-documenten. Ze kunnen worden gebruikt om gegevens te binden, bewerkingen te beperken of gebruikers te begeleiden bij het maken van documenten.

### Hoe kan ik de inhoud van het XML-onderdeel dynamisch bijwerken?
 U kunt de inhoud van het XML-onderdeel bijwerken door het`xmlPartContent` tekenreeks voordat u deze aan het document toevoegt. Werk eenvoudigweg de string bij met de nieuwe gegevens en voeg deze toe aan de`CustomXmlParts` verzameling.

### Kan ik meerdere XML-onderdelen aan verschillende SDT's in hetzelfde document binden?
Ja, u kunt meerdere XML-onderdelen aan verschillende SDT's in hetzelfde document binden. Elke SDT kan zijn eigen unieke XML-onderdeel en XPath-toewijzing hebben.

### Is het mogelijk om complexe XML-structuren aan SDT's toe te wijzen?
Absoluut! U kunt complexe XML-structuren aan SDT's toewijzen door gedetailleerde XPath-expressies te gebruiken die nauwkeurig naar de gewenste elementen binnen het XML-gedeelte verwijzen.

### Hoe kan ik een XML-onderdeel uit een document verwijderen?
 U kunt een XML-onderdeel verwijderen door het bestand`Remove` methode op de`CustomXmlParts` verzamelen, passeren van de`xmlPartId` van het XML-gedeelte dat u wilt verwijderen.