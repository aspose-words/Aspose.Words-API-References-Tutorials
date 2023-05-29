---
title: Obtenir les types de révision
linktitle: Obtenir les types de révision
second_title: Référence de l'API Aspose.Words pour .NET
description: Obtenez des types de révision dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-revisions/get-revision-types/
---

Dans ce guide étape par étape, nous allons vous expliquer comment obtenir les types de révisions dans un document Word à l'aide de Aspose.Words pour .NET. Nous vous fournirons le code source complet et vous montrerons comment formater la sortie Markdown.

## Étape 1 : Chargement du document

La première étape consiste à télécharger le document contenant les révisions.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Étape 2 : Parcourir les paragraphes

Ensuite, nous allons parcourir les paragraphes du document et vérifier les types de révisions associées à chaque paragraphe.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     if (paragraphs[i].IsMoveFromRevision)
         Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
     if (paragraphs[i].IsMoveToRevision)
         Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

### Exemple de code source pour obtenir les types de révision à l'aide d'Aspose.Words pour .NET

Voici le code source complet permettant d'obtenir les types de révision dans un document à l'aide d'Aspose.Words pour .NET :

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
	 if (paragraphs[i].IsMoveFromRevision)
		 Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
	 if (paragraphs[i].IsMoveToRevision)
		 Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```
