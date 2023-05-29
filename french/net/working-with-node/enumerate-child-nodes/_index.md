---
title: Énumérer les nœuds enfants
linktitle: Énumérer les nœuds enfants
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à énumérer les nœuds enfants dans un paragraphe avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-node/enumerate-child-nodes/
---

Voici un guide étape par étape pour expliquer le code source C # ci-dessous qui illustre comment énumérer les nœuds enfants à l'aide de Aspose.Words pour .NET.

## Étape 1 : Importez les références nécessaires
Avant de commencer, assurez-vous d'avoir importé les références nécessaires pour utiliser Aspose.Words pour .NET dans votre projet. Cela inclut l'importation de la bibliothèque Aspose.Words et l'ajout des espaces de noms requis à votre fichier source.

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
using Aspose.Words.NodeTypes;
```

## Étape 2 : Créer un nouveau document
 Dans cette étape, nous allons créer un nouveau document en utilisant le`Document` classe.

```csharp
Document doc = new Document();
```

## Étape 3 : Accéder au paragraphe et à ses nœuds enfants
 Pour énumérer les nœuds enfants d'un paragraphe, nous devons d'abord accéder au paragraphe lui-même. Utilisez le`GetChild` méthode avec la`Paragraph` type de nœud pour obtenir le premier paragraphe du document.

```csharp
Paragraph paragraph = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);
```

Ensuite, nous récupérons la collection des nœuds enfants du paragraphe à l'aide de la propriété`ChildNodes` propriété.

```csharp
NodeCollection children = paragraph. ChildNodes;
```

## Étape 4 : Parcourir les nœuds enfants
 Maintenant que nous avons la collection de nœuds enfants, nous pouvons les parcourir en boucle à l'aide d'un`foreach` boucle. Nous vérifions le type de chaque nœud enfant et effectuons des opérations spécifiques en fonction du type.

```csharp
foreach (Node child in children)
{
     // Un paragraphe peut contenir des enfants de différents types tels que des suites, des formes et autres.
     if (child. NodeType == NodeType.Run)
     {
         Run run = (Run)child;
         Console.WriteLine(run.Text);
     }
}
```

 Dans cet exemple, nous vérifions si le nœud enfant est de type`Run` (par exemple un fragment de texte). Si c'est le cas, nous convertissons le nœud en`Run` et afficher le texte à l'aide`run.Text`.

## Exemple de code source pour énumérer les nœuds enfants avec Aspose.Words pour .NET


```csharp
Document doc = new Document();
Paragraph paragraph = (Paragraph) doc.GetChild(NodeType.Paragraph, 0, true);

NodeCollection children = paragraph.ChildNodes;
foreach (Node child in children)
{
	// Un paragraphe peut contenir des enfants de différents types tels que des suites, des formes et autres.
	if (child.NodeType == NodeType.Run)
	{
		Run run = (Run) child;
		Console.WriteLine(run.Text);
	}
}
```

Ceci est un exemple de code complet pour énumérer les nœuds enfants d'un paragraphe avec Aspose.Words pour .NET. Assurez-vous d'importer les références

