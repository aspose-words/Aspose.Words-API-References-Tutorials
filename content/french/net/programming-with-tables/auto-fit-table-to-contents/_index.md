---
title: Ajuster automatiquement le tableau au contenu
linktitle: Ajuster automatiquement le tableau au contenu
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment adapter automatiquement un tableau à son contenu dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-tables/auto-fit-table-to-contents/
---

Dans ce didacticiel, nous allons apprendre à utiliser Aspose.Words for .NET pour ajuster automatiquement un tableau à son contenu dans un document Word à l'aide de C#. Nous passerons en revue le processus étape par étape d’écriture de code pour obtenir cette fonctionnalité. À la fin de ce didacticiel, vous comprendrez clairement comment manipuler par programmation les tableaux dans les documents Word.

## Étape 1 : Configurer le projet
1. Lancez Visual Studio et créez un nouveau projet C#.
2. Ajoutez une référence à la bibliothèque Aspose.Words pour .NET.

## Étape 2 : Chargez le document Word
Pour démarrer le traitement de texte avec le tableau, nous devons charger le document Word qui contient le tableau. Suivez ces étapes:

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Charger le document Word
Document doc = new Document(dataDir + "Tables.docx");
```

Assurez-vous de remplacer « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin réel d'accès à votre document.

## Étape 3 : accédez au tableau et ajustez-le automatiquement au contenu
Ensuite, nous devons accéder au tableau dans le document et appliquer le comportement d'ajustement automatique. Utilisez le code suivant :

```csharp
// Accéder au tableau
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

// Ajuster automatiquement le tableau à son contenu
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

 Ici, nous castons le premier nœud enfant de type`Table` à partir du document, puis en utilisant le`AutoFit` méthode avec le`AutoFitToContents` comportement pour ajuster la largeur du tableau en fonction de son contenu.

## Étape 4 : Enregistrez le document modifié
Enfin, nous devons enregistrer le document modifié avec le tableau auto-ajusté. Utilisez le code suivant :

```csharp
// Enregistrez le document modifié
doc.Save(dataDir + "WorkingWithTables.AutoFitTableToContents.docx");
```

Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects pour le document de sortie.

### Exemple de code source pour Ajuster automatiquement la table au contenu à l'aide d'Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	doc.Save(dataDir + "WorkingWithTables.AutoFitTableToContents.docx");
```

## Conclusion
Dans ce didacticiel, nous avons appris à ajuster automatiquement un tableau à son contenu dans un document Word à l'aide d'Aspose.Words pour .NET. En suivant le guide étape par étape et en implémentant le code C# fourni, vous pouvez manipuler les tableaux de vos documents Word par programme. Cela vous permet d'ajuster dynamiquement la largeur du tableau en fonction de son contenu, fournissant ainsi un document plus professionnel et visuellement attrayant.