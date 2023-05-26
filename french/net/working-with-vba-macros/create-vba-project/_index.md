---
title: Créer un projet Vba
linktitle: Créer un projet Vba
second_title: Référence de l'API Aspose.Words pour .NET
description: Dans ce didacticiel, découvrez comment créer un projet VBA dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-vba-macros/create-vba-project/
---

Dans ce didacticiel, nous allons vous expliquer comment créer un projet VBA dans un document Word à l'aide de la bibliothèque Aspose.Words pour .NET. La création d'un projet VBA vous permet d'ajouter du code VBA personnalisé à votre document Word. Nous vous guiderons étape par étape pour vous aider à comprendre et à implémenter le code dans votre projet .NET.

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

## Étape 2 : Créer un nouveau document et projet VBA
 Ensuite, nous allons créer un nouveau document en instanciant le`Document` classe et un projet VBA vide en instanciant la`VbaProject` classe.

```csharp
// Créer un nouveau document
Document doc = new Document();

// Créer un nouveau projet VBA
VbaProject project = new VbaProject();
project.Name = "AsposeProject";
doc.VbaProject = project;
```

## Étape 3 : Créer un nouveau module et spécifier le code source de la macro
 Nous allons créer un nouveau module en instanciant le`VbaModule` class et en spécifiant le nom, le type (module procédural) et le code source de la macro.

```csharp
// Créer un nouveau module
VbaModule module = new VbaModule();
module.Name = "AsposeModule";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New Source Code";

// Ajouter le module au projet VBA
doc.VbaProject.Modules.Add(module);
```

## Étape 4 : Enregistrez le document
Enfin, nous enregistrerons le document avec le projet VBA créé dans un fichier.

```csharp
doc.Save(dataDir + "WorkingWithVba.CreateVbaProject.docm");
```

### Exemple de code source pour créer un projet Vba à l'aide d'Aspose.Words pour .NET 

```csharp

// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
VbaProject project = new VbaProject();
project.Name = "AsposeProject";
doc.VbaProject = project;
// Créez un nouveau module et spécifiez un code source de macro.
VbaModule module = new VbaModule();
module.Name = "AsposeModule";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New source code";
// Ajoutez un module au projet VBA.
doc.VbaProject.Modules.Add(module);
doc.Save(dataDir + "WorkingWithVba.CreateVbaProject.docm");

```

## Conclusion
Dans ce tutoriel, nous avons vu comment créer un projet VBA dans un document Word en utilisant Aspose.Words pour .NET. La création d'un projet VBA vous permet d'ajouter et de personnaliser du code VBA dans votre document Word. N'hésitez pas à utiliser cette fonctionnalité pour automatiser des tâches ou ajouter des fonctionnalités personnalisées à vos documents Word.
