---
title: Insérer FieldIncludeText sans Document Builder
linktitle: Insérer FieldIncludeText sans Document Builder
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à insérer un champ FieldIncludeText dans vos documents Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fields/insert-field-include-text-without-document-builder/
---

Voici un guide étape par étape pour expliquer le code source C# ci-dessous, qui utilise la fonctionnalité "Insérer un champ FieldIncludeText" d'Aspose.Words pour .NET. Assurez-vous de suivre attentivement chaque étape pour obtenir les résultats souhaités.

## Étape 1 : configuration du répertoire de documents

Dans le code fourni, vous devez spécifier le répertoire de vos documents. Remplacez la valeur "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié vers votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Création du document et du paragraphe

Nous commençons par créer un nouveau document et initialiser un paragraphe.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Étape 3 : Insertion du champ FieldIncludeText

 Nous utilisons le`AppendField()` méthode pour insérer un champ FieldIncludeText dans le paragraphe.

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

Nous configurons ensuite les propriétés du champ FieldIncludeText en spécifiant le nom du signet et le nom du fichier source.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

Ensuite, nous ajoutons le paragraphe au corps du document.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

 Enfin, nous appelons le`Update()` méthode pour mettre à jour le champ.

```csharp
fieldIncludeText.Update();
```

### Exemple de code source pour insérer un champ FieldIncludeText avec Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Créez le document et le paragraphe.
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Insérer le champ FieldIncludeText.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

Dans cet exemple, nous avons créé un nouveau document, initialisé un paragraphe, inséré un FieldIncludeTexten spécifiant le nom du signet et le nom du fichier source, et enregistré le document avec un nom de fichier spécifié.

Ceci conclut notre guide sur l'utilisation de la fonctionnalité "Insérer un champIncludeText" avec Aspose.Words pour .NET.