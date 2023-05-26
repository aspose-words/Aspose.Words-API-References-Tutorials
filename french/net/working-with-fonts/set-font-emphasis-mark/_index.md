---
title: Définir la marque d'accentuation de la police
linktitle: Définir la marque d'accentuation de la police
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à définir le style d'accentuation de la police dans un document Word à l'aide de Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fonts/set-font-emphasis-mark/
---

Dans ce didacticiel, nous allons vous montrer comment définir le style d'accentuation de la police dans un document Word à l'aide de Aspose.Words pour .NET. L'accentuation de la police est utilisée pour mettre en évidence certains mots ou expressions dans le texte.

## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
- Une connaissance pratique du langage de programmation C#
- La bibliothèque Aspose.Words pour .NET installée dans votre projet

## Étape 1 : Définir le répertoire des documents
Commencez par définir le chemin du répertoire vers l'emplacement de votre document Word. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Créez et personnalisez le document
 Créer une instance de`Document` classe et un associé`DocumentBuilder` pour construire le contenu du document. Utilisez le`Font.EmphasisMark`propriété pour définir le style d'accentuation de la police sur`EmphasisMark.UnderSolidCircle` . Utilisez ensuite le`Write` et`Writeln` méthodes de la`DocumentBuilder` pour ajouter du texte avec l'emphase de police spécifiée.

```csharp
Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasized text");
builder. Writen();
builder.Font.ClearFormatting();
builder.Write("Simple text");
```

## Étape 3 : Enregistrez le document
 Enregistrez le document à l'aide de la`Save` méthode de la`Document` avec le chemin et le nom de fichier appropriés.

```csharp
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

### Exemple de code source pour Set Font Emphasis Mark à l'aide de Aspose.Words pour .NET 

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

## Conclusion
Dans ce didacticiel, vous avez appris à définir le style d'accentuation de la police dans un document Word à l'aide de Aspose.Words pour .NET. Expérimentez avec différents styles d'emphase et utilisez cette fonctionnalité pour mettre en évidence des mots ou des phrases dans vos documents.
