---
title: Charger le dictionnaire de césure pour la langue
linktitle: Charger le dictionnaire de césure pour la langue
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à charger un dictionnaire de césure pour une langue spécifique dans Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-hyphenation/load-hyphenation-dictionary-for-language/
---

Dans ce tutoriel étape par étape, nous allons vous montrer comment charger un dictionnaire de césure pour une langue spécifique dans Aspose.Words pour .NET. Nous expliquerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets.

Pour commencer, assurez-vous que Aspose.Words pour .NET est installé et configuré dans votre environnement de développement. Si vous ne l'avez pas déjà fait, téléchargez et installez la bibliothèque à partir du site officiel.

## Étape 1 : Chargement du document

Tout d'abord, chargez votre document depuis le répertoire spécifié :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Étape 2 : Chargement du dictionnaire de césure

Ensuite, ouvrez un flux vers le fichier du dictionnaire de césure et enregistrez-le pour la langue souhaitée. Dans cet exemple, nous chargeons un dictionnaire pour le suisse allemand (de-CH) :

```csharp
Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);
```

Assurez-vous d'avoir le fichier de dictionnaire approprié dans votre répertoire de données.

## Étape 3 : Enregistrer le document modifié

Enfin, enregistrez le document modifié :

```csharp
doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

Donc ! Vous avez chargé avec succès un dictionnaire de césure pour une langue spécifique dans Aspose.Words pour .NET.

### Exemple de code source pour le chargement du dictionnaire de césure pour une langue utilisant Aspose.Words pour .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);

doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

N'hésitez pas à utiliser ce code dans vos propres projets et à le modifier en fonction de vos besoins spécifiques.