---
title: Position du curseur
linktitle: Position du curseur
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à récupérer la position du curseur dans un document Word à l'aide du guide étape par étape Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/cursor-position/
---

Dans cet exemple étape par étape, vous découvrirez la position du curseur dans un document Word à l'aide de Aspose.Words pour .NET. Nous vous guiderons tout au long du processus et vous fournirons les extraits de code C# nécessaires. À la fin de ce guide, vous serez en mesure de récupérer le nœud et le paragraphe actuels où le curseur est positionné dans le document.

## Conditions préalables
Avant de commencer, assurez-vous que vous disposez des prérequis suivants :
- Bibliothèque Aspose.Words pour .NET installée sur votre système.

## Étape 1 : créer un nouveau document et DocumentBuilder
Pour commencer, créez un nouveau document à l'aide de la classe Document et initialisez un objet DocumentBuilder :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Accéder au nœud et au paragraphe actuels
Ensuite, récupérez le nœud et le paragraphe actuels où le curseur est positionné. Ceci peut être réalisé en utilisant les propriétés CurrentNode et CurrentParagraph de la classe DocumentBuilder :

```csharp
Node curNode = builder.CurrentNode;
Paragraph curParagraph = builder.CurrentParagraph;
```

## Étape 3 : Récupérer les informations sur la position du curseur
Maintenant, vous pouvez récupérer des informations sur la position du curseur. Dans l'extrait de code suivant, nous imprimons le texte du paragraphe actuel :

```csharp
Console.WriteLine("\nCursor move to paragraph: " + curParagraph.GetText());
```

### Exemple de code source pour la position du curseur à l'aide de Aspose.Words pour .NET
Voici le code source complet pour comprendre la position du curseur en utilisant Aspose.Words pour .NET :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Node curNode = builder.CurrentNode;
Paragraph curParagraph = builder.CurrentParagraph;

Console.WriteLine("\nCursor move to paragraph: " + curParagraph.GetText());
```

## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment travailler avec la position du curseur dans un document Word en utilisant Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez maintenant récupérer le nœud et le paragraphe actuels où le curseur est positionné dans le document.

Comprendre la position du curseur est utile pour divers scénarios, tels que la manipulation du contenu du document en fonction de l'emplacement du curseur ou la mise en œuvre de fonctionnalités d'édition personnalisées.

