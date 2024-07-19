---
title: Définir la position des notes de bas de page et des notes de fin
linktitle: Définir la position des notes de bas de page et des notes de fin
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment définir la position des notes de bas de page et des notes de fin dans les documents Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---

Dans ce didacticiel étape par étape, nous vous expliquerons comment utiliser Aspose.Words for .NET pour définir la position des notes de bas de page et des notes de fin dans un document Word. Nous expliquerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets.

 Pour commencer, assurez-vous que Aspose.Words for .NET est installé et configuré dans votre environnement de développement. Si vous ne l'avez pas fait, téléchargez et installez la bibliothèque depuis[Aspose.Releases]https://releases.aspose.com/words/net/.

## Étape 1 : initialisation de l'objet document

 Tout d'abord, initialisez le`Document` objectez en fournissant le chemin d’accès à votre document source :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");
```

## Étape 2 : Définition de la position des notes de bas de page et des notes de fin

 Ensuite, accédez au`FootnoteOptions`et`EndnoteOptions`propriétés du document pour définir la position des notes de bas de page et des notes de fin. Dans cet exemple, nous définissons la position des notes de bas de page sous le texte et la position des notes de fin à la fin de la section :

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

## Étape 3 : enregistrement du document

Enfin, enregistrez le document modifié :

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

C'est ça! Vous avez réussi à définir la position des notes de bas de page et des notes de fin dans un document Word à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour définir la position des notes de bas de page et des notes de fin à l'aide d'Aspose.Words pour .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");

doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

N'hésitez pas à utiliser ce code dans vos propres projets et à le modifier en fonction de vos besoins spécifiques.

### FAQ

#### Q : Comment puis-je positionner les notes de bas de page et les notes de fin dans Aspose.Words ?

 R : Pour positionner les notes de bas de page et de fin dans Aspose.Words, vous devez utiliser le`FootnoteOptions` la classe et le`Position` propriété. Vous pouvez définir cette propriété sur n'importe quelle valeur souhaitée, telle que`BottomOfPage` (en bas de page) ou`EndOfSection` (à la fin de la section).

#### Q : Est-il possible de personnaliser la position des notes de bas de page et des notes de fin pour chaque page ou section du document ?

: Oui, il est possible de personnaliser la position des notes de bas de page et des notes de fin pour chaque page ou section du document. Vous pouvez utiliser les méthodes de manipulation de section et de page Aspose.Words pour définir des positions spécifiques pour les notes de bas de page et les notes de fin.

#### Q : Comment puis-je supprimer les notes de bas de page ou de fin d'un document ?

 R : Pour supprimer des notes de bas de page ou de fin d'un document dans Aspose.Words, vous pouvez utiliser des méthodes appropriées telles que`RemoveAllFootnotes` pour supprimer toutes les notes de bas de page ou`RemoveAllEndnotes` pour supprimer toutes les notes de fin. Assurez-vous de sauvegarder le document après avoir effectué ces opérations.

#### Q : Les notes de bas de page et de fin peuvent-elles être positionnées en dehors des marges de la page ?

Non, par défaut, les notes de bas de page et de fin ne peuvent pas être positionnées en dehors des marges de la page dans Aspose.Words. Cependant, vous pouvez ajuster les marges du document pour laisser plus d'espace pour les notes de bas de page et de fin si nécessaire.

#### Q : Les notes de bas de page et les notes de fin peuvent-elles être personnalisées avec une police ou des styles de formatage spécifiques ?

R : Oui, vous pouvez personnaliser les notes de bas de page et les notes de fin avec des styles de police ou de formatage spécifiques dans Aspose.Words. Vous pouvez utiliser les méthodes et propriétés disponibles pour appliquer des styles de police, des couleurs, des tailles de police, etc., des notes de bas de page et des notes de fin.