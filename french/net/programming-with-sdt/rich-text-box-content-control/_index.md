---
title: Contrôle du contenu de la zone de texte enrichi
linktitle: Contrôle du contenu de la zone de texte enrichi
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à créer un contrôle de contenu de zone de texte enrichi dans un document Word à l'aide d'Aspose.Words pour .NET permettant la mise en forme et le style du texte.
type: docs
weight: 10
url: /fr/net/programming-with-sdt/rich-text-box-content-control/
---

Ce didacticiel montre comment créer un contrôle de contenu de zone de texte enrichi dans un document Word à l'aide de Aspose.Words pour .NET. Les contrôles de contenu de zone de texte enrichi permettent aux utilisateurs de saisir et de formater du texte avec différents styles et options de formatage.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et travail avec des documents Word.

## Étape 1 : Configurer le répertoire de documents
 Commencez par configurer le chemin d'accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"`avec le chemin d'accès réel au répertoire où vous souhaitez enregistrer le document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Créer un document et une balise StructuredDocumentTag
 Créez une nouvelle instance de`Document` classe et une`StructuredDocumentTag` pour représenter le contrôle du contenu de la zone de texte enrichi. Spécifier`SdtType.RichText` comme type et`MarkupLevel.Block` comme niveau de balisage pour créer une zone de texte enrichi au niveau du bloc.

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## Étape 3 : créer et mettre en forme le contenu en texte enrichi
Créez un paragraphe et exécutez-le pour représenter le contenu du texte enrichi. Définissez le texte et les options de mise en forme telles que la couleur, la police, etc.

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## Étape 4 : Ajoutez le contenu de texte enrichi au contrôle de contenu
Ajoutez le paragraphe avec le contenu de texte enrichi à la`ChildNodes` collection du contrôle de contenu de la zone de texte enrichi.

```csharp
sdtRichText.ChildNodes.Add(para);
```

## Étape 5 : Ajouter le contrôle de contenu au document
 Ajoutez le contrôle de contenu de la zone de texte enrichi au corps du document à l'aide de la`AppendChild` méthode du corps de la première section du document.

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## Étape 6 : Enregistrer le document
 Enregistrez le document dans le répertoire spécifié à l'aide de la`Save` méthode. Indiquez le nom de fichier souhaité avec l'extension de fichier appropriée. Dans cet exemple, nous enregistrons le document sous "WorkingWithSdt.RichTextBoxContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### Exemple de code source pour le contrôle du contenu de la zone de texte enrichi à l'aide de Aspose.Words pour .NET 

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

C'est ça! Vous avez créé avec succès un contrôle de contenu de zone de texte enrichi dans votre document Word à l'aide de Aspose.Words pour .NET.