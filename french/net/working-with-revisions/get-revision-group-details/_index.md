---
title: Obtenir les détails du groupe de révision
linktitle: Obtenir les détails du groupe de révision
second_title: API de traitement de documents Aspose.Words
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

## Conclusion

Dans ce didacticiel, nous avons appris à obtenir les détails d'un groupe de révisions dans un document Word à l'aide de Aspose.Words pour .NET. En utilisant une boucle et les propriétés appropriées, nous avons pu afficher des détails tels que le type de révision, l'auteur, la date et le texte révisé. Aspose.Words pour .NET offre de nombreuses fonctionnalités puissantes pour manipuler les documents Word, y compris la gestion des révisions. Vous pouvez maintenant utiliser ces connaissances pour obtenir les détails du groupe de révision dans vos propres documents Word à l'aide d'Aspose.Words pour .NET.

### FAQ

#### Q : Comment charger un document avec des révisions dans Aspose.Words pour .NET ?

 R : Utilisez le`Document`classe de Aspose.Words pour .NET pour charger un document à partir d'un fichier contenant des révisions. Vous pouvez spécifier le chemin d'accès complet au document.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q : Comment puis-je obtenir les détails d'un groupe de révision dans Aspose.Words pour .NET ?

 R : Parcourez les révisions du document à l'aide d'une boucle et accédez aux propriétés de chaque révision pour obtenir les détails souhaités. Vous pouvez utiliser le`RevisionType`, `Author`, `DateTime` et`ParentNode` properties pour obtenir respectivement le type de révision, l'auteur, la date et le texte révisé.

```csharp
foreach (Revision revision in doc.Revisions)
{
      Console.WriteLine("Type: " + revision.RevisionType

);
      Console.WriteLine("Author: " + revision.Author);
      Console.WriteLine("Date: " + revision.DateTime);
      Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
}
```

#### Q : Comment vérifier si une révision appartient à un groupe dans Aspose.Words pour .NET ?

 R : Utilisez le`Group`propriété de la`Revision` objet pour vérifier si une révision appartient à un groupe. Si la`Group` la propriété est`null`cela signifie que la révision n'appartient à aucun groupe.

```csharp
if (revision.Group != null)
{
      // La révision appartient à un groupe
}
else
{
      // La révision n'appartient à aucun groupe
}
```