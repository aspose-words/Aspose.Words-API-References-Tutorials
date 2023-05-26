---
title: Créer un tableau
linktitle: Créer un tableau
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à créer un tableau dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/build-table/
---

Dans ce didacticiel pas à pas, vous apprendrez à créer un tableau dans un document Word à l'aide de Aspose.Words pour .NET. Nous vous guiderons tout au long du processus et vous fournirons les extraits de code C# nécessaires. À la fin de ce guide, vous serez en mesure de créer un tableau avec une mise en forme et un contenu personnalisés à l'aide de la classe DocumentBuilder.

## Conditions préalables
Avant de commencer, assurez-vous que vous disposez des prérequis suivants :
- Bibliothèque Aspose.Words pour .NET installée sur votre système.

## Étape 1 : créer un nouveau document
Pour commencer, créez un nouveau document en utilisant la classe Document :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Démarrer le tableau
Ensuite, utilisez la méthode StartTable de la classe DocumentBuilder pour commencer à construire la table :

```csharp
Table table = builder.StartTable();
```

## Étape 3 : Insérer des cellules et ajouter du contenu
Désormais, vous pouvez insérer des cellules dans le tableau et leur ajouter du contenu à l'aide des méthodes InsertCell et Write de la classe DocumentBuilder. Personnalisez la mise en forme des cellules selon vos besoins :

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## Étape 4 : terminer la rangée
Après avoir ajouté du contenu aux cellules de la première ligne, utilisez la méthode EndRow de la classe DocumentBuilder pour terminer la ligne :

```csharp
builder.EndRow();
```

## Étape 5 : Personnalisez le formatage des lignes
Vous pouvez personnaliser la mise en forme d'une ligne en définissant les propriétés des objets RowFormat et CellFormat :

```csharp
builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");
```

## Étape 6 : terminer la table
Pour compléter le tableau, utilisez la méthode EndTable de la classe DocumentBuilder :

```csharp
builder.EndTable();
```

### Exemple de code source pour la construction d'une table à l'aide de Aspose.Words pour .NET
Voici le code source complet pour construire une table en utilisant Aspose.Words pour .NET :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.AutoFit(AutoFitBehavior.FixedColumnWidths);

builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");

builder.EndRow();

builder.InsertCell();

builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.BuildTable.docx");
```

## Conclusion
Toutes nos félicitations! Vous avez appris avec succès à créer un tableau dans un document Word à l'aide d'Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez désormais créer des tableaux avec une mise en forme personnalisée.