---
title: Lien automatique
linktitle: Lien automatique
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à insérer un lien automatique avec le guide étape par étape Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-markdown/autolink/
---

Dans cet exemple, nous expliquerons comment utiliser la fonctionnalité "Autolink" avec Aspose.Words pour .NET. Cette fonctionnalité vous permet d'insérer automatiquement des hyperliens dans votre document.

## Étape 1 : Utiliser un générateur de documents

Tout d'abord, nous allons utiliser un générateur de document pour ajouter du contenu à notre document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Étape 2 : Insertion d'un lien hypertexte

 Nous pouvons insérer un lien hypertexte en utilisant le`InsertHyperlink` méthode du générateur de documents. Nous spécifions l'URL et le texte à afficher pour le lien.

```csharp
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", faux);
```

## Étape 3 : Insertion d'une adresse e-mail en tant que lien

Nous pouvons également insérer une adresse e-mail en tant que lien en utilisant le préfixe "mailto :". Cela permettra aux utilisateurs de cliquer sur le lien pour ouvrir leur client de messagerie par défaut.

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## Étape 4 : Enregistrer le document

Enfin, nous pouvons enregistrer le document dans le format souhaité.

### Exemple de code source pour Autolink utilisant Aspose.Words pour .NET


```csharp
// Utilisez un générateur de document pour ajouter du contenu au document.
DocumentBuilder builder = new DocumentBuilder();

// Insérer un lien hypertexte.
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", faux);
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```


Félicitation ! Vous avez maintenant appris à utiliser la fonctionnalité "Autolink" avec Aspose.Words pour .NET.


### FAQ

#### Q : Comment puis-je créer un lien automatique vers une adresse URL dans Aspose.Words ?

 R : Pour créer un lien automatique vers une adresse URL dans Aspose.Words, vous pouvez utiliser le`<a>` étiquette avec le`href` attribut contenant l'adresse URL. Par exemple, vous pouvez utiliser`<a href="https://www.aspose.com">https://www.aspose.com</a>` pour créer automatiquement un lien vers le "https: //www.aspose.com".

#### Q : Est-il possible de personnaliser le texte d'affichage d'un lien automatique dans Aspose.Words ?

 R : Oui, vous pouvez personnaliser le texte d'affichage d'un lien automatique dans Aspose.Words. Au lieu d'utiliser l'adresse URL comme texte d'affichage, vous pouvez utiliser n'importe quel autre texte en remplaçant le contenu entre`<a>` Mots clés. Par exemple, vous pouvez utiliser`<a href="https://www.aspose.com">Click here</a>` pour afficher le texte "Cliquez ici" comme lien automatique.

#### Q : Comment puis-je ajouter des attributs supplémentaires à un lien automatique dans Aspose.Words ?

 : Pour ajouter des attributs supplémentaires à un lien automatique dans Aspose.Words, vous pouvez utiliser des attributs HTML supplémentaires dans le`<a>` étiqueter. Par exemple, vous pouvez utiliser`<a href="https://www.aspose.com" target="_blank">Link</a>` pour ouvrir le lien dans une nouvelle fenêtre ou un nouvel onglet à l'aide de la` attribute target="_blank"`.