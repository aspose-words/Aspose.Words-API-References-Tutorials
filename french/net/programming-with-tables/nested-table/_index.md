---
title: Tableau imbriqué
linktitle: Tableau imbriqué
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à créer un tableau imbriqué dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-tables/nested-table/
---

Dans ce didacticiel, nous allons apprendre à créer un tableau imbriqué dans un document Word à l'aide de Aspose.Words pour .NET. Nous suivrons un guide étape par étape pour comprendre le code et implémenter cette fonctionnalité. À la fin de ce didacticiel, vous serez en mesure de créer des tableaux imbriqués dans vos documents Word par programmation.

## Étape 1 : configuration du projet
1. Lancez Visual Studio et créez un nouveau projet C#.
2. Ajoutez une référence à la bibliothèque Aspose.Words pour .NET.

## Etape 2 : Création du document et initialisation du générateur de document
Pour commencer à travailler avec le document et le générateur de documents, suivez ces étapes :

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// création de documents
Document doc = new Document();

// Initialiser le générateur de documents
DocumentBuilder builder = new DocumentBuilder(doc);
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel à votre répertoire de documents.

## Étape 3 : Construire la table imbriquée
Ensuite, nous allons construire le tableau imbriqué en insérant des cellules dans le tableau externe et en créant un nouveau tableau à l'intérieur de la première cellule. Utilisez le code suivant :

```csharp
// Insérer la première cellule du tableau externe
Cell cell = builder. InsertCell();
builder.Writeln("Cell 1 of the outer table");

// Insérer la deuxième cellule du tableau externe
builder. InsertCell();
builder.Writeln("Cell 2 of the outer table");

// Terminaison de la table extérieure
builder. EndTable();

// Accéder à la première cellule du tableau externe
builder.MoveTo(cell.FirstParagraph);

// Construire la table intérieure
builder. InsertCell();
builder.Writeln("Cell 1 of inner table");
builder. InsertCell();
builder.Writeln("Cell 2 of the inner table");

// Fin de la table intérieure
builder. EndTable();
```

Ici, nous utilisons le générateur de documents pour insérer des cellules et du contenu dans le tableau externe. Ensuite, nous déplaçons le curseur du générateur de document vers la première cellule du tableau externe et construisons un nouveau tableau à l'intérieur en insérant des cellules et du contenu.

## Étape 4 : Enregistrer le document modifié
Enfin, nous devons enregistrer le document modifié avec le tableau imbriqué. Utilisez le code suivant :

```csharp
doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects pour le document de sortie.

### Exemple de code source pour Nested Table utilisant Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Cell cell = builder.InsertCell();
	builder.Writeln("Outer Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Outer Table Cell 2");
	// Cet appel est important pour créer une table imbriquée dans la première table.
	// Sans cet appel, les cellules insérées ci-dessous seront ajoutées au tableau externe.
	builder.EndTable();
	// Déplacez-vous vers la première cellule du tableau externe.
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
Dans ce didacticiel, nous avons appris à créer un tableau imbriqué dans un document Word à l'aide de Aspose.Words pour .NET. En suivant ce guide étape par étape et en implémentant le code C# fourni, vous pouvez créer des tableaux imbriqués en fonction de vos besoins spécifiques dans vos documents Word par programmation.
