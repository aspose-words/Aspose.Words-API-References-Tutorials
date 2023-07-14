---
title: Obtenir le séparateur de style de paragraphe
linktitle: Obtenir le séparateur de style de paragraphe
second_title: API de traitement de documents Aspose.Words
description: Apprenez à obtenir le séparateur de style de paragraphe avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/document-formatting/get-paragraph-style-separator/
---

Dans ce didacticiel, nous allons vous expliquer comment utiliser la fonctionnalité Get Paragraph Style Separator avec Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et appliquer les modifications.

## Étape 1 : Chargement du document

Pour commencer, spécifiez le répertoire de vos documents et chargez le document dans un objet Document. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## Étape 2 : Trouver des séparateurs de style de paragraphe

Nous allons maintenant parcourir tous les paragraphes du document et vérifier si un paragraphe est un séparateur de style. Voici comment:

```csharp
foreach(Paragraph paragraph in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (paragraph.BreakIsStyleSeparator)
     {
         Console.WriteLine("Separator found!");
     }
}
```

### Exemple de code source pour Get Paragraph Style Separator en utilisant Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité Get Paragraph Style Separator avec Aspose.Words pour .NET :

```csharp

            Document doc = new Document(MyDir + "Document.docx");

            foreach (Paragraph paragraph in doc.GetChildNodes(NodeType.Paragraph, true))
            {
                if (paragraph.BreakIsStyleSeparator)
                {
                    Console.WriteLine("Separator Found!");
                }
            }
        
```

Avec ce code, vous pourrez trouver les séparateurs de style de paragraphe dans un document en utilisant Aspose.Words pour .NET.

