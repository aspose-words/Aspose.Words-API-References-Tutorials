---
title: Tableau fractionné
linktitle: Tableau fractionné
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à diviser un tableau dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-tables/split-table/
---

Dans ce didacticiel, nous allons apprendre à diviser un tableau dans un document Word à l'aide de Aspose.Words pour .NET. Nous suivrons un guide étape par étape pour comprendre le code et implémenter cette fonctionnalité. À la fin de ce didacticiel, vous serez en mesure de fractionner un tableau à partir d'une certaine ligne dans vos documents Word.

## Étape 1 : configuration du projet
1. Lancez Visual Studio et créez un nouveau projet C#.
2. Ajoutez une référence à la bibliothèque Aspose.Words pour .NET.

## Étape 2 : Chargement du document
Pour commencer à travailler avec le document, procédez comme suit :

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Charger le document
Document doc = new Document(dataDir + "Tables.docx");
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel à votre répertoire de documents et fournissez le nom de fichier correct.

## Étape 3 : diviser le tableau
Ensuite, nous allons diviser le tableau à partir d'une certaine ligne. Utilisez le code suivant :

```csharp
// Récupérer le premier tableau
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

// Détermination de la ligne à partir de laquelle diviser le tableau
Row row = firstTable.Rows[2];

// Créer un nouveau conteneur pour la table fractionnée
Table table = (Table)firstTable.Clone(false);

// Insérez le conteneur après la table d'origine
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

Ici, nous utilisons le document pour récupérer la première table du nœud de document. Ensuite, nous déterminons la ligne à partir de laquelle nous voulons scinder la table, dans cet exemple, il s'agit de la troisième ligne (index 2). Nous créons ensuite un nouveau conteneur en clonant la table d'origine, puis en l'insérant après la table d'origine. Nous ajoutons également un paragraphe tampon pour maintenir une distance entre les deux tables. Ensuite, nous déplaçons les lignes de la table d'origine vers la table fractionnée à l'aide d'une boucle do-while jusqu'à ce que nous atteignions la ligne spécifiée.

## Étape 4 : Enregistrer le document modifié
Enfin, nous devons sauvegarder le

  document modifié avec la table fractionnée. Utilisez le code suivant :

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects pour le document de sortie.

### Exemple de code source pour Split Table en utilisant Aspose.Words pour .NET 

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
// Nous diviserons le tableau à la troisième rangée (inclus).
Row row = firstTable.Rows[2];
// Créez un nouveau conteneur pour la table fractionnée.
Table table = (Table) firstTable.Clone(false);
// Insérez le conteneur après l'original.
firstTable.ParentNode.InsertAfter(table, firstTable);
// Ajoutez un paragraphe tampon pour vous assurer que les tableaux restent séparés.
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
Dans ce didacticiel, nous avons appris à diviser un tableau dans un document Word à l'aide de Aspose.Words pour .NET. En suivant ce guide étape par étape et en implémentant le code C # fourni, vous pouvez facilement diviser des tableaux à partir d'une certaine ligne dans vos documents Word.