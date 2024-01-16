---
title: Vergelijk voor gelijk in Word-document
linktitle: Vergelijk voor gelijk in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding om de C#-broncode van Compare for Equals uit te leggen in de Word-documentfunctie met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/compare-documents/compare-for-equal/
---
In deze zelfstudie laten we u zien hoe u de functie Vergelijken voor gelijkheid in een Word-document kunt gebruiken met Aspose.Words voor .NET. Volg de onderstaande stappen om de broncode te begrijpen en de wijzigingen toe te passen.

## Stap 1: Documentvergelijking

 Laad om te beginnen twee documenten om te vergelijken. In dit voorbeeld gebruiken we de`Clone()` methode om een kopie van het originele document te maken. Hier is hoe:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document docA = new Document(dataDir + "Document.docx");
Document docB = docA.Clone();
```

## Stap 2: Documentvergelijking

 We zullen nu gebruik maken van de`Compare()` methode om de twee documenten te vergelijken. Deze methode markeert de wijzigingen in het originele document. Hier is hoe:

```csharp
// Vergelijk de documenten
docA.Compare(docB, "user", DateTime.Now);

// Controleer of de documenten gelijk zijn
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are identical": "Documents are not identical");
```

### Voorbeeldbroncode voor Compare For Equal met Aspose.Words voor .NET

Hier is de volledige broncode voor de functie Compare for Equals met Aspose.Words voor .NET:

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();
	
	// DocA bevat nu wijzigingen als revisies.
	docA.Compare(docB, "user", DateTime.Now);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

Met deze code kunt u twee documenten vergelijken en bepalen of ze hetzelfde zijn met behulp van Aspose.Words voor .NET.

## Conclusie

In deze zelfstudie hebben we onderzocht hoe u documenten kunt vergelijken op gelijkheid met behulp van de functie Compare for Equal van Aspose.Words voor .NET. Door twee documenten te vergelijken en de herzieningen te analyseren, kunt u bepalen of de documenten dezelfde inhoud hebben of dat er verschillen tussen de documenten bestaan. Aspose.Words voor .NET biedt krachtige mogelijkheden voor documentvergelijking, waardoor u het proces van het identificeren van overeenkomsten en verschillen tussen documenten kunt automatiseren.

### Veelgestelde vragen

#### Vraag: Wat is het doel van het vergelijken van documenten op gelijkheid in Aspose.Words voor .NET?

A: Door documenten op gelijkheid te vergelijken in Aspose.Words voor .NET kunt u vaststellen of twee documenten dezelfde inhoud hebben. Door de documenten met elkaar te vergelijken, kunt u bepalen of ze identiek zijn of dat er verschillen tussen zitten.

#### Vraag: Hoe vergelijk ik twee documenten op gelijkheid met Aspose.Words voor .NET?

A: Volg deze stappen om twee documenten op gelijkheid te vergelijken met Aspose.Words voor .NET:
1. Laad de twee documenten die u wilt vergelijken in afzonderlijke documentobjecten.
2.  Gebruik de`Compare()` methode op een van de documenten en geef het andere document op als parameter. Deze methode vergelijkt de documenten en markeert de wijzigingen in het originele document.
3.  Controleer de`Revisions` eigendom van het originele document. Als de telling nul is, betekent dit dat de documenten identiek zijn.

#### Vraag: Kan ik het vergelijkingsproces aanpassen of specifieke vergelijkingsopties bieden?

A: Ja, Aspose.Words voor .NET biedt verschillende opties om het vergelijkingsproces aan te passen. U kunt bepalen hoe de documenten worden vergeleken, vergelijkingsopties opgeven, zoals de vergelijkingsmethode, opmaakwijzigingen, of specifieke elementen negeren. Raadpleeg de Aspose.Words voor .NET-documentatie voor gedetailleerde informatie over het aanpassen van het vergelijkingsproces.

#### Vraag: Kan ik een meer gedetailleerde vergelijking uitvoeren om specifieke verschillen tussen documenten te identificeren?

A: Ja, u kunt een meer gedetailleerde vergelijking uitvoeren om specifieke verschillen tussen documenten te identificeren door de`Revisions` verzameling van het originele document. Elke revisie vertegenwoordigt een wijziging of verschil tussen de documenten. U hebt toegang tot de details van elke revisie, zoals het type wijziging (invoeging, verwijdering, opmaakwijziging) en het getroffen bereik van het document.