---
title: Détecter la forme d'art intelligente
linktitle: Détecter la forme d'art intelligente
second_title: API de traitement de documents Aspose.Words
description: Apprenez à détecter les formes Smart Art dans un document Word à l'aide d'Aspose.Words pour .NET, en identifiant les représentations graphiques.
type: docs
weight: 10
url: /fr/net/programming-with-shapes/detect-smart-art-shape/
---

Ce didacticiel explique comment détecter les formes Smart Art dans un document Word à l'aide de Aspose.Words pour .NET. Les formes Smart Art sont des représentations graphiques utilisées pour présenter visuellement des informations et des idées.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et du traitement de texte avec des documents Word.

## Étape 1 : Configurer le répertoire de documents
 Commencez par configurer le chemin d'accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel au répertoire où se trouve votre document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Charger le document
 Chargez le document Word à l'aide du`Document` constructeur, en passant le chemin d'accès au document en tant que paramètre.

```csharp
Document doc = new Document(dataDir + "Smart Art.docx");
```

## Étape 3 : Détecter les formes d'art intelligentes
 Itérer à travers les nœuds enfants de type`Shape` dans le document à l'aide de`GetChildNodes`méthode. Vérifiez si chaque forme a Smart Art en utilisant le`HasSmart Art` propriété.

```csharp
int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
```

## Étape 4 : sortie du résultat
Imprimez le nombre de formes avec Smart Art détectées dans le document.

```csharp
Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

### Exemple de code source pour détecter la forme d'art intelligente à l'aide de Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Smart Art.docx");
	int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
	Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

C'est ça! Vous avez détecté avec succès des formes Smart Art dans votre document Word à l'aide d'Aspose.Words pour .NET.