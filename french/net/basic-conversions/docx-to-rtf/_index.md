---
title: Docx vers RTF
linktitle: Docx vers RTF
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à convertir des documents Word du format Docx au format RTF en utilisant Aspose.Words pour .NET. Tutoriel étape par étape avec un exemple de code source.
type: docs
weight: 10
url: /fr/net/basic-conversions/docx-to-rtf/
---

Dans ce didacticiel étape par étape, nous vous expliquerons comment utiliser Aspose.Words pour .NET pour convertir un document Word au format Docx en RTF. Nous vous expliquerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets.

Pour commencer, assurez-vous que Aspose.Words pour .NET est installé et configuré dans votre environnement de développement. Si vous ne l'avez pas encore fait, téléchargez et installez la bibliothèque depuis le site officiel.

## Étape 1 : Lecture du document à partir du flux

Commencez par ouvrir un flux pour lire le document Docx :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Stream stream = File.OpenRead(MyDir + "Document.docx");
```

## Étape 2 : Chargement du document

Ensuite, chargez le document à partir du flux :

```csharp
Document doc = new Document(stream);
```

## Étape 3 : Fermer le flux

Le document étant chargé en mémoire, vous pouvez fermer le flux :

```csharp
stream.Close();
```

## Étape 4 : Exécution d'opérations sur le document

À ce stade, vous pouvez effectuer toutes les opérations souhaitées sur le document.

## Étape 5 : Enregistrer le document au format RTF

Pour enregistrer le document au format RTF, enregistrez-le dans un flux mémoire :

```csharp
MemoryStream dstStream = new MemoryStream();
doc.Save(dstStream, SaveFormat.Rtf);
```

## Étape 6 : Rembobiner le flux

Avant d'écrire le flux de mémoire dans un fichier, rembobinez sa position jusqu'à zéro :

```csharp
dstStream.Position = 0;
```

## Étape 7 : Écrire le flux dans un fichier

Enfin, écrivez le flux mémoire dans un fichier RTF :

```csharp
File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
```

C'est ça! Vous avez converti avec succès un document Word au format Docx en RTF à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour Docx To Rtf en utilisant Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// L'accès en lecture seule est suffisant pour qu'Aspose.Words charge un document.
	Stream stream = File.OpenRead(MyDir + "Document.docx");

	Document doc = new Document(stream);
	//Vous pouvez fermer le flux maintenant, il n'est plus nécessaire car le document est en mémoire.
	stream.Close();

	// ... faire quelque chose avec le document.

	// Convertissez le document dans un format différent et enregistrez-le en flux.
	MemoryStream dstStream = new MemoryStream();
	doc.Save(dstStream, SaveFormat.Rtf);

	// Rembobinez la position du flux jusqu'à zéro afin qu'il soit prêt pour le lecteur suivant.
	dstStream.Position = 0;

	File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
	
```

N'hésitez pas à utiliser ce code dans vos propres projets et à le modifier en fonction de vos besoins spécifiques.