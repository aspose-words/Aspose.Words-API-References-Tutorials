---
title: Voeg Ole-object in Word in met Ole-pakket
linktitle: Voeg Ole-object in Word in met Ole-pakket
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een OLE-object met een OLE-pakket invoegt in een document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

Hier is een stapsgewijze handleiding om de onderstaande C#-broncode uit te leggen, waarin wordt geïllustreerd hoe u een OLE-object in Word kunt invoegen met een OLE-pakket met behulp van Aspose.Words voor .NET.

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

## Stap 3: Voeg een OLE-object in met een OLE-pakket
 Gebruik de Documentgenerator`InsertOleObject`methode om een OLE-object met een OLE-pakket in het document in te voegen. Geef de gegevensstroom, het objecttype, de weergaveopties en andere noodzakelijke instellingen op.

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}
```

## Stap 4: Sla het document op
 Gebruik die van het document`Save` methode om het document in een bestand op te slaan.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

### Voorbeeldbroncode voor het invoegen van een OLE-object met een OLE-pakket met Aspose.Words voor .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Dit is een compleet codevoorbeeld voor het invoegen van een OLE-object met een OLE-pakket met Aspose.Words voor .NET. Zorg ervoor dat u de nodige referenties importeert en volg de eerder beschreven stappen om deze code in uw project te integreren.

## Conclusie

Concluderend hebben we een stapsgewijze handleiding doorlopen om een OLE-object in een Word-document in te voegen met een OLE-pakket met behulp van Aspose.Words voor .NET.

Door deze stappen te volgen, kunt u OLE-objecten met OLE-pakketten met succes in uw Word-documenten invoegen met behulp van Aspose.Words voor .NET. Zorg ervoor dat u de nodige referenties importeert en volg de instructies zorgvuldig om de gewenste resultaten te krijgen.

### Veelgestelde vragen over het invoegen van een ole-object in Word met een ole-pakket

#### Vraag: Welke inloggegevens moet ik importeren om Aspose.Words voor .NET te gebruiken?

A: Om Aspose.Words voor .NET te gebruiken, moet u de volgende referenties importeren:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

#### Vraag: Hoe maak ik een nieuw document en een documentgenerator?

 A: U kunt een nieuw document maken met behulp van de`Document` klasse en een documentbouwer met behulp van de`DocumentBuilder` klasse, zoals hieronder weergegeven:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Vraag: Hoe kan ik een OLE-object met een OLE-pakket in het document invoegen?

 EEN: Gebruik de`InsertOleObject` methode van de documentbouwer (`DocumentBuilder`) om een OLE-object met een OLE-pakket in het document in te voegen. Geef de gegevensstroom, het objecttype, de weergaveopties en andere noodzakelijke instellingen op. Hier is een voorbeeld :

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}
```

#### Vraag: Hoe kan ik het document opslaan?

 A: Gebruik het document`Save`methode om het document in een bestand op te slaan. Hier is een voorbeeld :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

#### Vraag: Kunt u een volledig voorbeeld geven van het invoegen van een OLE-object met een OLE-pakket met Aspose.Words voor .NET?

A: Hier is een volledige voorbeeldcode om een OLE-object in te voegen met een OLE-pakket met behulp van Aspose.Words voor .NET. Zorg ervoor dat u de benodigde referenties importeert en volg de eerder beschreven stappen om deze code in uw project te integreren:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Hiermee is onze tutorial afgesloten over het invoegen van een OLE-object met een OLE-pakket in een Word-document met Aspose.Words voor .NET. Importeer gerust de nodige referenties en volg de beschreven stappen om deze code in uw project te integreren. Indien u nog vragen heeft, aarzel dan niet om contact met ons op te nemen.