---
title: Tableau
linktitle: Tableau
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à créer un tableau avec le guide pas à pas Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-markdown/table/
---


Dans cet exemple, nous vous expliquerons comment créer une table à l'aide de Aspose.Words pour .NET. Un tableau est une structure de données qui organise les informations en lignes et en colonnes.

## Étape 1 : Utiliser un générateur de documents

Tout d'abord, nous allons utiliser un générateur de document pour ajouter du contenu à notre document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```


## Étape 2 : Ajouter des cellules et des données

 Nous allons ajouter des cellules et des données à notre tableau en utilisant le`InsertCell` méthode et la`Writeln` méthode du générateur de documents.

```csharp
builder. InsertCell();
builder.Writeln("a");
builder. InsertCell();
builder.Writeln("b");

builder. InsertCell();
builder.Writeln("c");
builder. InsertCell();
builder.Writeln("d");
```

### Exemple de code source pour créer une table avec Aspose.Words pour .NET

```csharp
	// Utilisez un générateur de document pour ajouter du contenu au document.
	DocumentBuilder builder = new DocumentBuilder();

	// Ajoutez la première ligne.
	builder.InsertCell();
	builder.Writeln("a");
	builder.InsertCell();
	builder.Writeln("b");

	// Ajoutez la deuxième rangée.
	builder.InsertCell();
	builder.Writeln("c");
	builder.InsertCell();
	builder.Writeln("d");
            
```

Félicitation ! Vous avez maintenant appris à créer une table avec Aspose.Words pour .NET.
