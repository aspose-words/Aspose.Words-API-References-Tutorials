---
title: Txt à Docx
linktitle: Txt à Docx
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à convertir des fichiers texte brut (Txt) en documents Word (Docx) à l'aide d'Aspose.Words pour .NET. Tutoriel étape par étape avec un exemple de code.
type: docs
weight: 10
url: /fr/net/basic-conversions/txt-to-docx/
---

Dans ce didacticiel étape par étape, nous vous expliquerons comment utiliser Aspose.Words pour .NET pour convertir un fichier texte brut (Txt) en un document Word au format Docx. Nous vous expliquerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets.

Pour commencer, assurez-vous que Aspose.Words pour .NET est installé et configuré dans votre environnement de développement. Si vous ne l'avez pas encore fait, téléchargez et installez la bibliothèque depuis le site officiel.

## Étape 1 : Initialisation de l'objet Document

 Tout d'abord, initialisez le`Document` objet en fournissant le chemin d'accès à votre fichier texte :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "English text.txt");
```

## Étape 2 : Enregistrer le document au format Docx

 Ensuite, enregistrez le document au format Docx en appelant le`Save` méthode sur la`Document`objet et en fournissant le chemin et le nom du fichier pour le document Docx de sortie :

```csharp
doc.Save(dataDir + "BaseConversions.TxtToDocx.docx");
```

C'est ça! Vous avez converti avec succès un fichier texte brut (Txt) en un document Word au format Docx à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour Txt To Docx en utilisant Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// L'encodage du fichier texte est automatiquement détecté.
	Document doc = new Document(MyDir + "English text.txt");

	doc.Save(dataDir + "BaseConversions.TxtToDocx.docx");

```

N'hésitez pas à utiliser ce code dans vos propres projets et à le modifier en fonction de vos besoins spécifiques.