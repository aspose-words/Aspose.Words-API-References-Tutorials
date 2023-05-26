---
title: Spécifier les paramètres régionaux au niveau du champ
linktitle: Spécifier les paramètres régionaux au niveau du champ
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à spécifier la localisation au niveau du champ dans les documents Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fields/specify-locale-at-field-level/
---

Voici un guide étape par étape pour expliquer le code source C# suivant qui permet de spécifier la localisation au niveau du champ à l'aide de la fonctionnalité Aspose.Words pour .NET. Assurez-vous d'avoir inclus la bibliothèque Aspose.Words dans votre projet avant d'utiliser ce code.

## Étape 1 : Définir le chemin du répertoire de documents

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Assurez-vous de spécifier le chemin correct vers votre répertoire de documents où le document modifié sera enregistré.

## Étape 2 : créer un générateur de documents

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

 Ici, nous créons une instance de`DocumentBuilder` class qui nous permettra d'ajouter des champs au document.

## Étape 3 : Insérez un champ de date avec un emplacement spécifique

```csharp
Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;
```

 On utilise le générateur de document pour insérer un champ de type`FieldType.FieldDate` dans le document. En réglant le`LocaleId` propriété à`1049`, nous spécifions la localisation russe pour ce champ.

## Étape 4 : Enregistrer le document modifié

```csharp
builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Enfin, nous enregistrons le document modifié avec l'emplacement spécifié dans un fichier spécifié.

### Exemple de code source pour spécifier la localisation au niveau du champ avec Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

DocumentBuilder builder = new DocumentBuilder();

Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;

builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Il s'agissait d'un exemple de code source pour spécifier la localisation au niveau du champ dans un document utilisant Aspose.Words pour .NET. Vous pouvez utiliser ce code pour insérer des champs de date avec des emplacements spécifiques dans vos documents Word.
