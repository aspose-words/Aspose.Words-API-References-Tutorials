---
title: Créer et ajouter un nœud de paragraphe
linktitle: Créer et ajouter un nœud de paragraphe
second_title: Référence de l'API Aspose.Words pour .NET
description: Créez et ajoutez un nœud de paragraphe à vos documents Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-node/create-and-add-paragraph-node/
---

Voici un guide étape par étape pour expliquer le code source C # ci-dessous qui illustre comment créer et ajouter un nœud de paragraphe à l'aide de Aspose.Words pour .NET.

## Étape 1 : Importez les références nécessaires
Avant de commencer, assurez-vous d'avoir importé les références nécessaires pour utiliser Aspose.Words pour .NET dans votre projet. Cela inclut l'importation de la bibliothèque Aspose.Words et l'ajout des espaces de noms requis à votre fichier source.

```csharp
using Aspose.Words;
```

## Étape 2 : Créer un nouveau document
 Dans cette étape, nous allons créer un nouveau document en utilisant le`Document` classe.

```csharp
Document doc = new Document();
```

## Étape 3 : Créer un nœud de paragraphe
 Nous allons maintenant créer un nœud de paragraphe en utilisant le`Paragraph` class et en passant le document en paramètre.

```csharp
Paragraph para = new Paragraph(doc);
```

## Étape 4 : Accéder à la section des documents
 Pour ajouter le paragraphe au document, nous devons accéder à la dernière section du document en utilisant le`LastSection` propriété.

```csharp
Section section = doc.LastSection;
```

## Étape 5 : Ajouter le nœud de paragraphe au document
 Maintenant que nous avons la section de document, nous pouvons ajouter le nœud de paragraphe à la section en utilisant le`AppendChild` méthode sur la section`Body` propriété.

```csharp
section.Body.AppendChild(para);
```

## Étape 6 : Enregistrez le document
 Enfin, pour enregistrer le document, vous pouvez utiliser la`Save` méthode en spécifiant le format de sortie souhaité, tel que le format DOCX.

```csharp
doc.Save("output.docx", SaveFormat.Docx);
```

### Exemple de code source pour créer et ajouter un nœud de paragraphe avec Aspose.Words pour .NET

```csharp
Document doc = new Document();

Paragraph para = new Paragraph(doc);

Section section = doc.LastSection;
section.Body.AppendChild(para);

```

Il s'agit d'un exemple de code complet pour créer et ajouter un nœud de paragraphe à l'aide de Aspose.Words pour .NET. Assurez-vous d'importer les références nécessaires et suivez les étapes décrites précédemment pour intégrer ce code dans votre projet.