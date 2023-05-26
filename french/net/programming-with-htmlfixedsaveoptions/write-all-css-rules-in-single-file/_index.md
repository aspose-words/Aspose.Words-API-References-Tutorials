---
title: Écrire toutes les règles CSS dans un seul fichier
linktitle: Écrire toutes les règles CSS dans un seul fichier
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à convertir un document Word en HTML fixe en écrivant toutes les règles CSS dans un seul fichier avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---

Lors de la conversion d'un document Word en HTML fixe dans une application C#, vous souhaiterez peut-être regrouper toutes les règles CSS dans un seul fichier pour une meilleure organisation et portabilité. Avec la bibliothèque Aspose.Words pour .NET, vous pouvez facilement spécifier cette fonctionnalité à l'aide des options d'enregistrement HtmlFixedSaveOptions. Dans ce guide étape par étape, nous vous expliquerons comment utiliser Aspose.Words pour le code source .NET C# pour convertir un document Word en HTML fixe en écrivant toutes les règles CSS dans un seul fichier à l'aide des options d'enregistrement HtmlFixedSaveOptions.

## Comprendre la bibliothèque Aspose.Words

Avant de plonger dans le code, il est important de comprendre la bibliothèque Aspose.Words pour .NET. Aspose.Words est une bibliothèque puissante pour créer, éditer, convertir et protéger des documents Word sur différentes plates-formes, y compris .NET. Il offre de nombreuses fonctionnalités pour manipuler des documents, telles que l'insertion de texte, la modification de la mise en forme, l'ajout de sections et bien plus encore.

## Chargement du document Word

La première étape consiste à charger le document Word que vous souhaitez convertir en HTML fixe. Utilisez la classe Document pour charger le document à partir du fichier source. Voici un exemple :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

Dans cet exemple, nous chargeons le document "Document.docx" situé dans le répertoire des documents.

## Configuration des options de sauvegarde

L'étape suivante consiste à configurer les options d'enregistrement pour la conversion en HTML fixe. Utilisez la classe HtmlFixedSaveOptions et définissez la propriété SaveFontFaceCssSeparately sur false pour écrire toutes les règles CSS dans un seul fichier. Voici comment procéder :

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };
```

Nous créons un nouvel objet HtmlFixedSaveOptions et définissons la propriété SaveFontFaceCssSeparately sur false pour écrire toutes les règles CSS dans un seul fichier.

## Conversion de document HTML fixe

Maintenant que nous avons configuré les options de sauvegarde, nous pouvons procéder à la conversion du document en HTML fixe. Utilisez la méthode Save de la classe Document pour enregistrer le document converti au format HTML fixe en spécifiant les options d'enregistrement. Voici un exemple :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

Dans cet exemple, nous enregistrons le document converti sous "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html" en utilisant les options d'enregistrement spécifiées.

### Exemple de code source pour HtmlFixedSaveOptions avec la fonction "Écrire toutes les règles CSS dans un seul fichier" en utilisant Aspose.Words pour .NET

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Charger le document Word
Document doc = new Document(dataDir + "Document.docx");

// Configurez les options de sauvegarde avec la fonction "Écrire toutes les règles CSS dans un seul fichier"
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };

// Convertir le document en HTML fixe
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## Conclusion

Dans ce guide, nous avons expliqué comment convertir un document Word en HTML fixe en écrivant toutes les règles CSS dans un seul fichier à l'aide de HtmlFixedSaveOptions avec la bibliothèque Aspose.Words pour .NET. En suivant les étapes fournies et en utilisant le code source C# fourni, vous pouvez facilement appliquer cette fonctionnalité dans votre application C#. L'écriture de toutes les règles CSS dans un seul fichier facilite l'organisation et la gestion du code HTML généré lors de la conversion du document.