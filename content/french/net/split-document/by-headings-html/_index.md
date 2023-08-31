---
title: Diviser un document Word par titres Html
linktitle: Par rubriques HTML
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour expliquer le code source C# du document Word divisé Par la fonctionnalité HTML d'en-tête d'Aspose.Words pour .NET
type: docs
weight: 10
url: /fr/net/split-document/by-headings-html/
---
Dans ce didacticiel, nous vous expliquerons comment diviser un document Word en parties plus petites à l'aide de la fonctionnalité Par titre HTML d'Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et générer des documents HTML distincts basés sur le titre.

## Étape 1 : Chargement du document

Pour commencer, spécifiez le répertoire de votre document et chargez le document dans un objet Document. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Étape 2 : Diviser le document par titre au format HTML

Nous allons maintenant définir les options de sauvegarde pour diviser le document en parties plus petites en fonction du titre au format HTML. Voici comment:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
// Divisez le document en parties plus petites, dans ce cas en le séparant par titre.
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### Exemple de code source pour By Headings HTML utilisant Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité Par titre HTML d'Aspose.Words pour .NET :

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	// Divisez un document en parties plus petites, dans ce cas divisé par titre.
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

Avec ce code, vous pourrez diviser un document Word en parties plus petites à l'aide d'Aspose.Words for .NET, en fonction des titres. Vous pouvez ensuite générer des documents HTML distincts pour chaque partie.

## Conclusion

 Dans ce didacticiel, nous avons appris à diviser un document Word en parties plus petites à l'aide de la fonctionnalité Par en-tête HTML d'Aspose.Words pour .NET. En précisant le`DocumentSplitCriteria` comme`HeadingParagraph` dans le`HtmlSaveOptions`, nous avons pu générer des documents HTML distincts basés sur les titres présents dans le document original.

Diviser un document par titres peut être utile pour organiser et gérer le contenu, en particulier dans les documents volumineux comportant plusieurs sections. Aspose.Words for .NET fournit une solution fiable et efficace pour gérer le fractionnement de documents et générer des sorties dans différents formats.

N'hésitez pas à explorer les fonctionnalités et options supplémentaires fournies par Aspose.Words for .NET pour améliorer davantage vos capacités de traitement de documents et rationaliser votre flux de travail.

### FAQ

#### Comment puis-je diviser un document Word en parties plus petites en fonction des titres à l'aide d'Aspose.Words pour .NET ?

 Pour diviser un document Word en fonction des titres, vous pouvez utiliser la fonctionnalité Par titre HTML d'Aspose.Words pour .NET. Suivez le code source fourni et définissez le`DocumentSplitCriteria` à`HeadingParagraph` dans le`HtmlSaveOptions` objet. Cela divisera le document en parties plus petites à chaque titre.

#### Dans quels formats puis-je diviser le document Word ?

Le code source fourni montre la division du document Word en parties plus petites au format HTML. Cependant, Aspose.Words for .NET prend en charge divers formats de sortie, notamment DOCX, PDF, EPUB, etc. Vous pouvez modifier le code et spécifier le format de sortie souhaité dans le`HtmlSaveOptions` objecter en conséquence.

#### Puis-je choisir un critère différent pour diviser le document ?

 Oui, vous pouvez choisir différents critères pour diviser le document en fonction de vos besoins. Aspose.Words for .NET propose plusieurs options de critères, telles que`HeadingParagraph`, `Page`, `Section` , et plus. Modifier le`DocumentSplitCriteria` propriété dans le`HtmlSaveOptions` objet pour sélectionner les critères appropriés pour le fractionnement.

#### Comment puis-je personnaliser le HTML de sortie pour les parties divisées ?

 Aspose.Words for .NET vous permet de personnaliser le code HTML de sortie pour les parties fractionnées en spécifiant des options supplémentaires dans le champ`HtmlSaveOptions` objet. Vous pouvez contrôler divers aspects tels que les styles CSS, les images, les polices, etc. Reportez-vous à la documentation Aspose.Words pour plus de détails sur la personnalisation de la sortie HTML.

#### Puis-je diviser le document en fonction de plusieurs critères ?

 Oui, vous pouvez diviser le document en fonction de plusieurs critères en combinant les options de critères en conséquence. Par exemple, vous pouvez diviser le document par titre et par page en définissant le`DocumentSplitCriteria` propriété à`HeadingParagraph | Page`. Cela divisera le document au niveau de chaque titre et de chaque page, créant ainsi des parties plus petites basées sur les deux critères.