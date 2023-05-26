---
title: Accès typé
linktitle: Accès typé
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à utiliser l'accès typé pour manipuler des tables dans Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-node/typed-access/
---

Voici un guide étape par étape pour expliquer le code source C # ci-dessous qui illustre comment utiliser la fonctionnalité d'accès typé avec Aspose.Words pour .NET.

## Étape 1 : Importez les références nécessaires
Avant de commencer, assurez-vous d'avoir importé les références nécessaires pour utiliser Aspose.Words pour .NET dans votre projet. Cela inclut l'importation de la bibliothèque Aspose.Words et l'ajout des espaces de noms requis à votre fichier source.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## Étape 2 : Créer un nouveau document
 Dans cette étape, nous allons créer un nouveau document en utilisant le`Document` classe.

```csharp
Document doc = new Document();
```

## Étape 3 : Accéder à la section et au corps
Pour accéder aux tableaux contenus dans le document, il faut d'abord accéder à la section et au corps du document.

```csharp
Section section = doc.FirstSection;
Body body = section.Body;
```

## Etape 4 : Accès rapide et typé aux tables
Maintenant que nous avons le corps du document, nous pouvons utiliser un accès rapide et typé pour accéder à toutes les tables contenues dans le corps.

```csharp
TableCollection tables = body.Tables;
```

## Étape 5 : Parcourir les tableaux
 En utilisant un`foreach` boucle, nous pouvons parcourir toutes les tables et effectuer des opérations spécifiques sur chaque table.

```csharp
foreach(Table table in tables)
{
     // Accès rapide et typé à la première ligne du tableau.
     table.FirstRow?.Remove();

     // Accès rapide et typé à la dernière ligne du tableau.
     table.LastRow?.Remove();
}
```

Dans cet exemple, nous supprimons la première et la dernière ligne de chaque table en utilisant l'accès rapide et typé fourni par Aspose.Words.

### Exemple de code source pour l'accès typé avec Aspose.Words pour .NET

```csharp
	Document doc = new Document();

	Section section = doc.FirstSection;
	Body body = section.Body;
	
	// Accès typé rapide à tous les nœuds enfants Table contenus dans le corps.
	TableCollection tables = body.Tables;

	foreach (Table table in tables)
	{
		// Accès tapé rapide à la première ligne du tableau.
		table.FirstRow?.Remove();

		// Accès tapé rapide à la dernière ligne du tableau.
		table.LastRow?.Remove();
	}
            
```

Il s'agit d'un exemple de code complet pour l'accès typé aux tables avec Aspose.Words pour .NET. Assurez-vous d'importer les références nécessaires et suivez les étapes décrites précédemment pour intégrer ce code dans votre projet.

---
