---
title: Vérifier la séquence
linktitle: Vérifier la séquence
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à vérifier la séquence des zones de texte dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-textboxes/check-sequence/
---

## Étape 1 : Configuration du document et création d'une forme TextBox

 Pour commencer, nous devons configurer le document et créer une forme TextBox. Le code suivant initialise une nouvelle instance de`Document` classe et crée une forme de zone de texte :

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## Étape 2 : Vérification de la séquence TextBox

 Nous allons maintenant vérifier la séquence de la TextBox en utilisant`if` conditions. Le code source fourni contient trois conditions distinctes pour vérifier la position de TextBox par rapport aux formes précédentes et suivantes.

## Étape 3 : Vérification de la tête de séquence :

```csharp
if (textBox. Next != null && textBox. Previous == null)
{
     Console.WriteLine("The head of the sequence");
}
```

Si le TextBox a une forme suivante (`Next`) mais pas de forme précédente (`Previous`), cela signifie qu'il s'agit de la tête de la séquence. Le message « La tête de la séquence » s'affichera.

## Étape 4 : Vérification du milieu de la séquence :

```csharp
if (textBox. Next != null && textBox. Previous != null)
{
     Console.WriteLine("The middle of the sequence.");
}
```

Si le TextBox a à la fois une forme Next (`Next`) et une forme précédente (`Previous`), cela indique qu'il est au milieu de la séquence. Le message "Le milieu de la séquence" s'affichera.

## Etape 5 : Vérification de la fin de la séquence :

```csharp
if (textBox. Next == null && textBox. Previous != null)
{
     Console.WriteLine("The end of the sequence.");
}
```

Si le TextBox n'a pas de forme suivante (`Next`) mais a une forme précédente (`Previous`), cela signifie que c'est la fin de la séquence. Le message "La fin de la séquence" s'affichera.

### Exemple de code source pour vérifier la séquence avec Aspose.Words pour .NET

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

if (textBox. Next != null && textBox. Previous == null)
{
     Console.WriteLine("The head of the sequence");
}

if (textBox. Next != null && textBox. Previous != null)
{
     Console.WriteLine("The middle of the sequence.");
}

if (textBox. Next == null && textBox. Previous != null)
{
     Console.WriteLine("The end of the sequence.");
}
```