---
title: Converteer Docx naar Rtf
linktitle: Converteer Docx naar Rtf
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u Word-documenten converteert van Docx naar RTF-indeling met Aspose.Words voor .NET. Stap-voor-stap handleiding met voorbeeldbroncode.
type: docs
weight: 10
url: /nl/net/basic-conversions/docx-to-rtf/
---

In deze stapsgewijze zelfstudie laten we u zien hoe u Aspose.Words voor .NET kunt gebruiken om een Word-document in Docx-indeling naar RTF te converteren. We leggen de meegeleverde C#-broncode uit en laten u zien hoe u deze in uw eigen projecten kunt implementeren.

 Om aan de slag te gaan, moet u ervoor zorgen dat Aspose.Words voor .NET is geïnstalleerd en ingesteld in uw ontwikkelomgeving. Als u dit nog niet hebt gedaan, downloadt en installeert u de bibliotheek van[Aspose.Releases]https://releases.aspose.com/words/net/.

## Stap 1: Het document uit Stream lezen

Open eerst een stream om het Docx-document te lezen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Stream stream = File.OpenRead(MyDir + "Document.docx");
```

## Stap 2: Het document laden

Laad vervolgens het document uit de stream:

```csharp
Document doc = new Document(stream);
```

## Stap 3: De stream sluiten

Omdat het document in het geheugen is geladen, kunt u de stream sluiten:

```csharp
stream.Close();
```

## Stap 4: Bewerkingen op het document uitvoeren

Op dit punt kunt u alle gewenste bewerkingen op het document uitvoeren.

## Stap 5: Het document opslaan in RTF-formaat

Om het document in RTF-indeling op te slaan, slaat u het op in een geheugenstroom:

```csharp
MemoryStream dstStream = new MemoryStream();
doc.Save(dstStream, SaveFormat.Rtf);
```

## Stap 6: De stream terugspoelen

Voordat u de geheugenstroom naar een bestand schrijft, moet u de positie ervan terugspoelen naar nul:

```csharp
dstStream.Position = 0;
```

## Stap 7: De stream naar bestand schrijven

Schrijf ten slotte de geheugenstroom naar een RTF-bestand:

```csharp
File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
```

Dat is het! U hebt met succes een Word-document in Docx-indeling naar RTF geconverteerd met Aspose.Words voor .NET.

### Voorbeeldbroncode voor Docx To Rtf met Aspose.Words voor .NET

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Alleen-lezen toegang is voldoende voor Aspose.Words om een document te laden.
	Stream stream = File.OpenRead(MyDir + "Document.docx");

	Document doc = new Document(stream);
	// U kunt de stream nu sluiten. Deze is niet langer nodig omdat het document in het geheugen staat.
	stream.Close();

	// ...doe iets met het document.

	// Converteer het document naar een ander formaat en sla het op om te streamen.
	MemoryStream dstStream = new MemoryStream();
	doc.Save(dstStream, SaveFormat.Rtf);

	// Spoel de streampositie terug naar nul, zodat deze klaar is voor de volgende lezer.
	dstStream.Position = 0;

	File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
	
```

U kunt deze code gerust in uw eigen projecten gebruiken en aanpassen aan uw specifieke vereisten.

### Veelgestelde vragen

#### Hoe kan ik een DOCX-bestand naar RTF-formaat converteren?

Om een DOCX-bestand naar RTF-formaat te converteren, kunt u verschillende softwaretools of bibliotheken gebruiken die deze functionaliteit bieden. Eén zo'n betrouwbaar hulpmiddel is Aspose.Words voor .NET. Het biedt een eenvoudige en efficiënte manier om DOCX-bestanden programmatisch naar RTF-formaat te converteren. U kunt de API van de bibliotheek gebruiken om het DOCX-bestand te laden en op te slaan in het gewenste RTF-formaat.

#### Zijn er beperkingen aan het conversieproces?

De beperkingen van het conversieproces zijn afhankelijk van de specifieke tool of bibliotheek die u gebruikt. Sommige tools kunnen beperkingen hebben op de grootte of complexiteit van het invoerdocument. Het is belangrijk om een tool te kiezen die aan de vereisten van uw conversietaak kan voldoen.

#### Kan ik de opmaak en lay-out van het originele document behouden?

Ja, met Aspose.Words kunt u de opmaak en lay-out van het originele document behouden tijdens het conversieproces. Aspose.Words voor .NET biedt bijvoorbeeld uitgebreide ondersteuning voor het behouden van de opmaak, stijlen en andere elementen van het DOCX-bestand in het geconverteerde RTF-document.

#### Is Aspose een betrouwbaar hulpmiddel voor DOCX naar RTF-conversie?

Ja, Aspose.Words voor .NET is een zeer betrouwbare tool voor DOCX naar RTF-conversie. Het wordt veel gebruikt door ontwikkelaars en bedrijven over de hele wereld vanwege de robuuste functies en uitstekende prestaties. De bibliotheek biedt uitgebreide documentatie, regelmatige updates en toegewijde technische ondersteuning, waardoor het een betrouwbare keuze is voor documentconversietaken.