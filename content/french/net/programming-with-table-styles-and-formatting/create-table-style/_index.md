---
title: Créer un style de tableau
linktitle: Créer un style de tableau
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour créer un style de tableau personnalisé à l’aide d’Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-table-styles-and-formatting/create-table-style/
---

Dans ce didacticiel, nous vous guiderons pas à pas à travers le processus de création d'un style de tableau à l'aide d'Aspose.Words pour .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous saurez comment créer un style personnalisé pour vos tableaux dans vos documents Word à l'aide d'Aspose.Words for .NET.

## Étape 1 : Définir le répertoire des documents
Tout d’abord, vous devez définir le chemin d’accès à votre répertoire de documents. C'est l'emplacement où vous souhaitez enregistrer votre document Word modifié. Remplacez « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Créer un nouveau document et un générateur de documents
 Ensuite, vous devez créer une nouvelle instance du`Document` classe et un constructeur de document pour ce document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : créez un nouveau tableau et ajoutez des cellules
Pour commencer à créer le tableau, nous utilisons le`StartTable()` méthode du générateur de documents, puis nous ajoutons des cellules au tableau en utilisant la`InsertCell()` méthode et nous écrivons le contenu des cellules dans la méthode`Write()` méthode.

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
 Nous pouvons maintenant créer un style de tableau en utilisant le`TableStyle` la classe et le`Add()` méthode à partir du document`s `Collection de styles. Nous définissons les propriétés du style, telles que les bordures, les marges et les remplissages.

```csharp
TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.Borders.LineStyle = LineStyle.Double;
tableStyle.Borders.LineWidth = 1;
tableStyle. LeftPadding = 18;
tableStyle. RightPadding = 18;
tableStyle.TopPadding = 12;
tableStyle.BottomPadding = 12;
```

## Étape 5 : appliquer le style de tableau au tableau
 Enfin, nous appliquons le style de tableau que nous avons créé au tableau en utilisant le`Style` propriété de la table.

```csharp
table.Style = tableStyle;
```

## Étape 6 : Enregistrez le document modifié
Enfin, enregistrez le document modifié dans un fichier. Vous pouvez choisir un nom et un emplacement appropriés pour le document de sortie.

```csharp


doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

Félicitation ! Vous avez maintenant créé un style personnalisé pour votre tableau à l'aide d'Aspose.Words for .NET.

### Exemple de code source pour créer un style de tableau à l'aide d'Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
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
Dans ce didacticiel, nous avons appris à créer un style de tableau à l'aide d'Aspose.Words pour .NET. En suivant ce guide étape par étape, vous pouvez facilement personnaliser le style de vos tableaux dans vos documents Word. Aspose.Words propose une API puissante et flexible pour manipuler et formater les tableaux de vos documents. Grâce à ces connaissances, vous pourrez améliorer la présentation visuelle de vos documents Word et répondre à des besoins spécifiques.