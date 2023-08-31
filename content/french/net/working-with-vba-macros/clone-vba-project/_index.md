---
title: Cloner un projet Vba à partir d'un document Word
linktitle: Cloner un projet Vba à partir d'un document Word
second_title: API de traitement de documents Aspose.Words
description: Dans ce didacticiel, découvrez comment cloner un projet VBA à partir d'un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-vba-macros/clone-vba-project/
---

Dans ce tutoriel, nous allons vous expliquer comment cloner un projet VBA à partir d'un document Word avec des macros à l'aide de la bibliothèque Aspose.Words pour .NET. Le clonage d'un projet VBA vous permet de copier tout le code VBA d'un document source vers un autre document. Nous vous guiderons étape par étape pour vous aider à comprendre et à implémenter le code dans votre projet .NET.

## Conditions préalables
Avant de commencer, assurez-vous de disposer des éléments suivants :
- Une connaissance pratique du langage de programmation C#
- La bibliothèque Aspose.Words pour .NET installée dans votre projet
- Un document Word contenant un projet VBA que vous souhaitez cloner

## Étape 1 : Définir le répertoire des documents
 Tout d’abord, vous devez définir le chemin du répertoire vers l’emplacement de votre document Word. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin approprié.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Charger le document source
Ensuite, nous chargerons le document Word source, qui contient le projet VBA que nous souhaitons cloner.

```csharp
// Charger le document source
Document doc = new Document(dataDir + "VBA project.docm");
```

## Étape 3 : Créez un nouveau document avec le projet VBA cloné
Nous allons créer un nouveau document avec un projet VBA vide et cloner le projet VBA à partir du document source.

```csharp
// Créer un nouveau document avec un projet VBA vide
Document destDoc = new Document { VbaProject = doc.VbaProject.Clone() };
```

## Étape 4 : Enregistrez le document de destination
Enfin, nous enregistrerons le document de destination ainsi que le projet VBA cloné dans un fichier.

```csharp
destDoc.Save(dataDir + "WorkingWithVba.CloneVbaProject.docm");
```

### Exemple de code source pour le projet Clone Vba à l'aide d'Aspose.Words pour .NET 
```csharp

//Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
Document destDoc = new Document { VbaProject = doc.VbaProject.Clone() };

destDoc.Save(dataDir + "WorkingWithVba.CloneVbaProject.docm");

```

## Conclusion
Dans ce tutoriel, nous avons vu comment cloner un projet VBA à partir d'un document Word avec des macros à l'aide d'Aspose.Words pour .NET. Le clonage de projets VBA vous permet de copier tout le code VBA d'un document source vers un autre document. N'hésitez pas à utiliser cette fonctionnalité pour organiser et gérer vos macros dans différents documents.

### FAQ

#### Q : Qu'est-ce que la duplication d'un projet VBA ?

R : Dupliquer un projet VBA consiste à copier tout le code VBA d'un document Word source vers un autre document. Cela vous permet de réutiliser le code VBA dans différents contextes ou de le partager avec d'autres documents.

#### Q : Quels sont les prérequis pour cloner un projet VBA à partir d'un document Word ?

R : Avant de pouvoir cloner un projet VBA à partir d'un document Word, vous devez avoir une connaissance pratique du langage de programmation C#. Vous devez également installer la bibliothèque Aspose.Words for .NET dans votre projet. Vous avez également besoin d'un document Word contenant un projet VBA que vous souhaitez cloner.

#### Q : Comment définir le répertoire des documents dans le code ?
 R : Dans le code fourni, vous devez remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le chemin approprié vers le répertoire où se trouve votre document Word contenant le projet VBA.

#### Q : Comment enregistrer le document de destination avec un projet VBA cloné ?

R : Pour enregistrer le document de destination avec le projet VBA cloné, vous pouvez utiliser l'outil`Save` méthode du`Document` classe en spécifiant le chemin de destination et le nom de fichier souhaités.

#### Q : Puis-je utiliser Aspose.Words pour .NET pour manipuler d’autres aspects des documents Word ?

R : Oui, Aspose.Words for .NET est une bibliothèque puissante qui vous permet de manipuler divers aspects des documents Word. Vous pouvez créer, modifier, convertir et extraire des données à partir de documents Word, notamment du contenu, du formatage, des images, des tableaux, des graphiques, etc.