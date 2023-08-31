---
title: Exporter des propriétés personnalisées dans un document PDF
linktitle: Exporter des propriétés personnalisées dans un document PDF
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment exporter des propriétés personnalisées lors de la conversion de documents au format PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/custom-properties-export/
---

Dans ce didacticiel, nous vous guiderons à travers les étapes pour exporter les propriétés personnalisées d'un document dans un document PDF à l'aide d'Aspose.Words for .NET. L'exportation de propriétés personnalisées vous permet d'inclure des informations supplémentaires dans le document PDF généré. Suivez les étapes ci-dessous :

## Étape 1 : Création d'un document et ajout de propriétés personnalisées

Commencez par créer une instance de la classe Document :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Étape 2 : Ajouter des propriétés personnalisées
 Ensuite, ajoutez les propriétés personnalisées souhaitées. Par exemple, pour ajouter une propriété « Société » avec la valeur « Aspose », utilisez le`Add` méthode de la collection CustomDocumentProperties :

```csharp
doc.CustomDocumentProperties.Add("Company", "Aspose");
```

Vous pouvez ajouter autant de propriétés personnalisées que nécessaire.

## Étape 3 : Définir les options d'exportation PDF

Créez une instance de la classe PdfSaveOptions et spécifiez comment exporter les propriétés personnalisées :

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };
```

Cette option contrôle l'exportation des propriétés personnalisées lors de la conversion au format PDF.

## Étape 4 : Convertir le document en PDF

 Utilisez le`Save` méthode pour convertir le document en PDF en spécifiant les options de conversion :

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
```

Assurez-vous de spécifier le chemin correct pour enregistrer le PDF converti.

### Exemple de code source pour l'exportation de propriétés personnalisées à l'aide d'Aspose.Words pour .NET

Voici le code source complet pour exporter les propriétés personnalisées d'un document à l'aide d'Aspose.Words for .NET :


```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	doc.CustomDocumentProperties.Add("Company", "Aspose");

	PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);

```

En suivant ces étapes, vous pouvez facilement exporter les propriétés personnalisées d'un document lors de la conversion au format PDF avec Aspose.Words pour .NET.


## Conclusion

Dans ce didacticiel, nous avons expliqué comment exporter les propriétés personnalisées d'un document vers un document PDF à l'aide d'Aspose.Words pour .NET. En suivant les étapes décrites, vous pouvez facilement inclure des informations supplémentaires dans le document PDF généré en exportant les propriétés personnalisées du document. Profitez des fonctionnalités d'Aspose.Words for .NET pour personnaliser et enrichir vos documents PDF en exportant des propriétés personnalisées.

### Questions fréquemment posées

#### Q : Qu'est-ce que l'exportation de propriétés personnalisées vers un document PDF ?
: L'exportation de propriétés personnalisées vers un document PDF permet d'inclure des informations supplémentaires dans le document PDF généré. Les propriétés personnalisées sont des métadonnées spécifiques à votre document, telles que des balises, des mots-clés ou des informations d'identification. En exportant ces propriétés personnalisées, vous pouvez les mettre à la disposition des utilisateurs lors de la visualisation du document PDF.

#### Q : Comment puis-je exporter les propriétés personnalisées d'un document vers un document PDF à l'aide d'Aspose.Words pour .NET ?
R : Pour exporter les propriétés personnalisées d'un document vers un document PDF à l'aide d'Aspose.Words for .NET, procédez comme suit :

 Créez une instance du`Document` classe.

 Ajoutez les propriétés personnalisées souhaitées à l'aide du`CustomDocumentProperties` collection. Par exemple, utilisez le`Add` méthode pour ajouter une propriété « Entreprise » avec la valeur « Aspose ».

 Créez une instance du`PdfSaveOptions` classe et spécifiez comment exporter les propriétés personnalisées à l'aide de la classe`CustomPropertiesExport` propriété. Le`PdfCustomPropertiesExport.Standard` value exporte les propriétés personnalisées en fonction des paramètres par défaut.

 Utilisez le`Save` méthode du`Document` classe pour convertir le document en PDF en spécifiant les options de conversion.

#### Q : Comment puis-je accéder aux propriétés personnalisées d'un document PDF ?
R : Pour accéder aux propriétés personnalisées d'un document PDF, vous pouvez utiliser un lecteur PDF compatible prenant en charge l'affichage des propriétés du document. Les lecteurs PDF les plus courants, tels qu'Adobe Acrobat Reader, permettent d'accéder aux métadonnées et aux propriétés d'un document PDF. Vous pouvez généralement trouver ces options dans le menu "Fichier" ou en cliquant avec le bouton droit sur le document et en sélectionnant "Propriétés".