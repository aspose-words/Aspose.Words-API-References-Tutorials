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

## Conclusion

Dans ce didacticiel, nous avons appris à accéder à la version révisée d'un document Word à l'aide de Aspose.Words pour .NET. En chargeant le document, en naviguant vers la version révisée et en parcourant les révisions, nous avons pu obtenir des informations spécifiques pour les paragraphes qui sont des éléments de liste. Aspose.Words pour .NET offre des fonctionnalités puissantes pour manipuler des documents Word, y compris l'accès aux révisions. Vous pouvez maintenant utiliser ces connaissances pour accéder à la version révisée de vos propres documents Word en utilisant Aspose.Words pour .NET.

### FAQ

#### Q : Comment charger un document avec des révisions dans Aspose.Words pour .NET ?

 R : Utilisez le`Document`classe de Aspose.Words pour .NET pour charger un document à partir d'un fichier contenant des révisions. Vous pouvez spécifier le chemin d'accès complet au document.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q : Comment accéder à la version révisée d'un document dans Aspose.Words pour .NET ?

 R : Utilisez le`RevisionsView` propriété de la`Document` objet pour accéder à la version révisée du document. Vous pouvez définir la valeur de la`RevisionsView` propriété à`RevisionsView.Final` pour afficher la version finale sans les révisions.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### Q : Comment parcourir les révisions de documents dans Aspose.Words pour .NET ?

 R : Utilisez un`foreach` boucle pour parcourir les révisions présentes dans le document. Vous pouvez utiliser le`Revisions` propriété de la`Document` objet pour obtenir une collection de toutes les révisions du document.

```csharp
foreach (Revision revision in doc.Revisions)
{
     // Traiter chaque révision ici
}
```

#### Q : Comment vérifier si un paragraphe est un élément de liste dans Aspose.Words pour .NET ?

 R : Utilisez le`IsListItem` propriété de la`Paragraph` objet pour vérifier si un paragraphe est un élément de liste. Le`IsListItem` retours de propriété`true` si le paragraphe est un élément de liste, sinon il renvoie`false`.

```csharp
if (paragraph.IsListItem)
{
     // Le paragraphe est un élément de liste
}
else
{
     // Le paragraphe n'est pas un élément de liste
}
```