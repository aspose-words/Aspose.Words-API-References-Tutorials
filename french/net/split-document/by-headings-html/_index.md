---
title: Diviser un document Word par titres Html
linktitle: Par Rubriques Html
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour expliquer le code source C # du document Word fractionné Par la fonction HTML de l'en-tête d'Aspose.Words pour .NET
type: docs
weight: 10
url: /fr/net/split-document/by-headings-html/
---
Dans ce didacticiel, nous vous expliquerons comment diviser un document Word en parties plus petites à l'aide de la fonctionnalité Par en-tête HTML de Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et générer des documents HTML distincts basés sur le titre.

## Étape 1 : Chargement du document

Pour commencer, spécifiez le répertoire de votre document et chargez le document dans un objet Document. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Étape 2 : Diviser le document par Titre au format HTML

Nous allons maintenant définir les options d'enregistrement pour diviser le document en parties plus petites en fonction de l'en-tête au format HTML. Voici comment:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
// Divisez le document en parties plus petites, dans ce cas en le séparant par titre.
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### Exemple de code source pour By Headings HTML en utilisant Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité By HTML Heading de Aspose.Words pour .NET :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	// Diviser un document en parties plus petites, dans ce cas divisé par en-tête.
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

Avec ce code, vous pourrez diviser un document Word en parties plus petites à l'aide d'Aspose.Words pour .NET, en fonction des en-têtes. Vous pouvez ensuite générer des documents HTML distincts pour chaque partie.

## Conclusion

 Dans ce didacticiel, nous avons appris à diviser un document Word en parties plus petites à l'aide de la fonctionnalité Par en-tête HTML d'Aspose.Words pour .NET. En précisant le`DocumentSplitCriteria` comme`HeadingParagraph` dans le`HtmlSaveOptions`, nous avons pu générer des documents HTML séparés en fonction des en-têtes présents dans le document d'origine.

Le fractionnement d'un document par titres peut être utile pour organiser et gérer le contenu, en particulier dans les documents volumineux comportant plusieurs sections. Aspose.Words pour .NET fournit une solution fiable et efficace pour gérer le fractionnement de documents et générer une sortie dans différents formats.

N'hésitez pas à explorer les fonctionnalités et options supplémentaires fournies par Aspose.Words pour .NET afin d'améliorer encore vos capacités de traitement de documents et de rationaliser votre flux de travail.

### FAQ

#### Comment puis-je diviser un document Word en parties plus petites en fonction des en-têtes à l'aide d'Aspose.Words pour .NET ?

 Pour diviser un document Word en fonction des en-têtes, vous pouvez utiliser la fonctionnalité Par en-tête HTML d'Aspose.Words pour .NET. Suivez le code source fourni et définissez le`DocumentSplitCriteria` pour`HeadingParagraph` dans le`HtmlSaveOptions` objet. Cela divisera le document en parties plus petites à chaque en-tête.

#### Dans quels formats puis-je diviser le document Word ?

Le code source fourni illustre la division du document Word en parties plus petites au format HTML. Cependant, Aspose.Words pour .NET prend en charge divers formats de sortie, notamment DOCX, PDF, EPUB, etc. Vous pouvez modifier le code et spécifier le format de sortie souhaité dans le`HtmlSaveOptions` objecter en conséquence.

#### Puis-je choisir un critère différent pour fractionner le document ?

 Oui, vous pouvez choisir un critère différent pour diviser le document en fonction de vos besoins. Aspose.Words pour .NET fournit plusieurs options de critères, telles que`HeadingParagraph`, `Page`, `Section` , et plus. Modifier le`DocumentSplitCriteria` propriété dans le`HtmlSaveOptions` objet pour sélectionner les critères appropriés pour le fractionnement.

#### Comment puis-je personnaliser le HTML de sortie pour les parties fractionnées ?

 Aspose.Words pour .NET vous permet de personnaliser le HTML de sortie pour les parties fractionnées en spécifiant des options supplémentaires dans le`HtmlSaveOptions` objet. Vous pouvez contrôler divers aspects tels que les styles CSS, les images, les polices, etc. Reportez-vous à la documentation Aspose.Words pour plus de détails sur la personnalisation de la sortie HTML.

#### Puis-je diviser le document en fonction de plusieurs critères ?

 Oui, vous pouvez diviser le document en fonction de plusieurs critères en combinant les options de critères en conséquence. Par exemple, vous pouvez diviser le document à la fois par en-tête et par page en définissant le`DocumentSplitCriteria` propriété à`HeadingParagraph | Page`. Cela divisera le document à chaque en-tête et à chaque page, créant des parties plus petites basées sur les deux critères.