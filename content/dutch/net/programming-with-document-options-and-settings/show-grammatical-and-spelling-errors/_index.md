---
title: Toon grammaticale en spelfouten
linktitle: Toon grammaticale en spelfouten
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding om grammatica- en spelfouten in een document weer te geven met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-document-options-and-settings/show-grammatical-and-spelling-errors/
---

In deze zelfstudie leiden we u door de C#-broncode om de weergave van grammaticale en spelfouten met Aspose.Words voor .NET mogelijk te maken. Met deze functie kunt u grammaticale en spelfouten in een document bekijken.

## Stap 1: Projectconfiguratie

Maak om te beginnen een nieuw C#-project in uw favoriete IDE. Zorg ervoor dat er in uw project naar de Aspose.Words voor .NET-bibliotheek wordt verwezen.

## Stap 2: Het document laden

In deze stap laden we het Word-document waarvoor we grammatica- en spelfouten willen weergeven. Gebruik de volgende code om het document te laden:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Vervangen`"YOUR DOCUMENTS DIRECTORY"` met het daadwerkelijke pad van de map waar uw document zich bevindt.

## Stap 3: Foutweergave inschakelen

Nu zullen we de weergave van grammaticale en spelfouten in het document inschakelen. Gebruik de volgende code om de foutweergave in te schakelen:

```csharp
doc. ShowGrammaticalErrors = true;
doc. ShowSpellingErrors = true;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");
```

Deze code maakt de weergave van grammaticale fouten mogelijk (`ShowGrammaticalErrors`) en spelfouten (`ShowSpellingErrors`) in het document.

### Voorbeeldbroncode voor Grammaticale en Spellingsfouten weergeven met Aspose.Words voor .NET

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.ShowGrammaticalErrors = true;
	doc.ShowSpellingErrors = true;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");

```

 Zorg ervoor dat u het juiste documentpad opgeeft in het`dataDir` variabel.

U hebt nu geleerd hoe u de weergave van grammaticale en spelfouten in een document kunt inschakelen met behulp van Aspose.Words voor .NET. Door de stapsgewijze handleiding in deze zelfstudie te volgen, kunt u deze functie eenvoudig in uw eigen documenten inschakelen.