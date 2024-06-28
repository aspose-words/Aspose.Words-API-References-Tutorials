---
title: Modifier l'espacement et les retraits des paragraphes asiatiques dans un document Word
linktitle: Modifier l'espacement et les retraits des paragraphes asiatiques dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment modifier l'espacement et les retraits des paragraphes asiatiques dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/document-formatting/change-asian-paragraph-spacing-and-indents/
---
Dans ce didacticiel, nous vous expliquerons comment modifier l'espacement et le retrait d'un paragraphe asiatique à l'aide d'Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et appliquer les modifications.

## Étape 1 : Chargement du document

Pour commencer, précisez le répertoire de vos documents et chargez le document contenant la typographie asiatique dans un objet Document. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Étape 2 : Modification de l'espacement et des retraits des paragraphes

Nous allons maintenant modifier l'espacement et les retraits du premier paragraphe du document asiatique. Voici comment:

```csharp
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.CharacterUnitLeftIndent = 10; // Mettre à jour ParagraphFormat.LeftIndent
format.CharacterUnitRightIndent = 10; // Mettre à jour ParagraphFormat.RightIndent
format.CharacterUnitFirstLineIndent = 20; //Mettre à jour ParagraphFormat.FirstLineIndent
format.LineUnitBefore = 5; // Mettre à jour ParagraphFormat.SpaceBefore
format.LineUnitAfter = 10; // Mettre à jour ParagraphFormat.SpaceAfter
```

## Étape 3 : Sauvegarde du document

 Après avoir inséré le champ du formulaire de saisie de texte, enregistrez le document à l'emplacement souhaité à l'aide du`Save` méthode. Assurez-vous de fournir le chemin de fichier approprié :

```csharp
doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");
```

### Exemple de code source pour modifier l'espacement et les retraits des paragraphes asiatiques à l'aide d'Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité Modifier l'espacement et les retraits des paragraphes asiatiques avec Aspose.Words pour .NET :

```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
	format.CharacterUnitLeftIndent = 10;       // ParagraphFormat.LeftIndent sera mis à jour.
	format.CharacterUnitRightIndent = 10;      // ParagraphFormat.RightIndent sera mis à jour.
	format.CharacterUnitFirstLineIndent = 20;  // ParagraphFormat.FirstLineIndent sera mis à jour.
	format.LineUnitBefore = 5;                 // ParagraphFormat.SpaceBefore sera mis à jour
	format.LineUnitAfter = 10;                 // ParagraphFormat.SpaceAfter sera mis à jour

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

Avec ce code, vous pourrez modifier l'espacement et les retraits d'un paragraphe asiatique à l'aide d'Aspose.Words pour .NET.

## Conclusion

 Dans ce didacticiel, nous avons appris à modifier l'espacement et le retrait d'un paragraphe asiatique à l'aide d'Aspose.Words pour .NET. En modifiant les propriétés pertinentes du`ParagraphFormat`nous pouvons contrôler la mise en page et l’apparence des paragraphes asiatiques dans un document Word. Cette fonctionnalité est utile pour personnaliser le formatage du texte avec des caractères asiatiques et obtenir la présentation visuelle souhaitée dans des documents au contenu multilingue.

### FAQ

#### Q : À quoi sert la fonctionnalité « Modifier l'espacement et les retraits des paragraphes asiatiques » dans Aspose.Words pour .NET ?

R : La fonctionnalité « Modifier l'espacement et les retraits des paragraphes asiatiques » dans Aspose.Words pour .NET vous permet de modifier les propriétés d'espacement et d'indentation d'un paragraphe asiatique dans un document Word. Vous pouvez ajuster les valeurs de retrait gauche et droit, de retrait de première ligne, d'espace avant et d'espace après pour contrôler la disposition et l'apparence du paragraphe.

#### Q : Comment modifier l'espacement et le retrait d'un paragraphe asiatique à l'aide d'Aspose.Words pour .NET ?

 R : Pour modifier l'espacement et le retrait d'un paragraphe asiatique, vous devez accéder au`ParagraphFormat`du paragraphe cible et modifier ses propriétés pertinentes. Dans l'exemple de code fourni, nous accédons au premier paragraphe du document et définissons le`CharacterUnitLeftIndent`, `CharacterUnitRightIndent`, `CharacterUnitFirstLineIndent`, `LineUnitBefore` , et`LineUnitAfter` propriétés pour ajuster l’espacement et les retraits.

#### Q : Puis-je appliquer ces modifications à d’autres paragraphes du document ?

 R : Oui, vous pouvez appliquer ces modifications à d'autres paragraphes du document en accédant à leurs`ParagraphFormat` objets. L'exemple de code cible le premier paragraphe du document, mais vous pouvez modifier d'autres paragraphes en ajustant l'index dans le`Paragraphs` collection ou en utilisant d’autres critères pour sélectionner les paragraphes souhaités.