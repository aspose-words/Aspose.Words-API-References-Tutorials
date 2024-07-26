---
title: Appliquer des bordures et un ombrage au paragraphe dans un document Word
linktitle: Appliquer des bordures et un ombrage au paragraphe dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Appliquez des bordures et un ombrage aux paragraphes des documents Word à l'aide d'Aspose.Words pour .NET. Suivez notre guide étape par étape pour améliorer la mise en forme de vos documents.
type: docs
weight: 10
url: /fr/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
## Introduction

Salut, vous êtes-vous déjà demandé comment faire ressortir vos documents Word avec des bordures et des ombrages fantaisistes ? Eh bien, vous êtes au bon endroit ! Aujourd'hui, nous plongeons dans le monde d'Aspose.Words for .NET pour égayer nos paragraphes. Imaginez votre document aussi élégant que le travail d'un concepteur professionnel avec seulement quelques lignes de code. Prêt à commencer? Allons-y!

## Conditions préalables

Avant de retrousser nos manches et de nous lancer dans le codage, assurons-nous que nous disposons de tout ce dont nous avons besoin. Voici votre liste de contrôle rapide :

-  Aspose.Words pour .NET : vous devez installer cette bibliothèque. Vous pouvez le télécharger depuis le[Site Aspose](https://releases.aspose.com/words/net/).
- Environnement de développement : Visual Studio ou tout autre IDE prenant en charge .NET.
- Connaissance de base de C# : juste assez pour comprendre et peaufiner les extraits de code.
- Une licence valide : soit un[permis temporaire](https://purchase.aspose.com/temporary-license/) ou acheté chez[Asposer](https://purchase.aspose.com/buy).

## Importer des espaces de noms

Avant de nous lancer dans le code, nous devons nous assurer que les espaces de noms nécessaires sont importés dans notre projet. Cela nous rend toutes les fonctionnalités intéressantes d’Aspose.Words accessibles.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
using Aspose.Words.Drawing;
using System.Drawing;
```

Maintenant, décomposons le processus en petites étapes. Chaque étape aura un titre et une explication détaillée. Prêt? Allons-y!

## Étape 1 : Configurez votre répertoire de documents

Tout d’abord, nous avons besoin d’un endroit pour enregistrer notre document magnifiquement formaté. Définissons le chemin d'accès à votre répertoire de documents.

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ce répertoire est l'endroit où votre document final sera enregistré. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel sur votre machine.

## Étape 2 : Créer un nouveau document et DocumentBuilder

 Ensuite, nous devons créer un nouveau document et un`DocumentBuilder` objet. Le`DocumentBuilder` est notre baguette magique qui nous permet de manipuler le document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Le`Document` l'objet représente l'intégralité de notre document Word, et le`DocumentBuilder` nous aide à ajouter et à formater du contenu.

## Étape 3 : définir les bordures de paragraphe

Maintenant, ajoutons quelques bordures élégantes à notre paragraphe. Nous définirons la distance par rapport au texte et définirons différents styles de bordure.

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders.DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

Ici, nous fixons une distance de 20 points entre le texte et les bordures. Les bordures de tous les côtés (gauche, droite, haut, bas) sont définies sur des lignes doubles. Fantaisie, non ?

## Étape 4 : appliquer un ombrage au paragraphe

Les bordures sont superbes, mais montons d'un cran avec un peu d'ombrage. Nous utiliserons un motif croisé en diagonale avec un mélange de couleurs pour faire ressortir notre paragraphe.

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

Dans cette étape, nous avons appliqué une texture croisée diagonale avec du corail clair comme couleur de fond et du saumon clair comme couleur de premier plan. C'est comme habiller votre paragraphe avec des vêtements de marque !

## Étape 5 : ajouter du texte au paragraphe

Qu'est-ce qu'un paragraphe sans texte ? Ajoutons un exemple de phrase pour voir notre formatage en action.

```csharp
builder.Write("I'm a formatted paragraph with double border and nice shading.");
```

Cette ligne insère notre texte dans le document. Simple, mais maintenant enveloppé dans un cadre élégant et un arrière-plan ombré.

## Étape 6 : Enregistrez le document

Enfin, il est temps de sauvegarder notre travail. Enregistrons le document dans le répertoire spécifié avec un nom descriptif.

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

 Cela enregistre notre document avec le nom`DocumentFormatting.ApplyBordersAndShadingToParagraph.doc` dans le répertoire que nous avons spécifié plus tôt.

## Conclusion

Et voila! Avec seulement quelques lignes de code, nous avons transformé un simple paragraphe en un contenu visuellement attrayant. Aspose.Words for .NET facilite incroyablement l'ajout d'une mise en forme d'aspect professionnel à vos documents. Que vous prépariez un rapport, une lettre ou tout autre document, ces astuces vous aideront à faire bonne impression. Alors n'hésitez plus, essayez-le et regardez vos documents prendre vie !

## FAQ

### Puis-je utiliser des styles de trait différents pour chaque bordure ?  
 Absolument! Aspose.Words for .NET vous permet de personnaliser chaque bordure individuellement. Il suffit de définir le`LineStyle` pour chaque type de bordure, comme indiqué dans le guide.

### Quelles autres textures d'ombrage sont disponibles ?  
 Vous pouvez utiliser plusieurs textures, telles qu'une bande unie, une bande horizontale, une bande verticale, etc. Vérifier la[Asposer la documentation](https://reference.aspose.com/words/net/) pour une liste complète.

### Comment puis-je changer la couleur de la bordure ?  
 Vous pouvez définir la couleur de la bordure à l'aide du`Color` propriété pour chaque frontière. Par exemple,`borders[BorderType.Left].Color = Color.Red;`.

### Est-il possible d'appliquer des bordures et des ombrages à une partie spécifique du texte ?  
 Oui, vous pouvez appliquer des bordures et un ombrage à des séquences de texte spécifiques à l'aide de l'option`Run` objet dans le`DocumentBuilder`.

### Puis-je automatiser ce processus pour plusieurs paragraphes ?  
Certainement! Vous pouvez parcourir vos paragraphes et appliquer les mêmes bordures et paramètres d’ombrage par programme.
