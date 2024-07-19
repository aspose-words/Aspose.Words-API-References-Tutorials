---
title: Obtenir la liste des polices disponibles
linktitle: Obtenir la liste des polices disponibles
second_title: API de traitement de documents Aspose.Words
description: Dans ce didacticiel, découvrez comment obtenir la liste des polices disponibles dans Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/working-with-fonts/get-list-of-available-fonts/
---
Dans ce tutoriel, nous expliquerons comment obtenir la liste des polices disponibles dans Aspose.Words for .NET. La liste des polices disponibles vous permet de savoir quelles polices vous pouvez utiliser dans vos documents. Nous vous guiderons étape par étape pour vous aider à comprendre et à implémenter le code dans votre projet .NET.

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

## Étape 2 : Configurer les sources de polices
 Ensuite, nous allons créer une instance de`FontSettings` et récupérez les sources de polices existantes en utilisant le`GetFontsSources()` méthode. Nous ajouterons également une nouvelle source de polices en spécifiant un dossier contenant les polices.

```csharp
// Configurer les sources de polices
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

// Ajouter une nouvelle source de police
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## Étape 3 : Obtenez la liste des polices disponibles
 Nous allons maintenant parcourir les polices disponibles en utilisant le`GetAvailableFonts()` méthode sur la première source de police mise à jour.

```csharp
// Obtenir la liste des polices disponibles
foreach(PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
Console.WriteLine("Font Family Name: " + fontInfo.FontFamilyName);
Console.WriteLine("Full font name: " + fontInfo.FullFontName);
Console.WriteLine("Version: " + fontInfo.Version);
Console.WriteLine("Path: " + fontInfo.FilePath);
}
```


### Exemple de code source pour obtenir la liste des polices disponibles à l'aide d'Aspose.Words pour .NET 

```csharp

// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Ajoutez une nouvelle source de dossier qui demandera à Aspose.Words de rechercher les polices dans le dossier suivant.
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
// Ajoutez le dossier personnalisé contenant nos polices à la liste des sources de polices existantes.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
	Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
	Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
	Console.WriteLine("Version  : " + fontInfo.Version);
	Console.WriteLine("FilePath : " + fontInfo.FilePath);
}

```

## Conclusion
Dans ce tutoriel, nous avons vu comment obtenir la liste des polices disponibles dans Aspose.Words for .NET. Cela vous permet de savoir quelles polices vous pouvez utiliser dans vos documents. N'hésitez pas à utiliser cette fonctionnalité pour choisir les polices appropriées à vos besoins.

### FAQ

#### Q : Comment puis-je récupérer la liste des polices disponibles dans Aspose.Words ?

 R : Pour récupérer la liste des polices disponibles dans Aspose.Words, vous pouvez utiliser le`FontsProvider` la classe et le`GetAvailableFonts` méthode. Cette méthode renverra une liste de toutes les polices installées sur votre système.

#### Q : Puis-je filtrer la liste des polices disponibles selon certains critères dans Aspose.Words ?

R : Oui, vous pouvez filtrer la liste des polices disponibles dans Aspose.Words en utilisant des critères spécifiques. Par exemple, vous pouvez filtrer les polices par famille, style ou langue.

#### Q : Comment puis-je utiliser la liste des polices disponibles dans mes documents Word ?

 R : Pour utiliser la liste des polices disponibles dans vos documents Word, vous pouvez parcourir la liste et sélectionner les polices appropriées à l'aide des méthodes et propriétés du`FontSettings` classe dans Aspose.Words.