---
title: Formatage des polices
linktitle: Formatage des polices
second_title: Référence de l'API Aspose.Words pour .NET
description: Dans ce didacticiel, apprenez à formater la police dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fonts/font-formatting/
---

Dans ce didacticiel, nous vous expliquerons comment effectuer le formatage des polices dans un document Word à l'aide de la bibliothèque Aspose.Words pour .NET. Le formatage de la police vous permet de personnaliser l'apparence du texte, y compris la taille, le gras, la couleur, la police, le soulignement, etc. Nous vous guiderons étape par étape pour vous aider à comprendre et à implémenter le code dans votre projet .NET.

## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
- Une connaissance pratique du langage de programmation C#
- La bibliothèque Aspose.Words pour .NET installée dans votre projet

## Étape 1 : Définir le répertoire des documents
 Tout d'abord, vous devez définir le chemin du répertoire vers l'emplacement de votre document Word. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin approprié.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Créer un nouveau document et un générateur de documents
 Ensuite, nous allons créer un nouveau document en instanciant le`Document` classe et un générateur de documents en instanciant la`DocumentBuilder` classe.

```csharp
// Créer un nouveau document
Document doc = new Document();

// Créer un générateur de documents
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Configurer la mise en forme des polices
 Nous allons maintenant accéder au`Font` objet du générateur de documents et configurez les propriétés de formatage de la police telles que la taille, le gras, la couleur, la police, le soulignement, etc.

```csharp
// Accéder à la police
Font font = builder.Font;

// Configurer le formatage des polices
font.Size = 16;
font. Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;
```

## Étape 4 : Ajouter du texte au document
Ensuite, nous utiliserons le générateur de document pour ajouter du texte formaté au document.

```csharp
// Ajouter du texte au document
builder.Write("Example text.");
```

## Étape 5 : Enregistrez le document
Enfin, nous enregistrerons le document contenant la mise en forme de la police.

```csharp
doc.Save(dataDir + "WorkingWithFonts.FontFormatting.docx");
```

### Exemple de code source pour le formatage des polices à l'aide d'Aspose.Words pour .NET 
```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;
builder.Write("Sample text.");
doc.Save(dataDir + "WorkingWithFonts.FontFormatting.docx");
```

## Conclusion
Dans ce didacticiel, nous avons vu comment effectuer le formatage des polices dans un document Word à l'aide de Aspose.Words pour .NET. Le formatage des polices vous permet de personnaliser l'apparence du texte dans vos documents. N'hésitez pas à utiliser cette fonctionnalité pour créer des documents attrayants et professionnels.