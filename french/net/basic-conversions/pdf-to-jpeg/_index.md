---
title: Pdf à Jpeg
linktitle: Pdf à Jpeg
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à convertir des documents PDF en images JPEG à l'aide d'Aspose.Words pour .NET. Tutoriel étape par étape avec un exemple de code source.
type: docs
weight: 10
url: /fr/net/basic-conversions/pdf-to-jpeg/
---

Dans ce didacticiel étape par étape, nous vous expliquerons comment utiliser Aspose.Words pour .NET pour convertir un document PDF en images JPEG. Nous vous expliquerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets.

Pour commencer, assurez-vous que Aspose.Words pour .NET est installé et configuré dans votre environnement de développement. Si vous ne l'avez pas encore fait, téléchargez et installez la bibliothèque depuis le site officiel.

## Étape 1 : Initialisation de l'objet Document

 Tout d'abord, initialisez le`Document` objet en fournissant le chemin d'accès à votre document PDF :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Pdf Document.pdf");
```

## Étape 2 : Enregistrer le document en tant qu'images JPEG

 Ensuite, enregistrez le document sous forme d'images Jpeg en appelant le`Save` méthode sur la`Document` objet et en fournissant le chemin et le nom du fichier pour les images Jpeg de sortie :

```csharp
doc.Save(dataDir + "BaseConversions.PdfToJpeg.jpeg");
```

C'est ça! Vous avez converti avec succès un document PDF en images Jpeg à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour Pdf To Jpeg en utilisant Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Pdf Document.pdf");

	doc.Save(dataDir + "BaseConversions.PdfToJpeg.jpeg");

```

N'hésitez pas à utiliser ce code dans vos propres projets et à le modifier en fonction de vos besoins spécifiques.