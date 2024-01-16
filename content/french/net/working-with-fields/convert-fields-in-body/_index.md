---
title: Convertir les champs dans le corps
linktitle: Convertir les champs dans le corps
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment utiliser Aspose.Words for .NET pour convertir les champs de page en texte dans le corps d'un document Word.
type: docs
weight: 10
url: /fr/net/working-with-fields/convert-fields-in-body/
---

Dans ce didacticiel étape par étape, nous vous expliquerons comment utiliser la fonctionnalité ConvertFieldsInBody d'Aspose.Words pour .NET à l'aide du code source C# fourni. Cette fonctionnalité vous permet de convertir des champs spécifiques du corps de votre document en texte brut, facilitant ainsi le traitement de vos documents. Suivez les étapes ci-dessous pour utiliser cette fonctionnalité efficacement.

## Étape 1 : prérequis

Avant de commencer, assurez-vous d'avoir installé Aspose.Words pour .NET et de disposer d'un document prêt à être traité. Assurez-vous également d'avoir le chemin du répertoire vers vos documents.

## Étape 2 : Charger le document

Commencez par déclarer une variable pour le chemin d'accès à votre répertoire de documents, puis utilisez cette variable pour initialiser un objet Document à partir du document spécifié. Dans notre exemple, le document s'appelle "Linked Fields.docx".

```csharp
// Le chemin d'accès à votre répertoire de documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document
Document doc = new Document(dataDir + "Linked fields.docx");
```

## Étape 3 : Convertir les champs de page en texte brut

 Maintenant que le document est chargé, nous pouvons passer aux étapes de conversion. Pour convertir les champs de la page en texte brut dans le corps de la première section, vous pouvez utiliser le`Range.Fields` méthode pour obtenir tous les champs de la plage spécifiée, puis filtrer les champs de type`FieldType.FieldPage` . Ensuite, vous pouvez utiliser le`ForEach` méthode pour parcourir chaque champ et appeler le`Unlink()` méthode pour le convertir en texte brut.

```csharp
// Transmettez les paramètres appropriés pour convertir les champs de la page en texte brut dans le corps de la première section.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.Unlink());
```

## Étape 4 : Enregistrez le document modifié

Une fois que vous avez converti les champs de la page en texte brut, vous pouvez enregistrer le document modifié à l'aide du`Save()` et en spécifiant le chemin et le nom du fichier de sortie. Dans notre exemple, nous l'enregistrons sous le nom "WorkingWithFields.ConvertFieldsInBody.docx".

```csharp
// Enregistrez le document modifié
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### Exemple de code source pour convertir les champs du corps avec Aspose.Words for .NET

Voici l'exemple de code source complet pour convertir les champs en corps à l'aide d'Aspose.Words pour .NET :

```csharp
// Le chemin d'accès à votre répertoire de documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document
Document doc = new Document(dataDir + "Linked fields.docx");

// Transmettez les paramètres appropriés pour convertir les champs de la page en texte brut dans le corps de la première section.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.A
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### FAQ

#### Q : Aspose.Words est-il compatible avec différentes versions de Microsoft Word ?

R : Oui, Aspose.Words est compatible avec différentes versions de Microsoft Word, notamment Word 2003, Word 2007, Word 2010, Word 2013, Word 2016 et Word 2019.

#### Q : Aspose.Words peut-il gérer des structures de champs complexes ?

R : Absolument ! Aspose.Words offre une prise en charge étendue des structures de champs complexes, notamment des champs imbriqués, des calculs et des expressions conditionnelles. Vous pouvez tirer parti de la puissante API pour travailler avec tout type de structure de champs.

#### Q : Aspose.Words prend-il en charge les opérations de mise à jour des champs ?

: Oui, Aspose.Words vous permet de mettre à jour les champs par programme. Vous pouvez facilement mettre à jour les valeurs des champs, actualiser les calculs et effectuer d'autres opérations liées aux champs à l'aide de l'API.

#### Q : Puis-je convertir des champs en texte brut à l'aide d'Aspose.Words ?

R : Certainement ! Aspose.Words fournit des méthodes pour convertir les champs en texte brut. Cela peut être utile lorsque vous devez extraire le contenu sans aucun formatage ou fonctionnalité lié au champ.

#### : Est-il possible de générer des documents Word avec des champs dynamiques à l'aide d'Aspose.Words ?

R : Absolument ! Aspose.Words offre des fonctionnalités robustes pour générer des documents Word avec des champs dynamiques. Vous pouvez créer des modèles avec des champs prédéfinis et les remplir dynamiquement avec des données, offrant ainsi une solution de génération de documents flexible et efficace.