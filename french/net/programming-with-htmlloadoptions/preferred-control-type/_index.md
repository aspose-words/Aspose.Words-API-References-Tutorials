---
title: Type de contrôle préféré
linktitle: Type de contrôle préféré
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour spécifier le type de contrôle préféré lors du chargement d'un document HTML avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-htmlloadoptions/preferred-control-type/
---

Cet article fournit un guide étape par étape sur la façon d'utiliser la fonctionnalité de type de contrôle préféré avec Aspose.Words pour .NET. Nous expliquerons chaque partie du code en détail. À la fin de ce didacticiel, vous serez en mesure de comprendre comment spécifier le type de champ préféré lors du chargement d'un document HTML.

Avant de commencer, assurez-vous d'avoir installé et configuré la bibliothèque Aspose.Words pour .NET dans votre projet. Vous pouvez trouver la bibliothèque et les instructions d'installation sur le site Web d'Aspose.

## Étape 1 : Définir le code HTML

 Pour commencer, vous devez définir le code HTML que vous souhaitez charger en tant que document. Dans cet exemple, nous avons défini un`html` variable contenant le code HTML d'un sélecteur avec options.

```csharp
const string html=@"
<html>
<select name='ComboBox' size='1'>
<option value='val1'>item1</option>
<option value='val2'></option>
</select>
</html>
";
```

## Étape 2 : Définir les options de chargement HTML

 Ensuite, nous créons un`HtmlLoadOptions` objet et définissez le`PreferredControlType` propriété à`HtmlControlType.StructuredDocumentTag`. Cela indique à Aspose.Words d'utiliser StructuredDocumentTags pour représenter le HTML lors du chargement.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## Étape 3 : Chargez et enregistrez le document

 Nous utilisons le`Document` class pour charger du code HTML à partir d'un flux mémoire avec les options de chargement définies précédemment. Ensuite, nous enregistrons le document dans le répertoire spécifié avec le`.docx` format de fichier.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### Exemple de code source pour le type de contrôle préféré avec Aspose.Words pour .NET

```csharp
	
	const string html = @"
		<html>
			<select name='ComboBox' size='1'>
				<option value='val1'>item1</option>
				<option value='val2'></option>                        
			</select>
		</html>
	";
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };

	Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

	doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);

```

C'est tout ! Vous avez spécifié avec succès le type de contrôle préféré lors du chargement d'un document HTML avec Aspose.Words pour .NET.