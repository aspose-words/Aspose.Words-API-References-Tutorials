---
title: Par rubriques
linktitle: Par rubriques
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à diviser un document Word en sections distinctes à l'aide d'Aspose.Words pour .NET avec un exemple de code complet.
type: docs
weight: 10
url: /fr/net/split-document/by-sections/
---

Dans cet exemple, nous allons vous montrer comment diviser un document Word en sections distinctes à l'aide de la fonctionnalité Par sections d'Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et obtenir des documents distincts pour chaque section.

## Étape 1 : Chargement du document

Pour commencer, nous devons spécifier le répertoire de votre document et charger le document dans un objet Document. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## Étape 2 : Divisez le document en sections

Nous allons maintenant parcourir chaque section du document et diviser le document en parties plus petites, section par section. Voici comment procéder :

```csharp
for (int i = 0; i < doc. Sections. Count; i++)
{
// Divisez le document en parties plus petites, dans ce cas, en le séparant par section.
Section section = doc.Sections[i].Clone();

Document newDoc = new Document();
newDoc.Sections.Clear();

Section newSection = (Section) newDoc.ImportNode(section, true);
newDoc.Sections.Add(newSection);

// Enregistrez chaque section dans un document distinct.
newDoc.Save(dataDir + $"SplitDocument.ParSections_{i}.docx");
}
```

### Exemple de code source pour By Sections utilisant Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité Par sections d'Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Big document.docx");

	for (int i = 0; i < doc.Sections.Count; i++)
	{
		// Diviser un document en parties plus petites, dans ce cas, divisé par section.
		Section section = doc.Sections[i].Clone();

		Document newDoc = new Document();
		newDoc.Sections.Clear();

		Section newSection = (Section) newDoc.ImportNode(section, true);
		newDoc.Sections.Add(newSection);

		// Enregistrez chaque section dans un document distinct.
		newDoc.Save(dataDir + $"SplitDocument.BySections_{i}.docx");
	}

```

Avec ce code, vous pourrez diviser un document Word en sections distinctes en utilisant Aspose.Words pour .NET.

Maintenant, vous pouvez facilement travailler avec des sections spécifiques.

