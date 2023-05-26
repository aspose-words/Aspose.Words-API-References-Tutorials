---
title: Convertir les champs dans le document
linktitle: Convertir les champs dans le document
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour convertir les champs de document en texte à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fields/convert-fields-in-document/
---

Dans ce didacticiel, nous vous guiderons étape par étape à l'aide de la fonction ConvertFieldsInDocument du logiciel Aspose.Words pour .NET. Nous expliquerons en détail le code source C# nécessaire pour cette fonctionnalité et fournirons des exemples de formats de sortie Markdown.

## Étape 1 : Prérequis
Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Aspose.Words pour .NET installé sur votre machine de développement.
- Un document Word contenant des champs liés que vous souhaitez convertir en texte.
- Un répertoire de documents dans lequel vous pouvez enregistrer le document transformé.

## Étape 2 : Configurer l'environnement
Assurez-vous d'avoir correctement configuré votre environnement de développement pour utiliser Aspose.Words pour .NET. Importez les espaces de noms nécessaires et définissez le chemin d'accès à votre répertoire de documents.

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 3 : Chargez le document
 Utilisez le`Document` classe de Aspose.Words pour charger le document Word contenant les champs liés que vous souhaitez convertir.

```csharp
Document doc = new Document(MyDir + "Linked fields.docx");
```

## Étape 4 : convertir les champs liés en texte
 Utilisez le`Unlink()` pour convertir tous les champs de type "IF" rencontrés dans le document en texte. Cette méthode est utilisée pour transformer les champs liés en leur contenu textuel.

```csharp
doc.Range.Fields.Where(f => f.Type == FieldType.FieldIf).ToList().ForEach(f => f.Unlink());
```

## Étape 5 : Enregistrez le document transformé
 Utilisez le`Save()` méthode pour enregistrer le document avec les champs convertis en texte dans le répertoire de documents spécifié.

```csharp
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInDocument.docx");
```

## Exemple de code source pour ConvertFieldsInDocument en utilisant Aspose.Words pour .NET

Voici le code source complet de la fonction ConvertFieldsInDocument :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(MyDir + "Linked fields.docx");

// Transmettez les paramètres appropriés pour convertir tous les champs IF rencontrés dans le document (y compris les en-têtes et les pieds de page) en texte.
doc.Range.Fields.Where(f => f.Type == FieldType.FieldIf).ToList().ForEach(f => f.Unlink());

// Enregistrez le document avec les champs transformés sur le disque
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInDocument.docx");
```

## Conclusion
La fonction ConvertFieldsInDocument d'Aspose.Words pour .NET est un outil puissant pour convertir les champs liés d'un document Word en texte. 