---
title: Cloner le projet Vba
linktitle: Cloner le projet Vba
second_title: Référence de l'API Aspose.Words pour .NET
description: Dans ce didacticiel, découvrez comment cloner un projet VBA à partir d'un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-vba-macros/clone-vba-project/
---

Dans ce didacticiel, nous allons vous expliquer comment cloner un projet VBA à partir d'un document Word avec des macros à l'aide de la bibliothèque Aspose.Words pour .NET. Le clonage d'un projet VBA vous permet de copier tout le code VBA d'un document source vers un autre document. Nous vous guiderons étape par étape pour vous aider à comprendre et à implémenter le code dans votre projet .NET.

## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
- Une connaissance pratique du langage de programmation C#
- La bibliothèque Aspose.Words pour .NET installée dans votre projet
- Un document Word contenant un projet VBA que vous souhaitez cloner

## Étape 1 : Définir le répertoire des documents
 Tout d'abord, vous devez définir le chemin du répertoire vers l'emplacement de votre document Word. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin approprié.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Charger le document source
Ensuite, nous allons charger le document Word source, qui contient le projet VBA que nous voulons cloner.

```csharp
// Charger le document source
Document doc = new Document(dataDir + "VBA project.docm");
```

## Étape 3 : Créer un nouveau document avec le projet VBA cloné
Nous allons créer un nouveau document avec un projet VBA vide et cloner le projet VBA à partir du document source.

```csharp
// Créer un nouveau document avec un projet VBA vide
Document destDoc = new Document { VbaProject = doc.VbaProject.Clone() };
```

## Étape 4 : Enregistrer le document de destination
Enfin, nous enregistrerons le document de destination avec le projet VBA cloné dans un fichier.

```csharp
destDoc.Save(dataDir + "WorkingWithVba.CloneVbaProject.docm");
```

### Exemple de code source pour le projet Clone Vba utilisant Aspose.Words pour .NET 
```csharp

// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
Document destDoc = new Document { VbaProject = doc.VbaProject.Clone() };

destDoc.Save(dataDir + "WorkingWithVba.CloneVbaProject.docm");

```

## Conclusion
Dans ce didacticiel, nous avons vu comment cloner un projet VBA à partir d'un document Word avec des macros à l'aide de Aspose.Words pour .NET. Le clonage de projets VBA vous permet de copier tout le code VBA d'un document source vers un autre document. N'hésitez pas à utiliser cette fonctionnalité pour organiser et gérer vos macros dans différents documents.
