---
title: Définir les dossiers de polices avec priorité
linktitle: Définir les dossiers de polices avec priorité
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour définir la priorité des dossiers de polices lors du rendu d'un document à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fonts/set-fonts-folders-with-priority/
---

Dans ce didacticiel, nous vous guiderons pas à pas à travers le processus permettant de définir les dossiers de polices en priorité lors du rendu d'un document à l'aide d'Aspose.Words for .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous saurez comment spécifier plusieurs dossiers de polices avec une priorité de recherche personnalisée lors du rendu de vos documents à l'aide d'Aspose.Words for .NET.

## Étape 1 : Définir le répertoire des documents
Tout d’abord, vous devez définir le chemin d’accès à votre répertoire de documents. Il s'agit de l'emplacement où vous souhaitez enregistrer votre document rendu modifié. Remplacez « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Définir les dossiers de polices en priorité
 Ensuite, vous pouvez définir les dossiers de polices en priorité à l'aide du`FontSettings` la classe et le`SetFontsSources()`méthode. Vous pouvez spécifier plusieurs sources de polices à l'aide d'instances de`SystemFontSource` et`FolderFontSource`. Dans cet exemple, nous avons défini deux sources de polices : la source de polices système par défaut et un dossier de polices personnalisé avec une priorité de 1.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

## Étape 3 : Chargez le document à rendre
 Vous pouvez maintenant charger le document à restituer à l'aide du`Document` classe. Assurez-vous de spécifier le chemin d'accès correct au document.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Étape 4 : Enregistrez le document rendu
 Enfin, vous pouvez enregistrer le document rendu dans un fichier à l'aide de l'option`Save()` méthode du`Document` classe. Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

### Exemple de code source pour définir les dossiers de polices avec priorité à l'aide d'Aspose.Words pour .NET 
```csharp
//Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true,1)
});
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

## Conclusion
Dans ce didacticiel, nous avons appris à définir la priorité des dossiers de polices lors du rendu d'un document à l'aide d'Aspose.Words pour .NET. En suivant ce guide étape par étape, vous pouvez facilement spécifier plusieurs dossiers de polices avec une priorité de recherche personnalisée lors du rendu de vos documents. Aspose.Words propose une API puissante et flexible pour le traitement de mots avec des polices dans vos documents. Grâce à ces connaissances, vous pouvez contrôler et personnaliser les sources de polices utilisées lors du rendu de vos documents selon vos besoins spécifiques.

### FAQ

#### Q : Comment puis-je définir la priorité des dossiers de polices dans Aspose.Words ?

 R : Pour définir les dossiers de polices avec priorité dans Aspose.Words, vous pouvez utiliser le`SetFontsFoldersWithPriority` méthode du`Fonts` classe en spécifiant les emplacements des dossiers de polices et leur ordre de priorité.

#### : Que se passe-t-il si une police est présente dans plusieurs dossiers avec des priorités différentes ?

R : Si une police est présente dans plusieurs dossiers avec une priorité différente, Aspose.Words utilisera la version du dossier ayant la priorité la plus élevée lors du traitement des documents.

#### Q : Puis-je spécifier plusieurs dossiers de polices avec la même priorité dans Aspose.Words ?

R : Oui, vous pouvez spécifier plusieurs dossiers de polices avec la même priorité dans Aspose.Words. Aspose.Words les considérera tous avec la même priorité lors de la recherche de polices dans vos documents.

#### Q : Comment puis-je vérifier les dossiers de polices définis en priorité dans Aspose.Words ?

 R : Pour vérifier les dossiers de polices définis en priorité dans Aspose.Words, vous pouvez utiliser le`GetFolders` méthode du`Fonts` class pour obtenir la liste des dossiers de polices configurés, y compris leur ordre de priorité.

#### Q : À quoi sert de définir des dossiers de polices avec priorité dans Aspose.Words ?

: Définir les dossiers de polices avec priorité dans Aspose.Words vous permet de contrôler l'ordre de recherche des polices dans vos documents Word. Cela vous permet de garantir que les polices souhaitées sont utilisées et d'éviter les problèmes de substitution de polices indésirables.