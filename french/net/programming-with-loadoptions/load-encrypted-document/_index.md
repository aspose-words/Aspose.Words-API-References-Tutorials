---
title: Charger le document chiffré
linktitle: Charger le document chiffré
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à charger et enregistrer des documents chiffrés avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-loadoptions/load-encrypted-document/
---

Lorsque vous travaillez avec des documents chiffrés dans une application C#, il est important de pouvoir les charger correctement en fournissant le mot de passe correct. Avec la bibliothèque Aspose.Words pour .NET, vous pouvez facilement charger des documents chiffrés à l'aide des options de chargement appropriées. Dans ce guide étape par étape, nous allons vous montrer comment utiliser le code source C# de Aspose.Words pour .NET pour charger un document chiffré à l'aide des options de chargement LoadOptions.

## Comprendre la bibliothèque Aspose.Words

Avant de plonger dans le code, il est important de comprendre la bibliothèque Aspose.Words pour .NET. Aspose.Words est une bibliothèque puissante pour créer, éditer, convertir et protéger des documents Word sur différentes plates-formes, y compris .NET. Il offre de nombreuses fonctionnalités pour manipuler des documents, telles que l'insertion de texte, la modification de la mise en forme, l'ajout de sections et bien plus encore.

## Chargement d'un document crypté

La première étape consiste à télécharger un document crypté à l'aide des options de téléchargement appropriées. Dans notre cas, nous utilisons la classe Document pour charger le document en spécifiant le chemin et le mot de passe du document. Voici un exemple :

```csharp
Document doc = new Document(dataDir + "Encrypted.docx", new LoadOptions("password"));
```

Dans cet exemple, nous chargeons le document "Encrypted.docx" situé dans le répertoire des documents en utilisant le mot de passe "password".

## Enregistrer un document crypté

Après avoir téléchargé un document crypté, vous pouvez également l'enregistrer en spécifiant un nouveau mot de passe pour le fichier de sortie. Dans notre exemple, nous utilisons la classe OdtSaveOptions pour enregistrer le document au format ODT avec un nouveau mot de passe. Voici comment procéder :

```csharp
doc.Save(dataDir + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newpassword"));
```

Dans cet exemple, nous enregistrons le document sous le nom "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt" en spécifiant le nouveau mot de passe "newpassword".

### Exemple de code source pour LoadOptions avec la fonctionnalité "Load Encrypted Document" à l'aide d'Aspose.Words pour .NET

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger un document crypté avec le mot de passe spécifié
Document doc = new Document(dataDir + "Encrypted.docx", new LoadOptions("password"));

//Enregistrer un document crypté avec un nouveau mot de passe
doc.Save(dataDir + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newpassword"));
```

## Conclusion

Dans ce guide, nous avons expliqué comment charger et enregistrer des documents chiffrés à l'aide de la bibliothèque Aspose.Words pour .NET. En suivant les étapes fournies et en utilisant le code source C# fourni, vous pouvez facilement appliquer cette fonctionnalité dans votre application C#. Le téléchargement de documents cryptés protège vos données et vous permet de travailler avec des documents protégés dans Aspose.Words.