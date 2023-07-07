---
title: Afficher les révisions dans des bulles
linktitle: Afficher les révisions dans des bulles
second_title: Référence de l'API Aspose.Words pour .NET
description: Affichez les révisions dans des ballons avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-revisions/show-revisions-in-balloons/
---

Dans ce guide étape par étape, nous allons vous montrer comment afficher les révisions dans des bulles dans un document Word à l'aide de Aspose.Words pour .NET. Nous vous fournirons le code source complet et vous montrerons comment formater la sortie Markdown.

## Étape 1 : Chargement du document

La première étape consiste à télécharger le document contenant les révisions.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Étape 2 : Configurer les options d'affichage des avis

Nous allons configurer les options d'affichage pour rendre les révisions visibles dans les bulles.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## Étape 3 : Enregistrez le document au format PDF

Enfin, nous enregistrerons le document au format PDF avec les révisions affichées dans des bulles.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Formats de sortie Markdown

La sortie peut être formatée en Markdown pour améliorer la lisibilité. Par exemple :

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### Exemple de code source pour Afficher les révisions dans les bulles à l'aide de Aspose.Words pour .NET

Voici le code source complet pour afficher les révisions dans les bulles d'un document utilisant Aspose.Words pour .NET :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

// Les rendus insèrent des révisions en ligne, suppriment et formatent les révisions dans des bulles.
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
// Rend les barres de révision sur le côté droit d'une page.
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Conclusion

Dans ce didacticiel, nous avons appris à afficher les révisions dans des bulles dans un document Word à l'aide de Aspose.Words pour .NET. En utilisant les options d'affichage appropriées, nous avons pu rendre les révisions visibles dans des bulles avec des barres de révision sur le côté droit. Aspose.Words pour .NET offre de nombreuses fonctionnalités puissantes pour manipuler les documents Word, y compris la gestion des révisions. Vous pouvez maintenant utiliser ces connaissances pour afficher les révisions dans des bulles dans vos propres documents Word à l'aide d'Aspose.Words pour .NET.


### FAQ

#### Q : Comment télécharger un document dans Aspose.Words pour .NET ?

 R : Utilisez le`Document` classe de Aspose.Words pour .NET pour charger un document à partir d'un fichier. Vous pouvez spécifier le chemin d'accès complet au document.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q : Comment afficher les révisions dans des bulles avec Aspose.Words pour .NET ?

 R : Utilisez le`ShowInBalloons` propriété de la`RevisionOptions` objet pour configurer l'affichage des révisions dans les bulles. Vous pouvez définir cette propriété sur`ShowInBalloons.FormatAndDelete` pour afficher les révisions dans des bulles avec les révisions de suppression et de mise en forme.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
```

#### Q : Comment enregistrer un document au format PDF avec Aspose.Words pour .NET ?

 R : Utilisez le`Save` méthode de la`Document` objet pour enregistrer le document au format PDF. Vous devez spécifier le chemin de destination complet avec l'extension ".pdf".

```csharp
doc.Save("path/to/destination/document.pdf");
```