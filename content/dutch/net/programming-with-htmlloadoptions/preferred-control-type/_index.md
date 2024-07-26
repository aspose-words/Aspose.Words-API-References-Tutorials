---
title: Voorkeursbesturingstype in Word-document
linktitle: Voorkeursbesturingstype in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een formulierveld met invoervak invoegt in een Word-document met Aspose.Words voor .NET. Volg deze stapsgewijze handleiding voor een naadloze integratie van HTML-inhoud.
type: docs
weight: 10
url: /nl/net/programming-with-htmlloadoptions/preferred-control-type/
---
## Invoering

we duiken in een spannende tutorial over hoe je kunt werken met HTML-laadopties in Aspose.Words voor .NET, waarbij we ons specifiek richten op het instellen van het gewenste besturingstype bij het invoegen van een keuzelijst met invoervak in een Word-document. Deze stapsgewijze handleiding helpt u te begrijpen hoe u effectief HTML-inhoud in uw Word-documenten kunt manipuleren en weergeven met behulp van Aspose.Words voor .NET.

## Vereisten

Voordat we ingaan op de code, zijn er een paar dingen die u moet regelen:

1.  Aspose.Words voor .NET: Zorg ervoor dat de Aspose.Words voor .NET-bibliotheek is geïnstalleerd. Je kunt het downloaden van de[website](https://releases.aspose.com/words/net/).
2. Ontwikkelomgeving: U moet een ontwikkelomgeving hebben, zoals Visual Studio.
3. Basiskennis van C#: Een fundamenteel begrip van C#-programmeren is noodzakelijk om samen met de tutorial te volgen.
4. HTML-inhoud: Basiskennis van HTML is nuttig, aangezien we in dit voorbeeld met HTML-inhoud gaan werken.

## Naamruimten importeren

Laten we eerst de benodigde naamruimten importeren om aan de slag te gaan:

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Words;
using Aspose.Words.Loading;
```

Laten we het voorbeeld nu in meerdere stappen opsplitsen om duidelijkheid en begrip te garanderen.

## Stap 1: Stel uw HTML-inhoud in

Eerst moeten we de HTML-inhoud definiëren die we in het Word-document willen invoegen. Dit is het HTML-fragment dat we gaan gebruiken:

```csharp
const string html = @"
    <html>
        <select name='ComboBox' size='1'>
            <option value='val1'>item1</option>
            <option value='val2'></option>                        
        </select>
    </html>
";
```

Deze HTML bevat een eenvoudige keuzelijst met twee opties. We laden deze HTML in een Word-document en specificeren hoe deze moet worden weergegeven.

## Stap 2: Definieer de documentmap

Geef vervolgens de map op waarin uw Word-document wordt opgeslagen. Dit helpt bij het organiseren van uw bestanden en het schoonhouden van het padbeheer.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad waar u uw Word-document wilt opslaan.

## Stap 3: Configureer HTML-laadopties

 Hier configureren we de HTML-laadopties, met name gericht op de`PreferredControlType`eigendom. Dit bepaalt hoe de keuzelijst met invoervak in het Word-document moet worden weergegeven.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

 Door in te stellen`PreferredControlType` naar`HtmlControlType.StructuredDocumentTag`, zorgen we ervoor dat de keuzelijst met invoervak wordt weergegeven als een gestructureerde documenttag (SDT) in het Word-document.

## Stap 4: Laad de HTML-inhoud in het document

Met behulp van de geconfigureerde laadopties laden we de HTML-inhoud in een nieuw Word-document.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
```

Hier converteren we de HTML-tekenreeks naar een byte-array en laden deze in het document met behulp van een geheugenstroom. Dit zorgt ervoor dat de HTML-inhoud correct wordt geïnterpreteerd en weergegeven door Aspose.Words.

## Stap 5: Sla het document op

Sla het document ten slotte op in de opgegeven map in DOCX-indeling.

```csharp
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

Hiermee wordt het Word-document met het weergegeven keuzelijstbesturingselement op de opgegeven locatie opgeslagen.

## Conclusie

En daar heb je het! We hebben met succes een keuzelijstformulierveld ingevoegd in een Word-document met behulp van Aspose.Words voor .NET door gebruik te maken van HTML-laadopties. Deze stapsgewijze handleiding moet u helpen het proces te begrijpen en toe te passen op uw projecten. Of u nu het maken van documenten automatiseert of HTML-inhoud manipuleert, Aspose.Words voor .NET biedt krachtige hulpmiddelen om uw doelen te bereiken.

## Veelgestelde vragen

### Wat is Aspose.Words voor .NET?
Aspose.Words voor .NET is een krachtige bibliotheek voor documentmanipulatie waarmee ontwikkelaars Word-documenten programmatisch kunnen maken, bewerken, converteren en weergeven.

### Kan ik andere HTML-besturingstypen gebruiken met Aspose.Words voor .NET?
Ja, Aspose.Words voor .NET ondersteunt verschillende HTML-besturingstypen. U kunt aanpassen hoe verschillende besturingselementen in het Word-document worden weergegeven.

### Hoe ga ik om met complexe HTML-inhoud in Aspose.Words voor .NET?
 Aspose.Words voor .NET biedt uitgebreide ondersteuning voor HTML, inclusief complexe elementen. Zorg ervoor dat u de`HtmlLoadOptions`op de juiste manier om te gaan met uw specifieke HTML-inhoud.

### Waar kan ik meer voorbeelden en documentatie vinden?
 Gedetailleerde documentatie en voorbeelden vindt u op de website[Aspose.Words voor .NET-documentatiepagina](https://reference.aspose.com/words/net/).

### Is er een gratis proefversie beschikbaar voor Aspose.Words voor .NET?
 Ja, u kunt een gratis proefversie downloaden van de[Aspose-website](https://releases.aspose.com/).
