---
title: Insérer un champ de fusion à l'aide de DOM
linktitle: Insérer un champ de fusion à l'aide de DOM
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment insérer et configurer des champs de fusion dans des documents Word à l'aide d'Aspose.Words for .NET avec ce didacticiel complet étape par étape.
type: docs
weight: 10
url: /fr/net/working-with-fields/insert-merge-field-using-dom/
---

Si vous travaillez avec le traitement de documents dans .NET, vous avez probablement rencontré Aspose.Words. Cette puissante bibliothèque offre un large éventail de fonctionnalités pour manipuler des documents Word par programmation. Dans ce didacticiel, nous nous concentrerons sur une fonctionnalité spécifique : l'insertion d'un champ de fusion à l'aide du modèle objet de document (DOM) dans Aspose.Words pour .NET. Ce guide vous guidera à travers chaque étape, de la configuration de votre environnement à l'insertion et à la mise à jour d'un champ de fusion dans un document Word.

## Conditions préalables

Avant de plonger dans le code, assurons-nous que vous disposez de tout ce dont vous avez besoin pour suivre ce didacticiel.

1. **Basic Knowledge of C#:** Vous devez être à l'aise avec la programmation C#.
2. **Visual Studio Installed:** Assurez-vous que Visual Studio ou tout autre IDE C# est installé sur votre ordinateur.
3. **Aspose.Words for .NET:** Téléchargez et installez la dernière version d'Aspose.Words pour .NET à partir du[Sorties](https://releases.aspose.com/words/net/).
4. **Valid License:** Si vous n'avez pas de permis, vous pouvez obtenir un[permis temporaire](https://purchase.aspose.com/temporary-license/) pour évaluation.

## Étape 1 : Configurez votre projet

Tout d’abord, configurons un nouveau projet dans Visual Studio.

1. **Open Visual Studio.**
2. **Create a New Project:** Accédez à Fichier > Nouveau > Projet. Sélectionnez une application console C#.
3. **Name Your Project:** Donnez à votre projet un nom significatif et cliquez sur Créer.

## Étape 2 : Installer Aspose.Words

Pour utiliser Aspose.Words, vous devez l'ajouter à votre projet. Cela peut être fait via NuGet Package Manager.

1. **Open NuGet Package Manager:** Cliquez avec le bouton droit sur votre projet dans l'Explorateur de solutions, puis sélectionnez Gérer les packages NuGet.
2. **Search for Aspose.Words:** Dans le gestionnaire de packages NuGet, recherchez « Aspose.Words ».
3. **Install the Package:** Cliquez sur Installer pour ajouter Aspose.Words à votre projet.

## Étape 3 : Importer des espaces de noms

Pour commencer à utiliser Aspose.Words, vous devez importer les espaces de noms nécessaires dans votre projet. Voici comment procéder :

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

## Étape 4 : initialisez votre document

Maintenant que tout est configuré, créons un nouveau document Word et initialisons DocumentBuilder.

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Créez le document et le DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 5 : déplacer le curseur vers un paragraphe spécifique

Ensuite, nous devons déplacer le curseur vers un paragraphe spécifique du document où nous souhaitons insérer le champ de fusion.

```csharp
// Déplacez le curseur sur le paragraphe.
builder.MoveToParagraph(2, 0);
```

## Étape 6 : Insérer le champ de fusion

 L'insertion d'un champ de fusion est simple. Nous utiliserons le`InsertField` méthode du`DocumentBuilder` classe.

```csharp
// Insérer un champ de fusion de champs.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

## Étape 7 : configurer le champ de fusion

Après avoir inséré le champ de fusion, vous pouvez définir diverses propriétés pour le configurer en fonction de vos besoins.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field.TextAfter = "Test3";
field.IsMapped = true;
field.IsVerticalFormatting = true;
```

## Étape 8 : mettre à jour et enregistrer le document

Enfin, mettez à jour le champ pour vous assurer que tous les paramètres sont appliqués et enregistrez le document.

```csharp
// Mettez à jour le champ.
field.Update();

// Enregistrez le document.
doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

## Conclusion

En suivant ces étapes, vous pouvez facilement insérer et configurer des champs de fusion dans un document Word à l'aide d'Aspose.Words pour .NET. Ce didacticiel a couvert les étapes essentielles depuis la configuration de votre environnement jusqu'à l'enregistrement du document final. Avec Aspose.Words, vous pouvez automatiser des tâches complexes de traitement de documents, rendant ainsi vos applications .NET plus puissantes et efficaces.

## FAQ

### 1. Qu'est-ce qu'un champ de fusion ?
Un champ de fusion est un espace réservé dans un document qui peut être remplacé dynamiquement par des données provenant d'une source de données, telle qu'une base de données ou un fichier CSV.

### 2. Puis-je utiliser Aspose.Words gratuitement ?
 Aspose.Words propose un essai gratuit que vous pouvez télécharger[ici](https://releases.aspose.com/). Pour une utilisation à long terme, vous devrez acheter une licence.

### 3. Comment puis-je obtenir une licence temporaire pour Aspose.Words ?
 Vous pouvez obtenir une licence temporaire sur le site Aspose[ici](https://purchase.aspose.com/temporary-license/).

### 4. Quelles versions de .NET sont prises en charge par Aspose.Words ?
Aspose.Words prend en charge plusieurs versions de .NET, notamment .NET Framework, .NET Core et .NET Standard.

### 5. Où puis-je trouver la documentation de l'API pour Aspose.Words ?
 La documentation de l'API est disponible[ici](https://reference.aspose.com/words/net/).