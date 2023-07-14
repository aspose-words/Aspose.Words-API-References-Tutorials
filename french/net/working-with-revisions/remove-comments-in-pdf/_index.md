---
title: Supprimer les commentaires dans le fichier PDF
linktitle: Supprimer les commentaires dans le fichier PDF
second_title: API de traitement de documents Aspose.Words
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

Voici le code source complet pour supprimer les commentaires dans un fichier PDF en utilisant Aspose.Words pour .NET :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

// Masquez les commentaires dans le PDF.
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Conclusion

Dans ce didacticiel, nous avons appris à supprimer les commentaires d'un fichier PDF à l'aide de Aspose.Words pour .NET. En utilisant les options de mise en page appropriées, nous avons pu masquer les commentaires lors de la génération du PDF. Aspose.Words pour .NET offre une grande flexibilité pour manipuler les fichiers Word et les convertir en différents formats, y compris PDF. Vous pouvez maintenant appliquer ces connaissances pour supprimer des commentaires dans vos propres fichiers PDF en utilisant Aspose.Words pour .NET.

### FAQ pour supprimer des commentaires dans un fichier pdf

#### Q : Comment télécharger un document dans Aspose.Words pour .NET ?

 R : Utilisez le`Document` classe de Aspose.Words pour .NET pour charger un document à partir d'un fichier. Vous pouvez spécifier le chemin d'accès complet au document.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q : Comment masquer les commentaires dans un PDF généré avec Aspose.Words pour .NET ?

 R : Utilisez le`CommentDisplayMode`propriété de la`LayoutOptions` objet pour configurer l'affichage des commentaires lors de la génération du PDF. Pour masquer les commentaires, définissez cette propriété sur`CommentDisplayMode.Hide`.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

#### Q : Comment enregistrer un document au format PDF avec Aspose.Words pour .NET ?

 R : Utilisez le`Save` méthode de la`Document` objet pour enregistrer le document au format PDF. Spécifiez le chemin complet du fichier PDF.

```csharp
doc.Save("path/to/the/file.pdf");
```