---
title: Ruim ongebruikte stijlen en lijsten op
linktitle: Ruim ongebruikte stijlen en lijsten op
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het opschonen van ongebruikte stijlen en lijsten in een document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-document-options-and-settings/cleanup-unused-styles-and-lists/
---

In deze zelfstudie leiden we u door de C#-broncode om ongebruikte stijlen en lijsten op te ruimen met Aspose.Words voor .NET. Met deze functie kunt u stijlen en lijsten verwijderen die niet in een document worden gebruikt.

## Stap 1: Projectconfiguratie

Maak om te beginnen een nieuw C#-project in uw favoriete IDE. Zorg ervoor dat er in uw project naar de Aspose.Words voor .NET-bibliotheek wordt verwezen.

## Stap 2: Het document laden

In deze stap laden we het Word-document met de ongebruikte stijlen en lijsten die we willen opruimen. Gebruik de volgende code om het document te laden:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Unused styles.docx");
```

 Vervangen`"YOUR DOCUMENTS DIRECTORY"` met het daadwerkelijke pad van de map waar uw document zich bevindt.

## Stap 3: Tel stijlen en lijsten voordat u gaat schoonmaken

Voordat we het document opschonen, tellen we het aantal stijlen en lijsten dat in het document aanwezig is. Gebruik de volgende code om de tellers weer te geven:

```csharp
Console.WriteLine($"Number of styles before cleaning: {doc.Styles.Count}\n" +
$"Number of lists before cleaning: {doc.Lists.Count}");
```

Deze instructies tonen het aantal stijlen en lijsten dat in het document aanwezig is vóór het opschonen.

## Stap 4: Ruim ongebruikte stijlen en lijsten op

Laten we nu ongebruikte stijlen en lijsten uit het document opruimen. Gebruik de volgende code om het opschonen uit te voeren:

```csharp
CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
doc. Cleanup(cleanupOptions);
```

 Deze code ruimt ongebruikte stijlen en lijsten uit het document op met behulp van de opgegeven opties. In dit voorbeeld hebben we de`UnusedStyles` optie om ongebruikte stijlen te verwijderen en de`UnusedLists` optie om de lijsten te behouden, zelfs als ze niet worden gebruikt.

## Stap 5: Tel stijlen en lijsten na het schoonmaken

Nadat we het opruimen hebben uitgevoerd, tellen we de stijlen en lijsten opnieuw om te controleren of ze zijn samengevouwen. Gebruik de volgende code om de nieuwe tellers weer te geven:

```csharp
Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
				  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
```

Deze instructies tonen het aantal stijlen en lijsten dat overblijft na het schoonmaken.

### Voorbeeldbroncode voor het opschonen van ongebruikte stijlen en lijsten met Aspose.Words voor .NET

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Unused styles.docx");

	// Gecombineerd met de ingebouwde stijlen heeft het document nu acht stijlen.
	// Een aangepaste stijl wordt gemarkeerd als 'gebruikt' terwijl er tekst in het document aanwezig is
	// in die stijl opgemaakt. Dit betekent dat de 4 stijlen die we hebben toegevoegd momenteel ongebruikt zijn.
	Console.WriteLine($"Count of styles before Cleanup: {doc.Styles.Count}\n" +
					  $"Count of lists before Cleanup: {doc.Lists.Count}");

	//Reinigt ongebruikte stijlen en lijsten uit het document, afhankelijk van de opgegeven CleanupOptions.
	CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
	doc.Cleanup(cleanupOptions);

	Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
					  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
    
```

 Zorg ervoor dat u het juiste documentpad opgeeft in het`dataDir` variabel.

U hebt nu geleerd hoe u ongebruikte stijlen en lijsten uit een document kunt opschonen met Aspose.Words voor .NET. Door de stapsgewijze handleiding in deze zelfstudie te volgen, kunt u deze functie eenvoudig op uw eigen documenten toepassen.

