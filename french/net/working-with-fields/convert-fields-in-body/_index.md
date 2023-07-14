---
title: Convertir les champs dans le corps
linktitle: Convertir les champs dans le corps
second_title: API de traitement de documents Aspose.Words
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

// Charger le document
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

Voici l'exemple de code source complet pour convertir les champs dans le corps à l'aide de Aspose.Words pour .NET :

```csharp
// Le chemin d'accès à votre répertoire de documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document
Document doc = new Document(dataDir + "Linked fields.docx");

// Passez les paramètres appropriés pour convertir les champs de la page en texte brut dans le corps de la première section.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.A
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### FAQ

#### Q : Aspose.Words est-il compatible avec différentes versions de Microsoft Word ?

R : Oui, Aspose.Words est compatible avec différentes versions de Microsoft Word, notamment Word 2003, Word 2007, Word 2010, Word 2013, Word 2016 et Word 2019.

#### Q : Aspose.Words peut-il gérer des structures de champs complexes ?

R : Absolument ! Aspose.Words fournit une prise en charge étendue des structures de champs complexes, y compris les champs imbriqués, les calculs et les expressions conditionnelles. Vous pouvez tirer parti de la puissante API pour travailler avec n'importe quel type de structure de champ.

#### Q : Aspose.Words prend-il en charge les opérations de mise à jour des champs ?

R : Oui, Aspose.Words vous permet de mettre à jour les champs par programmation. Vous pouvez facilement mettre à jour les valeurs des champs, actualiser les calculs et effectuer d'autres opérations liées aux champs à l'aide de l'API.

#### Q : Puis-je convertir des champs en texte brut à l'aide d'Aspose.Words ?

R : Certainement ! Aspose.Words fournit des méthodes pour convertir les champs en texte brut. Cela peut être utile lorsque vous devez extraire le contenu sans aucune mise en forme ou fonctionnalité liée au champ.

#### Q : Est-il possible de générer des documents Word avec des champs dynamiques à l'aide d'Aspose.Words ?

R : Absolument ! Aspose.Words offre des fonctionnalités robustes pour générer des documents Word avec des champs dynamiques. Vous pouvez créer des modèles avec des champs prédéfinis et les remplir avec des données de manière dynamique, offrant une solution de génération de documents flexible et efficace.