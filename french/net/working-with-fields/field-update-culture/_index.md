---
title: Culture de mise à jour sur le terrain
linktitle: Culture de mise à jour sur le terrain
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à mettre à jour la culture de champ dans vos documents Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fields/field-update-culture/
---

Voici un guide étape par étape pour expliquer le code source C# ci-dessous, qui utilise la fonctionnalité "Field Culture Update" d'Aspose.Words pour .NET. Assurez-vous de suivre attentivement chaque étape pour obtenir les résultats souhaités.

## Étape 1 : configuration du répertoire de documents

Dans le code fourni, vous devez spécifier le répertoire de vos documents. Remplacez la valeur "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié vers votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etape 2 : Création du document et du générateur de document

Nous commençons par créer un nouveau document et un générateur de documents.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Insertion du champ de l'heure

 Nous utilisons le`InsertField()` méthode pour insérer un champ d'heure dans le document.

```csharp
builder. InsertField(FieldType.FieldTime, true);
```

Cela insèrera un champ d'heure dans le document.

## Étape 4 : Configuration de la culture de mise à jour des champs

Nous configurons les options de champ pour spécifier que la culture de mise à jour de champ doit être basée sur le code de champ.

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();
```

Ces options déterminent la culture utilisée pour la mise à jour des champs.

### Exemple de code source pour la mise à jour de la culture de champ avec Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Créez le document et le générateur de documents.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insérez le champ de l'heure.
builder. InsertField(FieldType.FieldTime, true);

// Configurez la culture de mise à jour des champs.
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();

// Enregistrez le document.
doc.Save(dataDir + "UpdateCultureChamps.pdf");
```

Dans cet exemple, nous avons créé un nouveau document, inséré un champ d'heure et configuré la culture de mise à jour des champs. Ensuite, nous avons enregistré le document avec un nom de fichier spécifié.

Ceci conclut notre guide sur l'utilisation de la fonctionnalité "Mettre à jour la culture de champ" avec Aspose.Words pour .NET.