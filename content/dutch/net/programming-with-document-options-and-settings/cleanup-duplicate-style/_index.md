---
title: Dubbele stijl opruimen
linktitle: Dubbele stijl opruimen
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding om dubbele stijlen in een document op te ruimen met Aspose.Words voor .NET. Volledige broncode inbegrepen.
type: docs
weight: 10
url: /nl/net/programming-with-document-options-and-settings/cleanup-duplicate-style/
---

In deze zelfstudie leiden we u stap voor stap door de C#-broncode om dubbele stijlen op te ruimen met Aspose.Words voor .NET. Deze functie helpt bij het verwijderen van dubbele stijlen uit een document.

## Stap 1: Projectconfiguratie

Maak om te beginnen een nieuw C#-project in uw favoriete IDE. Zorg ervoor dat er in uw project naar de Aspose.Words voor .NET-bibliotheek wordt verwezen.

## Stap 2: Het document laden

In deze stap laden we het Word-document dat we willen opruimen. Gebruik de volgende code om het document te laden:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Vervangen`"YOUR DOCUMENTS DIRECTORY"` met het daadwerkelijke pad van de map waar uw document zich bevindt.

## Stap 3: Tel stijlen voordat u gaat schoonmaken

Voordat we verder gaan met het opschonen, tellen we het aantal stijlen dat in het document aanwezig is. Gebruik de volgende code om het aantal stijlen weer te geven:

```csharp
Console.WriteLine(doc.Styles.Count);
```

Deze verklaring geeft het aantal stijlen weer dat in het document aanwezig is.

## Stap 4: Ruim dubbele stijlen op

Laten we nu dubbele stijlen uit het document opruimen. Gebruik de volgende code om het opschonen uit te voeren:

```csharp
CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
doc. Cleanup(options);
```

 Deze code ruimt dubbele stijlen uit het document op met behulp van de opgegeven opties. In dit voorbeeld hebben we de`DuplicateStyle` optie om dubbele stijlen op te ruimen.

## Stap 5: Tel de stijlen na het schoonmaken

Na het schoonmaken tellen we het aantal stijlen opnieuw om te controleren of het is afgenomen. Gebruik de volgende code om het aantal nieuwe stijlen weer te geven:

```csharp
Console.WriteLine(doc.Styles.Count);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
```

Deze verklaring geeft het aantal resterende stijlen weer na het reinigen.

### Voorbeeldbroncode voor het opschonen van dubbele stijl met Aspose.Words voor .NET

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Aantal stijlen vóór Opschonen.
	Console.WriteLine(doc.Styles.Count);

	// Verwijdert dubbele stijlen uit het document.
	CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
	doc.Cleanup(options);

	// Het aantal stijlen na het opruimen is verlaagd.
	Console.WriteLine(doc.Styles.Count);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");

```