---
title: Maak een bladwijzer in een Word-document
linktitle: Maak een bladwijzer in een Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u bladwijzers in een Word-document kunt maken en voorbeeldniveaus van bladwijzers in een PDF kunt opgeven met behulp van Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-bookmarks/create-bookmark/
---

In dit artikel zullen we de bovenstaande C#-broncode verkennen om te begrijpen hoe u de functie Bladwijzer maken in de Aspose.Words voor .NET-bibliotheek kunt gebruiken. Met deze functie kunt u bladwijzers in een document maken en voorbeeldniveaus voor bladwijzers opgeven in een uitgevoerd PDF-bestand.

## Vereisten

- Basiskennis van de C#-taal.
- .NET-ontwikkelomgeving met Aspose.Words-bibliotheek geïnstalleerd.

## Stap 1: Het document en de generator maken

 Voordat we bladwijzers maken, moeten we een document en een documentbouwer maken met behulp van de`Document` En`DocumentBuilder` voorwerpen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: De hoofdbladwijzer maken

 Wij gebruiken de`StartBookmark` methode om een hoofdbladwijzer te starten en de`EndBookmark` methode om er een einde aan te maken. Tussendoor kunnen we tekst en andere bladwijzers toevoegen:

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

// Voeg hier meer bladwijzers of tekst toe.

builder. EndBookmark("My Bookmark");
```

## Stap 3: Geneste bladwijzers maken

 We kunnen ook geneste bladwijzers maken binnen een hoofdbladwijzer. Wij gebruiken hetzelfde`StartBookmark` En`EndBookmark` methoden om geneste bladwijzers te maken en te beëindigen:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## Stap 4: Voorvertoningsniveaus van bladwijzers opgeven in het uitgevoerde PDF-bestand

 Wij gebruiken de`PdfSaveOptions` object om de voorbeeldniveaus van de bladwijzers in het uitgevoerde PDF-bestand op te geven. Wij gebruiken de`BookmarksOutlineLevels` eigendom

  om hoofdbladwijzers en geneste bladwijzers met hun respectievelijke niveaus toe te voegen:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### Voorbeeldbroncode voor het maken van een bladwijzer met Aspose.Words voor .NET

Hier is de volledige voorbeeldbroncode om te demonstreren hoe u bladwijzers maakt met Aspose.Words voor .NET:

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartBookmark("My Bookmark");
	builder.Writeln("Text inside a bookmark.");

	builder.StartBookmark("Nested Bookmark");
	builder.Writeln("Text inside a NestedBookmark.");
	builder.EndBookmark("Nested Bookmark");

	builder.Writeln("Text after Nested Bookmark.");
	builder.EndBookmark("My Bookmark");

	PdfSaveOptions options = new PdfSaveOptions();
	options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
	options.OutlineOptions.BookmarksOutlineLevels.Add("Nested Bookmark", 2);

	doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
  
```

## Conclusie

In dit artikel hebben we de C#-broncode onderzocht om te begrijpen hoe u de Create Bookmark-functie van Aspose.Words voor .NET kunt gebruiken. We hebben een stapsgewijze handleiding gevolgd voor het maken van bladwijzers in een document en het opgeven van bladwijzervoorbeeldniveaus in een uitgevoerd PDF-bestand.

### Veelgestelde vragen

#### Vraag: Wat zijn de vereisten voor het gebruik van de functie "Bladwijzers maken" in Aspose.Words voor .NET?

A: Om de functie "Bladwijzers maken" in Aspose.Words voor .NET te gebruiken, moet u basiskennis van de taal C# hebben. U hebt ook een .NET-ontwikkelomgeving nodig waarin de Aspose.Words-bibliotheek is geïnstalleerd.

#### Vraag: Hoe maak ik een document in Aspose.Words voor .NET?

 A: Om een document in Aspose.Words voor .NET te maken, kunt u de`Document` klas. Hier is een voorbeeldcode:

```csharp
Document doc = new Document();
```

