---
title: Obtenir les détails du groupe de révision
linktitle: Obtenir les détails du groupe de révision
second_title: Référence de l'API Aspose.Words pour .NET
description: Obtenez les détails du groupe de révision dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-revisions/get-revision-group-details/
---

Dans ce guide étape par étape, nous allons vous montrer comment obtenir les détails d'un groupe de révisions dans un document Word en utilisant Aspose.Words pour .NET. Nous vous fournirons le code source complet et vous montrerons comment formater la sortie Markdown.

## Étape 1 : Chargement du document

La première étape consiste à télécharger le document contenant les révisions.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Étape 2 : Parcourir les révisions

Ensuite, nous allons parcourir les révisions présentes dans le document et afficher leurs détails, tels que le type, l'auteur, la date et le texte révisé.

```csharp
foreach (Revision revision in doc.Revisions)
{
     string groupText = revision.Group != null
         ? "Revision group text: " + revision.Group.Text
         : "The revision does not belong to any group";

     Console.WriteLine("Type: " + revision.RevisionType);
     Console.WriteLine("Author: " + revision.Author);
     Console.WriteLine("Date: " + revision.DateTime);
     Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
     Console.WriteLine(groupText);
}
```


### Exemple de code source pour obtenir les détails du groupe de révision à l'aide de Aspose.Words pour .NET

Voici le code source complet pour obtenir les détails d'un groupe de révisions dans un document en utilisant Aspose.Words pour .NET :

```csharp

	Document doc = new Document(MyDir + "Revisions.docx");

	foreach (Revision revision in doc.Revisions)
	{
		 string groupText = revision.Group != null
			 ? "Revision group text: " + revision.Group.Text
			 : "The revision does not belong to any group";

		 Console.WriteLine("Type: " + revision.RevisionType);
		 Console.WriteLine("Author: " + revision.Author);
		 Console.WriteLine("Date: " + revision.DateTime);
		 Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
		 Console.WriteLine(groupText);
	}
	
```

