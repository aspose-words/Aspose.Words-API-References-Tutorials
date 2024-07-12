---
title: Contrôle du contenu de la zone de texte enrichi
linktitle: Contrôle du contenu de la zone de texte enrichi
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment créer un contrôle de contenu de zone de texte enrichi dans un document Word à l'aide d'Aspose.Words for .NET, permettant le formatage et le style du texte.
type: docs
weight: 10
url: /fr/net/programming-with-sdt/rich-text-box-content-control/
---

Ce didacticiel montre comment créer un contrôle de contenu de zone de texte enrichi dans un document Word à l'aide d'Aspose.Words pour .NET. Les contrôles de contenu des zones de texte enrichi permettent aux utilisateurs de saisir et de formater du texte avec différents styles et options de formatage.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et du traitement de mots avec des documents Word.

## Étape 1 : configurer le répertoire de documents
 Commencez par configurer le chemin d’accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"`avec le chemin réel du répertoire dans lequel vous souhaitez enregistrer le document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Créer un document et un StructuredDocumentTag
 Créez une nouvelle instance du`Document` classe et un`StructuredDocumentTag` pour représenter le contrôle de contenu de la zone de texte enrichi. Spécifier`SdtType.RichText` comme le type et`MarkupLevel.Block` comme niveau de balisage pour créer une zone de texte enrichi au niveau du bloc.

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## Étape 3 : Créer et formater le contenu de texte enrichi
Créez un paragraphe et exécutez-le pour représenter le contenu du texte enrichi. Définissez le texte et les options de formatage telles que la couleur, la police, etc.

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## Étape 4 : ajouter le contenu de texte enrichi au contrôle de contenu
 Ajoutez le paragraphe avec le contenu en texte enrichi au`ChildNodes` collection du contrôle de contenu de la zone de texte enrichi.

```csharp
sdtRichText.ChildNodes.Add(para);
```

## Étape 5 : ajouter le contrôle de contenu au document
 Ajoutez le contrôle de contenu de la zone de texte enrichi au corps du document à l'aide de l'option`AppendChild` méthode du corps de la première section du document.

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## Étape 6 : Enregistrez le document
 Enregistrez le document dans le répertoire spécifié à l'aide du`Save` méthode. Fournissez le nom de fichier souhaité avec l'extension de fichier appropriée. Dans cet exemple, nous enregistrons le document sous le nom « WorkingWithSdt.RichTextBoxContentControl.docx ».

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### Exemple de code source pour le contrôle de contenu de zone de texte enrichi à l'aide d'Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
	Paragraph para = new Paragraph(doc);
	Run run = new Run(doc);
	run.Text = "Hello World";
	run.Font.Color = Color.Green;
	para.Runs.Add(run);
	sdtRichText.ChildNodes.Add(para);
	doc.FirstSection.Body.AppendChild(sdtRichText);
	doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

C'est ça! Vous avez créé avec succès un contrôle de contenu de zone de texte enrichi dans votre document Word à l'aide d'Aspose.Words pour .NET.