---
title: Insérer un champ de fusion à l'aide de DOM
linktitle: Insérer un champ de fusion à l'aide de DOM
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à insérer des champs de fusion de champs personnalisés dans vos documents Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fields/insert-merge-field-using-dom/
---

Voici un guide étape par étape pour expliquer le code source C # ci-dessous qui utilise la fonctionnalité "Insert Field Merge Field" de Aspose.Words pour .NET. Assurez-vous de suivre attentivement chaque étape pour obtenir les résultats souhaités.

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

## Étape 3 : Déplacer le curseur vers le paragraphe

 Nous utilisons le`MoveTo()` du DocumentBuilder pour déplacer le curseur vers le paragraphe où nous voulons insérer le champ de fusion de champ.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Étape 4 : Insertion du champ de fusion de champs

 Nous utilisons le DocumentBuilder`InsertField()` méthode pour insérer un champ de fusion de champ dans le paragraphe.

```csharp
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

Nous configurons ensuite les propriétés du champ de fusion de champ en spécifiant les options appropriées, telles que le nom du champ, le texte avant et après le champ et les options de formatage vertical.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;
```

 Enfin, nous appelons le`Update()` méthode pour mettre à jour le champ.

```csharp
field. Update();
```

### Exemple de code source pour insérer un champ de fusion de champ avec Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Créez le document et le DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Déplacez le curseur sur le paragraphe.
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);

// Insérer un champ de fusion de champ.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);

field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;

// Mettez à jour le champ.
field. Update();

doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

Dans cet exemple, nous avons créé un nouveau document, déplacé le curseur vers le paragraphe souhaité, puis inséré un champ de fusion de champ dans le document.