---
title: Insérer un champ
linktitle: Insérer un champ
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à insérer un champ dans vos documents Word avec Aspose.Words pour .NET. Personnalisez vos documents avec des champs dynamiques.
type: docs
weight: 10
url: /fr/net/working-with-fields/insert-field/
---

Voici un guide étape par étape pour expliquer le code source C # ci-dessous, qui utilise la fonctionnalité "Insérer un champ" de Aspose.Words pour .NET. Assurez-vous de suivre attentivement chaque étape pour obtenir les résultats souhaités.

## Étape 1 : configuration du répertoire de documents

Dans le code fourni, vous devez spécifier le répertoire de vos documents. Remplacez la valeur "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié vers votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Création du document et de DocumentBuilder

Nous commençons par créer un nouveau document et initialiser un DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Insertion du champ

 Nous utilisons le`InsertField()` méthode du DocumentBuilder pour insérer un champ dans le document. Dans cet exemple, nous insérons un champ de fusion (MERGEFIELD) avec le nom de champ "MyFieldName" et le format de fusion.

```csharp
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");
```

### Exemple de code source pour insérer un champ avec Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Créez le document et le DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insérez le champ.
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");

doc.Save(dataDir + "InsertionField.docx");
```

Dans cet exemple, nous avons créé un nouveau document, initialisé un DocumentBuilder, puis inséré un champ de fusion avec le nom de champ "MyFieldName" et le format de fusion. Le document est alors enregistré avec un nom de fichier spécifié.

Ceci conclut notre guide sur l'utilisation de la fonctionnalité "Insérer un champ" avec Aspose.Words pour .NET.
