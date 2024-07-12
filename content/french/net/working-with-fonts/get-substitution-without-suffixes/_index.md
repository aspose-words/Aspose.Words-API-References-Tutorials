---
title: Obtenez une substitution sans suffixes
linktitle: Obtenez une substitution sans suffixes
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment gérer la substitution de polices sans suffixes dans Aspose.Words pour .NET. Suivez notre guide étape par étape pour garantir que vos documents soient parfaits à chaque fois.
type: docs
weight: 10
url: /fr/net/working-with-fonts/get-substitution-without-suffixes/
---

Bienvenue dans ce guide complet sur la gestion de la substitution de polices à l'aide d'Aspose.Words pour .NET. Si vous avez déjà eu du mal à ce que les polices n'apparaissent pas correctement dans vos documents, vous êtes au bon endroit. Ce didacticiel vous guidera à travers un processus étape par étape pour gérer efficacement la substitution de polices sans suffixes. Commençons!

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous d'avoir les éléments suivants :

- Connaissance de base de C# : Comprendre la programmation C# facilitera le suivi et la mise en œuvre des étapes.
-  Aspose.Words for .NET Library : téléchargez et installez la bibliothèque à partir du[lien de téléchargement](https://releases.aspose.com/words/net/).
- Environnement de développement : configurez un environnement de développement tel que Visual Studio pour écrire et exécuter votre code.
- Exemple de document : Un exemple de document (par exemple,`Rendering.docx`) avec lequel travailler pendant ce didacticiel.

## Importer des espaces de noms

Tout d’abord, nous devons importer les espaces de noms nécessaires pour accéder aux classes et méthodes fournies par Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
using Aspose.Words.WarningInfo;
using System.Collections.Generic;
```

## Étape 1 : Définir le répertoire des documents

Pour commencer, précisez le répertoire où se trouve votre document. Cela aide à localiser le document sur lequel vous souhaitez travailler.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : configurer le gestionnaire d'avertissement de substitution

Ensuite, nous devons configurer un gestionnaire d'avertissement qui nous avertira chaque fois qu'une substitution de police se produit pendant le traitement du document. Ceci est crucial pour détecter et gérer tout problème de police.

```csharp
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
Document doc = new Document(dataDir + "Rendering.docx");
doc.WarningCallback = substitutionWarningHandler;
```

## Étape 3 : Ajouter des sources de polices personnalisées

Dans cette étape, nous ajouterons des sources de polices personnalisées pour garantir qu'Aspose.Words puisse localiser et utiliser les polices appropriées. Ceci est particulièrement utile si vous avez des polices spécifiques stockées dans des répertoires personnalisés.

```csharp
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());

FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

Dans ce code :
-  Nous récupérons les sources de polices actuelles et ajoutons une nouvelle`FolderFontSource` pointant vers notre répertoire de polices personnalisé (`C:\\MyFonts\\`).
- Nous mettons ensuite à jour les sources de polices avec cette nouvelle liste.

## Étape 4 : Enregistrez le document

Enfin, enregistrez le document après avoir appliqué les paramètres de substitution de police. Pour ce didacticiel, nous l'enregistrerons au format PDF.

```csharp
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

## Étape 5 : Créer la classe de gestionnaire d’avertissements

Pour gérer efficacement les avertissements, créez une classe personnalisée qui implémente le`IWarningCallback` interface. Cette classe capturera et enregistrera tous les avertissements de substitution de police.

```csharp
public class DocumentSubstitutionWarnings : IWarningCallback
{
    public void Warning(WarningInfo info)
    {
        if (info.WarningType == WarningType.FontSubstitution)
            FontWarnings.Warning(info);
    }

    public WarningInfoCollection FontWarnings = new WarningInfoCollection();
}
```

Dans cette classe:
-  Le`Warning` La méthode capture les avertissements liés à la substitution de polices.
-  Le`FontWarnings` La collection stocke ces avertissements pour une inspection ou une journalisation plus approfondie.

## Conclusion

Vous maîtrisez désormais le processus de gestion de la substitution de polices sans suffixes à l'aide d'Aspose.Words pour .NET. Cette connaissance garantira que vos documents conservent leur apparence prévue, quelles que soient les polices disponibles sur le système. Continuez à expérimenter avec différents paramètres et sources pour exploiter pleinement la puissance d'Aspose.Words.

## FAQ

### Q1 : Comment puis-je utiliser les polices de plusieurs répertoires personnalisés ?

 Vous pouvez en ajouter plusieurs`FolderFontSource` instances à la`fontSources` répertoriez et mettez à jour les sources de polices en conséquence.

### Q2 : Où puis-je télécharger un essai gratuit d'Aspose.Words pour .NET ?

 Vous pouvez télécharger un essai gratuit à partir du[Page d'essai gratuit d'Aspose](https://releases.aspose.com/).

###  Q3 : Puis-je gérer plusieurs types d'avertissements à l'aide de`IWarningCallback`?

 Oui le`IWarningCallback` L'interface vous permet de gérer différents types d'avertissements, pas seulement la substitution de polices.

### Q4 : Où puis-je obtenir de l'aide pour Aspose.Words ?

 Pour obtenir de l'aide, visitez le[Forum d'assistance Aspose.Words](https://forum.aspose.com/c/words/8).

### Q5 : Est-il possible d’acheter une licence temporaire ?

 Oui, vous pouvez obtenir une licence temporaire auprès du[page de licence temporaire](https://purchase.aspose.com/temporary-license/).