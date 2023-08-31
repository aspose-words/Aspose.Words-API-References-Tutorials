---
title: Exporter vers Markdown avec l'alignement du contenu du tableau
linktitle: Exporter vers Markdown avec l'alignement du contenu du tableau
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment exporter le contenu d'un tableau avec différents alignements vers des fichiers Markdown à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
Voici un guide étape par étape pour expliquer le code source C# suivant qui permet d'exporter du contenu vers un fichier Markdown avec l'alignement du contenu du tableau à l'aide de la bibliothèque Aspose.Words pour .NET. Assurez-vous d'avoir inclus la bibliothèque Aspose.Words dans votre projet avant d'utiliser ce code.

## Étape 1 : Définir le chemin du répertoire du document

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Assurez-vous de spécifier le chemin correct vers votre répertoire de documents où le document modifié sera enregistré.

## Étape 2 : Créer un document et un générateur de documents

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Ici, nous créons une instance du`Document` classe et une instance de`DocumentBuilder` classe qui nous permettra de manipuler le document et d’ajouter des éléments.

## Étape 3 : Insérez des cellules dans le tableau avec différents alignements de paragraphes

```csharp
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

Nous utilisons Document Builder pour insérer des cellules dans le tableau et définir différents alignements de paragraphe pour chaque cellule.

## Étape 4 : Définissez les options d'exportation Markdown et enregistrez le document modifié

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
     TableContentAlignment = TableContentAlignment.Left
};
doc.Save(dataDir + "Content_table_left_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "Content_table_right_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "Content_table_alignment_center.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Auto;
doc.Save(dataDir + "Content_table_auto_alignment.md", saveOptions);
```

Nous définissons les options d'exportation Markdown avec différents alignements du contenu du tableau, puis enregistrons le document modifié en utilisant chaque option d'alignement.

### Exemple de code source à exporter vers Markdown avec alignement du contenu du tableau à l'aide d'Aspose.Words pour .NET

```csharp

            
	// Le chemin d'accès au répertoire des documents.
    string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
	builder.Write("Cell1");
	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Write("Cell2");

	// Aligne tous les paragraphes du tableau.
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
	{
		TableContentAlignment = TableContentAlignment.Left
	};
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Right;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Center;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);

	// Dans ce cas, l'alignement sera pris à partir du premier paragraphe de la colonne correspondante du tableau.
	saveOptions.TableContentAlignment = TableContentAlignment.Auto;
	
	// Enregistrez le document modifié
	doc.Save(dataDir + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
            
        
```
