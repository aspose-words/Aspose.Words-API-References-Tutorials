---
title: Accéder à la version révisée
linktitle: Accéder à la version révisée
second_title: Référence de l'API Aspose.Words pour .NET
description: Accédez à une version révisée d'un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-revisions/access-revised-version/
---

Dans ce guide étape par étape, nous allons vous montrer comment accéder à la version révisée d'un document Word en utilisant Aspose.Words pour .NET. Nous vous fournirons le code source complet et vous montrerons comment formater la sortie Markdown.

## Étape 1 : Chargement du document

La première étape consiste à télécharger le document contenant les révisions.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## Étape 2 : Accéder à la version révisée

Nous allons maintenant passer à la version révisée du document.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## Étape 3 : Parcourir les révisions

Ensuite, nous allons parcourir les révisions présentes dans le document et afficher des informations spécifiques pour les paragraphes qui sont des éléments de liste.

```csharp
foreach (Revision revision in doc.Revisions)
{
     if (revision.ParentNode.NodeType == NodeType.Paragraph)
     {
         Paragraph paragraph = (Paragraph)revision.ParentNode;
         if (paragraph.IsListItem)
         {
             Console.WriteLine(paragraph.ListLabel.LabelString);
             Console.WriteLine(paragraph.ListFormat.ListLevel);
         }
     }
}
```

### Exemple de code source pour Access Revised Version utilisant Aspose.Words pour .NET

Voici le code source complet pour accéder à la version révisée d'un document en utilisant Aspose.Words pour .NET :

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();

// Passez à la version révisée du document.
doc.RevisionsView = RevisionsView.Final;

foreach (Revision revision in doc.Revisions)
{
	 if (revision.ParentNode.NodeType == NodeType.Paragraph)
	 {
		 Paragraph paragraph = (Paragraph)revision.ParentNode;
		 if (paragraph.IsListItem)
		 {
			 Console.WriteLine(paragraph.ListLabel.LabelString);
			 Console.WriteLine(paragraph.ListFormat.ListLevel);
		 }
	 }
}
```


