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

	//Insérer un lien hypertexte.
	builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", faux);
	builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
            
```


Félicitation ! Vous avez maintenant appris à utiliser la fonctionnalité "Autolink" avec Aspose.Words pour .NET.

