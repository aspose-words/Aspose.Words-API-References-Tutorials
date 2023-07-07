---
title: Activer Désactiver la substitution de police
linktitle: Activer Désactiver la substitution de police
second_title: Référence de l'API Aspose.Words pour .NET
description: Dans ce didacticiel, découvrez comment activer ou désactiver la substitution de polices dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fonts/enable-disable-font-substitution/
---
Dans ce didacticiel, nous vous expliquerons comment activer ou désactiver la substitution de polices dans un document Word lors de son rendu à l'aide de la bibliothèque Aspose.Words pour .NET. L'activation ou la désactivation de la substitution de polices vous permet de contrôler si les polices manquantes sont automatiquement remplacées par une police par défaut. Nous vous guiderons étape par étape pour vous aider à comprendre et à implémenter le code dans votre projet .NET.

## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
- Une connaissance pratique du langage de programmation C#
- La bibliothèque Aspose.Words pour .NET installée dans votre projet
- Un document Word que vous souhaitez afficher avec ou sans substitution de police

## Étape 1 : Définir le répertoire des documents
 Tout d'abord, vous devez définir le chemin du répertoire vers l'emplacement de votre document Word. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin approprié.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : téléchargez le document et configurez les paramètres de police
 Ensuite, nous chargerons le document Word que vous souhaitez rendre et créerons une instance du`FontSettings` classe pour gérer les paramètres de police. Nous allons définir le remplacement de police par défaut en spécifiant le nom de la police dans`DefaultFontName` et désactiver le remplacement des informations de police avec`Enabled` mis à`false`.

```csharp
//Charger le document
Document doc = new Document(dataDir + "Rendering.docx");

// Configurer les paramètres de police
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;

// Appliquer les paramètres de police au document
doc.FontSettings = fontSettings;
```

## Étape 3 : Enregistrer le document rendu
Enfin, nous enregistrerons le document rendu, qui respectera les paramètres de remplacement de police définis.

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```


### Exemple de code source pour activer la substitution de polices désactivée à l'aide d'Aspose.Words pour .NET 

```csharp

// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");

```

## Conclusion
Dans ce didacticiel, nous avons vu comment activer ou désactiver la substitution de polices dans un document Word lors de son rendu avec Aspose.Words pour .NET. En contrôlant la substitution des polices, vous pouvez influencer la manière dont les polices manquantes sont gérées dans vos documents rendus. N'hésitez pas à utiliser cette fonctionnalité pour personnaliser la gestion des polices dans vos documents Word.

### FAQ

#### Q : Comment puis-je activer la substitution de polices dans un document Word avec Aspose.Words ?

R : Pour activer la substitution de polices dans un document Word avec Aspose.Words, vous pouvez utiliser l'API pour spécifier les polices de substitution à utiliser lorsque les polices requises ne sont pas disponibles. Cela garantira une visualisation cohérente du texte, même sans les polices d'origine.

#### Q : Est-il possible de désactiver la substitution de polices dans un document Word avec Aspose.Words ?

R : Oui, avec Aspose.Words, vous pouvez désactiver la substitution de polices dans un document Word. En utilisant l'API, vous pouvez empêcher Word de remplacer les polices requises par d'autres polices, ce qui conserve l'apparence d'origine du texte.

#### Q : Que se passe-t-il lorsque les polices requises sont manquantes lors de la substitution dans un document Word ?

R : Lorsque les polices requises sont manquantes lors de la substitution dans un document Word, Aspose.Words peut détecter ce problème et vous proposer des options pour le résoudre. Vous pouvez choisir de remplacer les polices manquantes par d'autres polices ou d'inclure les polices manquantes dans le document, garantissant un affichage correct.

#### Q : Comment puis-je gérer les polices manquantes lors de la substitution dans un document Word avec Aspose.Words ?

R : Pour gérer les polices manquantes lors de la substitution dans un document Word avec Aspose.Words, vous pouvez utiliser l'API pour détecter les polices manquantes et fournir des options de résolution. Vous pouvez choisir de remplacer les polices manquantes par des polices alternatives ou d'inclure des polices manquantes dans le document, selon vos besoins.

#### Q : Est-il important de contrôler la substitution des polices dans un document Word ?

R : Oui, il est important de contrôler la substitution des polices dans un document Word pour maintenir l'intégrité visuelle du texte. En utilisant Aspose.Words pour activer ou désactiver la substitution de polices, vous pouvez vous assurer que les polices requises sont utilisées et éviter les problèmes de polices manquantes ou remplacées.