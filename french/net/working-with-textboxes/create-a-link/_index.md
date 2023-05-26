---
title: Créer un lien
linktitle: Créer un lien
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à créer un lien entre les zones de texte dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-textboxes/create-a-link/
---

## Étape 1 : Configurer le document et créer des formes TextBox

 Pour commencer, nous devons configurer le document et créer deux formes TextBox. Le code suivant initialise une nouvelle instance de`Document` classe et crée deux formes de zone de texte :

```csharp
Document doc = new Document();
Shape shape1 = new Shape(doc, ShapeType.TextBox);
Shape shape2 = new Shape(doc, ShapeType.TextBox);

TextBox textBox1 = shape1.TextBox;
TextBox textBox2 = shape2.TextBox;
```

## Étape 2 : Création d'un lien entre les zones de texte

 Nous allons maintenant créer un lien entre les deux TextBoxes en utilisant le`IsValidLinkTarget()` méthode et la`Next` propriété du premier TextBox.

```csharp
if (textBox1.IsValidLinkTarget(textBox2))
     textBox1. Next = textBox2;
```

 Le`IsValidLinkTarget()` La méthode vérifie si le deuxième TextBox peut être une cible valide pour le lien du premier TextBox. Si la validation réussit, le`Next` La propriété du premier TextBox est définie sur le second TextBox, créant ainsi un lien entre les deux.

### Exemple de code source à lier avec Aspose.Words pour .NET

```csharp
Document doc = new Document();
Shape shape1 = new Shape(doc, ShapeType.TextBox);
Shape shape2 = new Shape(doc, ShapeType.TextBox);

TextBox textBox1 = shape1.TextBox;
TextBox textBox2 = shape2.TextBox;

if (textBox1.IsValidLinkTarget(textBox2))
     textBox1. Next = textBox2;
```