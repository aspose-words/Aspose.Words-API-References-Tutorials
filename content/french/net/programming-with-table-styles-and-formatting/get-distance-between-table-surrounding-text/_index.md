---
title: Obtenir la distance entre le tableau entourant le texte
linktitle: Obtenir la distance entre le tableau entourant le texte
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour obtenir la distance entre le texte et un tableau dans un document Word à l'aide de Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-table-styles-and-formatting/get-distance-between-table-surrounding-text/
---

Dans ce didacticiel, nous vous expliquerons étape par étape le processus permettant d'obtenir la distance entre le texte environnant dans un tableau à l'aide de Aspose.Words pour .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous saurez comment accéder aux différentes distances entre un tableau et le texte qui l'entoure dans vos documents Word à l'aide d'Aspose.Words pour .NET.

## Étape 1 : Définir le répertoire des documents
Tout d'abord, vous devez définir le chemin d'accès à votre répertoire de documents. C'est là que se trouve votre document Word. Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Charger le document existant
 Ensuite, vous devez charger le document Word existant dans une instance du`Document` classe.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Étape 3 : Obtenir la distance entre le tableau et le texte environnant
 Pour obtenir la distance entre le tableau et le texte qui l'entoure, nous devons accéder au tableau dans le document à l'aide de la`GetChild()` méthode et la`NodeType.Table` propriété. On peut alors afficher les différentes distances en utilisant les propriétés du tableau`DistanceTop`, `DistanceBottom`, `DistanceRight` et`DistanceLeft`.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Console.WriteLine("Distance between table and top text: " + table.DistanceTop);
Console.WriteLine("Distance between table and bottom text: " + table.DistanceBottom);
Console.WriteLine("Distance between the table and the text on the right: " + table.DistanceRight);
Console.WriteLine("Distance between the table and the text on the left: " + table.DistanceLeft);
```

### Exemple de code source pour obtenir la distance entre le texte entourant la table à l'aide de Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Console.WriteLine("\nGet distance between table left, right, bottom, top and the surrounding text.");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Console.WriteLine(table.DistanceTop);
	Console.WriteLine(table.DistanceBottom);
	Console.WriteLine(table.DistanceRight);
	Console.WriteLine(table.DistanceLeft);
```

## Conclusion
Dans ce didacticiel, nous avons appris à obtenir la distance entre le texte environnant dans un tableau à l'aide de Aspose.Words pour .NET. En suivant ce guide étape par étape, vous pouvez facilement accéder aux différentes distances entre un tableau et le texte qui l'entoure dans vos documents Word. Aspose.Words offre une API puissante et flexible pour manipuler et formater des tableaux dans vos documents. Fort de ces connaissances, vous pourrez analyser la mise en page de vos tableaux par rapport au texte et répondre à des besoins spécifiques.