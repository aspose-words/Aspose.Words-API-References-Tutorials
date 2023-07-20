---
title: Groupe de saut de ligne de typographie asiatique dans un document Word
linktitle: Groupe de saut de ligne de typographie asiatique dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Apprenez à utiliser le groupe de sauts de ligne Asian Typography dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/document-formatting/asian-typography-line-break-group/
---
Dans ce didacticiel, nous allons vous montrer comment utiliser le groupe de sauts de ligne de typographie asiatique dans la fonctionnalité de document Word avec Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et appliquer les modifications de mise en forme.

## Étape 1 : Chargement du document

Pour commencer, spécifiez le répertoire de vos documents et chargez le document contenant la typographie asiatique dans un objet Document. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Étape 2 : configuration de la typographie asiatique

Nous allons maintenant configurer les paramètres de typographie asiatique pour le premier paragraphe du document. Voici comment:

```csharp
ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
format. FarEastLineBreakControl = false;
format. WordWrap = true;
format. HangingPunctuation = false;
```

## Étape 3 : Enregistrer le document

 Après avoir inséré le champ du formulaire de saisie de texte, enregistrez le document à l'emplacement souhaité à l'aide de la`Save` méthode. Assurez-vous de fournir le chemin d'accès au fichier approprié :

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### Exemple de code source pour le groupe de sauts de ligne de typographie asiatique utilisant Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité Asian Typography Line Break Group avec Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
	format.FarEastLineBreakControl = false;
	format.WordWrap = true;
	format.HangingPunctuation = false;

	doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
	
```
Avec ce code, vous pourrez appliquer un groupe de sauts de ligne de typographie asiatique en utilisant Aspose.Words pour .NET.

## Conclusion

 Dans ce didacticiel, nous avons exploré la fonctionnalité "Groupe de sauts de ligne de typographie asiatique" dans Aspose.Words pour .NET. En configurant le`FarEastLineBreakControl`, `WordWrap` , et`HangingPunctuation` propriétés de la`ParagraphFormat`, nous avons pu contrôler le comportement des sauts de ligne pour la typographie asiatique dans un document Word. Cette fonctionnalité est utile pour gérer les caractères asiatiques et garantir des sauts de ligne et des retours à la ligne appropriés dans les documents au contenu linguistique mixte.

### FAQ

#### Q : Qu'est-ce que la fonctionnalité "Groupe de sauts de ligne de typographie asiatique" dans Aspose.Words pour .NET ?

R : La fonctionnalité "Groupe de sauts de ligne de typographie asiatique" dans Aspose.Words pour .NET vous permet de contrôler le comportement des sauts de ligne pour la typographie asiatique dans un document Word. Plus précisément, cela affecte la manière dont les lignes sont interrompues et renvoyées à la ligne lorsqu'il s'agit de caractères asiatiques dans les paragraphes.

#### Q : Comment activer le "Groupe de saut de ligne de typographie asiatique" dans Aspose.Words pour .NET ?

 R : Pour activer le « Groupe de sauts de ligne de typographie asiatique », vous devez configurer le`FarEastLineBreakControl`, `WordWrap` , et`HangingPunctuation` propriétés de la`ParagraphFormat` pour le(s) paragraphe(s) pertinent(s) de votre document. Paramètre`FarEastLineBreakControl` pour`false` garantit que les caractères asiatiques sont traités de la même manière que les caractères latins en ce qui concerne les sauts de ligne.`WordWrap` mis à`true` permet l'habillage de mots pour la typographie asiatique, et`HangingPunctuation` mis à`false` empêche la ponctuation de se bloquer dans le texte asiatique.

#### Q : Puis-je appliquer le "Groupe de sauts de ligne de typographie asiatique" à des paragraphes spécifiques d'un document ?

R : Oui, vous pouvez appliquer les paramètres "Groupe de sauts de ligne de typographie asiatique" à des paragraphes spécifiques d'un document Word. Dans l'exemple de code, les paramètres sont appliqués au premier paragraphe du document. Vous pouvez ajuster le code pour cibler d'autres paragraphes selon vos besoins en y accédant via le`Paragraphs` collection de la ou des sections pertinentes dans le document.