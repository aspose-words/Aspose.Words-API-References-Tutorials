---
title: Cloner la table complète
linktitle: Cloner la table complète
second_title: API de traitement de documents Aspose.Words
description: Apprenez à cloner un tableau entier dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-tables/clone-complete-table/
---

Dans ce didacticiel, nous apprendrons à utiliser Aspose.Words pour .NET pour cloner un tableau entier dans un document Word. Nous suivrons un guide étape par étape pour comprendre le code et implémenter cette fonctionnalité. À la fin de ce didacticiel, vous serez en mesure de cloner des tableaux dans vos documents Word par programmation.

## Étape 1 : configuration du projet
1. Lancez Visual Studio et créez un nouveau projet C#.
2. Ajoutez une référence à la bibliothèque Aspose.Words pour .NET.

## Etape 2 : Chargement du document et accès au tableau
Pour démarrer le traitement de texte avec le tableau, nous devons charger le document qui le contient et y accéder. Suivez ces étapes:

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document
Document doc = new Document(dataDir + "Tables.docx");

// Accéder au tableau
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel à votre répertoire de documents.

## Étape 3 : Clonage complet de la baie
Ensuite, nous allons cloner le tableau entier et l'insérer dans le document après l'original. Utilisez le code suivant :

```csharp
// Cloner le tableau
Table tableClone = (Table)table.Clone(true);

// Insérez le tableau cloné dans le document après l'original
table.ParentNode.InsertAfter(tableClone, table);

// Insérer un paragraphe vide entre les deux tableaux
// Sinon, ils seront combinés en un seul lors de l'enregistrement (cela est dû à la validation du document)
table.ParentNode.InsertAfter(new Paragraph(doc), table);
```

 Ici, nous utilisons le`Clone` méthode pour créer une copie complète du tableau. Ensuite on utilise`InsertAfter` pour insérer le tableau cloné dans le document, après le tableau d'origine. Nous ajoutons également un paragraphe vide entre les deux tableaux pour éviter qu'ils ne soient fusionnés lors de l'enregistrement.

## Étape 4 : Enregistrer le document modifié
Enfin, nous devons enregistrer le document modifié avec la table clonée. Utilisez le code suivant :

```csharp
// Enregistrer le document modifié
doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects pour le document de sortie.
  
### Exemple de code source pour Clone Complete Table en utilisant Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	//Clonez le tableau et insérez-le dans le document après l'original.
	Table tableClone = (Table) table.Clone(true);
	table.ParentNode.InsertAfter(tableClone, table);
	// Insérer un paragraphe vide entre les deux tableaux,
	// ou bien ils seront combinés en un seul lors de l'enregistrement, cela a à voir avec la validation du document.
	table.ParentNode.InsertAfter(new Paragraph(doc), table);
	doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

## Conclusion
Dans ce didacticiel, nous avons appris à cloner un tableau entier dans un document Word à l'aide de Aspose.Words pour .NET. En suivant ce guide étape par étape et en implémentant le code C# fourni, vous pouvez cloner des tableaux dans vos documents Word par programmation. Cette fonctionnalité vous permet d'effectuer des manipulations avancées sur les baies en fonction de vos besoins spécifiques.