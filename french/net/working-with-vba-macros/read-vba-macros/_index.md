---
title: Lire les macros Vba
linktitle: Lire les macros Vba
second_title: Référence de l'API Aspose.Words pour .NET
description: Dans ce didacticiel, apprenez à lire des macros VBA à partir d'un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-vba-macros/read-vba-macros/
---
Dans ce didacticiel, nous expliquerons comment lire des macros VBA à partir d'un document Word à l'aide de la bibliothèque Aspose.Words pour .NET. La lecture des macros VBA vous permet d'accéder au code VBA existant dans votre document Word. Nous vous guiderons étape par étape pour vous aider à comprendre et à implémenter le code dans votre projet .NET.

## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
- Une connaissance pratique du langage de programmation C#
- La bibliothèque Aspose.Words pour .NET installée dans votre projet
- Un document Word contenant des macros VBA

## Étape 1 : Définir le répertoire des documents
 Tout d'abord, vous devez définir le chemin du répertoire vers l'emplacement de votre document Word. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin approprié.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Chargez le document et lisez les macros VBA
Ensuite, nous allons charger le document Word et vérifier s'il contient un projet VBA. Si le document a un projet VBA, nous allons parcourir tous les modules du projet et afficher le code source de chaque module.

```csharp
//Charger le document
Document doc = new Document(dataDir + "VBA project.docm");
if (doc.VbaProject!= null)
{
foreach(VbaModule module in doc.VbaProject.Modules)
{
Console.WriteLine(module.SourceCode);
}
}
```

### Exemple de code source pour lire les macros Vba à l'aide d'Aspose.Words pour .NET 

```csharp

// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
if (doc.VbaProject != null)
{
	foreach (VbaModule module in doc.VbaProject.Modules)
	{
		Console.WriteLine(module.SourceCode);
	}
}

```

## Conclusion
Dans ce didacticiel, nous avons vu comment lire des macros VBA à partir d'un document Word à l'aide de Aspose.Words pour .NET. La lecture des macros VBA vous permet d'accéder au code VBA existant dans votre document et d'effectuer des opérations selon vos besoins. N'hésitez pas à utiliser cette fonctionnalité pour examiner et analyser les macros VBA dans vos documents Word.


