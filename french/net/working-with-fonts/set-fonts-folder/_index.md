---
title: Définir le dossier des polices
linktitle: Définir le dossier des polices
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à définir le répertoire des polices dans Aspose.Words pour .NET et assurez-vous de la disponibilité des polices utilisées dans vos documents.
type: docs
weight: 10
url: /fr/net/working-with-fonts/set-fonts-folder/
---
Dans ce didacticiel, nous allons vous montrer comment définir le répertoire des polices dans Aspose.Words pour .NET. Vous apprendrez à spécifier le répertoire contenant les polices utilisées dans votre document Word.

## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
- Une connaissance pratique du langage de programmation C#
- La bibliothèque Aspose.Words pour .NET installée dans votre projet

## Étape 1 : Définir le répertoire des documents
Commencez par définir le chemin du répertoire vers l'emplacement de votre document Word. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Définir le répertoire des polices
 Créer une instance de`FontSettings` classe et utiliser le`SetFontsFolder` méthode pour spécifier le répertoire contenant les polices. Remplacer`"Fonts"` avec le nom du répertoire de polices réel.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

## Étape 3 : Chargez le document avec les paramètres de police
 Utilisez le`LoadOptions` classe pour spécifier les paramètres de police dans la`FontSettings` option. Utilisez ensuite le`Document` class pour charger le document à l'aide de ces options.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

### Exemple de code source pour Set Fonts Folder à l'aide de Aspose.Words pour .NET 

```csharp

// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Conclusion
Félicitation ! Vous savez maintenant comment définir le répertoire des polices dans Aspose.Words pour .NET. Vous pouvez utiliser cette fonction pour garantir la disponibilité des polices utilisées dans votre document et pour assurer la cohérence de l'affichage des polices.
