---
title: Évaluer la condition SI
linktitle: Évaluer la condition SI
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour évaluer la condition IF dans vos documents Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fields/evaluate-ifcondition/
---

Voici un guide étape par étape pour expliquer le code source C# ci-dessous, qui utilise la fonctionnalité "Évaluer la condition IF" d'Aspose.Words pour .NET. Assurez-vous de suivre attentivement chaque étape pour obtenir les résultats souhaités.

## Étape 1 : Création du générateur de documents

Dans le code fourni, nous commençons par créer un générateur de documents.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Étape 2 : Insérez le champ IF

 Nous utilisons le`InsertField()` méthode pour insérer le champ IF dans le document en spécifiant la condition à évaluer.

```csharp
FieldIf field = (FieldIf) builder.InsertField("IF 1 = 1", null);
```

Ici, nous avons utilisé la condition "1=1" comme exemple, mais vous pouvez personnaliser la condition selon vos besoins.

## Étape 3 : Évaluer la condition IF

 Le`EvaluateCondition()`La méthode est utilisée pour évaluer la condition du champ IF.

```csharp
FieldIfComparisonResult actualResult = field.EvaluateCondition();
```

 Le`actualResult` La variable contient le résultat de l'évaluation de la condition.

### Exemple de code source pour évaluer la condition IF avec Aspose.Words pour .NET

```csharp
// Création du générateur de documents.
DocumentBuilder builder = new DocumentBuilder();

// Insérez le champ SI dans le document.
FieldIf field = (FieldIf) builder.InsertField("IF 1 = 1", null);

// Évaluez la condition IF.
FieldIfComparisonResult actualResult = field.EvaluateCondition();

// Afficher le résultat de l'évaluation.
Console.WriteLine(actualResult);
```

Dans cet exemple, nous avons créé un générateur de document, inséré un champ IF avec une condition spécifiée, puis évalué la condition. Le résultat de l'évaluation est alors affiché dans la console.

Ceci conclut notre guide sur l'utilisation de la fonctionnalité "Évaluer la condition IF" avec Aspose.Words pour .NET.
