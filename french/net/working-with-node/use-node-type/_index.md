---
title: Utiliser le type de nœud
linktitle: Utiliser le type de nœud
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à utiliser le type de nœud pour accéder aux informations spécifiques au document avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-node/use-node-type/
---

Voici un guide étape par étape pour expliquer le code source C # ci-dessous qui illustre comment utiliser la fonctionnalité de type de nœud avec Aspose.Words pour .NET.

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

## Étape 3 : Obtenir le type de nœud de document
 Pour obtenir le type de nœud d'un document, nous utilisons le`NodeType` propriété.

```csharp
NodeType type = doc.NodeType;
```

### Exemple de code source pour l'utilisation du type de nœud avec Aspose.Words pour .NET

```csharp
Document doc = new Document();

NodeType type = doc.NodeType;
```

Il s'agit d'un exemple de code complet pour l'utilisation du type de nœud avec Aspose.Words pour .NET. Assurez-vous d'importer les références nécessaires et suivez les étapes décrites précédemment pour intégrer ce code dans votre projet.

