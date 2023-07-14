---
title: Formatage de liste à plusieurs niveaux
linktitle: Formatage de liste à plusieurs niveaux
second_title: API de traitement de documents Aspose.Words
description: Apprenez à créer une liste à plusieurs niveaux et à appliquer une mise en forme personnalisée avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/document-formatting/multilevel-list-formatting/
---

Dans ce didacticiel, nous allons vous montrer comment utiliser la fonctionnalité de formatage de liste à plusieurs niveaux avec Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et appliquer les modifications.

## Étape 1 : Création et configuration du document

Pour commencer, créez un nouveau document et un objet DocumentBuilder associé. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Formater la liste à plusieurs niveaux

Nous allons maintenant appliquer la mise en forme de la liste multiniveau en utilisant les méthodes disponibles dans l'objet DocumentBuilder. Voici comment:

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder. Writen("Element 2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.1");
builder.Writeln("Element 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.2.1");
builder.Writeln("Element 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 3");

builder.ListFormat.RemoveNumbers();
```

## Étape 3 : Enregistrer le document

 Après avoir inséré le champ du formulaire de saisie de texte, enregistrez le document à l'emplacement souhaité à l'aide de la`Save` méthode. Assurez-vous de fournir le chemin d'accès au fichier approprié :

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

### Exemple de code source pour le formatage de liste à plusieurs niveaux à l'aide d'Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité de formatage de liste à plusieurs niveaux avec Aspose.Words pour .NET :


```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.ListFormat.ApplyNumberDefault();
	builder.Writeln("Item 1");
	builder.Writeln("Item 2");

	builder.ListFormat.ListIndent();
	builder.Writeln("Item 2.1");
	builder.Writeln("Item 2.2");
	
	builder.ListFormat.ListIndent();
	builder.Writeln("Item 2.2.1");
	builder.Writeln("Item 2.2.2");

	builder.ListFormat.ListOutdent();
	builder.Writeln("Item 2.3");

	builder.ListFormat.ListOutdent();
	builder.Writeln("Item 3");

	builder.ListFormat.RemoveNumbers();
	
	doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");

```

Avec ce code, vous pourrez créer une liste à plusieurs niveaux et appliquer le formatage approprié à chaque niveau en utilisant Aspose.Words pour .NET.