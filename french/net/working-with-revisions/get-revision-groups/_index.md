---
title: Obtenir des groupes de révision
linktitle: Obtenir des groupes de révision
second_title: Référence de l'API Aspose.Words pour .NET
description: Obtenez des groupes de révision dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-revisions/get-revision-groups/
---

Dans ce guide étape par étape, nous allons vous expliquer comment obtenir les groupes de révision dans un document Word à l'aide d'Aspose.Words pour .NET. Nous vous fournirons le code source complet et vous montrerons comment formater la sortie Markdown.

## Étape 1 : Chargement du document

La première étape consiste à télécharger le document contenant les révisions.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Étape 2 : Parcourir les groupes de révision

Ensuite, nous allons parcourir les groupes de révision présents dans le document et afficher leurs détails, tels que l'auteur, le type de révision et le texte révisé.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### Exemple de code source pour Get Revision Groups en utilisant Aspose.Words pour .NET

Voici le code source complet pour obtenir les groupes de révision dans un document utilisant Aspose.Words pour .NET :

```csharp

	Document doc = new Document(MyDir + "Revisions.docx");

	foreach(RevisionGroup group in doc.Revisions.Groups)
	{
		 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
		 Console.WriteLine(group.Text);
	}
	
```


