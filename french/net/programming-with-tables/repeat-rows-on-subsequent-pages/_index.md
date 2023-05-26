---
title: Répéter les lignes sur les pages suivantes
linktitle: Répéter les lignes sur les pages suivantes
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à répéter les lignes d'un tableau sur les pages suivantes d'un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-tables/repeat-rows-on-subsequent-pages/
---

Dans ce didacticiel, nous allons apprendre à répéter les lignes d'un tableau sur les pages suivantes d'un document Word à l'aide de Aspose.Words pour .NET. Nous suivrons un guide étape par étape pour comprendre le code et implémenter cette fonctionnalité. À la fin de ce didacticiel, vous serez en mesure de spécifier les lignes à répéter sur les pages suivantes de votre tableau dans vos documents Word.

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

## Étape 3 : Construire le tableau avec des lignes répétées
Ensuite, nous allons créer un tableau avec des lignes répétées sur les pages suivantes. Utilisez le code suivant :

```csharp
// Début du tableau
builder. StartTable();

// Configuration des paramètres de la première ligne (lignes d'en-tête)
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;

// Insérer la première cellule de la première ligne
builder. InsertCell();
builder.Writeln("Header line 1");
builder. EndRow();

// Insérer la deuxième cellule de la première ligne
builder. InsertCell();
builder.Writeln("Header line 2");
builder. EndRow();

// Configurez les paramètres des lignes suivantes
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();

// Boucle pour insérer les cellules dans les lignes suivantes
for (int i = 0; i < 50; i++)
{
builder. InsertCell();
builder.RowFormat.HeadingFormat = false;
builder.Write("Text column 1");
builder. InsertCell();
builder.Write("Text column 2");
builder. EndRow();
}

// Fin de tableau
builder. EndTable();
```

 Ici, nous utilisons le générateur de documents pour créer un tableau avec deux lignes d'en-tête et plusieurs lignes de données. Le`RowFormat.HeadingFormat`Les paramètres sont utilisés pour marquer les lignes d'en-tête qui doivent être répétées sur les pages suivantes.

## Étape 4 : Enregistrer le document modifié
Enfin NOUS

  devez enregistrer le document modifié avec les lignes d'en-tête répétées sur les pages suivantes du tableau. Utilisez le code suivant :

```csharp
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects pour le document de sortie.

### Exemple de code source pour Répéter les lignes sur les pages suivantes à l'aide de Aspose.Words pour .NET 

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.StartTable();
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;
builder.InsertCell();
builder.Writeln("Heading row 1");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Heading row 2");
builder.EndRow();
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();
for (int i = 0; i < 50; i++)
{
	builder.InsertCell();
	builder.RowFormat.HeadingFormat = false;
	builder.Write("Column 1 Text");
	builder.InsertCell();
	builder.Write("Column 2 Text");
	builder.EndRow();
}
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

## Conclusion
Dans ce didacticiel, nous avons appris à répéter les lignes d'un tableau sur les pages suivantes d'un document Word à l'aide de Aspose.Words pour .NET. En suivant ce guide étape par étape et en implémentant le code C# fourni, vous pouvez spécifier les lignes à répéter en fonction de vos besoins spécifiques dans vos documents Word.