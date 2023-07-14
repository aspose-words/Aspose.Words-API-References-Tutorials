---
title: Ajuster automatiquement le tableau au contenu
linktitle: Ajuster automatiquement le tableau au contenu
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment ajuster automatiquement un tableau à son contenu dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-tables/auto-fit-table-to-contents/
---

Dans ce didacticiel, nous apprendrons à utiliser Aspose.Words pour .NET pour adapter automatiquement un tableau à son contenu dans un document Word à l'aide de C#. Nous allons passer par le processus étape par étape d'écriture de code pour réaliser cette fonctionnalité. À la fin de ce didacticiel, vous comprendrez clairement comment manipuler des tableaux dans des documents Word par programme.

## Étape 1 : Configurer le projet
1. Lancez Visual Studio et créez un nouveau projet C#.
2. Ajoutez une référence à la bibliothèque Aspose.Words pour .NET.

## Étape 2 : Chargez le document Word
Pour démarrer le traitement de texte avec le tableau, nous devons charger le document Word qui contient le tableau. Suivez ces étapes:

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Charger le document Word
Document doc = new Document(dataDir + "Tables.docx");
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel à votre document.

## Étape 3 : Accédez au tableau et adaptez-le automatiquement au contenu
Ensuite, nous devons accéder au tableau dans le document et appliquer le comportement d'ajustement automatique. Utilisez le code suivant :

```csharp
// Accéder au tableau
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

// Ajuster automatiquement le tableau à son contenu
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

 Ici, nous coulons le premier nœud enfant de type`Table` à partir du document, puis à l'aide de la`AutoFit` méthode avec la`AutoFitToContents` comportement pour ajuster la largeur du tableau en fonction de son contenu.

## Étape 4 : Enregistrer le document modifié
Enfin, nous devons enregistrer le document modifié avec le tableau ajusté automatiquement. Utilisez le code suivant :

```csharp
// Enregistrer le document modifié
doc.Save(dataDir + "WorkingWithTables.AutoFitTableToContents.docx");
```

Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects pour le document de sortie.

### Exemple de code source pour l'ajustement automatique du tableau au contenu à l'aide d'Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	doc.Save(dataDir + "WorkingWithTables.AutoFitTableToContents.docx");
```

## Conclusion
Dans ce didacticiel, nous avons appris à ajuster automatiquement un tableau à son contenu dans un document Word à l'aide de Aspose.Words pour .NET. En suivant le guide étape par étape et en implémentant le code C# fourni, vous pouvez manipuler des tableaux dans vos documents Word par programmation. Cela vous permet d'ajuster dynamiquement la largeur du tableau en fonction de son contenu, fournissant un document plus professionnel et visuellement attrayant.