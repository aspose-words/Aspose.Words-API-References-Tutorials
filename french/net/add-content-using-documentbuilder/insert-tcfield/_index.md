---
title: Insérer le champ TCField
linktitle: Insérer le champ TCField
second_title: Référence de l'API Aspose.Words pour .NET
description: Découvrez comment insérer et manipuler des TCFields dans des documents Word à l'aide de C# et Aspose.Words pour .NET dans ce guide étape par étape.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/insert-tcfield/
---

Dans cet exemple, nous vous guiderons tout au long du processus d'utilisation de la fonction Insérer TCField d'Aspose.Words pour .NET. Le TCField représente une entrée de table des matières dans un document Word. Nous fournirons une explication étape par étape du code source C #, ainsi que la sortie attendue au format Markdown. Commençons!

## Étape 1 : Initialisation du document et du générateur de documents

Pour commencer, nous devons initialiser le document et le générateur de document. Le générateur de documents est un outil puissant fourni par Aspose.Words pour .NET qui nous permet de construire et de manipuler des documents Word par programmation. Voici comment procéder :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Insertion du TCField

 Ensuite, nous allons insérer le TCField dans le document en utilisant le`InsertField` méthode. Le TCField représente une entrée de table des matières avec le texte d'entrée spécifié. Voici un exemple :

```csharp
builder.InsertField("TC \"Entry Text\" \\f t");
```

Le code ci-dessus insérera un TCField avec le texte d'entrée "Entry Text" dans le document.

## Étape 3 : Enregistrer le document

 Après avoir inséré le TCField, nous pouvons enregistrer le document à un emplacement spécifique en utilisant le`Save` méthode. Assurez-vous de fournir le chemin et le nom de fichier souhaités pour le document de sortie. Voici un exemple :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTCField.docx");
```

Le code ci-dessus enregistrera le document avec le TCField dans le répertoire spécifié.

## Formats de démarque de sortie

Lorsque le code est exécuté avec succès, le document de sortie contiendra une entrée de table des matières avec le texte d'entrée spécifié. Le TCField est représenté sous la forme d'un champ dans le document Word, et le format Markdown résultant dépendra de la façon dont le document est traité.

Veuillez noter que le document de sortie n'est pas directement au format Markdown mais plutôt au format Word. Cependant, lorsque vous convertissez le document Word en Markdown à l'aide d'outils ou de bibliothèques appropriés, le TCField sera traité en conséquence.

### Exemple de code source pour Insert TCField en utilisant Aspose.Words pour .NET

Voici l'exemple de code source complet pour insérer un TCField en utilisant Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertField("TC \"Entry Text\" \\f t");

	doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTCField.docx");
			
```

N'hésitez pas à modifier le code en fonction de vos besoins et à explorer d'autres fonctionnalités fournies par Aspose.Words pour .NET.

C'est ça! Vous avez appris avec succès comment insérer un TCField en utilisant Aspose.Words pour .NET.

