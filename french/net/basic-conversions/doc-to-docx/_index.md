---
title: Doc à Docx
linktitle: Doc à Docx
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à convertir des documents Word du format .doc au format Docx en utilisant Aspose.Words pour .NET. Tutoriel étape par étape avec un exemple de code source.
type: docs
weight: 10
url: /fr/net/basic-conversions/doc-to-docx/
---

Dans ce didacticiel, nous vous guiderons pas à pas dans le processus d'utilisation d'Aspose.Words pour .NET pour convertir un document Word au format .doc au format Docx. Nous expliquerons le code source C# fourni et vous guiderons sur la façon de l'implémenter dans vos propres projets.

Pour commencer, assurez-vous que Aspose.Words pour .NET est installé et configuré dans votre environnement de développement. Si vous ne l'avez pas encore fait, téléchargez et installez la bibliothèque depuis le site officiel.

## Étape 1 : Configuration de l'environnement de développement

Avant de commencer à coder, assurez-vous que vous disposez d'un environnement de développement approprié. Ouvrez Visual Studio ou votre IDE C# préféré et créez un nouveau projet.

## Étape 2 : Ajouter des références et importer des espaces de noms

Pour utiliser Aspose.Words pour .NET, vous devez ajouter des références à la bibliothèque dans votre projet. Cliquez avec le bouton droit sur le dossier Références de votre projet, sélectionnez "Ajouter une référence" et accédez à l'emplacement où vous avez installé la bibliothèque Aspose.Words pour .NET. Sélectionnez la version appropriée et cliquez sur "OK" pour ajouter la référence.

Ensuite, importez les espaces de noms nécessaires en haut de votre fichier C# :

```csharp
using Aspose.Words;
```

## Étape 3 : Initialisation de l'objet Document

 Dans cette étape, vous allez initialiser le`Document` objet avec le chemin vers votre document source au format .doc. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel du répertoire où se trouve votre document, et`"Document.doc"` avec le nom de votre document source. Voici l'extrait de code :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.doc");
```

## Étape 4 : Conversion du document au format Docx

 Maintenant que vous avez initialisé le`Document`objet, vous pouvez poursuivre le processus de conversion. Aspose.Words pour .NET fournit diverses options et paramètres de personnalisation, mais pour une conversion de base, aucun paramètre supplémentaire n'est requis.

## Étape 5 : Enregistrer le document converti

 Pour enregistrer le document converti au format Docx, vous devez appeler le`Save` méthode sur la`Document` objet. Indiquez le chemin et le nom de fichier du document de sortie. Dans cet exemple, nous allons l'enregistrer sous`"BaseConversions.DocToDocx.docx"`. Voici l'extrait de code :

```csharp
doc.Save(dataDir + "BaseConversions.DocToDocx.docx");
```

C'est ça! Vous avez converti avec succès un document Word au format .doc au format Docx à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour Doc To Docx utilisant Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.doc");

	doc.Save(dataDir + "BaseConversions.DocToDocx.docx");
	
```

N'hésitez pas à utiliser ce code dans vos propres projets et à le modifier en fonction de vos besoins spécifiques.




