---
title: Insérer un champ à l'aide du générateur de champs
linktitle: Insérer un champ à l'aide du générateur de champs
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à insérer des champs personnalisés dans vos documents Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fields/insert-field-using-field-builder/
---

Voici un guide étape par étape pour expliquer le code source C# ci-dessous, qui utilise la fonctionnalité "Insérer un champ à l'aide de FieldBuilder" d'Aspose.Words pour .NET. Assurez-vous de suivre attentivement chaque étape pour obtenir les résultats souhaités.

## Étape 1 : configuration du répertoire de documents

Dans le code fourni, vous devez spécifier le répertoire de vos documents. Remplacez la valeur "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié vers votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Création du document

Nous commençons par créer un nouveau document.

```csharp
Document doc = new Document();
```

## Étape 3 : Création du champ IF à l'aide de FieldBuilder

Nous utilisons la classe FieldBuilder pour construire un champ IF avec deux champs MERGEFIELD imbriqués. Dans cet exemple, le champ SI affiche le prénom et le nom en fonction d'une condition.

```csharp
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));
```

## Étape 4 : Insertion du champ IF dans le document

 Nous utilisons le`BuildAndInsert()` méthode pour construire et insérer le champ IF à un emplacement spécifique dans le document.

```csharp
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();
```

### Exemple de code source pour insérer un champ à l'aide de FieldBuilder avec Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Création de documents.
Document doc = new Document();

// Construction du champ IF à l'aide de FieldBuilder.
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));

// Insérez le champ SI dans le document.
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();

doc.Save(dataDir + "InsertFieldWithFieldBuilder.docx");
```

Dans cet exemple, nous avons créé un nouveau document, construit un champ IF avec des champs MERGEFIELD imbriqués, puis inséré ce champ dans le document à un emplacement spécifié. Le document est alors enregistré avec un nom de fichier spécifique.
