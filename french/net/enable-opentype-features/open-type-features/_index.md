---
title: Caractéristiques de type ouvert
linktitle: Caractéristiques de type ouvert
second_title: Référence de l'API Aspose.Words pour .NET
description: Découvrez comment activer et utiliser les fonctionnalités Open Type dans Aspose.Words pour .NET
type: docs
weight: 10
url: /fr/net/enable-opentype-features/open-type-features/
---

Dans ce didacticiel complet, vous apprendrez à activer et à utiliser les fonctionnalités Open Type dans Aspose.Words pour .NET. Nous vous guiderons tout au long du processus et vous fournirons les extraits de code C# nécessaires. À la fin de ce guide, vous serez en mesure de travailler avec les fonctionnalités Open Type dans vos documents Word.

## Conditions préalables
Avant de commencer, assurez-vous que vous disposez des prérequis suivants :
- Bibliothèque Aspose.Words pour .NET installée sur votre système.

## Étape 1 : Charger le document
Pour commencer, chargez le document à l'aide de la classe Document :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");
```

## Étape 2 : Activer les fonctionnalités Open Type
Pour activer les fonctionnalités Open Type, définissez la propriété TextShaperFactory de la classe LayoutOptions sur une instance de la fabrique de mise en forme de texte souhaitée. Dans cet exemple, nous utilisons la HarfBuzzTextShaperFactory :

```csharp
doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;
```

## Étape 3 : Enregistrer le document
Après avoir activé les fonctionnalités Open Type, enregistrez le document dans le format de sortie souhaité, tel que PDF :

```csharp
doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

### Exemple de code source pour les fonctionnalités Open Type utilisant Aspose.Words pour .NET
Voici le code source complet pour utiliser les fonctionnalités Open Type dans Aspose.Words pour .NET :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");

doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;

doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment activer et utiliser les fonctionnalités Open Type dans Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez désormais utiliser les fonctionnalités Open Type dans vos documents Word.

Les fonctionnalités Open Type offrent des capacités de typographie et de mise en forme de texte améliorées, vous permettant de créer des documents visuellement attrayants et d'aspect professionnel. Expérimentez avec différentes usines de mise en forme de texte et explorez les possibilités des fonctionnalités Open Type dans vos projets.
