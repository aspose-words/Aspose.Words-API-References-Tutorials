---
title: Insérer la table des matières
linktitle: Insérer la table des matières
second_title: API de traitement de documents Aspose.Words
description: Apprenez à insérer une table des matières dans des documents Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/insert-table-of-contents/
---

Dans ce didacticiel complet, vous apprendrez à insérer une table des matières dans un document Word à l'aide de Aspose.Words pour .NET. Nous vous guiderons tout au long du processus et vous fournirons les extraits de code C# nécessaires. À la fin de ce guide, vous serez en mesure de générer une table des matières avec les titres et les numéros de page appropriés.

## Conditions préalables
Avant de commencer, assurez-vous que vous disposez des prérequis suivants :
- Bibliothèque Aspose.Words pour .NET installée sur votre système.

## Étape 1 : créer un nouveau document et DocumentBuilder
Pour commencer, créez un nouveau document à l'aide de la classe Document et initialisez un objet DocumentBuilder :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Insérer une table des matières
Ensuite, utilisez la méthode InsertTableOfContents de la classe DocumentBuilder pour insérer une table des matières. Spécifiez les options de mise en forme requises dans la méthode :

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## Étape 3 : Ajouter le contenu du document
Après avoir inséré la table des matières, ajoutez le contenu réel du document. Définissez les styles de titre appropriés à l'aide de StyleIdentifier :

```csharp
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## Étape 4 : Mettre à jour la table des matières
La table des matières nouvellement insérée sera initialement vide. Pour le remplir, mettez à jour les champs du document :

```csharp
doc.UpdateFields();
```

## Étape 5 : Enregistrer le document
Après avoir inséré la table des matières et mis à jour les champs, enregistrez le document dans un fichier à l'aide de la méthode Save de la classe Document :

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### Exemple de code source pour insérer une table des matières à l'aide de Aspose.Words pour .NET
Voici le code source complet pour insérer une table des matières en utilisant Aspose.Words pour .NET :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Initialiser DocumentBuilder avec l'objet Document
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insérer une table des matièresa
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Commencez le contenu réel du document sur la deuxième page.
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");


// La table des matières nouvellement insérée sera initialement vide.
// Il doit être rempli en mettant à jour les champs du document.
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```
