---
title: Définir la position de la note de bas de page et de la note de fin
linktitle: Définir la position de la note de bas de page et de la note de fin
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à définir la position des notes de bas de page et des notes de fin dans les documents Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---

Dans ce didacticiel étape par étape, nous vous expliquerons comment utiliser Aspose.Words pour .NET pour définir la position des notes de bas de page et des notes de fin dans un document Word. Nous vous expliquerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets.

Pour commencer, assurez-vous que Aspose.Words pour .NET est installé et configuré dans votre environnement de développement. Si vous ne l'avez pas encore fait, téléchargez et installez la bibliothèque depuis le site officiel.

## Étape 1 : Initialisation de l'objet document

 Tout d'abord, initialisez le`Document` objet en fournissant le chemin d'accès à votre document source :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");
```

## Étape 2 : Définition de la position de la note de bas de page et de la note de fin

 Ensuite, accédez au`FootnoteOptions` et`EndnoteOptions`propriétés du document pour définir la position des notes de bas de page et des notes de fin. Dans cet exemple, nous définissons la position des notes de bas de page sous le texte et la position des notes de fin à la fin de la section :

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

## Étape 3 : Enregistrer le document

Enfin, enregistrez le document modifié :

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

C'est ça! Vous avez défini avec succès la position des notes de bas de page et des notes de fin dans un document Word à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour définir la position de la note de bas de page et de la note de fin à l'aide de Aspose.Words pour .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");

doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

N'hésitez pas à utiliser ce code dans vos propres projets et à le modifier en fonction de vos besoins spécifiques.
