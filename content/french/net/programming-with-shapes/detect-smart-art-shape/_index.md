---
title: Détecter la forme artistique intelligente
linktitle: Détecter la forme artistique intelligente
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment détecter les formes Smart Art dans un document Word à l'aide d'Aspose.Words for .NET, en identifiant les représentations graphiques.
type: docs
weight: 10
url: /fr/net/programming-with-shapes/detect-smart-art-shape/
---

Ce didacticiel explique comment détecter les formes Smart Art dans un document Word à l'aide d'Aspose.Words pour .NET. Les formes Smart Art sont des représentations graphiques utilisées pour présenter visuellement des informations et des idées.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et du traitement de mots avec des documents Word.

## Étape 1 : configurer le répertoire de documents
 Commencez par configurer le chemin d’accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers le répertoire où se trouve votre document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Charger le document
 Chargez le document Word à l'aide du`Document` constructeur, en passant le chemin d'accès au document en paramètre.

```csharp
Document doc = new Document(dataDir + "Smart Art.docx");
```

## Étape 3 : Détecter les formes artistiques intelligentes
 Parcourez les nœuds enfants de type`Shape` dans le document en utilisant le`GetChildNodes`méthode. Vérifiez si chaque forme a Smart Art en utilisant le`HasSmart Art` propriété.

```csharp
int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
```

## Étape 4 : Afficher le résultat
Imprimez le nombre de formes avec Smart Art détectées dans le document.

```csharp
Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

### Exemple de code source pour Détecter la forme artistique intelligente à l'aide d'Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Smart Art.docx");
	int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
	Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

C'est ça! Vous avez détecté avec succès les formes Smart Art dans votre document Word à l’aide d’Aspose.Words pour .NET.