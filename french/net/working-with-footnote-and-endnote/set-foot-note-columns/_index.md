---
title: Définir des colonnes de notes de bas de page
linktitle: Définir des colonnes de notes de bas de page
second_title: Référence de l'API Aspose.Words pour .NET
description: Découvrez comment définir le nombre de colonnes pour les notes de bas de page dans les documents Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-footnote-and-endnote/set-foot-note-columns/
---

Dans ce tutoriel étape par étape, nous vous expliquerons comment utiliser Aspose.Words pour .NET pour définir le nombre de colonnes pour les notes de bas de page dans un document Word. Nous vous expliquerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets.

Pour commencer, assurez-vous que Aspose.Words pour .NET est installé et configuré dans votre environnement de développement. Si vous ne l'avez pas encore fait, téléchargez et installez la bibliothèque depuis le site officiel.

## Étape 1 : Initialisation de l'objet Document

 Tout d'abord, initialisez le`Document` objet en fournissant le chemin d'accès à votre document source :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Étape 2 : Définition des colonnes de note de bas de page

 Ensuite, accédez au`FootnoteOptions`propriété du document et définissez la`Columns` propriété pour spécifier le nombre de colonnes pour les notes de bas de page. Dans cet exemple, nous le définissons sur 3 colonnes :

```csharp
doc.FootnoteOptions.Columns = 3;
```

## Étape 3 : Enregistrer le document

Enfin, enregistrez le document modifié :

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootNoteColumns.docx");
```

C'est ça! Vous avez défini avec succès le nombre de colonnes pour les notes de bas de page dans un document Word à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour Set Footnote Columns à l'aide de Aspose.Words pour .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
Document doc = new Document(dataDir + "Document.docx");

// Spécifiez le nombre de colonnes avec lesquelles la zone des notes de bas de page est formatée.
doc.FootnoteOptions.Columns = 3;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootNoteColumns.docx");
```

N'hésitez pas à utiliser ce code dans vos propres projets et à le modifier en fonction de vos besoins spécifiques.