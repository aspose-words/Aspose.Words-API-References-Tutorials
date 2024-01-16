---
title: Renommer les champs de fusion
linktitle: Renommer les champs de fusion
second_title: API de traitement de documents Aspose.Words
description: Dans ce didacticiel, vous apprendrez à renommer les champs de fusion dans un document à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fields/rename-merge-fields/
---

Voici un guide étape par étape pour expliquer le code source C# ci-dessous qui utilise la fonctionnalité de renommage de champ de fusion d'Aspose.Words pour .NET. Suivez attentivement chaque étape pour obtenir les résultats souhaités.

## Étape 1 : configuration du répertoire de documents

Dans le code fourni, vous devez préciser le répertoire de vos documents. Remplacez la valeur « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin approprié vers votre répertoire de documents.

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

## Étape 3 : Renommer les champs de fusion

Nous parcourons chaque champ de la plage de documents, et s'il s'agit d'un champ de fusion, nous renommons le champ en ajoutant le "_Suffixe "Renommé".

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

## Étape 4 : Sauvegarde du document

 Enfin, nous appelons le`Save()` méthode pour enregistrer le document modifié.

```csharp
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

### Exemple de code source pour renommer les champs de fusion avec Aspose.Words for .NET

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Créez le document et insérez les champs de fusion.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");

// Renommez les champs de fusion.
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

Suivez ces étapes pour renommer les champs de fusion dans votre document à l'aide d'Aspose.Words for .NET.

### FAQ

#### Q : Comment puis-je renommer les champs fusionnés dans un document Word à l'aide d'Aspose.Words pour .NET ?

 R : Pour renommer les champs fusionnés dans un document Word à l'aide d'Aspose.Words for .NET, vous pouvez parcourir les champs du document à l'aide de l'option`FieldMergingArgs` classe et utiliser le`FieldMergingArgs.FieldName` méthode pour renommer le champ.

#### Q : Est-il possible de renommer uniquement certains champs fusionnés dans un document Word avec Aspose.Words pour .NET ?

 : Oui, il est possible de renommer uniquement certains champs fusionnés dans un document Word avec Aspose.Words pour .NET. Vous pouvez filtrer les champs à renommer en utilisant des critères spécifiques, tels que le nom du champ ou d'autres propriétés pertinentes. Vous pouvez ensuite renommer les champs correspondants à l'aide du`FieldMergingArgs.FieldName` méthode.

#### Q : Comment puis-je vérifier si un champ fusionné a été renommé avec succès dans un document Word avec Aspose.Words pour .NET ?

 R : Pour vérifier si un champ fusionné a été renommé avec succès dans un document Word avec Aspose.Words for .NET, vous pouvez utiliser le`FieldMergedArgs` classe et accéder au`FieldMergedArgs.IsMerged` propriété pour déterminer si le champ a été renommé avec hit.

#### Q : Quelles sont les conséquences du renommage d'un champ fusionné dans un document Word avec Aspose.Words pour .NET ?

R : Lorsque vous renommez un champ fusionné dans un document Word avec Aspose.Words for .NET, cela modifie le nom du champ dans le document, ce qui peut avoir un impact sur d'autres fonctionnalités ou processus qui dépendent du nom du champ. Assurez-vous de prendre en compte ces conséquences potentielles avant de renommer les champs fusionnés.

#### Q : Est-il possible de restaurer le nom d'origine d'un champ fusionné après l'avoir renommé avec Aspose.Words pour .NET ?

R : Oui, il est possible de restaurer le nom d'origine d'un champ fusionné après l'avoir renommé avec Aspose.Words for .NET. Vous pouvez stocker le nom d'origine du champ dans une variable ou une liste, puis utiliser ces informations pour restaurer le nom d'origine si nécessaire.