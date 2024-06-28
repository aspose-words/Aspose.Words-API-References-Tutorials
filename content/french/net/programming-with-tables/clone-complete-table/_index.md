---
title: Cloner la table complète
linktitle: Cloner la table complète
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment cloner un tableau entier dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-tables/clone-complete-table/
---

Dans ce didacticiel, nous apprendrons comment utiliser Aspose.Words for .NET pour cloner un tableau entier dans un document Word. Nous suivrons un guide étape par étape pour comprendre le code et implémenter cette fonctionnalité. À la fin de ce didacticiel, vous serez en mesure de cloner des tableaux dans vos documents Word par programme.

## Étape 1 : Configuration du projet
1. Lancez Visual Studio et créez un nouveau projet C#.
2. Ajoutez une référence à la bibliothèque Aspose.Words pour .NET.

## Étape 2 : Chargement du document et accès au tableau
Pour démarrer le traitement de texte avec le tableau, nous devons charger le document qui le contient et y accéder. Suivez ces étapes:

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document
Document doc = new Document(dataDir + "Tables.docx");

// Accès au tableau
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Assurez-vous de remplacer « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin réel d'accès à votre répertoire de documents.

## Étape 3 : Clonage complet de la baie
Ensuite, nous clonerons l'intégralité du tableau et l'insérerons dans le document après l'original. Utilisez le code suivant :

```csharp
// Cloner le tableau
Table tableClone = (Table)table.Clone(true);

// Insérez le tableau cloné dans le document après l'original
table.ParentNode.InsertAfter(tableClone, table);

// Insérer un paragraphe vide entre les deux tableaux
// Sinon, ils seront regroupés en un seul lors de la sauvegarde (cela est dû à la validation du document)
table.ParentNode.InsertAfter(new Paragraph(doc), table);
```

 Nous utilisons ici le`Clone` méthode pour créer une copie complète du tableau. Ensuite, nous utilisons`InsertAfter` pour insérer le tableau cloné dans le document, après le tableau d'origine. Nous ajoutons également un paragraphe vide entre les deux tableaux pour éviter qu'ils ne soient fusionnés lors de la sauvegarde.

## Étape 4 : Sauvegarde du document modifié
Enfin, nous devons enregistrer le document modifié avec la table clonée. Utilisez le code suivant :

```csharp
// Enregistrez le document modifié
doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

Assurez-vous de spécifier le chemin et le nom de fichier corrects pour le document de sortie.
  
### Exemple de code source pour Clone Complete Table à l’aide d’Aspose.Words for .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Clonez le tableau et insérez-le dans le document après l'original.
	Table tableClone = (Table) table.Clone(true);
	table.ParentNode.InsertAfter(tableClone, table);
	//Insérez un paragraphe vide entre les deux tableaux,
	// sinon, ils seront combinés en un seul lors de la sauvegarde, cela a à voir avec la validation du document.
	table.ParentNode.InsertAfter(new Paragraph(doc), table);
	doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

## Conclusion
Dans ce didacticiel, nous avons appris à cloner un tableau entier dans un document Word à l'aide d'Aspose.Words pour .NET. En suivant ce guide étape par étape et en implémentant le code C# fourni, vous pouvez cloner des tables dans vos documents Word par programme. Cette fonctionnalité vous permet d'effectuer des manipulations avancées sur les baies pour répondre à vos besoins spécifiques.