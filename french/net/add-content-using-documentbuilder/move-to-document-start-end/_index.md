---
title: Déplacer vers le document Début Fin
linktitle: Déplacer vers le document Début Fin
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à utiliser Aspose.Words pour .NET pour passer au début et à la fin du document dans les documents Word avec ce guide étape par étape.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/move-to-document-start-end/
---

Dans cet exemple, nous allons explorer la fonctionnalité Déplacer vers le début/la fin du document d'Aspose.Words pour .NET. Aspose.Words est une puissante bibliothèque de manipulation de documents qui permet aux développeurs de créer, modifier et convertir des documents Word par programme. La fonctionnalité Déplacer vers le début/la fin du document nous permet de naviguer vers le début ou la fin d'un document à l'aide de la classe DocumentBuilder.

## Expliquer le code source étape par étape

Passons en revue le code source étape par étape pour comprendre comment utiliser la fonctionnalité Déplacer vers le début/la fin du document à l'aide de Aspose.Words pour .NET.


## Étape 1 : Initialisation du document et du générateur de documents

Ensuite, initialisez les objets Document et DocumentBuilder :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Passer au début du document

Pour déplacer la position du curseur au début du document, utilisez la méthode MoveToDocumentStart de la classe DocumentBuilder :

```csharp
builder.MoveToDocumentStart();
```

## Étape 3 : Déplacement vers la fin du document

Pour déplacer la position du curseur à la fin du document, utilisez la méthode MoveToDocumentEnd de la classe DocumentBuilder :

```csharp
builder.MoveToDocumentEnd();
```

## Étape 4 : sortie de la position du curseur

Vous pouvez afficher la position du curseur à l'aide de Console.WriteLine ou de toute autre méthode souhaitée. Par exemple:

```csharp
Console.WriteLine("\nThis is the beginning of the document.");
Console.WriteLine("\nThis is the end of the document.");
```

### Exemple de code source pour Déplacer vers le début/la fin du document à l'aide de Aspose.Words pour .NET

```csharp
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Déplacez la position du curseur au début de votre document.
	builder.MoveToDocumentStart();
	Console.WriteLine("\nThis is the beginning of the document.");

	// Déplacez la position du curseur à la fin de votre document.
	builder.MoveToDocumentEnd();
	Console.WriteLine("\nThis is the end of the document.");
	
```

## Conclusion

Dans cet exemple, nous avons exploré la fonctionnalité Déplacer vers le début/la fin du document d'Aspose.Words pour .NET. Nous avons appris à naviguer jusqu'au début et à la fin d'un document à l'aide de la classe DocumentBuilder. Cette fonctionnalité est utile lorsque vous travaillez par programmation avec des documents Word et que vous devez manipuler ou insérer du contenu à des positions spécifiques dans le document.