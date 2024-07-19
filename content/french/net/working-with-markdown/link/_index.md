---
title: Lien
linktitle: Lien
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment insérer des liens avec Aspose.Words pour .NET. Guide étape par étape.
type: docs
weight: 10
url: /fr/net/working-with-markdown/link/
---

Dans cet exemple, nous allons vous expliquer comment utiliser la fonctionnalité de liens avec Aspose.Words pour .NET. Les liens sont utilisés pour créer des références cliquables vers des sites Web ou d'autres documents.

## Étape 1 : Utiliser un générateur de documents

Tout d’abord, nous utiliserons un générateur de documents pour ajouter du contenu à notre document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Étape 2 : Insérer un lien

 Nous pouvons insérer un lien en utilisant le`InsertHyperlink` méthode du générateur de documents. Nous devons préciser le texte du lien, ici "Aspose", ainsi que l'URL de destination.

```csharp
builder.InsertHyperlink("Aspose", "https://www.aspose.com", faux);
```

### Exemple de code source pour les liens avec Aspose.Words for .NET


```csharp
// Utilisez un générateur de documents pour ajouter du contenu au document.
DocumentBuilder builder = new DocumentBuilder();

// Insérer un lien.
builder.InsertHyperlink("Aspose", "https://www.aspose.com", faux);
```
Félicitation ! Vous avez maintenant appris à utiliser la fonctionnalité de liens avec Aspose.Words for .NET.


### FAQ

#### Q : Comment puis-je créer un lien vers une URL dans Aspose.Words ?

 R : Pour créer un lien vers une adresse URL dans Aspose.Words, vous pouvez utiliser le`<a>` étiquette avec le`href` attribut contenant l'adresse URL. Par exemple, vous pouvez utiliser`<a href="https://www.aspose.com">Click Here</a>` pour créer un lien hypertexte vers l'URL "https://www.example.com" avec le texte affiché "Cliquez ici".

#### Q : Est-il possible de créer un lien vers un signet interne dans Aspose.Words ?

 R : Oui, il est possible de créer un lien vers un signet interne dans Aspose.Words. Vous pouvez utiliser le`<a>` étiquette avec le`href` attribut contenant le nom du signet précédé d'un dièse (#). Par exemple,`<a href="#bookmark1">Go to bookmark 1</a>` créera un lien vers le signet nommé « bookmark1 » dans le document.

#### Q : Comment puis-je personnaliser le texte d'affichage d'un lien dans Aspose.Words ?

 R : Pour personnaliser le texte d'affichage d'un lien dans Aspose.Words, vous pouvez modifier le contenu entre le`<a>` Mots clés. Par exemple,`<a href="https://www.aspose.com">Click here</a>` affichera le texte « Cliquez ici » sous forme de lien hypertexte.

#### Q : Puis-je spécifier une cible pour un lien dans Aspose.Words ?

R : Oui, vous pouvez spécifier une cible pour un lien dans Aspose.Words à l'aide du`target` attribut du`<a>` étiqueter. Par exemple,`<a href="https://www.aspose.com" target="_blank">Open in new window</a>` ouvrira le lien dans une nouvelle fenêtre ou un nouvel onglet.