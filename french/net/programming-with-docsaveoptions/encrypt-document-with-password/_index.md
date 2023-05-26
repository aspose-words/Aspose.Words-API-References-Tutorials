---
title: Crypter le document avec un mot de passe
linktitle: Crypter le document avec un mot de passe
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à chiffrer des documents avec un mot de passe en utilisant Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-docsaveoptions/encrypt-document-with-password/
---
La sécurité des documents est essentielle lorsque vous travaillez avec des fichiers dans une application C#. Avec la bibliothèque Aspose.Words pour .NET, vous pouvez facilement protéger vos documents en les cryptant avec un mot de passe. Dans ce guide étape par étape, nous vous expliquerons comment utiliser le code source Aspose.Words pour .NET C# pour chiffrer un document à l'aide des options d'enregistrement de DocSaveOptions.

## Comprendre la bibliothèque Aspose.Words

Avant de plonger dans le code, il est important de comprendre la bibliothèque Aspose.Words pour .NET. Aspose.Words est une bibliothèque puissante pour créer, éditer, convertir et protéger des documents Word sur différentes plates-formes, y compris .NET. Il offre de nombreuses fonctionnalités pour manipuler des documents, telles que l'insertion de texte, la modification de la mise en forme, l'ajout de sections et bien plus encore.

## Etape 1 : Définir le répertoire des documents

La première étape consiste à définir le répertoire dans lequel vous souhaitez enregistrer le document crypté. Vous devez spécifier le chemin d'accès complet au répertoire. Par exemple :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel à votre répertoire de documents.

## Étape 2 : Création et modification d'un document

Ensuite, vous pouvez créer un document et y ajouter du contenu. Utilisez la classe DocumentBuilder fournie par Aspose.Words pour créer le contenu de votre document. Par exemple :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");
```

Dans cet exemple, nous créons un nouveau document vierge, puis utilisons DocumentBuilder pour écrire le texte "Hello World!".

## Étape 3 : Configurer les options d'enregistrement

Configurons maintenant les options de sauvegarde de notre document. Utilisez la classe DocSaveOptions pour spécifier les paramètres d'enregistrement. Par exemple :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };
```

Dans cet exemple, nous créons un nouvel objet DocSaveOptions et définissons la propriété Password sur "password" pour chiffrer le document avec ce mot de passe.

## Étape 4 : Activation de la fonctionnalité "Crypter le document avec un mot de passe"

Nous avons déjà configuré les options pour

l'enregistrement avec le mot de passe spécifié, ce qui active automatiquement la fonction "Crypter le document avec le mot de passe". Cela garantit que le document est crypté avec le mot de passe spécifié lors de son enregistrement.

## Étape 5 : Enregistrer le document

Enfin, vous pouvez enregistrer le document à l'aide de la méthode Save de la classe Document. Spécifiez le chemin d'accès complet au fichier et le nom de fichier souhaité. Par exemple :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

Assurez-vous de remplacer "dataDir" par le chemin du répertoire vers vos documents.

### Exemple de code source pour les options de sauvegarde de DocSaveOptions avec la fonctionnalité "Crypter le document avec un mot de passe" à l'aide de Aspose.Words pour .NET

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Créer et modifier un document
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");

// Configurez les options d'enregistrement avec la fonction "Crypter le document avec un mot de passe"
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };

// Enregistrez le document avec les options spécifiées
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

## Conclusion

Dans ce guide, nous avons expliqué comment utiliser la bibliothèque Aspose.Words pour .NET pour chiffrer un document avec un mot de passe à l'aide des options d'enregistrement de DocSaveOptions. En suivant les étapes fournies et en utilisant le code source C# fourni, vous pouvez facilement appliquer cette fonctionnalité dans votre application C#. Le cryptage du document avec un mot de passe garantit sa confidentialité et sa sécurité lors de sa manipulation.