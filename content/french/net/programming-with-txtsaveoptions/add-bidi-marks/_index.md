---
title: Ajouter des marques Bidi dans un document Word
linktitle: Ajouter des marques Bidi dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment ajouter des marques bidirectionnelles (Bidi) dans des documents Word à l'aide d'Aspose.Words pour .NET avec ce guide. Assurez la bonne direction du texte pour le contenu multilingue.
type: docs
weight: 10
url: /fr/net/programming-with-txtsaveoptions/add-bidi-marks/
---
## Introduction

Dans le monde du traitement documentaire, le texte bidirectionnel (Bidi) peut souvent être un peu délicat à gérer. Cela est particulièrement vrai lorsqu’il s’agit de langues dont le texte a des orientations différentes, comme l’arabe ou l’hébreu. Heureusement, Aspose.Words for .NET facilite la gestion de tels scénarios. Dans ce didacticiel, nous verrons comment ajouter des marques Bidi à un document Word à l'aide d'Aspose.Words pour .NET.

## Conditions préalables

Avant de plonger dans le code, assurez-vous d'avoir les éléments suivants :

1.  Aspose.Words pour .NET : vous devez avoir installé Aspose.Words pour .NET. Vous pouvez le télécharger depuis le[Page de téléchargement d'Aspose](https://releases.aspose.com/words/net/).
2. .NET Framework ou .NET Core : assurez-vous que vous disposez d'un environnement .NET compatible configuré pour exécuter les exemples.
3. Connaissance de base de C# : Familiarité avec le langage de programmation C# et les opérations de base dans .NET.

## Importer des espaces de noms

Pour commencer, vous devez importer les espaces de noms nécessaires. Voici comment vous pouvez les inclure dans votre projet :

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Décomposons le processus d'ajout de marques Bidi dans un document Word en étapes claires. Chaque étape vous guidera à travers le code et son objectif.

## Étape 1 : Configurez votre document

 Commencez par créer une nouvelle instance du`Document` classe et un`DocumentBuilder` pour ajouter du contenu au document.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Créer le document et ajouter du contenu
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Dans cette étape, vous initialisez un nouveau document Word et configurez un`DocumentBuilder` pour faciliter l’insertion de contenu.

## Étape 2 : ajouter du contenu à votre document

Ensuite, ajoutez du texte à votre document. Ici, nous ajouterons du texte dans différentes langues pour illustrer la gestion du texte Bidi.

```csharp
builder.Writeln("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder.Writeln("שלום עולם!");
builder.Writeln("مرحبا بالعالم!");
```

Ici, nous ajoutons d’abord une phrase anglaise standard. Ensuite, nous activons le formatage du texte Bidi pour le texte suivant, qui est écrit en hébreu et en arabe. Cela montre comment incorporer du texte bidirectionnel.

## Étape 3 : Configurer les options d'enregistrement pour les marques Bidi

 Pour vous assurer que les marques Bidi sont correctement enregistrées dans le document, vous devez configurer le`TxtSaveOptions` et activer le`AddBidiMarks` option.

```csharp
// Ajouter des marques Bidi
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

 Dans cette étape, nous créons une instance de`TxtSaveOptions` et réglez le`AddBidiMarks`propriété à`true`. Cela garantit que les marques Bidi sont incluses lors de l'enregistrement du document sous forme de fichier texte.

## Conclusion

L'ajout de marques Bidi à vos documents Word peut être une étape cruciale lorsqu'il s'agit de contenu multilingue comprenant des langues avec des directions de texte différentes. Avec Aspose.Words pour .NET, ce processus est simple et efficace. En suivant les étapes décrites ci-dessus, vous pouvez vous assurer que vos documents représentent correctement le texte Bidi, améliorant ainsi la lisibilité et l'exactitude.

## FAQ

### Que sont les marques Bidi et pourquoi sont-elles importantes ?
Les marques Bidi sont des caractères spéciaux utilisés pour contrôler le sens du texte dans les documents. Ils sont essentiels pour afficher correctement les langues qui se lisent de droite à gauche, comme l'arabe et l'hébreu.

### Puis-je utiliser Aspose.Words for .NET pour gérer d’autres types de problèmes de direction de texte ?
Oui, Aspose.Words for .NET offre une prise en charge complète de divers besoins en matière d'orientation et de formatage du texte, y compris les langues s'écrivant de droite à gauche et de gauche à droite.

### Est-il possible d'appliquer le formatage Bidi uniquement à des parties spécifiques d'un document ?
Oui, vous pouvez appliquer le formatage Bidi à des paragraphes ou des sections spécifiques de votre document selon vos besoins.

### Dans quels formats puis-je enregistrer le document avec les marques Bidi ?
Dans l'exemple fourni, le document est enregistré sous forme de fichier texte. Cependant, Aspose.Words prend également en charge l'enregistrement de documents dans différents formats tout en préservant les marques Bidi.

### Où puis-je trouver plus d’informations sur Aspose.Words pour .NET ?
 Vous pouvez en savoir plus sur Aspose.Words pour .NET via le[Documentation Aspose](https://reference.aspose.com/words/net/) et accédez au[Forum d'assistance](https://forum.aspose.com/c/words/8) pour une aide supplémentaire.