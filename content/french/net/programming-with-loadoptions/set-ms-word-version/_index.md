---
title: Définir la version de MS Word
linktitle: Définir la version de MS Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment charger un document avec une version spécifiée de MS Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-loadoptions/set-ms-word-version/
---
Lors du traitement de texte avec des documents Word dans une application C#, il peut être nécessaire de spécifier la version de Microsoft Word à utiliser lors du chargement du document. Avec la bibliothèque Aspose.Words pour .NET, vous pouvez facilement définir la version de MS Word à utiliser à l'aide de LoadOptions. Dans ce guide étape par étape, nous vous expliquerons comment utiliser le code source Aspose.Words pour .NET C# pour charger un document avec une version spécifiée de MS Word à l'aide des options de chargement LoadOptions.

## Comprendre la bibliothèque Aspose.Words

Avant de plonger dans le code, il est important de comprendre la bibliothèque Aspose.Words pour .NET. Aspose.Words est une bibliothèque puissante pour créer, éditer, convertir et protéger des documents Word sur différentes plates-formes, dont .NET. Il offre de nombreuses fonctionnalités pour manipuler des documents, telles que l'insertion de texte, la modification du formatage, l'ajout de sections et bien plus encore.

## Configuration des options de chargement

La première étape consiste à configurer les options de chargement de notre document. Utilisez la classe LoadOptions pour spécifier les paramètres de chargement. Dans notre cas, nous devons définir la propriété MswVersion sur la version souhaitée de MS Word. Par exemple, nous utilisons la version Microsoft Word 2010. Voici comment faire:

```csharp
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };
```

Nous créons un nouvel objet LoadOptions et définissons la propriété MswVersion sur MsWordVersion.Word2010 pour spécifier la version de MS Word 2010.

## Chargement de documents avec la version spécifiée de MS Word

Maintenant que nous avons configuré les options de chargement, nous pouvons charger le document à l'aide de la classe Document et spécifier les options de chargement. Voici un exemple :

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

Dans cet exemple, nous chargeons le document "Document.docx" situé dans le répertoire documents en utilisant les options de chargement spécifiées.

### Exemple de code source pour LoadOptions avec la fonctionnalité « Définir la version MS Word » à l'aide d'Aspose.Words pour .NET

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Configurez les options de chargement avec la fonctionnalité « Définir la version MS Word »
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };

// Chargez le document avec la version spécifiée de MS Word
Document doc = new Document(dataDir + "Document.docx", loadOptions);

// Enregistrez le document
doc.Save(dataDir + "WorkingWithLoadOptions.SetMsWordVersion.docx");
```

## Conclusion

Dans ce guide, nous avons expliqué comment télécharger un document spécifiant une version spécifique de MS Word à l'aide de la bibliothèque Aspose.Words pour .NET. En suivant les étapes fournies et en utilisant la source de code C# fournie, vous pouvez facilement appliquer cette fonctionnalité dans votre application C#. Charger un document avec une version spécifiée de MS Word vous permet de garantir une bonne compatibilité et un bon traitement du document dans votre application.


### FAQ

#### Q : Pourquoi devrais-je spécifier la version de MS Word lors du chargement d'un document dans une application C# ?

Spécifier la version de MS Word garantit que le document est chargé et traité correctement, en particulier lorsqu'il s'agit d'un formatage spécifique ou de fonctionnalités qui peuvent varier entre les différentes versions.

#### Q : Quelles versions de MS Word Aspose.Words prend-il en charge ?

R : Aspose.Words for .NET prend en charge diverses versions de MS Word, notamment Word 97, Word 2003, Word 2007, Word 2010, Word 2013, Word 2016, Word 2019, etc.

#### Q : Puis-je charger un document avec une version de MS Word différente de celle installée sur mon système ?

R : Oui, Aspose.Words vous permet de spécifier une version différente de MS Word lors du chargement du document, garantissant ainsi la compatibilité même si le système cible dispose d'une version différente de MS Word.

#### Q : En quoi la configuration de la version MS Word profite-t-elle à mon application C# ?

R : La définition de la version MS Word garantit que le document est traité conformément au formatage et aux fonctionnalités prévus de cette version spécifique, fournissant ainsi une sortie cohérente.

#### Q : Aspose.Words est-il limité à la gestion uniquement des documents DOCX ?

R : Non, Aspose.Words prend en charge divers formats de documents, notamment DOC, RTF, HTML, PDF, etc., ce qui en fait un outil polyvalent pour gérer différents types de documents.