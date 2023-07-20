---
title: Définir la position de la note de bas de page et de la note de fin
linktitle: Définir la position de la note de bas de page et de la note de fin
second_title: API de traitement de documents Aspose.Words
description: Apprenez à définir la position des notes de bas de page et des notes de fin dans les documents Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---

Dans ce didacticiel étape par étape, nous vous expliquerons comment utiliser Aspose.Words pour .NET pour définir la position des notes de bas de page et des notes de fin dans un document Word. Nous vous expliquerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets.

 Pour commencer, assurez-vous que Aspose.Words pour .NET est installé et configuré dans votre environnement de développement. Si vous ne l'avez pas encore fait, téléchargez et installez la bibliothèque à partir de[Aspose.Releases] https://releases.aspose.com/words/net/.

## Étape 1 : Initialisation de l'objet document

 Tout d'abord, initialisez le`Document` objet en fournissant le chemin d'accès à votre document source :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");
```

## Étape 2 : Définition de la position de la note de bas de page et de la note de fin

 Ensuite, accédez au`FootnoteOptions` et`EndnoteOptions` propriétés du document pour définir la position des notes de bas de page et des notes de fin. Dans cet exemple, nous définissons la position des notes de bas de page sous le texte et la position des notes de fin à la fin de la section :

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

### FAQ

#### Q : Comment puis-je positionner les notes de bas de page et les notes de fin dans Aspose.Words ?

 R : Pour positionner les notes de bas de page et les notes de fin dans Aspose.Words, vous devez utiliser le`FootnoteOptions` classe et la`Position` propriété. Vous pouvez définir cette propriété sur la valeur de votre choix, telle que`BottomOfPage` (en bas de page) ou`EndOfSection`(en fin de rubrique).

#### Q : Est-il possible de personnaliser la position des notes de bas de page et des notes de fin pour chaque page ou section du document ?

R : Oui, il est possible de personnaliser la position des notes de bas de page et des notes de fin pour chaque page ou section du document. Vous pouvez utiliser les méthodes de manipulation de section et de page Aspose.Words pour définir des positions spécifiques pour les notes de bas de page et les notes de fin.

#### Q : Comment supprimer des notes de bas de page ou des notes de fin d'un document ?

 R : Pour supprimer des notes de bas de page ou des notes de fin d'un document dans Aspose.Words, vous pouvez utiliser des méthodes appropriées telles que`RemoveAllFootnotes` pour supprimer toutes les notes de bas de page ou`RemoveAllEndnotes` pour supprimer toutes les notes de fin. Veillez à enregistrer le document après avoir effectué ces opérations.

#### Q : Les notes de bas de page et les notes de fin peuvent-elles être placées en dehors des marges de la page ?

Non, par défaut, les notes de bas de page et les notes de fin ne peuvent pas être positionnées en dehors des marges de la page dans Aspose.Words. Cependant, vous pouvez ajuster les marges du document pour laisser plus d'espace pour les notes de bas de page et les notes de fin si nécessaire.

#### Q : Les notes de bas de page et les notes de fin peuvent-elles être personnalisées avec des styles de police ou de mise en forme spécifiques ?

R : Oui, vous pouvez personnaliser les notes de bas de page et les notes de fin avec des styles de police ou de formatage spécifiques dans Aspose.Words. Vous pouvez utiliser les méthodes et propriétés disponibles pour appliquer des styles de police, des couleurs, des tailles de police, etc. des notes de bas de page et des notes de fin.