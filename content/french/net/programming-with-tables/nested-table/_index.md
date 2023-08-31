---
title: Tableau imbriqué
linktitle: Tableau imbriqué
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment créer un tableau imbriqué dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-tables/nested-table/
---

Dans ce didacticiel, nous apprendrons comment créer un tableau imbriqué dans un document Word à l'aide d'Aspose.Words pour .NET. Nous suivrons un guide étape par étape pour comprendre le code et implémenter cette fonctionnalité. À la fin de ce didacticiel, vous serez en mesure de créer par programme des tableaux imbriqués dans vos documents Word.

## Étape 1 : Configuration du projet
1. Lancez Visual Studio et créez un nouveau projet C#.
2. Ajoutez une référence à la bibliothèque Aspose.Words pour .NET.

## Étape 2 : Création du document et initialisation du générateur de documents
Pour démarrer le traitement de texte avec le document et le générateur de documents, procédez comme suit :

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// création de documents
Document doc = new Document();

// Initialiser le générateur de documents
DocumentBuilder builder = new DocumentBuilder(doc);
```

Assurez-vous de remplacer « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin réel d'accès à votre répertoire de documents.

## Étape 3 : Création de la table imbriquée
Ensuite, nous allons créer le tableau imbriqué en insérant des cellules dans le tableau externe et en créant un nouveau tableau à l'intérieur de la première cellule. Utilisez le code suivant :

```csharp
// Insérer la première cellule du tableau externe
Cell cell = builder. InsertCell();
builder.Writeln("Cell 1 of the outer table");

// Insérez la deuxième cellule du tableau externe
builder. InsertCell();
builder.Writeln("Cell 2 of the outer table");

// Terminaison de la table extérieure
builder. EndTable();

// Passer à la première cellule du tableau externe
builder.MoveTo(cell.FirstParagraph);

// Construire la table intérieure
builder. InsertCell();
builder.Writeln("Cell 1 of inner table");
builder. InsertCell();
builder.Writeln("Cell 2 of the inner table");

// Fin de la table intérieure
builder. EndTable();
```

Ici, nous utilisons le générateur de documents pour insérer des cellules et du contenu dans le tableau externe. Ensuite, nous déplaçons le curseur du générateur de documents vers la première cellule du tableau externe et construisons un nouveau tableau à l'intérieur en insérant des cellules et du contenu.

## Étape 4 : Sauvegarde du document modifié
Enfin, nous devons enregistrer le document modifié avec le tableau imbriqué. Utilisez le code suivant :

```csharp
doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

Assurez-vous de spécifier le chemin et le nom de fichier corrects pour le document de sortie.

### Exemple de code source pour une table imbriquée utilisant Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Cell cell = builder.InsertCell();
	builder.Writeln("Outer Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Outer Table Cell 2");
	// Cet appel est important pour créer une table imbriquée au sein de la première table.
	// Sans cet appel, les cellules insérées ci-dessous seront ajoutées au tableau externe.
	builder.EndTable();
	// Accédez à la première cellule du tableau externe.
	builder.MoveTo(cell.FirstParagraph);
	// Construisez la table intérieure.
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 2");
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

## Conclusion
Dans ce didacticiel, nous avons appris à créer un tableau imbriqué dans un document Word à l'aide d'Aspose.Words pour .NET. En suivant ce guide étape par étape et en implémentant le code C# fourni, vous pouvez créer par programme des tableaux imbriqués en fonction de vos besoins spécifiques dans vos documents Word.
