---
title: Ole-object invoegen in Word-document
linktitle: Ole-object invoegen in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een OLE-object invoegt in een Word-document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-oleobjects-and-activex/insert-ole-object/
---

Hier is een stapsgewijze handleiding om de onderstaande C#-broncode uit te leggen, waarin wordt geïllustreerd hoe u een OLE-object in een Word-document kunt invoegen met Aspose.Words voor .NET.

## Stap 1: Importeer de benodigde referenties
Zorg ervoor dat u, voordat u begint, de benodigde referenties hebt geïmporteerd om Aspose.Words voor .NET in uw project te gebruiken. Dit omvat het importeren van de Aspose.Words-bibliotheek en het toevoegen van de vereiste naamruimten aan uw bronbestand.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Stap 2: Maak een nieuw document en een documentgenerator
 In deze stap maken we een nieuw document met behulp van de`Document` klasse en een documentbouwer met behulp van de`DocumentBuilder` klas.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 3: Voeg een OLE-object in
 Gebruik die van de Document Builder`InsertOleObject`methode om een OLE-object in het document in te voegen. Geef de OLE-object-URL, het objecttype, de weergaveopties en andere noodzakelijke instellingen op.

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", waar, waar, null);
```

## Stap 4: Sla het document op
 Gebruik die van het document`Save` methode om het document in een bestand op te slaan.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

### Voorbeeldbroncode voor het invoegen van een OLE-object met Aspose.Words voor .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", waar, waar, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

Dit is een compleet codevoorbeeld voor het invoegen van een OLE-object met Aspose.Words voor .NET. Zorg ervoor dat u de nodige referenties importeert en volg de eerder beschreven stappen om deze code in uw project te integreren.

## Conclusie

Concluderend: het invoegen van OLE-objecten in een Word-document is een krachtige functie die wordt aangeboden door Aspose.Words voor .NET. Met behulp van deze bibliotheek kunt u eenvoudig OLE-objecten, zoals HTML-bestanden, Excel-spreadsheets, PowerPoint-presentaties, enz., in uw Word-documenten insluiten.

In dit artikel hebben we een stapsgewijze handleiding doorlopen om de broncode in C# uit te leggen, waarin wordt geïllustreerd hoe u een OLE-object in een Word-document kunt invoegen. We hebben de nodige referenties behandeld, een nieuw document en een documentgenerator gemaakt, en de stappen om een OLE-object in te voegen en het document op te slaan.

### Veelgestelde vragen over het invoegen van een OLE-object in een Word-document

#### Vraag: Welke inloggegevens moet ik importeren om Aspose.Words voor .NET te gebruiken?

A: Om Aspose.Words voor .NET te gebruiken, moet u de volgende referenties importeren:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### Vraag: Hoe maak ik een nieuw document en een documentgenerator?

 A: U kunt een nieuw document maken met behulp van de`Document` klasse en een documentbouwer met behulp van de`DocumentBuilder` klasse, zoals hieronder weergegeven:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Vraag: Hoe kan ik een OLE-object in het document invoegen?

 EEN: Gebruik de`InsertOleObject` methode van de documentbouwer (`DocumentBuilder`) om een OLE-object in het document in te voegen. Geef de OLE-object-URL, het objecttype, de weergaveopties en andere noodzakelijke instellingen op. Hier is een voorbeeld :

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", waar, waar, null);
```

#### Vraag: Hoe kan ik het document opslaan?

 A: Gebruik het document`Save`methode om het document in een bestand op te slaan. Hier is een voorbeeld :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

#### Vraag: Kunt u een volledig voorbeeld geven van het invoegen van een OLE-object met Aspose.Words voor .NET?

A: Hier is een volledige voorbeeldcode om een OLE-object in te voegen met Aspose.Words voor .NET. Zorg ervoor dat u de benodigde referenties importeert en volg de eerder beschreven stappen om deze code in uw project te integreren:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", waar, waar, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```
