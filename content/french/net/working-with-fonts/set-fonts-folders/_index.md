---
title: Définir les dossiers de polices
linktitle: Définir les dossiers de polices
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour définir les dossiers de polices lors du rendu d'un document à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fonts/set-fonts-folders/
---

Dans ce didacticiel, nous vous guiderons pas à pas à travers le processus de définition des dossiers de polices lors du rendu d'un document à l'aide d'Aspose.Words for .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous saurez comment spécifier les dossiers de polices à utiliser lors du rendu de vos documents à l'aide d'Aspose.Words for .NET.

## Étape 1 : Définir le répertoire des documents
Tout d’abord, vous devez définir le chemin d’accès à votre répertoire de documents. Il s'agit de l'emplacement où vous souhaitez enregistrer votre document rendu modifié. Remplacez « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : définir les sources de polices
 Ensuite, vous pouvez définir les sources de polices à l'aide du`FontSettings.DefaultInstance` la classe et le`SetFontsSources()` méthode. Dans cet exemple, nous utilisons à la fois une source de police système et une source de police de dossier personnalisé. Assurez-vous d'ajuster le chemin d'accès au dossier des polices personnalisées en fonction de vos besoins.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
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
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

### Exemple de code source pour définir les dossiers de polices à l'aide d'Aspose.Words pour .NET 
```csharp
//Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true)
});
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

## Conclusion
Dans ce didacticiel, nous avons appris à définir des dossiers de polices lors du rendu d'un document à l'aide d'Aspose.Words pour .NET. En suivant ce guide étape par étape, vous pouvez facilement spécifier les sources de polices à utiliser lors du rendu de vos documents. Aspose.Words propose une API puissante et flexible pour le traitement de mots avec des polices dans vos documents. Grâce à ces connaissances, vous pouvez contrôler et personnaliser les sources de polices utilisées lors du rendu de vos documents selon vos besoins spécifiques.

### FAQ

#### Q : Comment puis-je configurer les dossiers de polices dans un document Word à l'aide d'Aspose.Words ?

R : Pour configurer les dossiers de polices dans un document Word à l'aide d'Aspose.Words, vous pouvez utiliser l'API pour spécifier des dossiers de polices personnalisés à utiliser lors de la génération ou de la modification du document. Cela permettra à Word de trouver les polices requises pour un rendu correct.

#### : Est-il possible d'ajouter des polices personnalisées à un document Word avec Aspose.Words ?

R : Oui, avec Aspose.Words, vous pouvez ajouter des polices personnalisées à un document Word. L'API vous permet d'intégrer des polices spécifiques dans votre document, garantissant ainsi qu'elles s'affichent correctement, même si les polices ne sont pas installées sur le système de l'utilisateur final.

#### Q : Que se passe-t-il si les polices requises sont manquantes dans un document Word ?

R : Si les polices requises sont manquantes dans un document Word, Aspose.Words peut détecter ce problème et vous proposer des options pour le résoudre. Vous pouvez choisir de remplacer les polices manquantes par des polices alternatives ou d'inclure les polices manquantes dans le document, ce qui garantit une visualisation correcte.

#### Q : Comment puis-je supprimer les polices personnalisées d'un document Word avec Aspose.Words ?

R : Pour supprimer les polices personnalisées d'un document Word à l'aide d'Aspose.Words, vous pouvez utiliser l'API pour nettoyer le document et supprimer les polices personnalisées qui ne sont plus nécessaires. Cela réduira la taille du fichier et facilitera la gestion des polices.

#### : Est-il important de configurer les dossiers de polices dans un document Word ?

R : Oui, il est important de configurer les dossiers de polices dans un document Word pour garantir que les polices utilisées s'affichent correctement. En spécifiant des dossiers de polices personnalisés à utiliser avec Aspose.Words, vous vous assurez que les polices requises sont disponibles pour restituer correctement les documents Word.