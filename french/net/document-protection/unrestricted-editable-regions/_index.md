---
title: Régions modifiables sans restriction
linktitle: Régions modifiables sans restriction
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à créer des zones modifiables sans restriction dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/document-protection/unrestricted-editable-regions/
---

Dans ce didacticiel, nous vous guiderons à travers les étapes d'utilisation de la fonctionnalité de zones modifiables sans restriction d'Aspose.Words pour .NET. Cette fonctionnalité vous permet de définir des zones dans un document Word où le contenu peut être modifié sans restriction, même si le reste du document est en lecture seule. Suivez les étapes ci-dessous :

## Étape 1 : chargement du document et définition de la protection

Commencez par charger le document existant :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
doc.Protect(ProtectionType.ReadOnly, "MyPassword");
```

Protégez le document en définissant un type de protection en lecture seule et un mot de passe

## Étape 2 : Création d'une zone modifiable

Commencez par créer une zone modifiable à l'aide des objets EditableRangeStart et EditableRangeEnd :

```csharp
EditableRangeStart edRangeStart = builder.StartEditableRange();
// Un objet EditableRange est créé pour le EditableRangeStart que nous venons de créer.
EditableRange editableRange = edRangeStart.EditableRange;

// Mettez quelque chose à l'intérieur de la plage modifiable.
builder.Writeln("Paragraph inside first editable range");

// Une plage modifiable est bien formée si elle a un début et une fin.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

```

## Étape 3 : Ajouter du contenu en dehors des zones modifiables

Vous pouvez ajouter du contenu en dehors des zones modifiables, qui resteront en lecture seule :

```csharp
builder.Writeln("This paragraph is outside of all editable areas and cannot be edited.");
```

## Étape 4 : Enregistrez le document

Enfin, enregistrez le document modifié :

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
```

Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects pour enregistrer le document avec des zones modifiables.

### Exemple de code source pour les régions modifiables sans restriction à l'aide d'Aspose.Words pour .NET

Voici le code source complet pour les zones modifiables sans restriction à l'aide d'Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Téléchargez un document et rendez-le en lecture seule.
	Document doc = new Document(MyDir + "Document.docx");
	DocumentBuilder builder = new DocumentBuilder(doc);

	doc.Protect(ProtectionType.ReadOnly, "MyPassword");

	builder.Writeln("Hello world! Since we have set the document's protection level to read-only, " + "we cannot edit this paragraph without the password.");

	// Commencez une plage modifiable.
	EditableRangeStart edRangeStart = builder.StartEditableRange();
	// Un objet EditableRange est créé pour le EditableRangeStart que nous venons de créer.
	EditableRange editableRange = edRangeStart.EditableRange;

	// Mettez quelque chose à l'intérieur de la plage modifiable.
	builder.Writeln("Paragraph inside first editable range");

	// Une plage modifiable est bien formée si elle a un début et une fin.
	EditableRangeEnd edRangeEnd = builder.EndEditableRange();

	builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

	doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");

```
En suivant ces étapes, vous pouvez facilement créer des zones modifiables sans restriction dans votre document Word avec Aspose.Words pour .NET.


