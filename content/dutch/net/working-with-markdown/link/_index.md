---
title: Koppeling
linktitle: Koppeling
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u koppelingen invoegt met Aspose.Words voor .NET. Stap-voor-stap handleiding.
type: docs
weight: 10
url: /nl/net/working-with-markdown/link/
---

In dit voorbeeld laten we u zien hoe u de koppelingsfunctie gebruikt met Aspose.Words voor .NET. Links worden gebruikt om klikbare verwijzingen naar websites of andere documenten te creëren.

## Stap 1: Een documentgenerator gebruiken

Eerst gebruiken we een documentgenerator om inhoud aan ons document toe te voegen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Stap 2: Een link invoegen

 We kunnen een link invoegen met behulp van de`InsertHyperlink` methode van de documentgenerator. We moeten de linktekst specificeren, hier "Apose", evenals de bestemmings-URL.

```csharp
builder.InsertHyperlink("Aspose", "https://www.aspose.com", false);
```

### Voorbeeldbroncode voor koppelingen met Aspose.Words voor .NET


```csharp
// Gebruik een documentbuilder om inhoud aan het document toe te voegen.
DocumentBuilder builder = new DocumentBuilder();

// Link invoegen.
builder.InsertHyperlink("Aspose", "https://www.aspose.com", false);
```
Gefeliciteerd! U hebt nu geleerd hoe u de koppelingsfunctie kunt gebruiken met Aspose.Words voor .NET.


### Veelgestelde vragen

#### Vraag: Hoe kan ik naar een URL linken in Aspose.Words?

 A: Om naar een URL-adres in Aspose.Words te linken, kunt u de`<a>` labelen met de`href` attribuut dat het URL-adres bevat. U kunt bijvoorbeeld gebruiken`<a href="https://www.aspose.com">Click Here</a>` om te hyperlinken naar de URL "https://www.example.com" met de weergavetekst "Klik hier".

#### Vraag: Is het mogelijk om te linken naar een interne bladwijzer in Aspose.Words?

 A: Ja, het is mogelijk om te linken naar een interne bladwijzer in Aspose.Words. U kunt gebruik maken van de`<a>` labelen met de`href` attribuut dat de naam van de bladwijzer bevat, voorafgegaan door een hekje (#). Bijvoorbeeld,`<a href="#bookmark1">Go to bookmark 1</a>` linkt naar de bladwijzer met de naam "bladwijzer1" in het document.

#### Vraag: Hoe kan ik de weergavetekst van een link in Aspose.Words aanpassen?

A: Om de weergavetekst van een link in Aspose.Words aan te passen, kunt u de inhoud tussen de`<a>` labels. Bijvoorbeeld,`<a href="https://www.aspose.com">Click here</a>` toont de tekst "Klik hier" als hyperlink.

#### Vraag: Kan ik een doel opgeven voor een link in Aspose.Words?

 A: Ja, u kunt een doel voor een link in Aspose.Words opgeven met behulp van de`target` attribuut van de`<a>` label. Bijvoorbeeld,`<a href="https://www.aspose.com" target="_blank">Open in new window</a>` opent de link in een nieuw venster of tabblad.