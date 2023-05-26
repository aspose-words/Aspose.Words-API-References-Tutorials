---
title: Insérer un champ de formulaire de saisie de texte
linktitle: Insérer un champ de formulaire de saisie de texte
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à utiliser Aspose.Words pour .NET pour insérer un champ de formulaire de saisie de texte dans des documents Word avec ce guide étape par étape.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/insert-text-input-form-field/
---

Dans ce guide étape par étape, nous allons explorer comment utiliser la fonctionnalité Insérer un champ de formulaire de saisie de texte dans Aspose.Words pour .NET pour ajouter et manipuler des champs de formulaire de saisie de texte dans vos documents Word à l'aide du code source C#. Les champs de formulaire de saisie de texte permettent aux utilisateurs de saisir du texte personnalisé dans un document, ce qui les rend idéaux pour créer des formulaires et des questionnaires interactifs. En suivant les instructions ci-dessous, vous pourrez facilement insérer et personnaliser des champs de formulaire de saisie de texte dans vos documents. Commençons!

## Introduction à la fonctionnalité Insérer un champ de formulaire de saisie de texte dans Aspose.Words pour .NET

La fonctionnalité Insérer un champ de formulaire de saisie de texte dans Aspose.Words pour .NET vous permet d'ajouter des champs de formulaire de saisie de texte par programme à vos documents Word. Ces champs de formulaire fournissent un élément interactif dans lequel les utilisateurs peuvent saisir du texte ou des données personnalisés.

## Comprendre les conditions d'utilisation de la fonctionnalité

Avant de procéder à la mise en œuvre, assurez-vous que vous remplissez les conditions suivantes :

1. Bibliothèque Aspose.Words pour .NET installée dans votre projet.
2. Connaissance de base du langage de programmation C#.
3. Un document Word existant ou un nouveau document pour insérer le champ du formulaire de saisie de texte.

Assurez-vous que ces conditions préalables sont en place pour procéder en douceur.

## Guide étape par étape pour implémenter Insérer un champ de formulaire de saisie de texte à l'aide du code source C #

Suivez les étapes ci-dessous pour implémenter la fonctionnalité Insérer un champ de formulaire de saisie de texte à l'aide du code source C# fourni :

### Étape 1 : Initialisation du document et du générateur de documents

Pour commencer, initialisez le document et le générateur de document. Le générateur de documents est un outil puissant fourni par Aspose.Words pour .NET qui nous permet de construire et de manipuler des documents Word par programmation. Utilisez l'extrait de code suivant :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### Étape 2 : Insertion du champ du formulaire de saisie de texte

 Ensuite, nous allons insérer le champ du formulaire de saisie de texte dans le document à l'aide de la`InsertTextInput` méthode. Cette méthode accepte divers paramètres, dont le nom du champ de formulaire, le type de champ de formulaire (dans ce cas,`TextFormFieldType.Regular`), la valeur par défaut et la longueur maximale. Voici un exemple :

```csharp
builder.InsertTextInput("TextInput", TextFormFieldType.Regular, "", "Hello", 0);
```

Le code ci-dessus insérera un champ de formulaire de saisie de texte avec le nom "TextInput", une valeur par défaut de "Hello", et aucune restriction de longueur maximale.

### Étape 3 : Enregistrer le document

 Après avoir inséré le champ du formulaire de saisie de texte, enregistrez le document à l'emplacement souhaité à l'aide de la`Save` méthode. Assurez-vous de fournir le chemin d'accès au fichier approprié :

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTextInputFormField.docx");
```

Ce code enregistrera le document avec le champ de formulaire de saisie de texte inséré à l'emplacement spécifié.

### Exemple de code source pour Insérer un champ de formulaire de saisie de texte à l'aide de Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertTextInput("TextInput", TextFormFieldType.Regular, "", "Hello", 0);

	doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTextInputFormField.docx");
            
        
```
