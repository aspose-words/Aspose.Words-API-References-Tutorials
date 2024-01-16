---
title: Voeg Ole-object in Word-document in als pictogram
linktitle: Voeg Ole-object in Word-document in als pictogram
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een OLE-object in een Word-document invoegt als pictogram met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

Hier is een stapsgewijze handleiding om de onderstaande C#-broncode uit te leggen, die illustreert hoe u een OLE-object in een Word-document als pictogram kunt invoegen met behulp van Aspose.Words voor .NET.

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

## Stap 3: Voeg een OLE-object in als pictogram
 Gebruik die van de Document Builder`InsertOleObjectAsIcon`methode om een OLE-object als pictogram in het document in te voegen. Geef het OLE-bestandspad, de weergavevlag, het pictogrampad en de naam van het ingesloten object op.

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## Stap 4: Sla het document op
 Gebruik die van het document`Save` methode om het document in een bestand op te slaan.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

### Voorbeeldbroncode voor het invoegen van een OLE-object als pictogram met Aspose.Words voor .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

Dit is een compleet codevoorbeeld voor het invoegen van een OLE-object als pictogram met Aspose.Words voor .NET. Zorg ervoor dat u de nodige referenties importeert en volg de eerder beschreven stappen om deze code in uw project te integreren.

## Conclusie

Concluderend hebben we een stapsgewijze handleiding onderzocht om een OLE-object als pictogram in een Word-document in te voegen met behulp van Aspose.Words voor .NET.

Door deze stappen te volgen, kunt u met Aspose.Words voor .NET met succes een OLE-object als pictogram in uw Word-documenten invoegen. Zorg ervoor dat u de nodige referenties importeert en volg de instructies zorgvuldig om de gewenste resultaten te krijgen.

### Veelgestelde vragen over het invoegen van een ole-object in een Word-document als pictogram

#### V. Welke referenties zijn nodig om een OLE-object als pictogram in een Word-document in te voegen met behulp van Aspose.Words voor .NET?

A: U moet de volgende referenties in uw project importeren om Aspose.Words voor .NET te gebruiken:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### V. Hoe maak ik een nieuw document en een documentgenerator in Aspose.Words voor .NET?

 A: U kunt een nieuw document maken met behulp van de`Document` klasse en een documentbouwer met behulp van de`DocumentBuilder` klas. Hier is een voorbeeld :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### V. Hoe kan ik een OLE-object als pictogram in het document invoegen?

 A: Gebruik die van Document Builder`InsertOleObjectAsIcon` methode om een OLE-object als pictogram in te voegen. Geef het OLE-bestandspad, de weergavevlag, het pictogrampad en de naam van het ingesloten object op. Hier is een voorbeeld :

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

#### V. Hoe kan ik het document opslaan terwijl het OLE-object als pictogram is ingevoegd?

 A: Gebruik het document`Save` methode om het document in een bestand op te slaan. Hier is een voorbeeld :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```