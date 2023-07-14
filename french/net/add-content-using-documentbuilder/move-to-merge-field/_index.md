---
title: Déplacer vers le champ de fusion
linktitle: Déplacer vers le champ de fusion
second_title: API de traitement de documents Aspose.Words
description: Apprenez à implémenter la fonctionnalité Déplacer vers le champ de fusion dans Aspose.Words pour .NET à l'aide d'un guide étape par étape.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/move-to-merge-field/
---

Dans cet exemple, nous allons explorer la fonctionnalité Move To Merge Field de Aspose.Words pour .NET. Aspose.Words est une puissante bibliothèque de manipulation de documents qui permet aux développeurs de créer, modifier et convertir des documents Word par programmation. La fonction Déplacer vers le champ de fusion nous permet de naviguer pour fusionner des champs dans un document et d'effectuer diverses opérations dessus.


## Expliquer le code source étape par étape

Passons en revue le code source étape par étape pour comprendre comment utiliser la fonctionnalité Move To Merge Field en utilisant Aspose.Words pour .NET.

## Étape 1 : Initialisation du document et du générateur de documents

Tout d'abord, initialisez les objets Document et DocumentBuilder :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 Insertion d'un champ de fusion et ajout de texte après celui-ci

Utilisez la méthode InsertField de la classe DocumentBuilder pour insérer un champ de fusion, puis ajoutez du texte après :

```csharp
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");
```

## Étape 3 : Le curseur du générateur se trouve actuellement à la fin du document.

```csharp
Assert.Null(builder.CurrentNode);
```
## Étape 4 : déplacement du curseur du générateur de document vers le champ de fusion

Pour déplacer le curseur du générateur de document vers le champ de fusion, utilisez la méthode MoveToField de la classe DocumentBuilder :

```csharp
builder.MoveToField(field, true);
```

## Ajouter du texte immédiatement après le champ de fusion

Une fois que le curseur du générateur de document se trouve dans le champ de fusion, vous pouvez ajouter du texte immédiatement après en utilisant la méthode Write :

```csharp
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

### Exemple de code source pour Move To Merge Field en utilisant Aspose.Words pour .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insérez un champ à l'aide de DocumentBuilder et ajoutez une suite de texte après celui-ci.
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");

// Le curseur du constructeur est actuellement à la fin du document.
Assert.Null(builder.CurrentNode);
// Nous pouvons déplacer le générateur vers un champ comme celui-ci, en plaçant le curseur immédiatement après le champ.
builder.MoveToField(field, true);

// Notez que le curseur se trouve à un endroit après le nœud FieldEnd du champ, ce qui signifie que nous ne sommes pas réellement à l'intérieur du champ.
// Si nous souhaitons déplacer le DocumentBuilder à l'intérieur d'un champ,
// nous devrons le déplacer vers le nœud FieldStart ou FieldSeparator d'un champ à l'aide de la méthode DocumentBuilder.MoveTo().
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

## Conclusion

nous avons exploré la fonctionnalité Move To Merge Field de Aspose.Words pour .NET. Nous avons appris à naviguer pour fusionner des champs dans un document à l'aide de la classe DocumentBuilder et à effectuer des opérations dessus. Cette fonctionnalité est utile lors du traitement de mots par programmation avec fusion

