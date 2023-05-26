---
title: Renommer les champs de fusion
linktitle: Renommer les champs de fusion
second_title: Référence de l'API Aspose.Words pour .NET
description: Dans ce didacticiel, vous apprendrez à renommer les champs de fusion dans un document à l'aide de Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fields/rename-merge-fields/
---

Voici un guide étape par étape pour expliquer le code source C # ci-dessous qui utilise la fonctionnalité de renommage du champ de fusion d'Aspose.Words pour .NET. Suivez attentivement chaque étape pour obtenir les résultats souhaités.

## Étape 1 : configuration du répertoire de documents

Dans le code fourni, vous devez spécifier le répertoire de vos documents. Remplacez la valeur "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié vers votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Création du document et insertion des champs de fusion

 Nous commençons par créer un nouveau document et en utilisant un`DocumentBuilder` pour insérer les champs de fusion.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");
```

## Étape 3 : renommer les champs de fusion

Nous parcourons chaque champ de la plage de documents, et s'il s'agit d'un champ de fusion, nous renommons le champ en ajoutant le "_Suffixe "renommé".

```csharp
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}
```

## Étape 4 : Enregistrer le document

 Enfin, nous appelons le`Save()` méthode pour enregistrer le document modifié.

```csharp
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

### Exemple de code source pour renommer les champs de fusion avec Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Créez le document et insérez les champs de fusion.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");

// Renommer les champs de fusion.
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}

// Enregistrez le document.
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

Suivez ces étapes pour renommer les champs de fusion dans votre document en utilisant Aspose.Words pour .NET.