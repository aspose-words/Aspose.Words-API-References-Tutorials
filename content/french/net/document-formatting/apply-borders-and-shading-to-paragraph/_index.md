---
title: Appliquer des bordures et un ombrage au paragraphe dans un document Word
linktitle: Appliquer des bordures et un ombrage au paragraphe dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment appliquer des bordures et un ombrage à un paragraphe dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
Dans ce didacticiel, nous allons vous montrer comment appliquer des bordures et un ombrage à un paragraphe dans un document Word à l'aide de la fonctionnalité d'Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et appliquer les modifications de formatage.

## Étape 1 : Création et configuration du document

Pour commencer, créez un nouveau document et un objet DocumentBuilder associé. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Configuration des bordures

Configurons maintenant les bordures de paragraphe en spécifiant le style de bordure pour chaque côté. Voici comment:

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders. DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

## Étape 3 : Configuration du remplissage

Nous allons maintenant configurer le remplissage du paragraphe en précisant la texture et les couleurs de remplissage. Voici comment:

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

## Étape 4 : Ajouter du contenu

Nous allons ajouter du contenu formaté au paragraphe. Voici comment:

```csharp
builder.Write("I'm a formatted paragraph with a double border and a nice shading.");
```

## Étape 3 : Sauvegarde du document

 Après avoir inséré le champ du formulaire de saisie de texte, enregistrez le document à l'emplacement souhaité à l'aide du`Save` méthode. Assurez-vous de fournir le chemin de fichier approprié :

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

### Exemple de code source pour appliquer des bordures et des ombres au paragraphe à l'aide d'Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité Appliquer des bordures et un ombrage au paragraphe avec Aspose.Words pour .NET :

```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	BorderCollection borders = builder.ParagraphFormat.Borders;
	borders.DistanceFromText = 20;
	borders[BorderType.Left].LineStyle = LineStyle.Double;
	borders[BorderType.Right].LineStyle = LineStyle.Double;
	borders[BorderType.Top].LineStyle = LineStyle.Double;
	borders[BorderType.Bottom].LineStyle = LineStyle.Double;

	Shading shading = builder.ParagraphFormat.Shading;
	shading.Texture = TextureIndex.TextureDiagonalCross;
	shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
	shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;

	builder.Write("I'm a formatted paragraph with double border and nice shading.");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");

```

## Conclusion

 Dans ce didacticiel, nous avons appris à appliquer des bordures et un ombrage à un paragraphe d'un document Word à l'aide d'Aspose.Words pour .NET. En configurant le paragraphe`Borders` et`Shading` propriétés, nous avons pu définir le style de bordure, la couleur de ligne et la couleur de remplissage du paragraphe. Aspose.Words for .NET offre de puissantes capacités de formatage pour personnaliser l'apparence des paragraphes et améliorer la représentation visuelle de vos documents.

### FAQ

#### Q : Comment appliquer des bordures et un ombrage à un paragraphe dans un document Word à l'aide d'Aspose.Words pour .NET ?

R : Pour appliquer des bordures et un ombrage à un paragraphe dans un document Word à l'aide d'Aspose.Words for .NET, procédez comme suit :
1.  Créez un nouveau document et un`DocumentBuilder` objet.
2.  Configurez les bordures de paragraphe en accédant au`Borders` propriété du`ParagraphFormat` et définir le style de bordure pour chaque côté.
3. Configurez le remplissage du paragraphe en accédant à`Shading` propriété du`ParagraphFormat` et en spécifiant la texture et les couleurs de remplissage.
4.  Ajoutez du contenu au paragraphe en utilisant le`Write` méthode du`DocumentBuilder`.
5.  Enregistrez le document à l'aide du`Save` méthode.

#### Q : Comment définir le style de bordure de chaque côté du paragraphe ?

 R : Pour définir le style de bordure de chaque côté du paragraphe, vous pouvez accéder à la`Borders` propriété du`ParagraphFormat` et réglez le`LineStyle` propriété pour chacun`BorderType` (par exemple.,`BorderType.Left`, `BorderType.Right`, `BorderType.Top`, `BorderType.Bottom` ). Vous pouvez spécifier différents styles de ligne tels que`LineStyle.Single`, `LineStyle.Double`, `LineStyle.Dotted`, etc.

#### Q : Comment puis-je spécifier la texture et les couleurs de remplissage pour l'ombrage du paragraphe ?

 R : Pour spécifier la texture et les couleurs de remplissage de l'ombrage du paragraphe, vous pouvez accéder au`Shading` propriété du`ParagraphFormat` et réglez le`Texture` propriété à un indice de texture souhaité (par exemple,`TextureIndex.TextureDiagonalCross` ). Vous pouvez également définir le`BackgroundPatternColor` et`ForegroundPatternColor` propriétés aux couleurs souhaitées en utilisant le`System.Drawing.Color` classe.