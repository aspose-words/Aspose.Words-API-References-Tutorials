---
title: Groupe de sauts de ligne de typographie asiatique dans un document Word
linktitle: Groupe de sauts de ligne de typographie asiatique dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Apprenez à utiliser le groupe de sauts de ligne de typographie asiatique dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/document-formatting/asian-typography-line-break-group/
---
Dans ce didacticiel, nous allons vous montrer comment utiliser le groupe de sauts de ligne de typographie asiatique dans la fonctionnalité de document Word avec Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et appliquer les modifications de formatage.

## Étape 1 : Chargement du document

Pour commencer, précisez le répertoire de vos documents et chargez le document contenant la typographie asiatique dans un objet Document. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Étape 2 : configuration de la typographie asiatique

Nous allons maintenant configurer les paramètres de typographie asiatique pour le premier paragraphe du document. Voici comment:

```csharp
ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
format. FarEastLineBreakControl = false;
format. WordWrap = true;
format. HangingPunctuation = false;
```

## Étape 3 : Sauvegarde du document

 Après avoir inséré le champ du formulaire de saisie de texte, enregistrez le document à l'emplacement souhaité à l'aide du`Save` méthode. Assurez-vous de fournir le chemin de fichier approprié :

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### Exemple de code source pour le groupe de sauts de ligne de typographie asiatique utilisant Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité Asian Typography Line Break Group avec Aspose.Words pour .NET :

```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
	format.FarEastLineBreakControl = false;
	format.WordWrap = true;
	format.HangingPunctuation = false;

	doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
	
```
Avec ce code, vous pourrez appliquer le groupe de sauts de ligne de typographie asiatique à l'aide d'Aspose.Words pour .NET.

## Conclusion

 Dans ce didacticiel, nous avons exploré la fonctionnalité « Groupe de sauts de ligne de typographie asiatique » dans Aspose.Words pour .NET. En configurant le`FarEastLineBreakControl`, `WordWrap` , et`HangingPunctuation` propriétés du`ParagraphFormat`, nous avons pu contrôler le comportement des sauts de ligne pour la typographie asiatique dans un document Word. Cette fonctionnalité est utile pour gérer les caractères asiatiques et garantir des sauts de ligne et un renvoi à la ligne appropriés dans les documents dont le contenu est multilingue.

### FAQ

#### Q : Qu'est-ce que la fonctionnalité « Groupe de sauts de ligne de typographie asiatique » dans Aspose.Words pour .NET ?

: La fonctionnalité « Groupe de sauts de ligne de typographie asiatique » dans Aspose.Words pour .NET vous permet de contrôler le comportement des sauts de ligne pour la typographie asiatique dans un document Word. Plus précisément, cela affecte la façon dont les lignes sont interrompues et renvoyées à la ligne lorsqu'il s'agit de caractères asiatiques dans les paragraphes.

#### Q : Comment puis-je activer le « Groupe de sauts de ligne de typographie asiatique » dans Aspose.Words pour .NET ?

 R : Pour activer le « Groupe de sauts de ligne de typographie asiatique », vous devez configurer le`FarEastLineBreakControl`, `WordWrap` , et`HangingPunctuation` propriétés du`ParagraphFormat` pour le(s) paragraphe(s) pertinent(s) de votre document. Paramètre`FarEastLineBreakControl` à`false` garantit que les caractères asiatiques sont traités de la même manière que les caractères latins en ce qui concerne les sauts de ligne.`WordWrap` mis à`true` permet le retour à la ligne automatique pour la typographie asiatique, et`HangingPunctuation` mis à`false` empêche la ponctuation de rester bloquée dans le texte asiatique.

#### Q : Puis-je appliquer le « Groupe de sauts de ligne de typographie asiatique » à des paragraphes spécifiques d'un document ?

 : Oui, vous pouvez appliquer les paramètres « Groupe de sauts de ligne de typographie asiatique » à des paragraphes spécifiques dans un document Word. Dans l'exemple de code, les paramètres sont appliqués au premier paragraphe du document. Vous pouvez ajuster le code pour cibler d'autres paragraphes selon vos besoins en y accédant via le`Paragraphs` collection de la ou des sections pertinentes du document.