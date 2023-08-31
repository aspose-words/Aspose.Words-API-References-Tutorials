---
title: Caractéristiques de type ouvert
linktitle: Caractéristiques de type ouvert
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment activer et utiliser les fonctionnalités Open Type dans Aspose.Words for .NET
type: docs
weight: 10
url: /fr/net/enable-opentype-features/open-type-features/
---

Dans ce didacticiel complet, vous apprendrez comment activer et utiliser les fonctionnalités Open Type dans Aspose.Words pour .NET. Nous vous guiderons tout au long du processus et vous fournirons les extraits de code C# nécessaires. À la fin de ce guide, vous serez en mesure de travailler avec les fonctionnalités Open Type dans vos documents Word.

## Conditions préalables
Avant de commencer, assurez-vous que vous disposez des prérequis suivants :
- Bibliothèque Aspose.Words pour .NET installée sur votre système.

## Étape 1 : Charger le document
Pour commencer, chargez le document à l'aide de la classe Document :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");
```

## Étape 2 : Activer les fonctionnalités de type ouvert
Pour activer les fonctionnalités Open Type, définissez la propriété TextShaperFactory de la classe LayoutOptions sur une instance de la fabrique de mise en forme de texte souhaitée. Dans cet exemple, nous utilisons HarfBuzzTextShaperFactory :

```csharp
doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;
```

## Étape 3 : Enregistrez le document
Après avoir activé les fonctionnalités Open Type, enregistrez le document dans le format de sortie souhaité, tel que PDF :

```csharp
doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

### Exemple de code source pour les fonctionnalités de type ouvert utilisant Aspose.Words pour .NET
Voici le code source complet pour utiliser les fonctionnalités Open Type dans Aspose.Words for .NET :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");

doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;

doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment activer et utiliser les fonctionnalités Open Type dans Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez désormais utiliser les fonctionnalités Open Type dans vos documents Word.

Les fonctionnalités Open Type offrent des capacités améliorées de typographie et de mise en forme du texte, vous permettant de créer des documents visuellement attrayants et d'aspect professionnel. Expérimentez avec différentes usines de mise en forme de texte et explorez les possibilités des fonctionnalités Open Type dans vos projets.

### FAQ

#### Q : Comment activer les fonctionnalités OpenType dans Aspose.Words pour .NET ?

R : Pour activer les fonctionnalités OpenType dans Aspose.Words for .NET, vous devez suivre les étapes mentionnées dans le didacticiel.

#### Q : Quelles fonctionnalités OpenType sont prises en charge dans Aspose.Words pour .NET ?

R : Aspose.Words for .NET prend en charge plusieurs fonctionnalités OpenType, telles que les ligatures, les variations de glyphes, les substitutions contextuelles, etc.

#### Q : Comment puis-je vérifier si une fonctionnalité OpenType est prise en charge dans une police spécifique ?

R : Vous pouvez vérifier si une fonctionnalité OpenType est prise en charge dans une police spécifique en utilisant le`Font.OpenTypeFeatures` méthode dans Aspose.Words pour .NET.

#### Q : Quelles autres fonctionnalités de formatage de texte Aspose.Words for .NET prend-il en charge ?

R : Outre les fonctionnalités OpenType, Aspose.Words for .NET prend également en charge d'autres fonctionnalités de formatage de texte telles que le formatage des paragraphes, la création de tableaux, l'ajout d'images, etc.

#### Q : Puis-je utiliser les fonctionnalités OpenType dans toutes les versions d’Aspose.Words for .NET ?

R : Les fonctionnalités OpenType sont prises en charge dans les versions plus récentes d'Aspose.Words pour .NET. Assurez-vous d'utiliser une version compatible pour bénéficier de ces fonctionnalités.