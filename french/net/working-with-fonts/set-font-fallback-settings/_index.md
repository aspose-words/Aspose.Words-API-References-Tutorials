---
title: Définir les paramètres de remplacement des polices
linktitle: Définir les paramètres de remplacement des polices
second_title: Référence de l'API Aspose.Words pour .NET
description: Découvrez comment définir les paramètres de substitution de police dans Aspose.Words pour .NET et personnaliser la substitution de police dans vos documents Word.
type: docs
weight: 10
url: /fr/net/working-with-fonts/set-font-fallback-settings/
---
Dans ce didacticiel, nous allons vous montrer comment définir les paramètres de substitution de police dans un document Word à l'aide de Aspose.Words pour .NET. Les paramètres de substitution de police vous permettent de spécifier les polices de remplacement à utiliser lorsque les polices spécifiées ne sont pas disponibles.

## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
- Une connaissance pratique du langage de programmation C#
- La bibliothèque Aspose.Words pour .NET installée dans votre projet

## Étape 1 : Définir le répertoire des documents
Commencez par définir le chemin du répertoire vers l'emplacement de votre document Word. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Charger les paramètres de substitution de police
 Créer une instance de`FontSettings` classe et utiliser le`Load`méthode pour charger les paramètres de remplacement de police à partir d'un fichier XML. Le fichier XML spécifié doit contenir les règles de substitution de police à utiliser.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font Fallback Rules.xml");
```

## Étape 3 : Appliquer les paramètres de substitution de police
 Associez les paramètres de substitution de police au document en les attribuant aux`FontSettings` propriété.

```csharp
doc.FontSettings = fontSettings;
```

## Étape 4 : Enregistrez le document
 Enregistrez le document à l'aide de la`Save` méthode de la`Document` avec le chemin et le nom de fichier appropriés.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

### Exemple de code source pour définir les paramètres de remplacement des polices à l'aide d'Aspose.Words pour .NET 
```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font fallback rules.xml");
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

## Conclusion
Dans ce didacticiel, vous avez appris à définir les paramètres de substitution de police dans un document Word à l'aide de Aspose.Words pour .NET. Expérimentez avec différentes règles de substitution de polices pour vous assurer que votre document semble cohérent, même lorsque les polices spécifiées ne sont pas disponibles.
