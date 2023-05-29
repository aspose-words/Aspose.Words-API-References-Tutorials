---
title: Docx à Txt
linktitle: Docx à Txt
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à convertir des documents Word de Docx en texte brut (Txt) à l'aide d'Aspose.Words pour .NET. Tutoriel étape par étape avec un exemple de code source.
type: docs
weight: 10
url: /fr/net/basic-conversions/docx-to-txt/
---

Dans ce didacticiel étape par étape, nous vous expliquerons comment utiliser Aspose.Words pour .NET pour convertir un document Word au format Docx en texte brut (Txt). Nous vous expliquerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets.

Pour commencer, assurez-vous que Aspose.Words pour .NET est installé et configuré dans votre environnement de développement. Si vous ne l'avez pas encore fait, téléchargez et installez la bibliothèque depuis le site officiel.

## Étape 1 : Initialisation de l'objet Document

 Tout d'abord, initialisez le`Document` object avec le chemin vers votre document source au format Docx :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## Étape 2 : Enregistrer le document au format Txt

 Ensuite, enregistrez le document au format texte brut (Txt) en appelant le`Save` méthode sur la`Document` objet et en fournissant le chemin et le nom du fichier pour le document Txt de sortie :

```csharp
doc.Save(dataDir + "BaseConversions.DocxToTxt.txt");
```

C'est ça! Vous avez converti avec succès un document Word au format Docx en texte brut (Txt) à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour Docx To Txt en utilisant Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	doc.Save(dataDir + "BaseConversions.DocxToTxt.txt");

```

N'hésitez pas à utiliser ce code dans vos propres projets et à le modifier en fonction de vos besoins spécifiques.