---
title: Document invoegen bij samenvoegen
linktitle: Document invoegen bij samenvoegen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een document in een ander document kunt invoegen tijdens het samenvoegen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/clone-and-combine-documents/insert-document-at-mail-merge/
---
In deze zelfstudie laten we u zien hoe u tijdens het samenvoegen een document in een ander document kunt invoegen met behulp van de functie Document invoegen tijdens samenvoegen van Aspose.Words voor .NET. Volg de onderstaande stappen om de broncode te begrijpen en het document in te voegen.

## Stap 1: Het hoofddocument laden

Om te beginnen geeft u de directory voor uw documenten op en laadt u het hoofddocument in een Document-object. Hier is hoe:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Stap 2: Configureer Afdruk samenvoegen

Laten we nu de samenvoegbewerking configureren en de callback voor het samenvoegen van velden opgeven om een document in een ander document in te voegen. Hier is hoe:

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## Stap 3: Het samenvoegen uitvoeren

We voeren de samenvoegbewerking uit door de namen van de samenvoegvelden en de bijbehorende gegevens op te geven. Hier is hoe:

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

### Voorbeeldbroncode voor Document invoegen bij Afdruk samenvoegen met Aspose.Words voor .NET

Hier is de volledige broncode voor de functie Document invoegen in Mail Merge van Aspose.Words voor .NET:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
// Het hoofddocument bevat een samenvoegveld met de naam "Document_1".
// De overeenkomstige gegevens voor dit veld bevatten een volledig gekwalificeerd pad naar het document.
// Dat moet in dit veld worden ingevoegd.
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });

mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

Met deze code kunt u tijdens het samenvoegen een document in een ander document invoegen met behulp van Aspose.Words voor .NET. Het resulterende document wordt onder een nieuwe naam opgeslagen


## Conclusie

In deze zelfstudie hebben we onderzocht hoe u een document in een ander document kunt invoegen tijdens het samenvoegen met behulp van de functie Document invoegen tijdens het samenvoegen van Aspose.Words voor .NET. Door de samenvoegbewerking te configureren en de benodigde gegevens op te geven, kunt u documenten dynamisch samenstellen door verschillende documentsjablonen of secties samen te voegen. Aspose.Words voor .NET biedt een flexibele en krachtige manier om complexe scenario's voor het genereren van documenten te beheren, waardoor het een waardevol hulpmiddel is voor het automatiseren van taken voor het maken en manipuleren van documenten.

### Veelgestelde vragen

#### Vraag: Wat is het doel van het invoegen van een document in een ander document tijdens het samenvoegen?

A: Als u tijdens het samenvoegen een document in een ander document invoegt, kunt u verschillende documentsjablonen of secties dynamisch combineren op basis van de gegevens die tijdens het samenvoegproces worden verstrekt. Deze functie is vooral handig als u complexe documenten wilt samenstellen door verschillende vooraf gedefinieerde sjablonen of secties samen te voegen tot een definitief document.

#### Vraag: Hoe voeg ik een document in een ander document in tijdens het samenvoegen met Aspose.Words voor .NET?

A: Volg deze stappen om een document in een ander document in te voegen tijdens het samenvoegen met Aspose.Words voor .NET:
1. Laad het hoofddocument dat als basis zal dienen in een Document-object.
2. Configureer de samenvoegbewerking en specificeer de terugroepactie voor het samenvoegen van velden om het invoegen van documenten af te handelen.
3. Voer de samenvoegbewerking uit met de namen van de samenvoegvelden en de bijbehorende gegevens (pad naar het in te voegen document).

#### Vraag: Hoe kan ik het invoeggedrag tijdens het samenvoegen aanpassen?

A: Om het invoeggedrag tijdens het samenvoegen aan te passen, kunt u een aangepaste FieldMergingCallback implementeren door deze over te nemen van de IFieldMergingCallback-interface. Hierdoor kunt u bepalen hoe de documenten worden ingevoegd en samengevoegd op basis van uw specifieke vereisten.

#### Vraag: Kan ik meerdere documenten invoegen tijdens het samenvoegen?

A: Ja, u kunt meerdere documenten invoegen tijdens het samenvoegen door de juiste gegevens voor elk samenvoegveld op te geven. Voor elk samenvoegveld waarvoor documentinvoeging vereist is, geeft u het pad naar het overeenkomstige document op als gegevens.