#### Vraag: Hoe maak ik een hoofdbladwijzer in een document met Aspose.Words voor .NET?

 A: Om een hoofdbladwijzer in een document te maken met Aspose.Words voor .NET, kunt u de`StartBookmark` methode om de bladwijzer te starten, tekst of andere bladwijzers toe te voegen en vervolgens de` EndBookmark` om er een einde aan te maken. Hier is een voorbeeldcode:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### Vraag: Hoe maak ik een geneste bladwijzer in een hoofdbladwijzer met Aspose.Words voor .NET?

 A: Om een geneste bladwijzer binnen een hoofdbladwijzer te maken met behulp van Aspose.Words voor .NET, kunt u dezelfde`StartBookmark` En`EndBookmark` methoden om de geneste bladwijzer te starten en te beëindigen. Hier is een voorbeeldcode:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

#### Vraag: Hoe kan ik de voorbeeldniveaus van bladwijzers opgeven in een uitvoer-PDF met Aspose.Words voor .NET?

 A: Om de voorbeeldniveaus van bladwijzers in een uitvoer-PDF op te geven met behulp van Aspose.Words voor .NET, kunt u de`PdfSaveOptions` klasse en de`BookmarksOutlineLevels` eigendom. U kunt hoofdbladwijzers en geneste bladwijzers met hun respectievelijke niveaus toevoegen. Hier is een voorbeeldcode:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
```

#### Vraag: Hoe kan ik een document opslaan nadat ik bladwijzers heb gemaakt met Aspose.Words voor .NET?

 A: Om een document op te slaan nadat u bladwijzers hebt gemaakt met Aspose.Words voor .NET, kunt u de`Save` werkwijze van de`Document` object dat het doelbestandspad specificeert. Hier is een voorbeeldcode:

```csharp
doc.Save("path/to/your/output-document.docx");
```

#### Vraag: Hoe kan ik de voorbeeldniveaus van bladwijzers opgeven in een uitvoer-PDF met Aspose.Words voor .NET?

 A: Om de voorbeeldniveaus van bladwijzers in een uitvoer-PDF op te geven met behulp van Aspose.Words voor .NET, kunt u de`PdfSaveOptions` klasse en de`BookmarksOutlineLevels` eigendom. U kunt hoofdbladwijzers en geneste bladwijzers met hun respectievelijke niveaus toevoegen. Hier is een voorbeeldcode:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save("path/to/your/output-pdf-file.pdf", options);
```

#### Vraag: Hoe kan ik geneste bladwijzers maken in een hoofdbladwijzer met Aspose.Words voor .NET?

 A: Om geneste bladwijzers binnen een hoofdbladwijzer te maken met Aspose.Words voor .NET, kunt u dezelfde`StartBookmark` En`EndBookmark` methoden om geneste bladwijzers te starten en te beëindigen. Zorg ervoor dat u de bovenliggende bladwijzer opgeeft als parameter bij het aanroepen van de`StartBookmark` methode. Hier is een voorbeeldcode:

```csharp
builder.StartBookmark("Main bookmark");
builder.Writeln("Text inside main bookmark.");

builder.StartBookmark("Nested bookmark 1");
builder.Writeln("Text inside first nested bookmark.");
builder.EndBookmark("Nested bookmark 1");

builder.StartBookmark("Nested bookmark 2");
builder.Writeln("Text inside second nested bookmark.");
builder.EndBookmark("Nested bookmark 2");

builder.EndBookmark("Main bookmark");
```

#### Vraag: Hoe kan ik tekst toevoegen aan een bladwijzer met Aspose.Words voor .NET?

 A: Om tekst toe te voegen aan een bladwijzer met Aspose.Words voor .NET, kunt u de`Write` werkwijze van de`DocumentBuilder`object dat de toe te voegen tekst specificeert. Hier is een voorbeeldcode:

```csharp
builder.StartBookmark("My Bookmark");
builder.Write("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### Vraag: Hoe maak ik een hoofdbladwijzer in een document met Aspose.Words voor .NET?

 A: Om een hoofdbladwijzer in een document te maken met Aspose.Words voor .NET, kunt u de`StartBookmark` methode om de bladwijzer te starten en de`EndBookmark` methode om er een einde aan te maken. Hier is een voorbeeldcode:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```