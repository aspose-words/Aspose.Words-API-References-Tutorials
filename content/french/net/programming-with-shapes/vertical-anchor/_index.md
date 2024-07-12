---
title: Ancrage vertical
linktitle: Ancrage vertical
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment positionner une forme verticalement dans un document à l'aide de la fonction d'ancrage vertical d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-shapes/vertical-anchor/
---

Ce didacticiel explique comment utiliser la fonctionnalité d'ancrage vertical dans Aspose.Words for .NET pour positionner une forme verticalement dans un document. En définissant la propriété d'ancrage vertical d'une forme, vous pouvez contrôler son alignement vertical par rapport au texte ou à la page.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et du traitement de mots avec des documents Word.

## Étape 1 : configurer le répertoire de documents
 Commencez par configurer le chemin d’accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"`avec le chemin réel du répertoire dans lequel vous souhaitez enregistrer le document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Créer un nouveau document et DocumentBuilder
 Créez une nouvelle instance du`Document` classe et un`DocumentBuilder` s'opposer à travailler avec le document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Insérer et configurer une forme
 Insérez une forme dans le document à l'aide du`InsertShape` méthode du`DocumentBuilder` objet. Définissez les dimensions souhaitées pour la forme.

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## Étape 4 : définir l'ancrage vertical
Définissez la propriété d'ancrage vertical de la forme pour contrôler son alignement vertical. Dans cet exemple, nous le définissons sur "Bas" pour ancrer la forme au bas du texte ou de la page.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## Étape 5 : Ajouter du contenu à la forme
 Utilisez le`MoveTo` méthode du`DocumentBuilder` objet pour déplacer le curseur vers le premier paragraphe de la forme. Ensuite, utilisez le`Write` méthode pour ajouter du contenu à la forme.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## Étape 6 : Enregistrez le document
 Enregistrez le document dans le répertoire spécifié à l'aide du`Save`méthode. Fournissez le nom de fichier souhaité avec l'extension de fichier appropriée. Dans cet exemple, nous enregistrons le document sous le nom « WorkingWithShapes.VerticalAnchor.docx ».

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### Exemple de code source pour Vertical Anchor utilisant Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
	textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
	builder.MoveTo(textBox.FirstParagraph);
	builder.Write("Textbox contents");
	doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

C'est ça! Vous avez utilisé avec succès la fonctionnalité d'ancrage vertical dans Aspose.Words for .NET pour positionner une forme verticalement dans un document.