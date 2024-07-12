---
title: Voeg Ole-object in als pictogram met behulp van Stream
linktitle: Voeg Ole-object in als pictogram met behulp van Stream
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een OLE-object als pictogram invoegt met behulp van een stream met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

Hier is een stapsgewijze handleiding om de onderstaande C#-broncode uit te leggen, waarin wordt geïllustreerd hoe u een OLE-object als pictogram kunt invoegen met behulp van een stream met Aspose.Words voor .NET.

## Stap 1: Importeer de benodigde referenties
Zorg ervoor dat u, voordat u begint, de benodigde referenties hebt geïmporteerd om Aspose.Words voor .NET in uw project te gebruiken. Dit omvat het importeren van de Aspose.Words-bibliotheek en het toevoegen van de vereiste naamruimten aan uw bronbestand.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## Stap 2: Maak een nieuw document en een documentgenerator
 In deze stap maken we een nieuw document met behulp van de`Document` klasse en een documentbouwer met behulp van de`DocumentBuilder` klas.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 3: Voeg een OLE-object in als een pictogram uit een stream
 Gebruik die van de Document Builder`InsertOleObjectAsIcon` methode om een OLE-object als een pictogram uit een stream in het document in te voegen. Geef de gegevensstroom, het objecttype, het pictogrampad en de naam van het ingesloten object op.

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

## Stap 4: Sla het document op
 Gebruik die van het document`Save` methode om het document in een bestand op te slaan.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

### Voorbeeldbroncode voor het invoegen van een OLE-object als pictogram met behulp van een stream met Aspose.Words voor .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

Dit is een compleet codevoorbeeld voor het invoegen van een OLE-object als pictogram met behulp van een stream met Aspose.Words voor .NET. Zorg ervoor dat u de nodige referenties importeert en volg de eerder beschreven stappen om deze code in uw project te integreren.

## Conclusie

In de stapsgewijze handleiding hierboven wordt uitgelegd hoe u een OLE-object als pictogram in een Word-document kunt invoegen met behulp van een stroom met Aspose.Words voor .NET. Door de beschreven stappen te volgen, kunt u deze functionaliteit in uw project integreren. Zorg ervoor dat u de benodigde referenties importeert, een nieuwe document- en documentgenerator maakt, het OLE-object invoegt als een pictogram uit de stream en het document vervolgens opslaat. Gebruik de meegeleverde voorbeeldcode als uitgangspunt en pas deze aan uw behoeften aan.

### Veelgestelde vragen

#### V. Hoe importeer ik de benodigde referenties om Aspose.Words voor .NET te gebruiken?

A. Om de benodigde referenties te importeren, moet u deze stappen volgen:

 Voeg het volgende toe`using` uitspraken bovenaan uw bronbestand:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```
Zorg ervoor dat u de Aspose.Words-bibliotheek aan uw project hebt toegevoegd.

#### V. Hoe maak ik een nieuw document en een nieuwe documentbuilder met Aspose.Words voor .NET?

A. Om een nieuw document en documentgenerator aan te maken, kunt u deze stappen volgen:

 Gebruik de`Document` klasse om een nieuw document te maken:

```csharp
Document doc = new Document();
```
 Gebruik de`DocumentBuilder`class om een documentbouwer te maken die is gekoppeld aan het eerder gemaakte document:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### V. Hoe kan ik een OLE-object invoegen als een pictogram uit een stream met behulp van Aspose.Words voor .NET?

A. Om een OLE-object als pictogram uit een stream in te voegen, kunt u deze stappen volgen:

 Gebruik de`InsertOleObjectAsIcon` methode van de documentgenerator om het OLE-object in te voegen:

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
  builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

#### V. Hoe kan ik het document in een bestand opslaan?

A.  Om het document in een bestand op te slaan, kunt u de`Save` methode van het document waarin het bestemmingspad wordt gespecificeerd:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

#### V. Hoe sluit ik de code in voor het invoegen van een OLE-object als een pictogram uit een stream in mijn project?

A. Volg deze stappen om de code voor het invoegen van een OLE-object als een pictogram uit een stream in uw project in te sluiten:
-  Importeer de benodigde referenties door de juiste toe te voegen`using` verklaringen.
-  Maak een nieuw document en een documentbuilder met behulp van de`Document`En`DocumentBuilder` klassen.
- Gebruik de code voor het invoegen van het OLE-object als een pictogram uit een stream.
-  Sla het document op met behulp van de`Save` methode met het juiste bestemmingspad.

Door deze stappen te volgen, kunt u met Aspose.Words voor .NET een OLE-object als pictogram uit een stream invoegen. Zorg ervoor dat u de instructies volgt en de nodige referenties importeert om de gewenste resultaten te krijgen.