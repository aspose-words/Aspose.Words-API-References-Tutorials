---
title: Exporter vers Markdown avec l'alignement du contenu du tableau
linktitle: Exporter vers Markdown avec l'alignement du contenu du tableau
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment exporter des documents Word vers Markdown avec des tableaux alignés à l'aide d'Aspose.Words pour .NET. Suivez notre guide étape par étape pour des tableaux Markdown parfaits.
type: docs
weight: 10
url: /fr/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
## Introduction

Salut! Vous êtes-vous déjà demandé comment exporter votre document Word au format Markdown avec des tableaux parfaitement alignés ? Que vous soyez un développeur travaillant sur de la documentation ou simplement quelqu'un qui aime Markdown, ce guide est fait pour vous. Nous allons plonger dans le vif du sujet de l'utilisation d'Aspose.Words for .NET pour y parvenir. Prêt à transformer vos tableaux Word en tableaux Markdown parfaitement alignés ? Commençons!

## Conditions préalables

Avant de plonger dans le code, vous devez mettre en place quelques éléments :

1.  Bibliothèque Aspose.Words pour .NET : assurez-vous de disposer de la bibliothèque Aspose.Words pour .NET. Vous pouvez le télécharger depuis le[Page des versions Aspose](https://releases.aspose.com/words/net/).
2. Environnement de développement : configurez votre environnement de développement. Visual Studio est un choix populaire pour le développement .NET.
3. Connaissance de base de C# : Comprendre C# est essentiel car nous allons écrire du code dans ce langage.
4. Exemple de document Word : disposez d'un document Word que vous pouvez utiliser pour les tests.

## Importer des espaces de noms

Avant de commencer le codage, importons les espaces de noms nécessaires. Ceux-ci nous donneront accès aux classes et méthodes Aspose.Words que nous utiliserons.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Étape 1 : initialiser le document et DocumentBuilder

Tout d'abord, nous devons créer un nouveau document Word et initialiser un`DocumentBuilder` objet de commencer à construire notre document.

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Créez un nouveau document.
Document doc = new Document();

// Initialisez DocumentBuilder.
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Insérer des cellules et aligner le contenu

Ensuite, nous allons insérer quelques cellules dans notre document et définir leur alignement. Ceci est crucial pour garantir que l’exportation Markdown conserve le bon alignement.

```csharp
// Insérez une cellule et définissez l'alignement à droite.
builder.InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");

// Insérez une autre cellule et définissez l'alignement sur le centre.
builder.InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

## Étape 3 : Définir l'alignement du contenu du tableau pour l'exportation Markdown

 Il est maintenant temps de configurer le`MarkdownSaveOptions` pour contrôler l'alignement du contenu du tableau dans le fichier Markdown exporté. Nous enregistrerons le document avec différents paramètres d'alignement pour voir comment il fonctionne.

```csharp
// Créez un objet MarkdownSaveOptions.
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
    TableContentAlignment = TableContentAlignment.Left
};

// Enregistrez le document avec un alignement à gauche.
doc.Save(dataDir + "LeftTableContentAlignment.md", saveOptions);

// Changez l'alignement à droite et enregistrez.
saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "RightTableContentAlignment.md", saveOptions);

// Modifiez l'alignement au centre et enregistrez.
saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "CenterTableContentAlignment.md", saveOptions);
```

## Étape 4 : Utiliser l'alignement automatique du contenu des tableaux

 Le`Auto`L'option d'alignement prend l'alignement du premier paragraphe de la colonne du tableau correspondante. Cela peut être pratique lorsque vous avez des alignements mixtes dans une seule table.

```csharp
// Définissez l’alignement sur Auto.
saveOptions.TableContentAlignment = TableContentAlignment.Auto;

// Enregistrez le document avec alignement automatique.
doc.Save(dataDir + "AutoTableContentAlignment.md", saveOptions);
```

## Conclusion

Et voila! Exporter des documents Word dans Markdown avec des tableaux alignés à l'aide d'Aspose.Words pour .NET est un jeu d'enfant une fois que vous savez comment le faire. Cette puissante bibliothèque facilite le contrôle du formatage et de l'alignement de vos tableaux, garantissant ainsi que vos documents Markdown ressemblent exactement à ce que vous souhaitez. Bon codage !

## FAQ

### Qu’est-ce qu’Aspose.Words pour .NET ?
Aspose.Words for .NET est une bibliothèque puissante qui permet aux développeurs de créer, modifier, convertir et exporter des documents Word par programme.

### Puis-je définir différents alignements pour différentes colonnes du même tableau ?
 Oui, en utilisant le`Auto` option d'alignement, vous pouvez avoir différents alignements en fonction du premier paragraphe de chaque colonne.

### Ai-je besoin d’une licence pour utiliser Aspose.Words pour .NET ?
 Oui, Aspose.Words for .NET nécessite une licence pour bénéficier de toutes les fonctionnalités. Vous pouvez obtenir un[permis temporaire](https://purchase.aspose.com/temporary-license/) pour évaluation.

### Est-il possible d'exporter d'autres éléments du document vers Markdown à l'aide d'Aspose.Words ?
Oui, Aspose.Words prend en charge l'exportation de divers éléments tels que des titres, des listes et des images au format Markdown.

### Où puis-je obtenir de l'aide si je rencontre des problèmes ?
 Vous pouvez bénéficier du soutien du[Forum d'assistance Aspose.Words](https://forum.aspose.com/c/words/8).
