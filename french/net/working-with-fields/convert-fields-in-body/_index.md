---
title: Convertir les champs dans le corps
linktitle: Convertir les champs dans le corps
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à utiliser Aspose.Words pour .NET pour convertir les champs Page en texte dans le corps d'un document Word.
type: docs
weight: 10
url: /fr/net/working-with-fields/convert-fields-in-body/
---

Dans ce didacticiel pas à pas, nous vous expliquerons comment utiliser la fonctionnalité ConvertFieldsInBody de Aspose.Words pour .NET à l'aide du code source C# fourni. Cette fonctionnalité vous permet de convertir des champs spécifiques du corps de votre document en texte brut, ce qui facilite le traitement de vos documents. Suivez les étapes ci-dessous pour utiliser efficacement cette fonctionnalité.

## Étape 1 : Prérequis

Avant de commencer, assurez-vous d'avoir installé Aspose.Words pour .NET et d'avoir un document prêt à être traité. Assurez-vous également que vous avez le chemin du répertoire vers vos documents.

## Étape 2 : Chargez le document

Commencez par déclarer une variable pour le chemin d'accès à votre répertoire de documents, puis utilisez cette variable pour initialiser un objet Document à partir du document spécifié. Dans notre exemple, le document s'appelle "Champs liés.docx".

```csharp
// Le chemin d'accès à votre répertoire de documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Charger le document
Document doc = new Document(dataDir + "Linked fields.docx");
```

## Étape 3 : convertir les champs de page en texte brut

Maintenant que le document est chargé, nous pouvons passer aux étapes de conversion. Pour convertir les champs de la page en texte brut dans le corps de la première section, vous pouvez utiliser la`Range.Fields` méthode pour obtenir tous les champs dans la plage spécifiée, puis filtrer les champs de type`FieldType.FieldPage` . Ensuite, vous pouvez utiliser le`ForEach` méthode pour parcourir chaque champ et appeler la`Unlink()` méthode pour le convertir en texte brut.

```csharp
// Passez les paramètres appropriés pour convertir les champs de la page en texte brut dans le corps de la première section.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.Unlink());
```

## Étape 4 : Enregistrer le document modifié

 Une fois que vous avez converti les champs de la page en texte brut, vous pouvez enregistrer le document modifié à l'aide de la`Save()` méthode et en spécifiant le chemin et le nom du fichier de sortie. Dans notre exemple, nous l'enregistrons sous "WorkingWithFields.ConvertFieldsInBody.docx".

```csharp
// Enregistrer le document modifié
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### Exemple de code source pour convertir des champs dans le corps avec Aspose.Words pour .NET

Voici l'exemple de code source complet pour convertir des champs dans le corps à l'aide de Aspose.Words pour .NET :

```csharp
// Le chemin d'accès à votre répertoire de documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Charger le document
Document doc = new Document(dataDir + "Linked fields.docx");

// Passez les paramètres appropriés pour convertir les champs de la page en texte brut dans le corps de la première section.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.A
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```