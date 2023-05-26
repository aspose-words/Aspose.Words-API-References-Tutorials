---
title: Insérer un champ avancé sans Document Builder
linktitle: Insérer un champ avancé sans Document Builder
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à insérer un champ avancé dans vos documents Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fields/insert-advance-field-with-out-document-builder/
---

Voici un guide étape par étape pour expliquer le code source C # ci-dessous, qui utilise la fonctionnalité « Insertion de champ avancée sans DocumentBuilder » d'Aspose.Words pour .NET. Assurez-vous de suivre attentivement chaque étape pour obtenir les résultats souhaités.

## Étape 1 : configuration du répertoire de documents

Dans le code fourni, vous devez spécifier le répertoire de vos documents. Remplacez la valeur "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié vers votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Création du document et du paragraphe

Nous commençons par créer un nouveau document et récupérons le premier paragraphe.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Étape 3 : Insertion du champ avancé

 Nous utilisons le`AppendField()`méthode pour insérer un champ avancé dans le paragraphe.

```csharp
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);
```

On configure ensuite les différentes propriétés du champ avancé en précisant les valeurs souhaitées.

```csharp
field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";
```

 Enfin, nous appelons le`Update()` méthode pour mettre à jour le champ.

```csharp
field. Update();
```

### Exemple de code source pour insérer un champ avancé sans DocumentBuilder avec Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Création de documents.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Insérez le champ avancé.
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);

field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";

field. Update();

doc.Save(dataDir + "InsertionFieldAdvanceWithoutDocumentBuilder.docx");
```

Dans cet exemple, nous avons créé un nouveau document, inséré un champ avancé sans utiliser DocumentBuilder, configuré les différentes propriétés de champ et enregistré le document avec un nom de fichier spécifié.

Ceci conclut notre guide sur l'utilisation de la fonctionnalité "Insérer un champ avancé sans DocumentBuilder" avec Aspose.Words pour .NET.

