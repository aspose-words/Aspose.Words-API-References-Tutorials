---
title: Persoonlijke gegevens verwijderen
linktitle: Persoonlijke gegevens verwijderen
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het verwijderen van persoonlijke gegevens uit een document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-document-properties/remove-personal-information/
---

In deze zelfstudie leiden we u door de C#-broncode om persoonlijke gegevens uit een document te verwijderen met Aspose.Words voor .NET. Met deze functie kunt u gevoelige persoonlijke informatie uit een document verwijderen, zoals identificatiegegevens van de auteur.

## Stap 1: Projectconfiguratie

Maak om te beginnen een nieuw C#-project in uw favoriete IDE. Zorg ervoor dat er in uw project naar de Aspose.Words voor .NET-bibliotheek wordt verwezen.

## Stap 2: Het document laden

In deze stap uploaden we het Word-document waaruit we de persoonlijke gegevens willen verwijderen. Gebruik de volgende code om het document te laden:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };
```

 Vervangen`"YOUR DOCUMENTS DIRECTORY"` met het daadwerkelijke pad van de map waar uw document zich bevindt.

## Stap 3: Persoonlijke gegevens verwijderen

 Nu zullen we de verwijdering van persoonlijke informatie inschakelen door de`RemovePersonalInformation`eigendom aan`true`. Gebruik de volgende code:

```csharp
doc.RemovePersonalInformation = true;
```

Deze code activeert het verwijderen van persoonlijke gegevens in het document.

## Stap 4: Het document opslaan

Ten slotte slaan we het document op, waarbij de persoonlijke gegevens zijn verwijderd. Gebruik de volgende code:

```csharp
doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
```

Met deze code wordt het document met de verwijderde persoonlijke gegevens opgeslagen in een nieuw bestand.

### Voorbeeldbroncode voor het verwijderen van persoonlijke gegevens met Aspose.Words voor .NET

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };

	doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
	
```

 Zorg ervoor dat u het juiste documentpad opgeeft in het`dataDir` variabel.

hebt nu geleerd hoe u persoonlijke gegevens uit een document kunt verwijderen met Aspose.Words voor .NET. Door de stapsgewijze handleiding in deze zelfstudie te volgen, kunt u eenvoudig gevoelige informatie uit uw eigen documenten verwijderen.