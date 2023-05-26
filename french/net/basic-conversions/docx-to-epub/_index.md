---
title: Docx vers Epub
linktitle: Docx vers Epub
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à convertir des documents Word du format Docx au format Epub en utilisant Aspose.Words pour .NET. Tutoriel étape par étape avec un exemple de code source.
type: docs
weight: 10
url: /fr/net/basic-conversions/docx-to-epub/
---

Dans ce didacticiel étape par étape, nous vous expliquerons comment utiliser Aspose.Words pour .NET pour convertir un document Word au format Docx au format Epub. Nous vous expliquerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets.

Pour commencer, assurez-vous que Aspose.Words pour .NET est installé et configuré dans votre environnement de développement. Si vous ne l'avez pas encore fait, téléchargez et installez la bibliothèque depuis le site officiel.

## Étape 1 : Initialisation de l'objet document

 Tout d'abord, vous devez initialiser le`Document` objet en fournissant le chemin d'accès à votre document source au format Docx. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel du répertoire où se trouve votre document, et`"Document.docx"` avec le nom de votre document source. Voici l'extrait de code :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Étape 2 : Conversion du document au format Epub

 Ensuite, vous pouvez poursuivre le processus de conversion. Appeler le`Save` méthode sur la`Document` objet et indiquez le chemin et le nom de fichier du document de sortie au format Epub. Dans cet exemple, nous allons l'enregistrer sous`"BaseConversions.DocxToEpub.epub"`. Voici l'extrait de code :

```csharp
doc.Save(dataDir + "BaseConversions.DocxToEpub.epub");
```

C'est ça! Vous avez converti avec succès un document Word au format Docx au format Epub en utilisant Aspose.Words pour .NET.

### Exemple de code source pour Docx To Epub en utilisant Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.Save(dataDir + "BaseConversions.DocxToEpub.epub");

```

N'hésitez pas à utiliser ce code dans vos propres projets et à le modifier en fonction de vos besoins spécifiques.