---
title: Barré
linktitle: Barré
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment appliquer une mise en forme barrée au texte à l'aide d'Aspose.Words for .NET grâce à notre guide étape par étape. Améliorez vos compétences en traitement de documents.
type: docs
weight: 10
url: /fr/net/working-with-markdown/strikethrough/
---
## Introduction

Bienvenue dans ce guide détaillé sur la façon d'appliquer une mise en forme barrée au texte à l'aide d'Aspose.Words pour .NET. Si vous souhaitez améliorer vos compétences en traitement de documents et ajouter une touche unique à votre texte, vous êtes au bon endroit. Allons-y !

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

-  Aspose.Words pour .NET : téléchargez-le[ici](https://releases.aspose.com/words/net/).
- .NET Framework : assurez-vous que .NET Framework est installé sur votre système.
- Environnement de développement : un IDE comme Visual Studio.
- Connaissance de base de C# : Une connaissance de la programmation C# est nécessaire.

## Importer des espaces de noms

Pour commencer, vous devrez importer les espaces de noms nécessaires. Ceux-ci sont indispensables pour accéder à la bibliothèque Aspose.Words et à ses fonctionnalités.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## Étape 1 : initialiser DocumentBuilder

 Le`DocumentBuilder` class est un outil puissant dans Aspose.Words qui vous permet d'ajouter facilement du contenu à votre document.

```csharp
// Initialisez un DocumentBuilder.
DocumentBuilder builder = new DocumentBuilder();
```

## Étape 2 : définir la propriété barrée

Maintenant, appliquons la propriété barré à notre texte. Cela implique de définir le`StrikeThrough` propriété du`Font` s'opposer à`true`.

```csharp
// Faites le texte barré.
builder.Font.StrikeThrough = true;
```

## Étape 3 : Écrivez du texte barré

 Avec la propriété barré définie, nous pouvons maintenant ajouter notre texte. Le`Writeln` La méthode ajoutera le texte au document.

```csharp
// Écrivez du texte barré.
builder.Writeln("This text will be StrikeThrough");
```

## Conclusion

Et voilà ! Vous avez réussi à ajouter une mise en forme barrée à votre texte à l'aide d'Aspose.Words pour .NET. Cette puissante bibliothèque ouvre un monde de possibilités pour le traitement et la personnalisation des documents. Que vous créiez des rapports, des lettres ou tout autre type de document, la maîtrise de ces fonctionnalités améliorera sans aucun doute votre productivité et la qualité de vos sorties.

## FAQ

### Qu’est-ce qu’Aspose.Words pour .NET ?
Aspose.Words for .NET est une puissante bibliothèque de traitement de documents qui permet aux développeurs de créer, manipuler et convertir des documents Word par programme.

### Puis-je utiliser Aspose.Words pour .NET dans un projet commercial ?
 Oui, vous pouvez utiliser Aspose.Words pour .NET dans des projets commerciaux. Pour les options d'achat, visitez le[page d'achat](https://purchase.aspose.com/buy).

### Existe-t-il un essai gratuit disponible pour Aspose.Words pour .NET ?
 Oui, vous pouvez télécharger un essai gratuit[ici](https://releases.aspose.com/).

### Comment puis-je obtenir une assistance pour Aspose.Words pour .NET ?
Vous pouvez bénéficier du soutien de la communauté Aspose et d'experts sur le sujet.[forum d'assistance](https://forum.aspose.com/c/words/8).

### Puis-je appliquer d’autres options de formatage de texte à l’aide d’Aspose.Words pour .NET ?
Absolument! Aspose.Words for .NET prend en charge un large éventail d'options de formatage de texte, notamment le gras, l'italique, le souligné, etc.