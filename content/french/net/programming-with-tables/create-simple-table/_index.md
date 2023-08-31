---
title: Créer un tableau simple
linktitle: Créer un tableau simple
second_title: API de traitement de documents Aspose.Words
description: Apprenez à créer un tableau simple dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-tables/create-simple-table/
---

Dans ce didacticiel, nous allons apprendre à créer un tableau simple dans un document Word à l'aide d'Aspose.Words pour .NET. Nous suivrons un guide étape par étape pour comprendre le code et implémenter cette fonctionnalité. À la fin de ce didacticiel, vous pourrez créer des tableaux personnalisés dans vos documents Word par programmation.

## Étape 1 : Configuration du projet
1. Lancez Visual Studio et créez un nouveau projet C#.
2. Ajoutez une référence à la bibliothèque Aspose.Words pour .NET.

## Étape 2 : Création du document et initialisation du générateur de documents
Pour commencer à construire la table, nous devons créer un nouveau document et initialiser le générateur de documents. Suivez ces étapes:

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Créer le document et initialiser le générateur de documents
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Assurez-vous de remplacer « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin réel d'accès à votre répertoire de documents.

## Étape 3 : Construire le tableau
Ensuite, nous allons construire le tableau en utilisant les méthodes fournies par le générateur de documents. Utilisez le code suivant :

```csharp
// Commencer la construction du tableau
builder. StartTable();

// Construction de la première cellule de la première rangée
builder. InsertCell();
builder.Write("Contents of cell 1 of row 1.");

// Construction de la deuxième cellule de la première rangée
builder. InsertCell();
builder.Write("Contents of cell 2 of row 1.");

//Appelez la méthode suivante pour terminer la première ligne et démarrer une nouvelle ligne
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

 Ici, nous utilisons le générateur de documents pour construire le tableau étape par étape. On commence par appeler`StartTable()` pour initialiser la table, puis utilisez`InsertCell()` pour insérer des cellules et`Write()` pour ajouter du contenu à chaque cellule. Nous utilisons également`EndRow()` pour terminer une ligne et commencer une nouvelle ligne. Enfin, nous appelons`EndTable()` pour indiquer que la construction de la table est terminée.

## Étape 4 : Enregistrez le document
Enfin, nous devons économiser

  le document avec le tableau créé. Utilisez le code suivant :

```csharp
// Enregistrez le document
doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

Assurez-vous de spécifier le chemin et le nom de fichier corrects pour le document de sortie.

### Exemple de code source pour créer une table simple à l'aide d'Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Commencez à construire la table.
	builder.StartTable();
	builder.InsertCell();
	builder.Write("Row 1, Cell 1 Content.");
	// Construisez la deuxième cellule.
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content.");
	// Appelez la méthode suivante pour terminer la ligne et démarrer une nouvelle ligne.
	builder.EndRow();
	// Construisez la première cellule de la deuxième ligne.
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
Dans ce didacticiel, nous avons appris à créer un tableau simple dans un document Word à l'aide d'Aspose.Words pour .NET. En suivant ce guide étape par étape et en implémentant le code C# fourni, vous pouvez créer des tableaux personnalisés dans vos documents Word par programme. Cette fonctionnalité vous permet de formater et d'organiser vos données de manière structurée et claire.