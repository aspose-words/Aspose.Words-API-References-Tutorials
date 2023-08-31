---
title: Insérer un tableau à partir de HTML
linktitle: Insérer un tableau à partir de HTML
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment insérer un tableau HTML dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-tables/insert-table-from-html/
---

Dans ce didacticiel, nous apprendrons comment insérer un tableau dans un document Word à partir de HTML à l'aide d'Aspose.Words pour .NET. Nous suivrons un guide étape par étape pour comprendre le code et implémenter cette fonctionnalité. À la fin de ce didacticiel, vous serez en mesure d'insérer par programme des tableaux HTML dans vos documents Word.

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

## Étape 3 : Insérer le tableau à partir du HTML
Ensuite, nous insérerons le tableau dans le document en utilisant le code HTML. Utilisez le code suivant :

```csharp
builder.InsertHtml("<table>" +
"<tr>" +
"<td>Line 1, Cell 1</td>" +
"<td>Line 1, Cell 2</td>" +
"</tr>" +
"<tr>" +
"<td>Line 2, Cell 1</td>" +
"<td>Line 2, Cell 2</td>" +
"</tr>" +
"</table>");
```

 Ici, nous utilisons le`InsertHtml` méthode du générateur de documents pour insérer le code HTML contenant le tableau. Le HTML spécifié crée un tableau avec deux lignes et deux cellules dans chaque ligne. Vous pouvez personnaliser le contenu du tableau en modifiant le code HTML selon vos besoins.

## Étape 4 : Sauvegarde du document modifié
Enfin, nous devons enregistrer le document modifié avec le tableau inséré depuis HTML. Utilisez le code suivant :

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

Assurez-vous de spécifier le chemin et le nom de fichier corrects pour le document de sortie.

### Exemple de code source pour Insérer une table à partir de HTML à l'aide d'Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Notez qu'AutoFitSettings ne s'applique pas aux tableaux insérés à partir de HTML.
	builder.InsertHtml("<table>" +
					   "<tr>" +
					   "<td>Row 1, Cell 1</td>" +
					   "<td>Row 1, Cell 2</td>" +
					   "</tr>" +
					   "<tr>" +
					   "<td>Row 2, Cell 2</td>" +
					   "<td>Row 2, Cell 2</td>" +
					   "</tr>" +
					   "</table>");
	doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

## Conclusion
Dans ce didacticiel, nous avons appris à insérer un tableau dans un document Word à partir de HTML à l'aide d'Aspose.Words pour .NET. En suivant ce guide étape par étape et en implémentant le code C# fourni, vous pouvez insérer des tableaux HTML dans vos documents Word par programme. Cette fonctionnalité vous permet de convertir et d'importer des données tabulaires à partir de sources HTML dans vos documents Word.
