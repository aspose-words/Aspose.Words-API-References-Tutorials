---
title: Document du propriétaire
linktitle: Document du propriétaire
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à utiliser le document propriétaire dans Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-node/owner-document/
---

Voici un guide étape par étape pour expliquer le code source C # ci-dessous qui illustre comment utiliser la fonctionnalité de document propriétaire avec Aspose.Words pour .NET.

## Étape 1 : Importez les références nécessaires
Avant de commencer, assurez-vous d'avoir importé les références nécessaires pour utiliser Aspose.Words pour .NET dans votre projet. Cela inclut l'importation de la bibliothèque Aspose.Words et l'ajout des espaces de noms requis à votre fichier source.

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
using Aspose.Words.Paragraphs;
```

## Étape 2 : Créer un nouveau document
 Dans cette étape, nous allons créer un nouveau document en utilisant le`Document` classe.

```csharp
Document doc = new Document();
```

## Étape 3 : Créer un nœud avec le document propriétaire
 Lorsque vous créez un nouveau nœud de n'importe quel type, vous devez passer le document dans le constructeur. Dans cet exemple, nous créons un nouveau nœud de paragraphe en utilisant le document`doc`.

```csharp
Paragraph para = new Paragraph(doc);
```

## Étape 4 : Vérifier le nœud parent et le document propriétaire
 Maintenant que nous avons créé le nœud de paragraphe, nous pouvons vérifier s'il a un nœud parent et si le document propriétaire est le même que`doc`.

```csharp
Console.WriteLine("The paragraph has no parent node: " + (para.ParentNode == null));
Console.WriteLine("The documents of the two nodes are identical: " + (para.Document == doc));
```

## Étape 5 : Modifier les propriétés du nœud avec les données du document
La relation entre un nœud et un document permet l'accès et la modification des propriétés qui font référence à des données spécifiques au document, telles que les styles ou les listes. Dans cet exemple, nous définissons le nom du style de paragraphe sur "Titre 1".

```csharp
para.ParagraphFormat.StyleName = "Heading 1";
```

## Étape 6 : Ajouter le paragraphe au document
Nous pouvons maintenant ajouter le nœud de paragraphe à la section principale du document.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Étape 7 : Vérifier le nœud parent après l'ajout
Après avoir ajouté le paragraphe au document, nous vérifions à nouveau s'il a maintenant un nœud parent.

```csharp
Console.WriteLine("The paragraph has a parent node: " + (para.ParentNode != null));
```

### Exemple de code source pour le document propriétaire avec Aspose.Words pour .NET

```csharp
	Document doc = new Document();

	// La création d'un nouveau nœud de n'importe quel type nécessite un document transmis au constructeur.
	Paragraph para = new Paragraph(doc);

	// Le nouveau nœud de paragraphe n'a pas encore de parent.
	Console.WriteLine("Paragraph has no parent node: " + (para.ParentNode == null));

	// Mais le nœud de paragraphe connaît son document.
	Console.WriteLine("Both nodes' documents are the same: " + (para.Document == doc));

	// Le fait qu'un nœud appartienne toujours à un document nous permet d'accéder et de modifier
	// les propriétés qui référencent les données à l'échelle du document, telles que les styles ou les listes.
	para.ParagraphFormat.StyleName = "Heading 1";

	// Ajoutez maintenant le paragraphe au texte principal de la première section.
	doc.FirstSection.Body.AppendChild(para);

	//Le nœud Paragraphe est maintenant un enfant du nœud Corps.
	Console.WriteLine("Paragraph has a parent node: " + (para.ParentNode != null));
            
```



