---
title: Créer un style de tableau
linktitle: Créer un style de tableau
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour créer un style de tableau personnalisé à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-table-styles-and-formatting/create-table-style/
---

Dans ce didacticiel, nous vous expliquerons étape par étape le processus de création d'un style de tableau à l'aide de Aspose.Words pour .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous saurez comment créer un style personnalisé pour vos tableaux dans vos documents Word à l'aide d'Aspose.Words pour .NET.

## Étape 1 : Définir le répertoire des documents
Tout d'abord, vous devez définir le chemin d'accès à votre répertoire de documents. Il s'agit de l'emplacement où vous souhaitez enregistrer votre document Word modifié. Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Créer un nouveau document et un générateur de documents
 Ensuite, vous devez créer une nouvelle instance de`Document` classe et un constructeur de document pour ce document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Commencez un nouveau tableau et ajoutez des cellules
Pour commencer à créer le tableau, nous utilisons le`StartTable()` méthode du générateur de documents, puis nous ajoutons des cellules au tableau à l'aide de la`InsertCell()` méthode et nous écrivons le contenu des cellules à l'aide de la`Write()` méthode.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
builder.Write("Name");
builder. InsertCell();
builder.Write("Value");
builder. EndRow();
builder. InsertCell();
builder. InsertCell();
builder. EndTable();
```

## Étape 4 : Créer un style de tableau
 Nous pouvons maintenant créer un style de tableau en utilisant le`TableStyle` classe et la`Add()` méthode du document`s `Collection Styles. Nous définissons les propriétés du style, telles que les bordures, les marges et les rembourrages.

```csharp
TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.Borders.LineStyle = LineStyle.Double;
tableStyle.Borders.LineWidth = 1;
tableStyle. LeftPadding = 18;
tableStyle. RightPadding = 18;
tableStyle.TopPadding = 12;
tableStyle.BottomPadding = 12;
```

## Étape 5 : Appliquer le style de tableau au tableau
 Enfin, nous appliquons le style de tableau que nous avons créé au tableau à l'aide de la`Style` propriété du tableau.

```csharp
table.Style = tableStyle;
```

## Étape 6 : Enregistrez le document modifié
Enfin, enregistrez le document modifié dans un fichier. Vous pouvez choisir un nom et un emplacement appropriés pour le document de sortie.

```csharp


doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

Félicitation ! Vous avez maintenant créé un style personnalisé pour votre tableau en utilisant Aspose.Words pour .NET.

### Exemple de code source pour Créer un style de tableau à l'aide d'Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Name");
	builder.InsertCell();
	builder.Write("Value");
	builder.EndRow();
	builder.InsertCell();
	builder.InsertCell();
	builder.EndTable();
	TableStyle tableStyle = (TableStyle) doc.Styles.Add(StyleType.Table, "MyTableStyle1");
	tableStyle.Borders.LineStyle = LineStyle.Double;
	tableStyle.Borders.LineWidth = 1;
	tableStyle.LeftPadding = 18;
	tableStyle.RightPadding = 18;
	tableStyle.TopPadding = 12;
	tableStyle.BottomPadding = 12;
	table.Style = tableStyle;
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

## Conclusion
Dans ce didacticiel, nous avons appris à créer un style de tableau à l'aide de Aspose.Words pour .NET. En suivant ce guide étape par étape, vous pouvez facilement personnaliser le style de vos tableaux dans vos documents Word. Aspose.Words offre une API puissante et flexible pour manipuler et formater des tableaux dans vos documents. Grâce à ces connaissances, vous pouvez améliorer la présentation visuelle de vos documents Word et répondre à des besoins spécifiques.