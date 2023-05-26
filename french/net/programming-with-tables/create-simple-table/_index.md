---
title: Créer un tableau simple
linktitle: Créer un tableau simple
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à créer un tableau simple dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-tables/create-simple-table/
---

Dans ce didacticiel, nous allons apprendre à créer un tableau simple dans un document Word à l'aide de Aspose.Words pour .NET. Nous suivrons un guide étape par étape pour comprendre le code et implémenter cette fonctionnalité. À la fin de ce didacticiel, vous serez en mesure de créer des tableaux personnalisés dans vos documents Word par programmation.

## Étape 1 : configuration du projet
1. Lancez Visual Studio et créez un nouveau projet C#.
2. Ajoutez une référence à la bibliothèque Aspose.Words pour .NET.

## Etape 2 : Création du document et initialisation du générateur de document
Pour commencer à construire la table, nous devons créer un nouveau document et initialiser le générateur de documents. Suivez ces étapes:

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Créer le document et initialiser le générateur de document
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel à votre répertoire de documents.

## Étape 3 : Construire le tableau
Ensuite, nous allons construire la table en utilisant les méthodes fournies par le générateur de document. Utilisez le code suivant :

```csharp
// Commencer la construction du tableau
builder. StartTable();

// Construction de la première cellule de la première rangée
builder. InsertCell();
builder.Write("Contents of cell 1 of row 1.");

// Construction de la deuxième cellule de la première rangée
builder. InsertCell();
builder.Write("Contents of cell 2 of row 1.");

//Appelez la méthode suivante pour terminer la première ligne et commencer une nouvelle ligne
builder. EndRow();

// Construction de la première cellule de la deuxième rangée
builder. InsertCell();
builder.Write("Contents of cell 1 of row 2.");

// Construction de la deuxième cellule de la deuxième rangée
builder. InsertCell();
builder.Write("Contents of cell 2 of row 2.");

// Appelez la méthode suivante pour terminer la deuxième ligne
builder. EndRow();

// Indication que la construction de la table est terminée
builder. EndTable();
```

 Ici, nous utilisons le générateur de documents pour construire le tableau étape par étape. On commence par appeler`StartTable()` pour initialiser la table, puis utilisez`InsertCell()` pour insérer des cellules et`Write()` pour ajouter du contenu à chaque cellule. Nous utilisons également`EndRow()` pour terminer une rangée et commencer une nouvelle rangée. Enfin, nous appelons`EndTable()` pour indiquer que la construction de la table est terminée.

## Étape 4 : Enregistrez le document
Enfin, il faut économiser

  le document avec le tableau créé. Utilisez le code suivant :

```csharp
// Enregistrer le document
doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects pour le document de sortie.

### Exemple de code source pour Créer une table simple à l'aide d'Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Commencez à construire le tableau.
	builder.StartTable();
	builder.InsertCell();
	builder.Write("Row 1, Cell 1 Content.");
	// Construisez la deuxième cellule.
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content.");
	// Appelez la méthode suivante pour terminer la ligne et commencer une nouvelle ligne.
	builder.EndRow();
	// Construisez la première cellule de la deuxième rangée.
	builder.InsertCell();
	builder.Write("Row 2, Cell 1 Content");
	// Construisez la deuxième cellule.
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content.");
	builder.EndRow();
	//Signalez que nous avons fini de construire la table.
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

## Conclusion
Dans ce didacticiel, nous avons appris à créer un tableau simple dans un document Word à l'aide de Aspose.Words pour .NET. En suivant ce guide étape par étape et en implémentant le code C# fourni, vous pouvez créer des tableaux personnalisés dans vos documents Word par programmation. Cette fonctionnalité vous permet de mettre en forme et d'organiser vos données de manière structurée et claire.