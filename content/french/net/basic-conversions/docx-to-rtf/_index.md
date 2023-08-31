---
title: Convertir Docx en Rtf
linktitle: Convertir Docx en Rtf
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment convertir des documents Word du format Docx au format RTF à l'aide d'Aspose.Words pour .NET. Tutoriel étape par étape avec un exemple de code source.
type: docs
weight: 10
url: /fr/net/basic-conversions/docx-to-rtf/
---

Dans ce didacticiel étape par étape, nous vous expliquerons comment utiliser Aspose.Words for .NET pour convertir un document Word au format Docx en RTF. Nous expliquerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets.

 Pour commencer, assurez-vous que Aspose.Words for .NET est installé et configuré dans votre environnement de développement. Si vous ne l'avez pas fait, téléchargez et installez la bibliothèque depuis[Aspose.Releases]https://releases.aspose.com/words/net/.

## Étape 1 : Lire le document à partir du flux

Tout d’abord, ouvrez un flux pour lire le document Docx :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Stream stream = File.OpenRead(MyDir + "Document.docx");
```

## Étape 2 : chargement du document

Ensuite, chargez le document depuis le flux :

```csharp
Document doc = new Document(stream);
```

## Étape 3 : Fermer le flux

Le document étant chargé en mémoire, vous pouvez fermer le flux :

```csharp
stream.Close();
```

## Étape 4 : effectuer des opérations sur le document

À ce stade, vous pouvez effectuer toutes les opérations souhaitées sur le document.

## Étape 5 : enregistrement du document au format RTF

Pour enregistrer le document au format RTF, enregistrez-le dans un flux mémoire :

```csharp
MemoryStream dstStream = new MemoryStream();
doc.Save(dstStream, SaveFormat.Rtf);
```

## Étape 6 : Rembobiner le flux

Avant d'écrire le flux mémoire dans un fichier, rembobinez sa position à zéro :

```csharp
dstStream.Position = 0;
```

## Étape 7 : écriture du flux dans un fichier

Enfin, écrivez le flux mémoire dans un fichier RTF :

```csharp
File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
```

C'est ça! Vous avez converti avec succès un document Word au format Docx en RTF à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour Docx To Rtf utilisant Aspose.Words pour .NET

```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// L'accès en lecture seule est suffisant pour qu'Aspose.Words charge un document.
	Stream stream = File.OpenRead(MyDir + "Document.docx");

	Document doc = new Document(stream);
	// Vous pouvez fermer le flux maintenant, il n'est plus nécessaire car le document est en mémoire.
	stream.Close();

	// ... faire quelque chose avec le document.

	// Convertissez le document dans un format différent et enregistrez-le en streaming.
	MemoryStream dstStream = new MemoryStream();
	doc.Save(dstStream, SaveFormat.Rtf);

	// Rembobinez la position du flux à zéro afin qu'il soit prêt pour le prochain lecteur.
	dstStream.Position = 0;

	File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
	
```

N'hésitez pas à utiliser ce code dans vos propres projets et à le modifier en fonction de vos besoins spécifiques.

### FAQ

#### Comment puis-je convertir un fichier DOCX au format RTF ?

Pour convertir un fichier DOCX au format RTF, vous pouvez utiliser divers outils logiciels ou bibliothèques offrant cette fonctionnalité. Aspose.Words for .NET est l'un de ces outils fiables. Il offre un moyen simple et efficace de convertir des fichiers DOCX au format RTF par programme. Vous pouvez utiliser l'API de la bibliothèque pour charger le fichier DOCX et l'enregistrer au format RTF souhaité.

#### Y a-t-il des limites au processus de conversion ?

Les limites du processus de conversion dépendent de l'outil ou de la bibliothèque spécifique que vous utilisez. Certains outils peuvent avoir des restrictions sur la taille ou la complexité du document d'entrée. Il est important de choisir un outil capable de répondre aux exigences de votre tâche de conversion.

#### Puis-je conserver le formatage et la mise en page du document original ?

Oui, avec Aspose.Words, vous pouvez conserver le formatage et la mise en page du document original pendant le processus de conversion. Aspose.Words for .NET, par exemple, fournit une prise en charge complète pour conserver le formatage, les styles et d'autres éléments du fichier DOCX dans le document RTF converti.

#### Aspose est-il un outil fiable pour la conversion DOCX en RTF ?

Oui, Aspose.Words for .NET est un outil hautement fiable pour la conversion DOCX en RTF. Il est largement utilisé par les développeurs et les entreprises du monde entier pour ses fonctionnalités robustes et ses excellentes performances. La bibliothèque propose une documentation complète, des mises à jour régulières et un support technique dédié, ce qui en fait un choix fiable pour les tâches de conversion de documents.