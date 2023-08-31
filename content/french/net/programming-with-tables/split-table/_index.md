---
title: Tableau divisé
linktitle: Tableau divisé
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment diviser un tableau dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-tables/split-table/
---

Dans ce didacticiel, nous allons apprendre à diviser un tableau dans un document Word à l'aide d'Aspose.Words pour .NET. Nous suivrons un guide étape par étape pour comprendre le code et implémenter cette fonctionnalité. À la fin de ce didacticiel, vous pourrez diviser un tableau d'une certaine ligne dans vos documents Word.

## Étape 1 : Configuration du projet
1. Lancez Visual Studio et créez un nouveau projet C#.
2. Ajoutez une référence à la bibliothèque Aspose.Words pour .NET.

## Étape 2 : Chargement du document
Pour démarrer le traitement de texte avec le document, procédez comme suit :

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document
Document doc = new Document(dataDir + "Tables.docx");
```

Assurez-vous de remplacer « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin réel d'accès à votre répertoire de documents et fournissez le nom de fichier correct.

## Étape 3 : Diviser la table
Ensuite, nous diviserons le tableau d'une certaine ligne. Utilisez le code suivant :

```csharp
// Récupérer le premier tableau
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

// Détermination de la ligne à partir de laquelle diviser le tableau
Row row = firstTable.Rows[2];

// Créer un nouveau conteneur pour la table fractionnée
Table table = (Table)firstTable.Clone(false);

// Insérez le conteneur après le tableau d'origine
firstTable.ParentNode.InsertAfter(table, firstTable);

// Ajouter un paragraphe tampon pour maintenir une distance entre les tableaux
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);

// Déplacer les lignes de la table d'origine vers la table fractionnée
Row currentRow;
do
{
currentRow = firstTable.LastRow;
table. PrependChild(currentRow);
} while (currentRow != row);
```

Ici, nous utilisons le document pour récupérer la première table du nœud de document. Ensuite, nous déterminons la ligne à partir de laquelle nous voulons diviser le tableau, dans cet exemple il s'agit de la troisième ligne (index 2). Nous créons ensuite un nouveau conteneur en clonant la table d'origine, puis l'insérons après la table d'origine. Nous ajoutons également un paragraphe tampon pour maintenir une distance entre les deux tableaux. Ensuite, nous déplaçons les lignes de la table d'origine vers la table fractionnée à l'aide d'une boucle do-while jusqu'à ce que nous atteignions la ligne spécifiée.

## Étape 4 : Sauvegarde du document modifié
Enfin, nous devons sauvegarder le

  document modifié avec la table fractionnée. Utilisez le code suivant :

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

Assurez-vous de spécifier le chemin et le nom de fichier corrects pour le document de sortie.

### Exemple de code source pour Split Table à l'aide d'Aspose.Words pour .NET 

```csharp
//Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
// Nous diviserons le tableau à la troisième ligne (incluse).
Row row = firstTable.Rows[2];
// Créez un nouveau conteneur pour la table fractionnée.
Table table = (Table) firstTable.Clone(false);
// Insérez le récipient après l'original.
firstTable.ParentNode.InsertAfter(table, firstTable);
// Ajoutez un paragraphe tampon pour garantir que les tableaux restent séparés.
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);
Row currentRow;
do
{
	currentRow = firstTable.LastRow;
	table.PrependChild(currentRow);
} while (currentRow != row);
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

## Conclusion
Dans ce didacticiel, nous avons appris à diviser un tableau dans un document Word à l'aide d'Aspose.Words pour .NET. En suivant ce guide étape par étape et en implémentant le code C# fourni, vous pouvez facilement diviser les tableaux d'une certaine ligne dans vos documents Word.