---
title: Définir les dossiers de polices
linktitle: Définir les dossiers de polices
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment définir des dossiers de polices personnalisés dans Aspose.Words for .NET avec ce guide complet étape par étape. Parfait pour les développeurs cherchant à améliorer les polices de documents.
type: docs
weight: 10
url: /fr/net/working-with-fonts/set-fonts-folders/
---
## Introduction

Salut! Prêt à plonger dans le monde des polices personnalisées dans Aspose.Words for .NET ? Commençons. Ce didacticiel vous guidera tout au long du processus de définition de dossiers de polices personnalisés, garantissant que vos documents auront exactement l'apparence que vous souhaitez. Que vous soyez un développeur chevronné ou débutant, ce guide vous guidera à travers chaque étape. Alors, donnons à ces polices un look fabuleux !

## Conditions préalables

Avant de nous lancer, assurons-nous que vous disposez de tout ce dont vous avez besoin :

-  Aspose.Words pour .NET : vous pouvez[télécharger](https://releases.aspose.com/words/net/) si vous ne l'avez pas déjà fait.
- Visual Studio : n'importe quelle version fonctionnera, mais la dernière est toujours la meilleure.
- Un document : nous utiliserons un document Word pour ce didacticiel. Vous pouvez créer le vôtre ou en utiliser un existant.
- Polices personnalisées : préparez des polices personnalisées. Nous les utiliserons pour montrer comment définir les dossiers de polices.

## Importer des espaces de noms

Tout d’abord, importons les espaces de noms nécessaires. Ceci est essentiel pour accéder aux classes et méthodes dont nous avons besoin depuis Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

Une fois ces espaces de noms importés, nous sommes prêts à commencer à configurer nos dossiers de polices personnalisés.

## Étape 1 : définissez votre répertoire de documents

 Commençons par définir le chemin d'accès à votre répertoire de documents. C'est ici que votre document Word est stocké. Nous utiliserons une variable appelée`dataDir` pour stocker ce chemin.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel de votre répertoire. Ceci est crucial car Aspose.Words devra savoir où trouver votre document.

## Étape 2 : définir les sources de polices

 Ensuite, nous devons configurer les sources des polices. C'est ici que nous indiquons à Aspose.Words où trouver nos polices personnalisées. Nous allons utiliser le`FontSettings.DefaultInstance.SetFontsSources` méthode pour y parvenir.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true)
});
```

Voici ce que nous faisons :

- SystemFontSource : cela indique à Aspose.Words d'utiliser les polices par défaut du système.
-  FolderFontSource : C'est ici que nous spécifions le dossier contenant nos polices personnalisées. Remplacer`"C:\\MyFonts\\"` avec le chemin d'accès à votre répertoire de polices personnalisées. Le`true` Le paramètre indique que les sous-répertoires doivent également être inclus.

## Étape 3 : Chargez votre document

Maintenant que nous avons configuré nos sources de polices, il est temps de charger le document avec lequel nous voulons travailler. Nous utiliserons le`Document` classe d'Aspose.Words pour cela.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

 Assurez-vous que`"Rendering.docx"` est le nom de votre document Word. Si votre document porte un nom différent, assurez-vous de le mettre à jour en conséquence.

## Étape 4 : Enregistrez votre document au format PDF

 Enfin, enregistrons notre document au format PDF pour voir les polices personnalisées en action. Nous utiliserons le`Save` méthode du`Document` classe.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

Cela enregistrera votre document au format PDF dans le répertoire spécifié, en utilisant les polices personnalisées que nous avons configurées précédemment.

## Conclusion

Et voilà ! Vous avez configuré avec succès des dossiers de polices personnalisées dans Aspose.Words pour .NET et enregistré votre document au format PDF avec ces polices personnalisées. Plutôt cool, non ? La personnalisation des polices peut faire une énorme différence dans l’apparence de vos documents, et vous savez désormais exactement comment procéder. Bon codage !

## FAQ

### Comment installer Aspose.Words pour .NET ?

 Tu peux[télécharger](https://releases.aspose.com/words/net/) la dernière version d’Aspose.Words pour .NET sur le site Web.

### Puis-je utiliser plusieurs dossiers de polices personnalisées ?

 Oui, vous pouvez en ajouter plusieurs`FolderFontSource` instances à la`SetFontsSources`méthode pour utiliser des polices de différents répertoires.

### Est-il nécessaire d’inclure les polices système ?

L'inclusion des polices système est facultative mais recommandée pour garantir que toutes les polices standard sont disponibles.

### Quels types de fichiers sont pris en charge par Aspose.Words ?

Aspose.Words prend en charge un large éventail de formats de fichiers, notamment DOCX, DOC, PDF, TXT, HTML et bien d'autres.

### Comment puis-je obtenir une licence temporaire pour Aspose.Words ?

 Vous pouvez obtenir un[permis temporaire](https://purchase.aspose.com/temporary-license/) sur le site Web Aspose pour essayer toutes les fonctionnalités d’Aspose.Words.