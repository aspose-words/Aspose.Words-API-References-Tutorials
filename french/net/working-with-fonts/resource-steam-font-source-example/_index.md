---
title: Ressource Exemple de source de police Steam
linktitle: Ressource Exemple de source de police Steam
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à utiliser Resource Stream Font Source pour charger des polices personnalisées dans Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fonts/resource-steam-font-source-example/
---

Dans ce didacticiel, nous allons vous expliquer comment utiliser Resource Flow Font Source avec Aspose.Words pour .NET. Cette source de polices vous permet de charger des polices à partir d'un flux de ressources, ce qui peut être utile lorsque vous souhaitez incorporer des polices personnalisées dans votre application.

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

## Étape 2 : Télécharger le document et définir la source de police du flux de ressources
 Ensuite, nous allons charger le document en utilisant le`Document` classe et définissez la source de police du flux de ressources à l'aide de la`FontSettings.DefaultInstance.SetFontsSources()` classe. Cela permettra à Aspose.Words de trouver les polices dans le flux de ressources.

```csharp
// Charger le document et définir la source de police du flux de ressources
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{ new SystemFontSource(), new ResourceSteamFontSource() });
```

## Étape 3 : Enregistrez le document
Enfin, nous enregistrerons le document. Les polices seront chargées à partir du flux de ressources spécifié et incorporées dans le document.

```csharp
// Enregistrer le document
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

### Exemple de code source pour Resource Steam Font Source Example utilisant Aspose.Words pour .NET 

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
	{ new SystemFontSource(), new ResourceSteamFontSource() });
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

## Conclusion
Dans ce didacticiel, vous avez appris à utiliser Resource Flow Font Source avec Aspose.Words pour .NET. Cette fonctionnalité vous permet de charger des polices à partir d'un flux de ressources, ce qui est utile lorsque vous souhaitez incorporer des polices personnalisées dans vos documents. Expérimentez avec différentes polices et explorez les possibilités offertes par Aspose.Words pour la gestion des polices.

### FAQ

#### Q : Comment puis-je charger une police à partir d'un flux de ressources dans Aspose.Words ?

 R : Pour charger une police à partir d'un flux de ressources dans Aspose.Words, vous pouvez utiliser le`FontSettings` classe et la`SetFontsSources` méthode pour spécifier la source de la police à l'aide d'un flux de ressources. Cela permet à la police d'être chargée directement à partir du flux de ressources plutôt qu'à partir d'un fichier physique.

#### Q : Quels sont les avantages de l'utilisation de flux de ressources pour spécifier les sources de polices dans Aspose.Words ?

R : L'utilisation de flux de ressources pour spécifier les sources de polices présente plusieurs avantages :
- Vous permet de charger des polices à partir de ressources intégrées à votre application, ce qui facilite le déploiement et la distribution de documents.
- Fournit une flexibilité accrue dans la gestion des polices car vous pouvez charger des polices à partir de différents flux de ressources en fonction de vos besoins.

#### Q : Comment puis-je ajouter des polices à un flux de ressources dans mon application .NET ?

 R : Pour ajouter des polices à un flux de ressources dans votre application .NET, vous devez incorporer les fichiers de polices dans les ressources de votre projet. Vous pouvez ensuite accéder à ces fichiers de polices en utilisant des méthodes spécifiques à votre plate-forme de développement (par exemple,`GetManifestResourceStream` en utilisant le`System.Reflection` espace de noms).

#### Q : Est-il possible de charger plusieurs polices à partir de différents flux de ressources dans un seul document Aspose.Words ?

 R : Oui, il est tout à fait possible de charger plusieurs polices à partir de différents flux de ressources dans un seul document Aspose.Words. Vous pouvez spécifier plusieurs sources de polices à l'aide de la`SetFontsSources` méthode de la`FontSettings` classe, fournissant les flux de ressources appropriés pour chaque police.

#### Q : Quels types de flux de ressources puis-je utiliser pour charger des polices dans Aspose.Words ?

R : Vous pouvez utiliser différents types de flux de ressources pour charger des polices dans Aspose.Words, tels que des flux de ressources intégrés à votre application .NET, des flux de ressources à partir d'un fichier externe, des flux de ressources à partir d'une base de données, etc. flux de ressources en fonction de votre configuration et de vos besoins.