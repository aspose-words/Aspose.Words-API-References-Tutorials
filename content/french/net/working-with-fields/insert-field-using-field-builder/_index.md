---
title: Insérer un champ à l'aide du générateur de champs
linktitle: Insérer un champ à l'aide du générateur de champs
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment insérer des champs personnalisés dans vos documents Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fields/insert-field-using-field-builder/
---

Voici un guide étape par étape pour expliquer le code source C# ci-dessous, qui utilise la fonctionnalité « Insérer un champ à l'aide de FieldBuilder » d'Aspose.Words pour .NET. Assurez-vous de suivre attentivement chaque étape pour obtenir les résultats souhaités.

## Étape 1 : configuration du répertoire de documents

Dans le code fourni, vous devez préciser le répertoire de vos documents. Remplacez la valeur « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin approprié vers votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Création du document

Nous commençons par créer un nouveau document.

```csharp
Document doc = new Document();
```

## Étape 3 : Création du champ IF à l'aide de FieldBuilder

Nous utilisons la classe FieldBuilder pour construire un champ IF avec deux champs MERGEFIELD imbriqués. Dans cet exemple, le champ IF affiche le prénom et le nom en fonction d'une condition.

```csharp
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));
```

## Étape 4 : Insertion du champ IF dans le document

 Nous utilisons le`BuildAndInsert()` méthode pour construire et insérer le champ IF à un emplacement spécifique dans le document.

```csharp
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();
```

### Exemple de code source pour insérer un champ à l'aide de FieldBuilder avec Aspose.Words pour .NET

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Création de documents.
Document doc = new Document();

// Construction du champ IF à l'aide de FieldBuilder.
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));

// Insérez le champ IF dans le document.
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();

doc.Save(dataDir + "InsertFieldWithFieldBuilder.docx");
```

Dans cet exemple, nous avons créé un nouveau document, construit un champ IF avec des champs MERGEFIELD imbriqués, puis inséré ce champ dans le document à un emplacement spécifié. Le document est ensuite enregistré sous un nom de fichier spécifique.

### FAQ

#### Q : Qu'est-ce qu'un constructeur de champ dans Aspose.Words ?

: Un générateur de champs dans Aspose.Words est un outil puissant pour créer et manipuler des champs dans un document Word. Il offre des fonctionnalités avancées pour créer et personnaliser des champs, notamment l'insertion de codes de champ et la gestion des options de formatage.

#### Q : Quels types de champs peuvent être insérés à l’aide du générateur de champs ?

R : Le générateur de champs d'Aspose.Words vous permet d'insérer différents types de champs dans un document Word. Voici quelques exemples de types de champs couramment utilisés :

- MERGEFIELD : utilisé pour fusionner des données provenant de sources externes.
- DATE : affiche la date actuelle.
- PAGE : affiche le numéro de la page actuelle.
- IF : permet de conditionner l'affichage d'un contenu selon une condition.
- TOC : génère automatiquement une table des matières basée sur les styles de titre du document.

#### Q : Comment personnaliser les champs insérés avec le générateur de champs ?

R : Le générateur de champs propose des options de personnalisation pour les champs insérés. Vous pouvez utiliser les méthodes et propriétés du constructeur de champ pour définir des options telles que le formatage des champs, les arguments, les commutateurs et les valeurs par défaut. Par exemple, vous pouvez définir le format de date, le format des nombres, le séparateur de milliers, etc.
  