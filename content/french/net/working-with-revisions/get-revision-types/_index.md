---
title: Obtenir les types de révision de mots
linktitle: Obtenir les types de révision de mots
second_title: API de traitement de documents Aspose.Words
description: Obtenez les types de révision de mots dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-revisions/get-revision-types/
---

Dans ce guide étape par étape, nous allons vous expliquer comment obtenir les types de révisions de mots dans un document Word à l'aide d'Aspose.Words pour .NET. Nous vous fournirons le code source complet et vous montrerons comment formater la sortie markdown.

## Étape 1 : Chargement du document

La première étape consiste à télécharger le document contenant les révisions.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Étape 2 : Parcourez les paragraphes

Ensuite, nous passerons en revue les paragraphes du document et vérifierons les types de mots révisés associés à chaque paragraphe.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     if (paragraphs[i].IsMoveFromRevision)
         Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
     if (paragraphs[i].IsMoveToRevision)
         Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

### Exemple de code source pour obtenir les types de révision à l'aide d'Aspose.Words pour .NET

Voici le code source complet pour obtenir les types de révision dans un document à l'aide d'Aspose.Words for .NET :

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
	 if (paragraphs[i].IsMoveFromRevision)
		 Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
	 if (paragraphs[i].IsMoveToRevision)
		 Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

## Conclusion

Dans ce didacticiel, nous avons appris comment obtenir les types de révisions de mots dans un document Word à l'aide d'Aspose.Words pour .NET. Nous avons suivi les étapes pour charger le document, parcourir les paragraphes et vérifier les types de critiques de mots associés à chaque paragraphe. Vous pouvez désormais appliquer ces connaissances pour analyser les critiques de mots dans vos propres documents Word à l'aide d'Aspose.Words pour .NET.

### FAQ pour obtenir des types de mots de révision

#### Q : Comment télécharger un document dans Aspose.Words pour .NET ?

 R : Utilisez le`Document` classe d'Aspose.Words pour .NET pour charger un document à partir d'un fichier. Vous pouvez spécifier le chemin complet du document.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q : Comment parcourir les paragraphes d’un document dans Aspose.Words for .NET ?

 R : Utilisez le`Paragraphs` propriété de la section du document pour obtenir la collection de paragraphes. Vous pouvez ensuite utiliser une boucle pour parcourir chaque paragraphe.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     // Traitez chaque paragraphe ici
}
```

#### Q : Comment vérifier si un paragraphe a été déplacé (supprimé) dans Aspose.Words pour .NET ?

 R : Utilisez le texte d'un paragraphe`IsMoveFromRevision`propriété pour vérifier si elle a été déplacée (supprimée).

```csharp
if (paragraph. IsMove

FromRevision)
{
     // Le paragraphe a été déplacé (supprimé)
}
```

#### Q : Comment vérifier si un paragraphe a été déplacé (inséré) dans Aspose.Words pour .NET ?

 R : Utilisez le texte d'un paragraphe`IsMoveToRevision` propriété pour vérifier si elle a été déplacée (insérée).

```csharp
if (paragraph.IsMoveToRevision)
{
     // Le paragraphe a été déplacé (inséré)
}
```