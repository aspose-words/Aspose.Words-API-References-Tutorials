---
title: Modifier le champ Mettre à jour la source de culture
linktitle: Modifier le champ Mettre à jour la source de culture
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment modifier la source de culture de mise à jour de champ dans Aspose.Words for .NET avec ce guide. Contrôlez facilement le formatage de la date en fonction de différentes cultures.
type: docs
weight: 10
url: /fr/net/working-with-fields/change-field-update-culture-source/
---
## Introduction

Dans ce didacticiel, nous allons plonger dans le monde d'Aspose.Words pour .NET et explorer comment modifier la source de culture de mise à jour des champs. Si vous utilisez des documents Word comportant des champs de date et que vous devez contrôler la façon dont ces dates sont formatées en fonction de différentes cultures, ce guide est fait pour vous. Parcourons le processus étape par étape, en nous assurant que vous comprenez chaque concept et que vous pouvez l'appliquer efficacement dans vos projets.

## Conditions préalables

Avant de passer au code, assurez-vous d'avoir les éléments suivants :

-  Aspose.Words pour .NET : vous pouvez le télécharger depuis[ici](https://releases.aspose.com/words/net/).
- Environnement de développement : tout IDE compatible .NET (par exemple, Visual Studio).
- Connaissance de base de C# : ce didacticiel suppose que vous possédez une compréhension fondamentale de la programmation C#.

## Importer des espaces de noms

Tout d’abord, importons les espaces de noms nécessaires à notre projet. Cela garantira que nous avons accès à toutes les classes et méthodes requises fournies par Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Maintenant, décomposons l'exemple en plusieurs étapes pour vous aider à comprendre comment modifier la source de culture de mise à jour de champ dans Aspose.Words pour .NET.

## Étape 1 : initialiser le document

 La première étape consiste à créer une nouvelle instance du`Document` classe et un`DocumentBuilder`. Cela jette les bases de la création et de la manipulation de notre document Word.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Insérer des champs avec des paramètres régionaux spécifiques

Ensuite, nous devons insérer des champs dans le document. Pour cet exemple, nous allons insérer deux champs de date. Nous allons définir les paramètres régionaux de la police sur allemand (LocaleId = 1031) pour démontrer comment la culture affecte le format de date.

```csharp
builder.Font.LocaleId = 1031; // Allemand
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

## Étape 3 : Définir la source de culture de mise à jour du champ

 Pour contrôler la culture utilisée lors de la mise à jour des champs, nous définissons le`FieldUpdateCultureSource` propriété du`FieldOptions`classe. Cette propriété détermine si la culture est issue du code de champ ou du document.

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

## Étape 4 : Exécuter le publipostage

Nous devons maintenant exécuter un publipostage pour remplir les champs avec les données réelles. Dans cet exemple, nous définirons le deuxième champ de date (`Date2`) au 1er janvier 2011.

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

## Étape 5 : Enregistrez le document

Enfin, nous enregistrons le document dans le répertoire spécifié. Cette étape termine le processus de modification de la source de culture de mise à jour sur le terrain.

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## Conclusion

Et voila! Vous avez modifié avec succès la source de culture de mise à jour de champ dans Aspose.Words pour .NET. En suivant ces étapes, vous pouvez vous assurer que vos documents Word affichent les dates et autres valeurs de champ en fonction des paramètres culturels spécifiés. Cela peut être particulièrement utile lors de la génération de documents destinés à un public international.

## FAQ

###  Quel est le but de définir le`LocaleId`?
 Le`LocaleId` spécifie les paramètres de culture du texte, qui affectent la façon dont les dates et autres données sensibles aux paramètres régionaux sont formatées.

### Puis-je utiliser une langue autre que l’allemand ?
 Oui, vous pouvez définir le`LocaleId`à tout identifiant de paramètres régionaux valide. Par exemple, 1033 pour l'anglais (États-Unis).

###  Que se passe-t-il si je ne règle pas le`FieldUpdateCultureSource` property?
Si cette propriété n'est pas définie, les paramètres de culture par défaut du document seront utilisés lors de la mise à jour des champs.

### Est-il possible de mettre à jour les champs en fonction de la culture du document plutôt que du code du champ ?
 Oui, vous pouvez définir`FieldUpdateCultureSource` à`FieldUpdateCultureSource.Document` pour utiliser les paramètres de culture du document.

### Comment formater les dates selon un modèle différent ?
 Vous pouvez modifier le modèle de format de date dans le`InsertField` méthode en modifiant la`\\@` valeur de commutation.