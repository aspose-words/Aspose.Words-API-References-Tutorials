---
title: Automatische koppeling
linktitle: Automatische koppeling
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u autolink invoegt met Aspose.Words voor .NET Stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/working-with-markdown/autolink/
---

In dit voorbeeld leggen we uit hoe u de functie "Autolink" kunt gebruiken met Aspose.Words voor .NET. Met deze functie kunt u automatisch hyperlinks in uw document invoegen.

## Stap 1: Een documentgenerator gebruiken

Eerst gebruiken we een documentgenerator om inhoud aan ons document toe te voegen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Stap 2: Een hyperlink invoegen

 We kunnen een hyperlink invoegen met behulp van de`InsertHyperlink` methode van de documentgenerator. We specificeren de URL en de tekst die voor de link moet worden weergegeven.

```csharp
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", false);
```

## Stap 3: Een e-mailadres als link invoegen

We kunnen ook een e-mailadres als link invoegen met het voorvoegsel "mailto:". Hierdoor kunnen gebruikers op de link klikken om hun standaard e-mailclient te openen.

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## Stap 4: Het document opslaan

Ten slotte kunnen we het document in het gewenste formaat opslaan.

### Voorbeeldbroncode voor Autolink met Aspose.Words voor .NET


```csharp
// Gebruik een documentbuilder om inhoud aan het document toe te voegen.
DocumentBuilder builder = new DocumentBuilder();

//Voeg hyperlink in.
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", false);
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```


Gefeliciteerd! U hebt nu geleerd hoe u de functie "Autolink" kunt gebruiken met Aspose.Words voor .NET.


### Veelgestelde vragen

#### Vraag: Hoe kan ik een automatische link naar een URL-adres in Aspose.Words maken?

 A: Om een automatische link naar een URL-adres in Aspose.Words te maken, kunt u de`<a>` labelen met de`href` attribuut dat het URL-adres bevat. U kunt bijvoorbeeld gebruiken`<a href="https://www.aspose.com">https://www.aspose.com</a>` om automatisch te linken naar "https://www.aspose.com".

#### Vraag: Is het mogelijk om de weergavetekst van een automatische link in Aspose.Words aan te passen?

 A: Ja, u kunt de weergavetekst van een automatische link in Aspose.Words aanpassen. In plaats van het URL-adres als weergavetekst te gebruiken, kunt u elke andere tekst gebruiken door de inhoud tussen de`<a>` labels. U kunt bijvoorbeeld gebruiken`<a href="https://www.aspose.com">Click here</a>` om de tekst "Klik hier" als automatische link weer te geven.

#### Vraag: Hoe kan ik extra attributen toevoegen aan een autolink in Aspose.Words?

A: Om extra attributen toe te voegen aan een automatische link in Aspose.Words, kunt u extra HTML-attributen gebruiken in de`<a>` label. U kunt bijvoorbeeld gebruiken`<a href="https://www.aspose.com" target="_blank">Link</a>` om de link in een nieuw venster of tabblad te openen met behulp van de` attribute target="_blank"`.