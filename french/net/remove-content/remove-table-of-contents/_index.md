---
title: Supprimer la table des matières
linktitle: Supprimer la table des matières
second_title: Référence de l'API Aspose.Words pour .NET
description: Découvrez comment supprimer la table des matières d'un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/remove-content/remove-table-of-contents/
---

Dans ce didacticiel, nous vous expliquerons comment supprimer la table des matières d'un document Word à l'aide de la bibliothèque Aspose.Words pour .NET. La table des matières peut parfois être redondante ou inutile, et ce code vous aidera à la supprimer efficacement. Nous vous fournirons un guide étape par étape pour vous aider à comprendre et à implémenter le code dans votre propre projet .NET.

## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
- Une connaissance pratique du langage de programmation C#
- La bibliothèque Aspose.Words pour .NET installée dans votre projet
- Un document Word contenant une table des matières que vous souhaitez supprimer

## Étape 1 : Définir le répertoire des documents
 Tout d'abord, vous devez définir le chemin du répertoire vers l'emplacement de votre document Word. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin approprié.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Téléchargez le document
 Ensuite, nous allons charger le document Word dans une instance du`Document` classe à l'aide de`Load` méthode.

```csharp
//Charger le document
Document doc = new Document(dataDir + "your-document.docx");
```

## Étape 3 : Supprimer la table des matières
 Pour supprimer la table des matières, nous allons parcourir le type TOC (table des matières)`FieldStart` nœuds dans le document. Nous allons stocker ces nœuds afin de pouvoir y accéder rapidement et créer une liste de nœuds à supprimer.

```csharp
// Stockez les nœuds FieldStart des champs TOC dans le document pour un accès rapide.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Il s'agit d'une liste pour stocker les nœuds trouvés dans la table des matières spécifiée. Ils seront supprimés à la fin de cette méthode.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
     if (start.FieldType == FieldType.FieldTOC)
     {
         fieldStarts.Add(start);
     }
}

// Vérifiez si l'index TOC spécifié existe.
if (index > fieldStarts.Count - 1)
     throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
     // Il est plus sûr de stocker ces nœuds et de les supprimer tous à la fin.
     nodeList.Add(currentNode);
     currentNode = currentNode.NextPreOrder(doc);

     // Lorsque nous rencontrons un nœud FieldEnd de type FieldTOC,
     // nous savons que nous sommes à la fin de la table des matières actuelle et nous nous arrêtons ici.
     if (currentNode.NodeType == NodeType.FieldEnd)
     {
         FieldEnd fieldEnd = (FieldEnd)currentNode;
         if (fieldEnd.FieldType == FieldType.FieldTOC)


             isRemoving = false;
     }
}

foreach(Node node in nodeList)
{
     node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```


### Exemple de code source pour supprimer la table des matières à l'aide de Aspose.Words pour .NET 
```csharp

// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
//Charger le document
Document doc = new Document(dataDir + "your-document.docx");

// Stockez les nœuds FieldStart des champs TOC dans le document pour un accès rapide.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Il s'agit d'une liste pour stocker les nœuds trouvés dans la table des matières spécifiée. Ils seront supprimés à la fin de cette méthode.
List<Node> nodeList = new List<Node>();

foreach (FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
	if (start.FieldType == FieldType.FieldTOC)
	{
		fieldStarts.Add(start);
	}
}

// Assurez-vous que la table des matières spécifiée par l'index transmis existe.
if (index > fieldStarts.Count - 1)
	throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
	// Il est plus sûr de stocker ces nœuds et de les supprimer tous en même temps plus tard.
	nodeList.Add(currentNode);
	currentNode = currentNode.NextPreOrder(doc);

	// Une fois que nous rencontrons un nœud FieldEnd de type FieldTOC,
	// nous savons que nous sommes à la fin de la table des matières actuelle et nous nous arrêtons ici.
	if (currentNode.NodeType == NodeType.FieldEnd)
	{
		FieldEnd fieldEnd = (FieldEnd) currentNode;
		if (fieldEnd.FieldType == FieldType.FieldTOC)
			isRemoving = false;
	}
}

foreach (Node node in nodeList)
{
	node.Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
        
```

## Conclusion
Dans ce didacticiel, nous avons présenté un guide étape par étape pour supprimer la table des matières d'un document Word à l'aide de la bibliothèque Aspose.Words pour .NET. En suivant le code et les instructions fournis, vous pouvez facilement éliminer la table des matières et améliorer la mise en page de votre document. N'oubliez pas d'adapter le chemin d'accès au répertoire et les noms de fichiers en fonction de vos besoins spécifiques.