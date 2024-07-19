---
title: Accents
linktitle: Accents
second_title: API de traitement de documents Aspose.Words
description: Apprenez à utiliser les accents (gras et italique) avec le guide étape par étape d'Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/working-with-markdown/emphases/
---

Dans cet exemple, nous expliquerons comment utiliser les accents avec Aspose.Words pour .NET. les accents sont utilisés pour mettre en valeur certaines parties du texte, telles que le gras et l'italique.

## Étape 1 : Initialisation du document

 Tout d'abord, nous allons initialiser le document en créant une instance du`Document` classe.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Étape 2 : Utiliser un générateur de documents

Ensuite, nous utiliserons un générateur de documents pour ajouter du contenu à notre document.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : ajouter du texte avec des accents

Nous pouvons ajouter du texte accentué en modifiant les propriétés de police du générateur de documents. Dans cet exemple, nous utilisons le gras et l'italique pour mettre en valeur différentes parties du texte.

```csharp
builder.Writeln("Markdown treats asterisks (*) and underscores (_) as emphases indicators.");
builder.Write("You can write");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(".");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("bold and italic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder. Write(".");

```

## Étape 4 : Sauvegarde du document

 Enfin, nous pouvons enregistrer le document au format souhaité. Dans cet exemple, nous utilisons le`.md` extension pour un format Markdown.

```csharp
builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

Félicitation ! Vous avez maintenant appris à utiliser les accents avec Aspose.Words pour .NET.

### Exemple de code source pour Empphases utilisant Aspose.Words pour .NET


```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Markdown treats asterisks (*) and underscores (_) as indicators of emphases.");
builder.Write("You can write ");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(" text. ");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("BoldItalic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder.Write("text.");

builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

### FAQ

#### Q : Comment surligner du texte à l’aide de Markdown ?

 : Pour surligner du texte à l'aide de Markdown, entourez simplement le texte avec les symboles appropriés. Utiliser`*` ou`_` pour les italiques,`**` ou`__` pour gras, et`~~` pour le barré.

#### Q : Pouvons-nous combiner différents surlignages dans le même texte ?

 R : Oui, il est possible de combiner différents surlignages dans un même texte. Par exemple, vous pouvez mettre un mot en gras et en italique en utilisant à la fois`**`et`*` autour du monde.

#### Q : Quelles options de surbrillance sont disponibles dans Markdown ?

R : Les options de surbrillance disponibles dans Markdown sont en italique (`*` ou`_`), audacieux (`**` ou`__`), et barré (`~~`).

#### Q : Comment gérer les cas où le texte contient des caractères spéciaux utilisés par Markdown pour le surlignage ?

 R : Si votre texte contient des caractères spéciaux utilisés par Markdown pour le surlignage, vous pouvez les échapper en les faisant précéder d'un`\` . Par exemple,`\*` affichera un astérisque littéral.

#### Q : Pouvons-nous personnaliser l’apparence du surlignage à l’aide de CSS ?

: La surbrillance dans Markdown est généralement rendue en utilisant les styles par défaut du navigateur. Si vous convertissez votre Markdown en HTML, vous pouvez personnaliser l'apparence de la surbrillance à l'aide des règles CSS.