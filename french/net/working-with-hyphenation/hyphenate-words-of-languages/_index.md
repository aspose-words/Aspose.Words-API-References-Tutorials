---
title: Césure des mots des langues
linktitle: Césure des mots des langues
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à couper des mots dans différentes langues dans des documents Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-hyphenation/hyphenate-words-of-languages/
---

Dans ce didacticiel étape par étape, nous vous expliquerons comment couper des mots dans différentes langues dans des documents Word à l'aide d'Aspose.Words pour .NET. Nous expliquerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets.

Pour commencer, assurez-vous que Aspose.Words pour .NET est installé et configuré dans votre environnement de développement. Si vous ne l'avez pas déjà fait, téléchargez et installez la bibliothèque à partir du site officiel.

## Étape 1 : Initialisation de l'objet Document

 Tout d'abord, initialisez le`Document` objet en spécifiant le chemin d'accès à votre document source contenant du texte dans différentes langues :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Étape 2 : Enregistrer les dictionnaires de césure

Ensuite, enregistrez les dictionnaires de césure pour les différentes langues que vous souhaitez traiter. Dans cet exemple, nous enregistrons des dictionnaires pour l'anglais américain et le suisse allemand :

```csharp
Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");
```

Assurez-vous d'avoir les fichiers de dictionnaire appropriés dans votre répertoire de données.

## Étape 3 : Traitement des mots par césure

 Vous pouvez désormais utiliser les fonctions de césure pour traiter des mots dans différentes langues. Vous pouvez utiliser différentes méthodes de`Document` ou`DocumentBuilder`en fonction de vos besoins spécifiques.

```csharp
// Exemple : Utilisation de la méthode Hyphenate de DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Example of text to hyphenate");
builder.InsertHyphenation();
```

## Étape 4 : Enregistrez le document

Enfin, enregistrez le document modifié :

```csharp
doc.Save(dataDir + "TreatmentByCesure.pdf");
```

Donc ! Vous avez traité avec succès des mots en les coupant dans différentes langues dans un document Word à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour la césure des mots à l'aide d'Aspose.Words pour .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");

doc.Save(dataDir + "TreatmentByCesure.pdf");
```

N'hésitez pas à utiliser ce code dans vos propres projets et à le modifier en fonction de vos besoins spécifiques.
