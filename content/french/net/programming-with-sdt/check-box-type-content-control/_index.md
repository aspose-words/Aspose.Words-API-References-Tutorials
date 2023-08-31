---
title: Contrôle du contenu du type de case à cocher
linktitle: Contrôle du contenu du type de case à cocher
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment créer un contrôle de contenu de type case à cocher dans un document Word à l’aide d’Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-sdt/check-box-type-content-control/
---

Ce didacticiel explique comment créer un contrôle de contenu de type case à cocher dans un document Word à l'aide d'Aspose.Words pour .NET. Les contrôles de contenu des cases à cocher permettent aux utilisateurs de sélectionner ou de décocher une case dans le document.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et du traitement de mots avec des documents Word.

## Étape 1 : configurer le répertoire de documents
 Commencez par configurer le chemin d’accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel du répertoire dans lequel vous souhaitez enregistrer le document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Créer un document et DocumentBuilder
 Créez une nouvelle instance du`Document` classe et un`DocumentBuilder` pour construire le contenu du document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : ajouter un contrôle de contenu de type case à cocher
 Créer un`StructuredDocumentTag` avec`SdtType.Checkbox` pour représenter le contrôle de contenu de la case à cocher. Spécifier`MarkupLevel.Inline` pour le placer dans le texte.

```csharp
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
builder.InsertNode(sdtCheckBox);
```

## Étape 4 : Enregistrez le document
 Enregistrez le document dans le répertoire spécifié à l'aide du`Save` méthode. Fournissez le nom de fichier souhaité avec l'extension de fichier appropriée. Dans cet exemple, nous enregistrons le document sous le nom « WorkingWithSdt.CheckBoxTypeContentControl.docx ».

```csharp
doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

### Exemple de code source pour le contrôle de contenu de type case à cocher à l'aide d'Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
	builder.InsertNode(sdtCheckBox);
	doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

C'est ça! Vous avez créé avec succès un contrôle de contenu de type case à cocher dans votre document Word à l’aide d’Aspose.Words pour .NET.