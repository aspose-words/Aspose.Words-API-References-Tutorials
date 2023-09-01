---
title: Instance par défaut des paramètres de police
linktitle: Instance par défaut des paramètres de police
second_title: API de traitement de documents Aspose.Words
description: Dans ce didacticiel, découvrez comment configurer les paramètres de police par défaut dans un document Word avec Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/working-with-fonts/font-settings-default-instance/
---

Dans ce didacticiel, nous vous expliquerons comment configurer les paramètres de police par défaut dans un document Word à l'aide de la bibliothèque Aspose.Words pour .NET. Les paramètres de police par défaut vous permettent de spécifier les sources de polices utilisées lors du chargement et du rendu des documents. Nous vous guiderons étape par étape pour vous aider à comprendre et à implémenter le code dans votre projet .NET.

## Conditions préalables
Avant de commencer, assurez-vous de disposer des éléments suivants :
- Une connaissance pratique du langage de programmation C#
- La bibliothèque Aspose.Words pour .NET installée dans votre projet

## Étape 1 : Définir le répertoire des documents
 Tout d’abord, vous devez définir le chemin du répertoire vers l’emplacement de votre document Word. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin approprié.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : configurer les paramètres de police par défaut
 Ensuite, nous allons créer une instance de`FontSettings` en utilisant`FontSettings.DefaultInstance`, puis nous spécifierons les sources de polices utilisées lors du chargement et du rendu des documents. Dans cet exemple, nous utilisons une source de police système et une source de police de dossier.

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
// Chargez le document avec les paramètres de police
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
Dans ce didacticiel, nous avons vu comment configurer les paramètres de police par défaut dans un document Word avec Aspose.Words for .NET. En spécifiant les sources de polices utilisées lors du chargement et du rendu des documents, vous pouvez contrôler l'apparence des polices dans vos documents. N'hésitez pas à utiliser cette fonctionnalité pour personnaliser les paramètres de police dans vos projets.

### FAQ

#### Q : Comment puis-je définir la police par défaut dans Aspose.Words ?

 R : Pour définir la police par défaut dans Aspose.Words, vous pouvez utiliser le`FontSettings` la classe et le`DefaultFontName` propriété spécifiant le nom de la police souhaitée.

#### Q : Puis-je spécifier la taille de police par défaut dans Aspose.Words ?

 R : Oui, vous pouvez spécifier la taille de police par défaut dans Aspose.Words à l'aide du`DefaultFontSize` propriété du`FontSettings` classe. Vous pouvez définir la taille de point souhaitée.

#### Q : Est-il possible de définir la couleur de police par défaut dans Aspose.Words ?

 R : Oui, vous pouvez définir la couleur de police par défaut dans Aspose.Words à l'aide du`DefaultColor` propriété du`FontSettings` classe. Vous pouvez spécifier la couleur à l'aide de valeurs RVB ou de noms prédéfinis.

#### Q : Les paramètres de police par défaut s'appliquent-ils à tous les documents ?

R : Oui, les paramètres de police par défaut s'appliquent à tous les documents créés ou modifiés dans Aspose.Words, sauf si des paramètres spécifiques sont définis pour un document individuel.