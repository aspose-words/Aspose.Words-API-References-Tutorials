---
title: Définir le formatage de la police
linktitle: Définir le formatage de la police
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment définir le formatage de la police dans un document Word à l'aide d'Aspose.Words for .NET et créer des documents attrayants.
type: docs
weight: 10
url: /fr/net/working-with-fonts/set-font-formatting/
---
Dans ce didacticiel, nous allons vous montrer comment définir le formatage de la police dans un document Word à l'aide d'Aspose.Words pour .NET. Vous apprendrez à appliquer des styles tels que le gras, la couleur, l'italique, la police, la taille, l'espacement et le soulignement.

## Conditions préalables
Avant de commencer, assurez-vous de disposer des éléments suivants :
- Une connaissance pratique du langage de programmation C#
- La bibliothèque Aspose.Words pour .NET installée dans votre projet

## Étape 1 : Définir le répertoire des documents
Commencez par définir le chemin du répertoire vers l’emplacement de votre document Word. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Créer et formater le document
 Créez une instance du`Document` la classe et le`DocumentBuilder` classe pour construire le document. Utilisez le`Font` propriété du`DocumentBuilder` pour accéder aux propriétés de formatage des polices.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font. Bold = true;
font.Color = Color.DarkBlue;
font. Italic = true;
font.Name = "Arial";
font.Size = 24;
font. Spacing = 5;
font.Underline = Underline.Double;
builder.Writeln("I'm a very nicely formatted string.");
```

## Étape 3 : Enregistrez le document
 Utilisez le`Save`méthode pour enregistrer le document avec le formatage de police appliqué. Remplacer`"WorkingWithFonts.SetFontFormatting.docx"` avec le nom de fichier souhaité.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFormatting.docx");
```

### Exemple de code source pour définir le formatage des polices à l'aide d'Aspose.Words for .NET 
```csharp

// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font.Bold = true;
font.Color = Color.DarkBlue;
font.Italic = true;
font.Name = "Arial";
font.Size = 24;
font.Spacing = 5;
font.Underline = Underline.Double;
builder.Writeln("I'm a very nice formatted string.");
doc.Save(dataDir + "WorkingWithFonts.SetFontFormatting.docx");

```

## Conclusion
Félicitation ! Vous savez maintenant comment définir le formatage de la police dans un document Word à l'aide d'Aspose.Words pour .NET. Vous pouvez explorer davantage d’options de formatage de police et créer des documents Word personnalisés et attrayants.

### FAQ

#### Q : Comment puis-je appliquer le style gras à une police dans un document Word à l'aide d'Aspose.Words ?

R : Pour appliquer le style gras à une police dans un document Word à l'aide d'Aspose.Words, vous pouvez utiliser l'API pour accéder à la police souhaitée et définir son style sur « gras ». Cela appliquera le style gras à la police spécifiée.

#### Q : Est-il possible d'appliquer le style italique à une partie spécifique du texte dans un document Word avec Aspose.Words ?

: Oui, avec Aspose.Words, vous pouvez appliquer le style italique à une partie spécifique du texte dans un document Word. Vous pouvez utiliser l'API pour sélectionner la plage de texte souhaitée et définir son style sur « italique ».

#### Q : Comment puis-je changer la couleur de la police dans un document Word à l'aide d'Aspose.Words ?

R : Pour modifier la couleur de la police dans un document Word à l'aide d'Aspose.Words, vous pouvez accéder à la police souhaitée à l'aide de l'API et définir sa couleur sur la couleur souhaitée. Cela changera la couleur de la police dans le document.

#### Q : Est-il possible de modifier la taille de la police dans un document Word à l'aide d'Aspose.Words ?

R : Oui, vous pouvez modifier la taille de la police dans un document Word à l'aide d'Aspose.Words. L'API vous permet d'accéder à la police et de définir sa taille en points ou en points d'échelle, en fonction de vos besoins.

#### Q : Puis-je appliquer plusieurs formats de police, tels que gras et italique, au même texte dans un document Word ?

: Oui, avec Aspose.Words, vous pouvez appliquer plusieurs formats de police, tels que le gras et l'italique, au même texte dans un document Word. Vous pouvez utiliser l'API pour définir les différents styles de police souhaités pour différentes parties du texte.