---
title: Unité de mesure
linktitle: Unité de mesure
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment configurer la fonctionnalité d'unité de mesure dans Aspose.Words for .NET pour préserver le formatage du document lors de la conversion ODT.
type: docs
weight: 10
url: /fr/net/programming-with-odtsaveoptions/measure-unit/
---
## Introduction

Avez-vous déjà dû convertir vos documents Word dans différents formats mais aviez besoin d'une unité de mesure spécifique pour votre mise en page ? Qu'il s'agisse de pouces, de centimètres ou de points, il est crucial de garantir que votre document conserve son intégrité pendant le processus de conversion. Dans ce didacticiel, nous verrons comment configurer la fonctionnalité d'unité de mesure dans Aspose.Words pour .NET. Cette fonctionnalité puissante garantit que la mise en forme de votre document est conservée exactement comme vous en avez besoin lors de la conversion au format ODT (Open Document Text).

## Conditions préalables

Avant de plonger dans le code, vous aurez besoin de quelques éléments pour commencer :

1. Aspose.Words pour .NET : assurez-vous que la dernière version d'Aspose.Words pour .NET est installée. Si vous ne l'avez pas encore, vous pouvez le télécharger depuis[ici](https://releases.aspose.com/words/net/).
2. Environnement de développement : un IDE comme Visual Studio pour écrire et exécuter votre code C#.
3. Connaissance de base de C# : Comprendre les bases de C# vous aidera à suivre le didacticiel.
4. Un document Word : préparez un exemple de document Word que vous pourrez utiliser pour la conversion.

## Importer des espaces de noms

Avant de commencer à coder, assurons-nous que les espaces de noms nécessaires sont importés. Ajoutez-les à l'aide de directives en haut de votre fichier de code :

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Étape 1 : Configurez votre répertoire de documents

Tout d’abord, vous devez définir le chemin d’accès à votre répertoire de documents. C'est ici que se trouve votre document Word et que le fichier converti sera enregistré.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le chemin réel de votre répertoire. Cela garantit que votre code sait où trouver votre document Word.

## Étape 2 : Charger le document Word

 Ensuite, vous devez charger le document Word que vous souhaitez convertir. Cela se fait en utilisant le`Document` classe d’Aspose.Words.

```csharp
// Charger le document Word
Document doc = new Document(dataDir + "Document.docx");
```

Assurez-vous que votre document Word, nommé « Document.docx », est présent dans le répertoire spécifié.

## Étape 3 : Configurer l'unité de mesure

 Maintenant, configurons l'unité de mesure pour la conversion ODT. C'est là que la magie opère. Nous allons mettre en place le`OdtSaveOptions` d'utiliser les pouces comme unité de mesure.

```csharp
// Paramétrage des options de sauvegarde avec la fonctionnalité "Unité de mesure"
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

 Dans cet exemple, nous définissons l'unité de mesure en pouces. Vous pouvez également choisir d'autres unités telles que`OdtSaveMeasureUnit.Centimeters` ou`OdtSaveMeasureUnit.Points` en fonction de vos besoins.

## Étape 4 : Convertir le document en ODT

 Enfin, nous convertirons le document Word au format ODT en utilisant le paramètre configuré`OdtSaveOptions`.

```csharp
// Convertir le document en ODT
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

Cette ligne de code enregistre le document converti dans le répertoire spécifié avec la nouvelle unité de mesure appliquée.

## Conclusion

Et voilà ! En suivant ces étapes, vous pouvez facilement configurer la fonctionnalité d'unité de mesure dans Aspose.Words for .NET pour garantir que la mise en page de votre document est préservée lors de la conversion. Que vous travailliez avec des pouces, des centimètres ou des points, ce didacticiel vous a montré comment contrôler facilement la mise en forme de votre document.

## FAQ

### Qu’est-ce qu’Aspose.Words pour .NET ?
Aspose.Words for .NET est une bibliothèque puissante permettant de travailler avec des documents Word par programmation. Il permet aux développeurs de créer, modifier, convertir et traiter des documents Word sans nécessiter Microsoft Word.

### Puis-je utiliser d’autres unités de mesure que les pouces ?
 Oui, Aspose.Words for .NET prend en charge d'autres unités de mesure telles que les centimètres et les points. Vous pouvez spécifier l'unité souhaitée à l'aide du`OdtSaveMeasureUnit` énumération.

### Existe-t-il un essai gratuit disponible pour Aspose.Words pour .NET ?
 Oui, vous pouvez télécharger un essai gratuit d'Aspose.Words pour .NET à partir de[ici](https://releases.aspose.com/).

### Où puis-je trouver de la documentation pour Aspose.Words pour .NET ?
 Vous pouvez accéder à une documentation complète pour Aspose.Words pour .NET à l'adresse[ce lien](https://reference.aspose.com/words/net/).

### Comment puis-je obtenir de l’assistance pour Aspose.Words pour .NET ?
 Pour obtenir de l'aide, vous pouvez visiter le forum Aspose.Words à l'adresse[ce lien](https://forum.aspose.com/c/words/8).
