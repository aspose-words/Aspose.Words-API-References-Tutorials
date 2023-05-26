---
title: Instance par défaut des paramètres de police
linktitle: Instance par défaut des paramètres de police
second_title: Référence de l'API Aspose.Words pour .NET
description: Dans ce didacticiel, découvrez comment configurer les paramètres de police par défaut dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fonts/font-settings-default-instance/
---

Dans ce didacticiel, nous vous expliquerons comment configurer les paramètres de police par défaut dans un document Word à l'aide de la bibliothèque Aspose.Words pour .NET. Les paramètres de police par défaut vous permettent de spécifier les sources de police utilisées lors du chargement et du rendu des documents. Nous vous guiderons étape par étape pour vous aider à comprendre et à implémenter le code dans votre projet .NET.

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

## Étape 2 : Configurer les paramètres de police par défaut
 Ensuite, nous allons créer une instance de`FontSettings` en utilisant`FontSettings.DefaultInstance`puis nous spécifierons les sources de polices utilisées lors du chargement et du rendu des documents. Dans cet exemple, nous utilisons une source de police système et une source de police de dossier.

```csharp
// Configurer les paramètres de police par défaut
FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## Étape 3 : Téléchargez le document avec les paramètres de police
 Nous allons maintenant charger le document en utilisant`LoadOptions` et en spécifiant les paramètres de police à utiliser.

```csharp
// Charger le document avec les paramètres de police
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```


### Exemple de code source pour l'instance par défaut des paramètres de police à l'aide d'Aspose.Words pour .NET 
```csharp

// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(),
	new FolderFontSource("C:\\MyFonts\\", true)
});
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Conclusion
Dans ce didacticiel, nous avons vu comment configurer les paramètres de police par défaut dans un document Word avec Aspose.Words pour .NET. En spécifiant les sources de polices utilisées lors du chargement et du rendu des documents, vous pouvez contrôler l'apparence des polices dans vos documents. N'hésitez pas à utiliser cette fonctionnalité pour personnaliser les paramètres de police dans vos projets.