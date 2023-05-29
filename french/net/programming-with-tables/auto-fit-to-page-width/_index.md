---
title: Ajustement automatique à la largeur de la page
linktitle: Ajustement automatique à la largeur de la page
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à ajuster automatiquement un tableau à la largeur de la page dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-tables/auto-fit-to-page-width/
---

Dans ce didacticiel, nous apprendrons à utiliser Aspose.Words pour .NET pour ajuster automatiquement un tableau à la largeur de la page dans un document Word. Nous suivrons un guide étape par étape pour comprendre le code et implémenter cette fonctionnalité. À la fin de ce didacticiel, vous serez en mesure de manipuler par programmation des tableaux dans des documents Word.

## Étape 1 : configuration du projet
1. Lancez Visual Studio et créez un nouveau projet C#.
2. Ajoutez une référence à la bibliothèque Aspose.Words pour .NET.

## Étape 2 : Création et configuration du document
Pour commencer à travailler avec le tableau, nous devons créer un document et configurer le générateur de documents. Suivez ces étapes:

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Créer le document et le générateur de documents
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel à votre répertoire de documents.

## Étape 3 : Insertion et configuration du tableau
Ensuite, nous allons insérer un tableau dans le document avec une largeur qui occupe la moitié de la largeur de la page. Utilisez le code suivant :

```csharp
// Insérez le tableau et configurez sa largeur
Table table = builder. StartTable();
builder. InsertCell();
table. PreferredWidth = PreferredWidth. FromPercent(50);
builder.Writeln("Cell #1");
builder. InsertCell();
builder.Writeln("Cell #2");
builder. InsertCell();
builder.Writeln("Cell #3");
```

Ici, nous utilisons le générateur de documents pour commencer à créer le tableau, insérer des cellules et définir la largeur préférée du tableau à 50 % de la largeur de la page. Ensuite, nous ajoutons du texte dans chaque cellule.

## Étape 4 : Enregistrer le document modifié
Enfin, nous devons enregistrer le document modifié avec le tableau ajusté à la largeur de la page. Utilisez le code suivant :

```csharp
// Enregistrer le document modifié
doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects pour le document de sortie.
  
### Exemple de code source pour l'ajustement automatique à la largeur de la page à l'aide de Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Insérez un tableau dont la largeur occupe la moitié de la largeur de la page.
	Table table = builder.StartTable();
	builder.InsertCell();
	table.PreferredWidth = PreferredWidth.FromPercent(50);
	builder.Writeln("Cell #1");
	builder.InsertCell();
	builder.Writeln("Cell #2");
	builder.InsertCell();
	builder.Writeln("Cell #3");
	doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

## Conclusion
Dans ce didacticiel, nous avons appris à ajuster automatiquement un tableau à la largeur de la page dans un document Word à l'aide de Aspose.Words pour .NET. En suivant ce guide étape par étape et en implémentant le code C# fourni, vous pouvez manipuler des tableaux dans vos documents Word par programmation. Cette fonctionnalité permet d'adapter dynamiquement la largeur du tableau en fonction de la page, offrant ainsi un document professionnel et visuellement attrayant.