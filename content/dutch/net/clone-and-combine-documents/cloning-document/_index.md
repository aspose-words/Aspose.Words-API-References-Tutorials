---
title: Kloon een Word-document
linktitle: Kloon een Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een Word-document kunt klonen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/clone-and-combine-documents/cloning-document/
---
In deze zelfstudie gaan we u vertellen hoe u een Word-document kunt klonen met behulp van de kloonfunctie van Aspose.Words voor .NET. Volg de onderstaande stappen om de broncode te begrijpen en een exacte kopie van een bestaand document te maken.

## Stap 1: Het document laden

Om te beginnen geeft u uw documentmap op en laadt u het bestaande document in een Document-object. Hier is hoe:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## Stap 2: Kloon het document

Nu gaan we het document klonen en er een exacte kopie van maken. Hier is hoe:

```csharp
Document clone = doc.Clone();
clone.Save(dataDir + "CloneAndCombineDocuments.ClonageDocument.docx");
```

### Voorbeeldbroncode voor het klonen van documenten met Aspose.Words voor .NET

Hier is de volledige broncode voor de Aspose.Words-documentkloonfunctie voor .NET:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";            
Document doc = new Document(MyDir + "Document.docx");

Document clone = doc.Clone();
clone.Save(dataDir + "CloneAndCombineDocuments.CloningDocument.docx");
```

Met deze code kun je een Word-document klonen met Aspose.Words voor .NET. De exacte kopie van het document wordt opgeslagen onder een nieuwe bestandsnaam.


## Conclusie

In deze zelfstudie hebben we onderzocht hoe u een Word-document kunt klonen met behulp van de kloonfunctie van Aspose.Words voor .NET. Door een bestaand document te laden en een kloon te maken, kunt u een exacte kopie van het document maken zonder het origineel te wijzigen. Deze functionaliteit is waardevol wanneer u onafhankelijke bewerkingen op een document moet uitvoeren zonder het bronbestand te beïnvloeden. Aspose.Words voor .NET biedt een eenvoudige manier om documenten te klonen, waardoor het gemakkelijk wordt om programmatisch met Word-documenten te werken en documentversies effectief te beheren.

### Veelgestelde vragen over het klonen van een Word-document

#### Vraag: Wat is het doel van het klonen van een Word-document met Aspose.Words voor .NET?

A: Door een Word-document te klonen met Aspose.Words voor .NET kunt u een exacte kopie van een bestaand document maken. Deze functie is vooral handig als u de inhoud en opmaak van het originele document wilt behouden terwijl u een nieuwe versie maakt of verdere wijzigingen uitvoert zonder het originele bestand te beïnvloeden.

#### Vraag: Hoe kloon ik een Word-document met Aspose.Words voor .NET?

A: Volg deze stappen om een Word-document te klonen met Aspose.Words voor .NET:
1.  Laad het bestaande document in een Document-object met behulp van`Document doc = new Document("file_path")`.
2.  Kloon het document met`Document clone = doc.Clone()`.
3.  Sla het gekloonde document op in een nieuw bestand met behulp van`clone.Save("new_file_path")`.

#### Vraag: Kan ik het gekloonde document wijzigen zonder het originele document te beïnvloeden?

A: Ja, het gekloonde document is een afzonderlijk exemplaar van het originele document en wijzigingen die aan de kloon worden aangebracht, hebben geen invloed op het originele document. Hierdoor kunt u het gekloonde document veilig manipuleren zonder het brondocument te wijzigen.

#### Vraag: Is het mogelijk om meerdere documenten te klonen en deze te combineren tot één document?

A: Ja, u kunt meerdere documenten klonen met behulp van de kloonfunctie en deze indien nodig combineren tot één document. Door meerdere documenten te laden en te klonen, kunt u de inhoud ervan samenvoegen en een nieuw, verenigd document maken.