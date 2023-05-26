---
title: Modifier les macros Vba
linktitle: Modifier les macros Vba
second_title: Référence de l'API Aspose.Words pour .NET
description: Dans ce didacticiel, découvrez comment modifier les macros VBA d'un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-vba-macros/modify-vba-macros/
---
Dans ce tutoriel, nous expliquerons comment modifier les macros VBA d'un document Word à l'aide de la bibliothèque Aspose.Words pour .NET. L'édition de macros VBA vous permet de mettre à jour le code VBA existant dans votre document Word. Nous vous guiderons étape par étape pour vous aider à comprendre et à implémenter le code dans votre projet .NET.

## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
- Une connaissance pratique du langage de programmation C#
- La bibliothèque Aspose.Words pour .NET installée dans votre projet
- Un document Word contenant des macros VBA que vous souhaitez modifier

## Étape 1 : Définir le répertoire des documents
 Tout d'abord, vous devez définir le chemin du répertoire vers l'emplacement de votre document Word. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin approprié.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Chargez le document contenant les macros VBA
Ensuite, nous allons charger le document Word contenant les macros VBA que nous voulons modifier.

```csharp
// Charger le document contenant les macros VBA
Document doc = new Document(dataDir + "VBA project.docm");
VbaProject project = doc.VbaProject;
```

## Étape 3 : Modifier le code source de la macro
 Nous allons maintenant modifier le code source de la première macro du projet VBA. Remplace le`newSourceCode` variable avec le nouveau code source que vous souhaitez utiliser.

```csharp
const string newSourceCode = "Test change source code";
project.Modules[0].SourceCode = newSourceCode;
```

## Étape 4 : Enregistrer le document modifié
Enfin, nous enregistrerons le document modifié avec les macros VBA mises à jour dans un fichier.

```csharp
doc.Save(dataDir + "WorkingWithVba.ModifyVbaMacros.docm");
```

### Exemple de code source pour modifier les macros Vba à l'aide d'Aspose.Words pour .NET
 
```csharp

// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
VbaProject project = doc.VbaProject;
const string newSourceCode = "Test change source code";
project.Modules[0].SourceCode = newSourceCode;
doc.Save(dataDir + "WorkingWithVba.ModifyVbaMacros.docm");

```

## Conclusion
Dans ce didacticiel, nous avons vu comment modifier des macros VBA dans un document Word à l'aide de Aspose.Words pour .NET. La modification des macros VBA vous permet de mettre à jour le code VBA existant dans votre document pour apporter des modifications ou des améliorations. N'hésitez pas à utiliser cette fonctionnalité pour personnaliser et automatiser davantage vos documents Word.