---
title: Obtenir l'espacement des lignes de police
linktitle: Obtenir l'espacement des lignes de police
second_title: Référence de l'API Aspose.Words pour .NET
description: Dans ce didacticiel, découvrez comment obtenir l'espacement des lignes de police dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fonts/get-font-line-spacing/
---
Dans ce didacticiel, nous allons vous expliquer comment obtenir l'espacement des lignes de police dans un document Word à l'aide de la bibliothèque Aspose.Words pour .NET. L'interligne de la police définit l'espace vertical entre les lignes de texte. Nous vous guiderons étape par étape pour vous aider à comprendre et à implémenter le code dans votre projet .NET.

## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
- Une connaissance pratique du langage de programmation C#
- La bibliothèque Aspose.Words pour .NET installée dans votre projet

## Étape 1 : Créer un nouveau document et un générateur de documents
 Tout d'abord, nous allons créer un nouveau document en instanciant le`Document` classe et un générateur de documents en instanciant la`DocumentBuilder` classe.

```csharp
// Créer un nouveau document
Document doc = new Document();

//Créer un générateur de documents
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Configurez la police
 Ensuite, nous allons configurer la police en définissant le`Name` propriété du générateur de documents.

```csharp
// Configurer la police
builder.Font.Name = "Calibri";
```

## Étape 3 : Ajouter du texte au document
Nous allons maintenant utiliser le générateur de document pour ajouter du texte formaté au document.

```csharp
// Ajouter du texte au document
builder. Writen("qText");
```

## Étape 4 : Obtenir l'espacement des lignes de police
 Nous allons maintenant accéder au`Font` objet du premier paragraphe du document et récupérer la valeur de`LineSpacing` propriété.

```csharp
// Obtenir l'interligne de la police
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

### Exemple de code source pour obtenir l'espacement des lignes de police à l'aide de Aspose.Words pour .NET 
```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Calibri";
builder.Writeln("qText");
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## Conclusion
Dans ce didacticiel, nous avons vu comment obtenir l'espacement des lignes de police dans un document Word avec Aspose.Words pour .NET. L'espacement des lignes de police est important pour contrôler l'espacement vertical entre les lignes de texte. N'hésitez pas à utiliser cette fonctionnalité pour personnaliser l'apparence de votre texte dans vos documents.

### FAQ

#### Q : Comment puis-je modifier l'interligne d'un texte spécifique dans un document Word ?

R : Avec Aspose.Words, vous pouvez facilement modifier l'interligne d'un texte spécifique dans un document Word. Utilisez l'API pour sélectionner le texte souhaité et ajuster l'espacement entre les lignes en spécifiant la valeur appropriée.

#### Q : Est-il possible d'appliquer un espacement exact entre les lignes dans un document Word ?

R : Oui, Aspose.Words vous permet d'appliquer un espacement exact entre les lignes dans un document Word. Vous pouvez spécifier une valeur précise pour l'interligne à l'aide de l'API.

#### Q : Comment puis-je ajuster l'espacement des lignes pour l'ensemble du document Word ?

R : Avec Aspose.Words, vous pouvez facilement ajuster l'espacement des lignes pour l'ensemble du document Word. Utilisez les méthodes fournies par l'API pour spécifier l'interligne souhaité pour l'ensemble du document.

#### Q : Aspose.Words prend-il en charge plusieurs interlignes ?

R : Oui, Aspose.Words prend en charge plusieurs interlignes dans les documents Word. Vous pouvez définir plusieurs espacements, tels que 1,5 fois ou 2 fois l'espacement normal, pour les lignes de votre texte.

#### Q : Comment puis-je éviter les problèmes de chevauchement de lignes lors du réglage de l'interligne ?

R : Pour éviter les problèmes de chevauchement de lignes lors du réglage de l'espacement entre les lignes, assurez-vous de choisir les valeurs d'espacement appropriées. Testez également le rendu final de votre document pour vous assurer que le texte reste lisible et bien formaté.