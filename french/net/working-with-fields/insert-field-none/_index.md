---
title: Insérer un champ Aucun
linktitle: Insérer un champ Aucun
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à insérer un champ AUCUN dans vos documents Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fields/insert-field-none/
---

Voici un guide étape par étape pour expliquer le code source C# ci-dessous, qui utilise la fonctionnalité "Insert NONE Field" d'Aspose.Words pour .NET. Assurez-vous de suivre attentivement chaque étape pour obtenir les résultats souhaités.

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

## Étape 3 : Insertion du champ AUCUN

 Nous utilisons le`InsertField()` méthode du DocumentBuilder pour insérer un champ NONE dans le document.

```csharp
FieldUnknown field = (FieldUnknown)builder.InsertField(FieldType.FieldNone, false);
```

### Exemple de code source pour insérer un champ NONE avec Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Créez le document et le DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insérez le champ AUCUN.
FieldUnknown field = (FieldUnknown)builder.InsertField(FieldType.FieldNone, false);

doc.Save(dataDir + "InsertionFieldNone.docx");
```

Dans cet exemple, nous avons créé un nouveau document, initialisé un DocumentBuilder, puis inséré un champ NONE. Le document est alors enregistré avec un nom de fichier spécifié.

Ceci conclut notre guide sur l'utilisation de la fonctionnalité "Insert NONE Field" avec Aspose.Words pour .NET.