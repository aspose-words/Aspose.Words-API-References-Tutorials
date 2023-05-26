---
title: Redémarrer le numéro de la liste
linktitle: Redémarrer le numéro de la liste
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à réinitialiser le numéro d'une liste dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-list/restart-list-number/
---
Dans ce didacticiel pas à pas, nous vous montrerons comment réinitialiser le numéro d'une liste dans un document Word à l'aide de Aspose.Words pour .NET. Nous expliquerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets.

Pour commencer, assurez-vous que Aspose.Words pour .NET est installé et configuré dans votre environnement de développement. Si vous ne l'avez pas déjà fait, téléchargez et installez la bibliothèque à partir du site officiel.

## Étape 1 : Création du document et du générateur de documents

Commencez par créer un nouveau document et un générateur de documents associé :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Création et personnalisation de la première liste

Ensuite, créez une liste basée sur un modèle existant, puis personnalisez ses niveaux :

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

## Étape 3 : Ajouter des éléments à la première liste

Utilisez le générateur de documents pour ajouter des éléments à la première liste et supprimer des numéros de liste :

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Étape 4 : Création et personnalisation de la deuxième liste

Pour réutiliser la première liste en réinitialisant le nombre, créez une copie de la disposition de liste d'origine :

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

Vous pouvez également apporter des modifications supplémentaires à la deuxième liste si nécessaire.

## Étape 5 : Ajouter des éléments à la deuxième liste

Utilisez à nouveau le générateur de documents pour ajouter des éléments à la deuxième liste et supprimer les numéros de liste :

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Étape 6 : Enregistrez le document modifié

Enfin, enregistrez le document modifié :

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

Donc ! Vous avez réinitialisé avec succès le numéro d'une liste dans un document Word à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour la réinitialisation du numéro de liste

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Créer une liste basée sur un modèle.
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;

builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

// Pour réutiliser la première liste, nous devons redémarrer la numérotation en créant une copie de la mise en forme de la liste d'origine.
List list2 = doc.Lists.AddCopy(list1);

// Nous pouvons modifier la nouvelle liste de quelque manière que ce soit, y compris en définissant un nouveau numéro de départ.
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```




