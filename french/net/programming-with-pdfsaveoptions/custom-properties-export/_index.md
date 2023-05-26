---
title: Exportation des propriétés personnalisées
linktitle: Exportation des propriétés personnalisées
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à exporter des propriétés personnalisées lors de la conversion de documents au format PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/custom-properties-export/
---

Dans ce didacticiel, nous vous guiderons à travers les étapes pour exporter les propriétés personnalisées d'un document à l'aide de Aspose.Words pour .NET. L'exportation de propriétés personnalisées vous permet d'inclure des informations supplémentaires dans le document PDF généré. Suivez les étapes ci-dessous :

## Étape 1 : Création d'un document et ajout de propriétés personnalisées

Commencez par créer une instance de la classe Document :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Étape 2 : Ajoutez des propriétés personnalisées
Ensuite, ajoutez les propriétés personnalisées souhaitées. Par exemple, pour ajouter une propriété "Société" avec la valeur "Aspose", utilisez la propriété`Add` méthode de la collection CustomDocumentProperties :

```csharp
doc.CustomDocumentProperties.Add("Company", "Aspose");
```

Vous pouvez ajouter autant de propriétés personnalisées que nécessaire.

## Étape 3 : Définir les options d'exportation PDF

Créez une instance de la classe PdfSaveOptions et spécifiez comment exporter les propriétés personnalisées :

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };
```

Cette option contrôle l'exportation des propriétés personnalisées lors de la conversion au format PDF.

## Étape 4 : Convertir le document en PDF

 Utilisez le`Save` méthode pour convertir le document en PDF en spécifiant les options de conversion :

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
```

Assurez-vous de spécifier le chemin d'accès correct pour enregistrer le PDF converti.

### Exemple de code source pour l'exportation de propriétés personnalisées à l'aide de Aspose.Words pour .NET

Voici le code source complet pour exporter les propriétés personnalisées d'un document à l'aide d'Aspose.Words pour .NET :


```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	doc.CustomDocumentProperties.Add("Company", "Aspose");

	PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);

```

En suivant ces étapes, vous pouvez facilement exporter les propriétés personnalisées d'un document lors de la conversion au format PDF avec Aspose.Words pour .NET.

