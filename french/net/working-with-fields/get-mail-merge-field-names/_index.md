---
title: Obtenir les noms des champs de publipostage
linktitle: Obtenir les noms des champs de publipostage
second_title: Référence de l'API Aspose.Words pour .NET
description: Découvrez comment obtenir des noms de champs de fusion et publipostage dans vos documents Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fields/get-mail-merge-field-names/
---

Voici un guide étape par étape pour expliquer le code source C# ci-dessous, qui utilise la fonctionnalité "Get Merge Field Names" d'Aspose.Words pour .NET. Assurez-vous de suivre attentivement chaque étape pour obtenir les résultats souhaités.

## Étape 1 : configuration du répertoire de documents

Dans le code fourni, vous devez spécifier le répertoire de vos documents. Remplacez la valeur "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié vers votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Chargement du document

La première étape consiste à charger le document dans lequel vous souhaitez obtenir les noms des champs de fusion.

```csharp
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");
```

Assurez-vous de remplacer "VOTRE FICHIER DE DOCUMENT" par le nom de votre propre fichier.

## Étape 3 : Obtenir les noms des champs de fusion

 Nous utilisons le`GetFieldNames()` pour obtenir un tableau contenant les noms des champs de fusion présents dans le document.

```csharp
string[] fieldNames = doc.MailMerge.GetFieldNames();
```

 Le`fieldNames` La variable contient maintenant les noms des champs de fusion.

### Exemple de code source pour Get Merge Field Names avec Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Chargez le document.
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");

// Obtenez les noms des champs de fusion.
string[] fieldNames = doc.MailMerge.GetFieldNames();

// Afficher le nombre de champs de fusion.
Console.WriteLine("\nDocument contains " + fieldNames.Length + " merge fields.");
```

 Dans cet exemple, nous avons chargé un document, obtenu les noms des champs de fusion à l'aide de la`GetFieldNames()` et affiche le nombre de champs de fusion présents dans le document.

Ceci conclut notre guide sur l'utilisation de la fonctionnalité "Get Merge Field Names" avec Aspose.Words pour .NET.