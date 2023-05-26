---
title: Insérer des champs imbriqués
linktitle: Insérer des champs imbriqués
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à insérer facilement des champs imbriqués dans vos documents Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-fields/insert-nested-fields/
---

Voici un guide étape par étape pour expliquer le code source C# ci-dessous, qui utilise la fonctionnalité "Insérer des champs imbriqués" d'Aspose.Words pour .NET. Assurez-vous de suivre attentivement chaque étape pour obtenir les résultats souhaités.

## Étape 1 : configuration du répertoire de documents

Dans le code fourni, vous devez spécifier le répertoire de vos documents. Remplacez la valeur "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié vers votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Création du document et de DocumentBuilder

Nous commençons par créer un nouveau document et initialiser un DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Insertion de sauts de page

Nous utilisons une boucle pour insérer plusieurs sauts de page dans le document.

```csharp
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);
```

## Étape 4 : Déplacer vers le pied de page

 Nous utilisons le`MoveToHeaderFooter()` du DocumentBuilder pour déplacer le curseur vers le pied de page principal.

```csharp
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

## Étape 5 : Insertion du champ imbriqué

 Nous utilisons le DocumentBuilder`InsertField()` méthode pour insérer un champ imbriqué dans le pied de page.

```csharp
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");
```

 Enfin, nous appelons le`Update()` méthode pour mettre à jour le champ.

```csharp
field. Update();
```

### Exemple de code source pour insérer des champs imbriqués avec Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Créez le document et le DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insérer des sauts de page.
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);

// Déplacer vers le pied de page.
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// Insérer un champ imbriqué.
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");

// Mettez à jour le champ.
field. Update();

doc.Save(dataDir + "InsertNestedFields.docx");
```

Dans cet exemple, nous avons créé un nouveau document, inséré des sauts de page, déplacé le curseur vers le pied de page, puis inséré un champ imbriqué dans le pied de page.