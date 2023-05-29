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



