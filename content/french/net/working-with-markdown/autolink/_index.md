---
title: Lien automatique
linktitle: Lien automatique
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment insérer une liaison automatique avec Aspose.Words pour .NET Guide étape par étape.
type: docs
weight: 10
url: /fr/net/working-with-markdown/autolink/
---

Dans cet exemple, nous expliquerons comment utiliser la fonctionnalité « Autolink » avec Aspose.Words pour .NET. Cette fonctionnalité vous permet d'insérer automatiquement des hyperliens dans votre document.

## Étape 1 : Utiliser un générateur de documents

Tout d’abord, nous utiliserons un générateur de documents pour ajouter du contenu à notre document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Étape 2 : Insérer un lien hypertexte

 Nous pouvons insérer un lien hypertexte en utilisant le`InsertHyperlink` méthode du générateur de documents. Nous précisons l'URL et le texte à afficher pour le lien.

```csharp
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", faux) ;
```

## Étape 3 : Insérer une adresse e-mail comme lien

On peut également insérer une adresse email comme lien en utilisant le préfixe "mailto:". Cela permettra aux utilisateurs de cliquer sur le lien pour ouvrir leur client de messagerie par défaut.

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## Étape 4 : Sauvegarde du document

Enfin, nous pouvons enregistrer le document au format souhaité.

### Exemple de code source pour Autolink utilisant Aspose.Words pour .NET


```csharp
// Utilisez un générateur de documents pour ajouter du contenu au document.
DocumentBuilder builder = new DocumentBuilder();

// Insérer un lien hypertexte.
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", faux) ;
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```


Félicitation ! Vous avez maintenant appris à utiliser la fonctionnalité « Autolink » avec Aspose.Words for .NET.


### FAQ

#### Q : Comment puis-je créer un lien automatique vers une adresse URL dans Aspose.Words ?

R : Pour créer un lien automatique vers une adresse URL dans Aspose.Words, vous pouvez utiliser le`<a>` étiquette avec le`href` attribut contenant l'adresse URL. Par exemple, vous pouvez utiliser`<a href="https://www.aspose.com">https://www.aspose.com</a>` pour créer automatiquement un lien vers le "https://www.aspose.com".

#### Q : Est-il possible de personnaliser le texte d'affichage d'un lien automatique dans Aspose.Words ?

 R : Oui, vous pouvez personnaliser le texte d'affichage d'un lien automatique dans Aspose.Words. Au lieu d'utiliser l'adresse URL comme texte à afficher, vous pouvez utiliser n'importe quel autre texte en remplaçant le contenu entre le`<a>` Mots clés. Par exemple, vous pouvez utiliser`<a href="https://www.aspose.com">Click here</a>` pour afficher le texte "Cliquez ici" sous forme de lien automatique.

#### Q : Comment puis-je ajouter des attributs supplémentaires à un lien automatique dans Aspose.Words ?

 R : Pour ajouter des attributs supplémentaires à un lien automatique dans Aspose.Words, vous pouvez utiliser des attributs HTML supplémentaires dans le fichier`<a>` étiqueter. Par exemple, vous pouvez utiliser`<a href="https://www.aspose.com" target="_blank">Link</a>` pour ouvrir le lien dans une nouvelle fenêtre ou un nouvel onglet à l'aide du` attribute target="_blank"`.