---
title: Par sections Html
linktitle: Par sections Html
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à diviser un document Word en sections Html en utilisant Aspose.Words pour .NET avec un exemple de code complet.
type: docs
weight: 10
url: /fr/net/split-document/by-sections-html/
---

Dans cet exemple, nous allons vous montrer comment diviser un document Word en sections distinctes au format HTML à l'aide de la fonctionnalité Par sections HTML d'Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et générer des documents HTML distincts pour chaque section.

## Étape 1 : Chargement du document

Pour commencer, spécifiez le répertoire de votre document et chargez le document dans un objet Document. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Étape 2 : Diviser le document en sections au format HTML

Nous allons maintenant définir les options d'enregistrement pour diviser le document en sections au format HTML. Voici comment procéder :

```csharp
HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };

doc.Save(dataDir + "SplitDocument.ParSectionsHtml.html", options);
```

### Exemple de code source pour By Sections HTML en utilisant Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité Par sections HTML d'Aspose.Words pour .NET :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");


HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };


doc.Save(dataDir + "SplitDocument.BySectionsHtml.html", options);
```

Avec ce code, vous pourrez diviser un document Word en sections distinctes au format HTML en utilisant Aspose.Words pour .NET.

Vous pouvez désormais générer des documents HTML distincts pour chaque section du document initial.



