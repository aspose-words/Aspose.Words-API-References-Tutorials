---
title: Supprimer les commentaires dans le pdf
linktitle: Supprimer les commentaires dans le pdf
second_title: Référence de l'API Aspose.Words pour .NET
description: Supprimez les commentaires dans un fichier PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-revisions/remove-comments-in-pdf/
---

Dans ce guide étape par étape, nous allons vous expliquer comment supprimer des commentaires dans un fichier PDF à l'aide de Aspose.Words pour .NET. Nous vous fournirons le code source complet et vous montrerons comment formater la sortie Markdown.

## Étape 1 : Chargement du document

La première étape consiste à charger le document contenant les commentaires.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Étape 2 : Masquer les commentaires dans le PDF

Nous allons configurer l'option de mise en page pour masquer les commentaires lors de la génération du PDF.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## Étape 3 : Enregistrez le document au format PDF

Enfin, nous enregistrerons le document au format PDF en supprimant les commentaires.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Formats de sortie Markdown

La sortie peut être formatée en Markdown pour améliorer la lisibilité. Par exemple :

```markdown
- Comments are hidden in the generated PDF.
```

### Exemple de code source pour Supprimer les commentaires dans Pdf en utilisant Aspose.Words pour .NET

Voici le code source complet pour supprimer les commentaires dans un fichier PDF en utilisant Aspose.Words pour .NET :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

// Masquez les commentaires dans le PDF.
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```