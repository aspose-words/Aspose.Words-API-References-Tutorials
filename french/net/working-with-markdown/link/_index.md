---
title: Lien
linktitle: Lien
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à insérer des liens avec Aspose.Words pour .NET. Guide étape par étape.
type: docs
weight: 10
url: /fr/net/working-with-markdown/link/
---

Dans cet exemple, nous vous expliquerons comment utiliser la fonctionnalité de liens avec Aspose.Words pour .NET. Les liens sont utilisés pour créer des références cliquables vers des sites Web ou d'autres documents.

## Étape 1 : Utiliser un générateur de documents

Tout d'abord, nous allons utiliser un générateur de document pour ajouter du contenu à notre document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Étape 2 : Insertion d'un lien

 Nous pouvons insérer un lien en utilisant le`Insertlink` méthode du générateur de documents. Il faut préciser le texte du lien, ici "Aspose", ainsi que l'URL de destination.

```csharp
builder.Insertlink("Aspose", "https://www.aspose.com", faux);
```

### Exemple de code source pour les liens avec Aspose.Words pour .NET


```csharp
// Utilisez un générateur de document pour ajouter du contenu au document.
DocumentBuilder builder = new DocumentBuilder();

// Insérer un lien.
builder.Insertlink("Aspose", "https://www.aspose.com", faux);
```
Félicitation ! Vous avez maintenant appris à utiliser la fonction de liens avec Aspose.Words pour .NET.

