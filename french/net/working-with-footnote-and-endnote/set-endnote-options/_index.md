---
title: Définir les options de note de fin
linktitle: Définir les options de note de fin
second_title: Référence de l'API Aspose.Words pour .NET
description: Découvrez comment définir les options de note de fin dans les documents Word à l'aide d'Aspose.Words pour .NET. Tutoriel étape par étape avec un exemple de code source.
type: docs
weight: 10
url: /fr/net/working-with-footnote-and-endnote/set-endnote-options/
---

Dans ce didacticiel étape par étape, nous vous expliquerons comment utiliser Aspose.Words pour .NET pour définir les options de note de fin dans un document Word. Nous vous expliquerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets.

Pour commencer, assurez-vous que Aspose.Words pour .NET est installé et configuré dans votre environnement de développement. Si vous ne l'avez pas encore fait, téléchargez et installez la bibliothèque depuis le site officiel.

## Étape 1 : Initialisation de l'objet Document

 Tout d'abord, initialisez le`Document` objet en fournissant le chemin d'accès à votre document source :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Étape 2 : Initialisation de l'objet DocumentBuilder

 Ensuite, initialisez le`DocumentBuilder` objet pour effectuer des opérations sur le document :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Ajouter du texte et une note de fin

 Utilisez le`Write` méthode de la`DocumentBuilder` objet pour ajouter du texte au document, et l'objet`InsertFootnote` méthode pour insérer une note de fin :

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## Étape 4 : Définition des options de note de fin

 Accéder au`EndnoteOptions` propriété du document pour modifier les options de note de fin. Dans cet exemple, nous définissons la règle de redémarrage pour redémarrer sur chaque page et la position à la fin de la section :

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## Étape 5 : Enregistrer le document

Enfin, enregistrez le document modifié :

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

C'est ça! Vous avez défini avec succès les options de note de fin dans un document Word à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour Définir les options de note de fin à l'aide de Aspose.Words pour .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");

EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

N'hésitez pas à utiliser ce code dans vos propres projets et à le modifier en fonction de vos besoins spécifiques.
