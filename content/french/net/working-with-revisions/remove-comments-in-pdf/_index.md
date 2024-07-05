---
title: Supprimer les commentaires dans un fichier PDF
linktitle: Supprimer les commentaires dans un fichier PDF
second_title: API de traitement de documents Aspose.Words
description: Supprimez les commentaires dans un fichier PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-revisions/remove-comments-in-pdf/
---

Dans ce guide étape par étape, nous allons vous expliquer comment supprimer des commentaires dans un fichier PDF à l'aide d'Aspose.Words pour .NET. Nous vous fournirons le code source complet et vous montrerons comment formater la sortie markdown.

## Étape 1 : Chargement du document

La première étape consiste à charger le document contenant les commentaires.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Étape 2 : Masquer les commentaires dans le PDF

Nous allons configurer l'option de mise en page pour masquer les commentaires lors de la génération du PDF.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## Étape 3 : Enregistrez le document au format PDF

Enfin, nous enregistrerons le document au format PDF en supprimant les commentaires.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Formats de sortie Markdown

La sortie peut être formatée en markdown pour améliorer la lisibilité. Par exemple :

```markdown
- Comments are hidden in the generated PDF.
```

### Exemple de code source pour supprimer les commentaires dans un PDF à l'aide d'Aspose.Words pour .NET

Voici le code source complet pour supprimer les commentaires dans un fichier PDF à l'aide d'Aspose.Words for .NET :

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

// Masquer les commentaires dans le PDF.
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Conclusion

Dans ce didacticiel, nous avons appris à supprimer les commentaires d'un fichier PDF à l'aide d'Aspose.Words for .NET. En utilisant les options de mise en page appropriées, nous avons pu masquer les commentaires lors de la génération du PDF. Aspose.Words for .NET offre une grande flexibilité pour manipuler des fichiers Word et les convertir en différents formats, dont PDF. Vous pouvez désormais appliquer ces connaissances pour supprimer des commentaires dans vos propres fichiers PDF à l'aide d'Aspose.Words for .NET.

### FAQ pour supprimer des commentaires dans un fichier pdf

#### Q : Comment télécharger un document dans Aspose.Words pour .NET ?

 R : Utilisez le`Document` classe d'Aspose.Words pour .NET pour charger un document à partir d'un fichier. Vous pouvez spécifier le chemin complet du document.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q : Comment masquer les commentaires dans un PDF généré avec Aspose.Words for .NET ?

 R : Utilisez le`CommentDisplayMode` propriété du`LayoutOptions` objet pour configurer la manière dont les commentaires sont affichés lors de la génération du PDF. Pour masquer les commentaires, définissez cette propriété sur`CommentDisplayMode.Hide`.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

#### Q : Comment enregistrer un document au format PDF avec Aspose.Words pour .NET ?

 R : Utilisez le`Save` méthode du`Document` objet pour enregistrer le document au format PDF. Spécifiez le chemin complet du fichier PDF.

```csharp
doc.Save("path/to/the/file.pdf");
```