---
title: PDF à Docx
linktitle: PDF à Docx
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à convertir des documents PDF au format Docx en utilisant Aspose.Words pour .NET. Tutoriel étape par étape avec un exemple de code source.
type: docs
weight: 10
url: /fr/net/basic-conversions/pdf-to-docx/
---

Dans ce didacticiel étape par étape, nous vous expliquerons comment utiliser Aspose.Words pour .NET pour convertir un document PDF au format Docx. Nous vous expliquerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets.

Pour commencer, assurez-vous que Aspose.Words pour .NET est installé et configuré dans votre environnement de développement. Si vous ne l'avez pas encore fait, téléchargez et installez la bibliothèque depuis le site officiel.

## Étape 1 : Initialisation de l'objet document

 Tout d'abord, initialisez le`Document` objet en fournissant le chemin d'accès à votre document PDF :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Pdf Document.pdf");
```

## Étape 2 : Enregistrer le document au format Docx

 Ensuite, enregistrez le document au format Docx en appelant le`Save` méthode sur la`Document`objet et en fournissant le chemin et le nom du fichier pour le document Docx de sortie :

```csharp
doc.Save(dataDir + "BaseConversions.PdfToDocx.docx");
```

C'est ça! Vous avez réussi à convertir un document PDF au format Docx en utilisant Aspose.Words pour .NET.

### Exemple de code source pour Pdf To Docx en utilisant Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Pdf Document.pdf");

	doc.Save(dataDir + "BaseConversions.PdfToDocx.docx");
	
```

N'hésitez pas à utiliser ce code dans vos propres projets et à le modifier en fonction de vos besoins spécifiques.