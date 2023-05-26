---
title: Utiliser la source d'avertissement
linktitle: Utiliser la source d'avertissement
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à utiliser la source d'avertissement avec le guide étape par étape Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-markdown/use-warning-source/
---

Dans cet exemple, nous allons vous montrer comment utiliser la source d'avertissement avec Aspose.Words pour .NET. La source d'avertissement indique l'origine de l'avertissement lors de l'utilisation de la fonction de rappel.

## Étape 1 : Chargement du document

 Nous allons charger un document existant qui contient des avertissements en utilisant le`Load` méthode de la`Document` classe.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## Étape 3 : Utilisation de la source d'avertissement

 Nous utiliserons la source d'avertissement en définissant le document`WarningCallback` propriété à une collection de`WarningInfo` objets.

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## Étape 4 : Enregistrer le document

Enfin, nous pouvons enregistrer le document dans le format souhaité.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");
foreach (WarningInfo warningInfo in warnings)
{
if (warningInfo.Source == WarningSource.Markdown)
	Console.WriteLine(warningInfo.Description);
}
```

### Exemple de code source pour l'utilisation de la source d'avertissement avec Aspose.Words pour .NET

```csharp
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Emphases markdown warning.docx");

	WarningInfoCollection warnings = new WarningInfoCollection();
	doc.WarningCallback = warnings;

	doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");

	foreach (WarningInfo warningInfo in warnings)
	{
		if (warningInfo.Source == WarningSource.Markdown)
			Console.WriteLine(warningInfo.Description);
	}
            
```

Félicitation ! Vous avez maintenant appris à utiliser la source d'avertissement avec Aspose.Words pour .NET.