---
title: Accents
linktitle: Accents
second_title: API de traitement de documents Aspose.Words
description: Apprenez à utiliser les accents (gras et italique) avec Aspose.Words pour le guide étape par étape .NET.
type: docs
weight: 10
url: /fr/net/working-with-markdown/emphases/
---

Dans cet exemple, nous expliquerons comment utiliser les emphases avec Aspose.Words pour .NET. emphases est utilisé pour souligner certaines parties du texte, comme le gras et l'italique.

## Étape 1 : Initialisation du document

 Tout d'abord, nous allons initialiser le document en créant une instance de`Document` classe.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Étape 2 : Utiliser un générateur de documents

Ensuite, nous utiliserons un générateur de document pour ajouter du contenu à notre document.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Ajouter du texte avec Emphases

Nous pouvons ajouter du texte d'emphase en modifiant les propriétés de police du générateur de documents. Dans cet exemple, nous utilisons le gras et l'italique pour souligner différentes parties du texte.

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

## Étape 4 : Enregistrer le document

 Enfin, nous pouvons enregistrer le document dans le format souhaité. Dans cet exemple, nous utilisons le`.md` extension pour un format Markdown.

```csharp
builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

Félicitation ! Vous avez maintenant appris à utiliser les emphases avec Aspose.Words pour .NET.

### Exemple de code source pour Emphases utilisant Aspose.Words pour .NET


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

#### Q : Comment mettre en surbrillance du texte à l'aide de Markdown ?

R : Pour mettre en surbrillance du texte à l'aide de Markdown, entourez simplement le texte des symboles appropriés. Utiliser`*` ou`_` pour les italiques,`**` ou`__` pour gras, et`~~` pour barré.

#### Q : Pouvons-nous combiner différents surlignages dans le même texte ?

 R : Oui, il est possible de combiner différents surlignages dans le même texte. Par exemple, vous pouvez mettre en gras et en italique un mot en utilisant à la fois`**` et`*` autour du monde.

#### Q : Quelles sont les options de mise en surbrillance disponibles dans Markdown ?

R : Les options de mise en surbrillance disponibles dans Markdown sont en italique (`*` ou`_`), gras (`**` ou`__`) et barré (`~~`).

#### Q : Comment gérer les cas où le texte contient des caractères spéciaux utilisés par Markdown pour la mise en surbrillance ?

 R : Si votre texte contient des caractères spéciaux utilisés par Markdown pour la mise en surbrillance, vous pouvez les échapper en les faisant précéder d'un`\` . Par exemple,`\*` affichera un astérisque littéral.

#### Q : Pouvons-nous personnaliser l'apparence de la surbrillance à l'aide de CSS ?

R : La surbrillance dans Markdown est généralement rendue à l'aide des styles par défaut du navigateur. Si vous convertissez votre Markdown en HTML, vous pouvez personnaliser l'apparence de la surbrillance à l'aide des règles CSS.