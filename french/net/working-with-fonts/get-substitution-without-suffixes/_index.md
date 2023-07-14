---
title: Obtenir une substitution sans suffixes
linktitle: Obtenir une substitution sans suffixes
second_title: API de traitement de documents Aspose.Words
description: Dans ce didacticiel, découvrez comment obtenir des remplacements sans suffixe dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fonts/get-substitution-without-suffixes/
---

Dans ce didacticiel, nous allons vous montrer comment obtenir les remplacements sans suffixes dans un document Word à l'aide de la bibliothèque Aspose.Words pour .NET. Les substitutions sans suffixes sont utilisées pour résoudre les problèmes de substitution de police lors de l'affichage ou de l'impression de documents. Nous vous guiderons étape par étape pour vous aider à comprendre et à implémenter le code dans votre projet .NET.

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

## Étape 2 : Chargez le document et configurez les substitutions sans suffixes
 Ensuite, nous allons charger le document en utilisant le`Document` classer et configurer des substitutions sans suffixe à l'aide de`DocumentSubstitutionWarnings` classe. Nous ajouterons également une source de polices en spécifiant un dossier contenant les polices.

```csharp
// Charger le document et configurer les substitutions sans suffixes
Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;

List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

## Étape 3 : Enregistrez le document
Enfin, nous enregistrerons le document avec les remplacements sans suffixe appliqués.

```csharp
// Enregistrer le document
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

### Exemple de code source pour obtenir une substitution sans suffixes à l'aide d'Aspose.Words pour .NET 
```csharp

//Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");

```

## Conclusion
Dans ce didacticiel, nous avons vu comment obtenir les remplacements sans suffixes dans un document Word avec Aspose.Words pour .NET. Les substitutions sans suffixes sont utiles pour résoudre les problèmes de substitution de polices. N'hésitez pas à utiliser cette fonctionnalité pour améliorer l'affichage et l'impression de vos documents.

### FAQ

#### Q : Pourquoi Aspose.Words ajoute-t-il des suffixes aux substitutions de police ?

R : Aspose.Words ajoute des suffixes aux substitutions de polices pour éviter les conflits entre les polices d'origine et les polices de substitution. Cela permet d'assurer une compatibilité maximale lors de la conversion et de la manipulation de documents.

#### Q : Comment puis-je récupérer des substitutions de polices sans suffixes dans Aspose.Words ?

 R : Pour récupérer des substitutions de polices sans suffixes dans Aspose.Words, vous pouvez utiliser le`FontSubstitutionSettings` classe et la`RemoveSuffixes` propriété. Définir cette propriété sur`true` obtiendra les substitutions de polices sans les suffixes ajoutés.

#### Q : Est-il possible de désactiver l'ajout de suffixes aux substitutions de polices dans Aspose.Words ?

: Non, il n'est pas possible de désactiver l'ajout de suffixes aux substitutions de polices dans Aspose.Words. Les suffixes sont ajoutés par défaut pour assurer la compatibilité et la cohérence du document.

#### Q : Comment puis-je filtrer les suffixes indésirables dans les substitutions de polices dans Aspose.Words ?

 R : Pour filtrer les suffixes indésirables dans les substitutions de polices dans Aspose.Words, vous pouvez utiliser des techniques de traitement de chaîne, telles que l'utilisation de`Replace` ou`Substring` méthodes pour supprimer les suffixes spécifiques que vous ne souhaitez pas inclure.