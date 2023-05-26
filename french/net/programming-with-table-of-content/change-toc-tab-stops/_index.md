---
title: Modifier les taquets de tabulation de la table des matières
linktitle: Modifier les taquets de tabulation de la table des matières
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à modifier les onglets de la table des matières dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words pour .NET est une bibliothèque puissante pour créer, éditer et manipuler des documents Word dans une application C#. Parmi les fonctionnalités offertes par Aspose.Words, il y a la possibilité de modifier les onglets utilisés dans une table des matières d'un document Word. Dans ce guide, nous allons vous montrer comment utiliser le code source C# de Aspose.Words pour .NET pour modifier les onglets dans la table des matières d'un document.

## Comprendre la bibliothèque Aspose.Words

Avant de plonger dans le code, il est important de comprendre la bibliothèque Aspose.Words pour .NET. Aspose.Words est une bibliothèque populaire qui rend le travail avec les documents Word simple et efficace. Il offre un large éventail de fonctionnalités pour créer, éditer et manipuler des documents Word, y compris la modification des onglets de la table des matières.

## Chargement du document contenant la table des matières

La première étape consiste à charger le document Word contenant la table des matières que vous souhaitez modifier. Utilisez la classe Document pour charger le document à partir du fichier source. Voici un exemple :

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

Dans cet exemple, nous chargeons le document "Table of contents.docx" situé dans le répertoire documents.

## Changement d'onglet dans la table des matières

Une fois le document chargé, nous parcourons chaque paragraphe du document et vérifions s'il est formaté à l'aide des styles de résultat de la table des matières (TOC). Si c'est le cas, nous modifions les onglets utilisés pour aligner les numéros de page. Voici comment:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}
```

Dans cet exemple, nous utilisons une boucle pour parcourir chaque paragraphe du document. Nous vérifions ensuite si le paragraphe est formaté à l'aide des styles Table of Contents Result (TOC). Si tel est le cas, nous accédons au premier onglet utilisé dans ce paragraphe et le modifions en supprimant l'ancien onglet et en ajoutant un nouvel onglet avec une position modifiée.

## Enregistrer le document modifié

Une fois que vous avez apporté les modifications nécessaires aux onglets de la table des matières, vous pouvez enregistrer le document modifié à l'aide de la méthode Save de la classe Document. Voici un exemple :

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

Dans cet exemple, nous enregistrons le document modifié sous "WorkingWithTableOfContent.ChangeTocTabStops.docx".

### Exemple de code source pour la fonctionnalité "Modifier les onglets de la table des matières" avec Aspose.Words pour .NET

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document contenant la table des matières
Document doc = new Document(dataDir + "Table of contents.docx");

// Modifier les onglets de la table des matières
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}

// Enregistrer le document modifié
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

## Conclusion

Dans ce guide, nous avons expliqué comment utiliser Aspose.Words pour .NET pour modifier les onglets dans la table des matières d'un document Word à l'aide du code source C# fourni. En suivant les étapes fournies, vous pouvez facilement personnaliser les onglets de la table des matières de vos documents Word dans votre application C#. Aspose.Words offre une flexibilité et une puissance considérables pour travailler avec les styles et la mise en forme de vos documents, vous permettant de créer des documents Word attrayants et professionnels.