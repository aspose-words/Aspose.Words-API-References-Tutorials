---
title: Insérer le champ Auteur
linktitle: Insérer le champ Auteur
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à insérer un champ AUTEUR dans vos documents Word avec Aspose.Words pour .NET. Indiquez le nom de l'auteur pour personnaliser vos documents.
type: docs
weight: 10
url: /fr/net/working-with-fields/insert-author-field/
---


Voici un guide étape par étape pour expliquer le code source C# ci-dessous, qui utilise la fonctionnalité "Insérer un champ AUTHOR" d'Aspose.Words pour .NET. Assurez-vous de suivre attentivement chaque étape pour obtenir les résultats souhaités.

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

## Étape 3 : Insérer le champ AUTEUR

 Nous utilisons le`AppendField()` méthode pour insérer un champ AUTEUR dans le paragraphe.

```csharp
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);
```

 Nous configurons ensuite le champ`AuthorName` propriété pour spécifier le nom de l'auteur.

```csharp
field. AuthorName = "Test1";
```

 Enfin, nous appelons le`Update()` méthode pour mettre à jour le champ.

```csharp
field. Update();
```

### Exemple de code source pour insérer un champ AUTHOR avec Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Création de documents.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Insérez le champ AUTEUR.
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);

field. AuthorName = "Test1";

field. Update();

doc.Save(dataDir + "InsertionAuthorField.docx");
```

Dans cet exemple, nous avons créé un nouveau document, inséré un champ AUTEUR, configuré le nom de l'auteur et enregistré le document avec un nom de fichier spécifié.

Ceci conclut notre guide sur l'utilisation de la fonctionnalité "Insérer le champ AUTHOR" avec Aspose.Words pour .NET.
