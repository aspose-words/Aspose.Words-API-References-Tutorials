---
title: Docx à Markdown
linktitle: Docx à Markdown
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à convertir des documents Word du format Docx au format Markdown en utilisant Aspose.Words pour .NET. Tutoriel étape par étape avec un exemple de code source.
type: docs
weight: 10
url: /fr/net/basic-conversions/docx-to-markdown/
---

Dans ce didacticiel étape par étape, nous vous expliquerons comment utiliser Aspose.Words pour .NET pour convertir un document Word au format Docx en Markdown. Nous vous expliquerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets.

Pour commencer, assurez-vous que Aspose.Words pour .NET est installé et configuré dans votre environnement de développement. Si vous ne l'avez pas encore fait, téléchargez et installez la bibliothèque depuis le site officiel.

## Étape 1 : Initialisation des objets Document et DocumentBuilder

 Tout d'abord, initialisez le`Document` objet et le`DocumentBuilder` objet:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Ajouter du contenu au document

 Ensuite, utilisez le`DocumentBuilder` objet pour ajouter du contenu au document. Dans cet exemple, nous allons ajouter un simple paragraphe de texte en utilisant la`Writeln` méthode:

```csharp
builder.Writeln("Some text!");
```

N'hésitez pas à ajouter du contenu plus complexe tel que des titres, des tableaux, des listes ou une mise en forme selon vos besoins.

## Étape 3 : Enregistrer le document au format Markdown

 Pour enregistrer le document au format Markdown, utilisez le`Save` méthode sur la`Document` objet et indiquez le chemin et le nom de fichier du document de sortie. Dans cet exemple, nous allons l'enregistrer sous`"BaseConversions.DocxToMarkdown.md"`:

```csharp
doc.Save(dataDir + "BaseConversions.DocxToMarkdown.md");
```

C'est ça! Vous avez converti avec succès un document Word au format Docx en Markdown à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour Docx To Markdown en utilisant Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Some text!");

	doc.Save(dataDir + "BaseConversions.DocxToMarkdown.md");

```

N'hésitez pas à utiliser ce code dans vos propres projets et à le modifier en fonction de vos besoins spécifiques.