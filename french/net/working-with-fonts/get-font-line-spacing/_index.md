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

// Créer un générateur de documents
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Configurez la police
 Ensuite, nous allons configurer la police en définissant le`Name` propriété du générateur de documents.

```csharp
//Configurer la police
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
