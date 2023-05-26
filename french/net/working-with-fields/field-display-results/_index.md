---
title: Résultats d'affichage des champs
linktitle: Résultats d'affichage des champs
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour afficher les résultats de champ dans vos documents Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fields/field-display-results/
---

Voici un guide étape par étape pour expliquer le code source C# ci-dessous, qui utilise la fonctionnalité "Afficher les résultats de champ" d'Aspose.Words pour .NET. Assurez-vous de suivre attentivement chaque étape pour obtenir les résultats souhaités.

## Étape 1 : configuration du répertoire de documents

Dans le code fourni, vous devez spécifier le répertoire de vos documents. Remplacez la valeur "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié vers votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Chargement du document

La première étape consiste à charger le document dans lequel vous souhaitez afficher les résultats des champs.

```csharp
Document document = new Document(dataDir + "Miscellaneous fields.docx");
```

Assurez-vous de remplacer "Miscellaneous Fields.docx" par le nom de votre propre fichier.

## Étape 3 : Mettre à jour les champs

 Nous utilisons le`UpdateFields()` méthode pour mettre à jour tous les champs du document.

```csharp
document. UpdateFields();
```

Cette étape est importante car elle garantit que les résultats des champs s'affichent correctement.

## Étape 4 : Affichage des résultats de champ

 Nous utilisons un`foreach` boucle pour parcourir tous les champs du document et afficher leurs résultats.

```csharp
foreach(Field field in document.Range.Fields)
     Console.WriteLine(field.DisplayResult);
```

 A chaque itération de la boucle, on accède au`DisplayResult` propriété du champ pour obtenir le résultat affiché.

### Exemple de code source pour afficher les résultats de champ avec Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Chargez le document.
Document document = new Document(dataDir + "Miscellaneous fields.docx");

// Mettre à jour les champs.
document. UpdateFields();

// Affichage des résultats de terrain.
foreach(Field field in document.Range.Fields)
     Console.WriteLine(field.DisplayResult);
```

Dans cet exemple, nous avons téléchargé un document, mis à jour tous les champs, puis parcouru les champs pour afficher leurs résultats. Vous pouvez personnaliser cette étape en utilisant votre propre logique pour traiter les résultats de champ.

Ceci conclut notre guide d'utilisation de la fonctionnalité "Afficher les résultats du champ" avec Aspose.Words pour .NET.