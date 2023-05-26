---
title: Supprimer le champ
linktitle: Supprimer le champ
second_title: Référence de l'API Aspose.Words pour .NET
description: Dans ce guide, vous apprendrez à supprimer un champ spécifique dans un document à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fields/remove-field/
---
Voici un guide étape par étape pour expliquer le code source C# ci-dessous, qui utilise la fonctionnalité "Suppression de champ" d'Aspose.Words pour .NET. Suivez attentivement chaque étape pour obtenir les résultats souhaités.

## Étape 1 : configuration du répertoire de documents

Dans le code fourni, vous devez spécifier le répertoire de vos documents. Remplacez la valeur "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié vers votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Chargement du document

Nous commençons par charger le document existant à partir du fichier spécifié.

```csharp
Document doc = new Document(dataDir + "Various fields.docx");
```

## Étape 3 : suppression du champ

 Nous sélectionnons le premier champ de la plage de documents et utilisons le`Remove()` méthode pour le supprimer.

```csharp
Field field = doc.Range.Fields[0];
field. Remove();
```

## Étape 4 : Enregistrer le document

 Enfin, nous appelons le`Save()` méthode pour enregistrer le document modifié.

```csharp
doc.Save(dataDir + "WorkingWithFields.RemoveField.docx");
```

### Exemple de code source pour la suppression de champs avec Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Chargez le document.
Document doc = new Document(dataDir + "Various fields.docx");

// Sélection du champ à supprimer.
Field field = doc.Range.Fields[0];
field. Remove();

// Enregistrez le document.
doc.Save(dataDir + "WorkingWithFields.RemoveField.docx");
```

Suivez ces étapes pour supprimer un champ spécifique dans votre document en utilisant Aspose.Words pour .NET.
