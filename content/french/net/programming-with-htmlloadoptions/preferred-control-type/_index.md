---
title: Type de contrôle préféré dans un document Word
linktitle: Type de contrôle préféré dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour spécifier le type de contrôle préféré dans un document Word lors du chargement d'un document HTML avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-htmlloadoptions/preferred-control-type/
---
Cet article fournit un guide étape par étape sur la façon d'utiliser la fonctionnalité de type de contrôle préféré avec Aspose.Words pour .NET. Nous expliquerons chaque partie du code en détail. A la fin de ce tutoriel, vous pourrez comprendre comment spécifier le type de champ préféré lors du chargement d'un document HTML.

Avant de commencer, assurez-vous d'avoir installé et configuré la bibliothèque Aspose.Words for .NET dans votre projet. Vous pouvez trouver la bibliothèque et les instructions d'installation sur le site Web d'Aspose.

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

 Ensuite, nous créons un`HtmlLoadOptions` objet et définissez le`PreferredControlType`propriété à`HtmlControlType.StructuredDocumentTag`. Cela indique à Aspose.Words d'utiliser StructuredDocumentTags pour représenter le HTML lors du chargement.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## Étape 3 : Charger et enregistrer le document

 Nous utilisons le`Document` classe pour charger du code HTML à partir d’un flux mémoire avec les options de chargement définies précédemment. Ensuite, nous sauvegardons le document dans le répertoire spécifié avec le`.docx`format de fichier.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### Exemple de code source pour le type de contrôle préféré avec Aspose.Words for .NET

```csharp
	
	const string html = @"
		<html>
			<select name='ComboBox' size='1'>
				<option value='val1'>item1</option>
				<option value='val2'></option>                        
			</select>
		</html>
	";
	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };

	Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

	doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);

```

C'est tout ! Vous avez correctement spécifié le type de contrôle préféré lors du chargement d'un document HTML avec Aspose.Words pour .NET.

## Conclusion

 En suivant ce guide étape par étape, vous avez appris à utiliser la fonctionnalité « Type de contrôle préféré » dans Aspose.Words for .NET pour spécifier le type de contrôle souhaité lors du chargement d'un document HTML. Réglage du`PreferredControlType`propriété à`HtmlControlType.StructuredDocumentTag` permet à Aspose.Words d'utiliser StructuredDocumentTags (SDT) pour une meilleure représentation et un meilleur traitement du contenu HTML. Vous pouvez également explorer d’autres types de contrôles pour répondre à vos besoins spécifiques. L'utilisation de cette fonctionnalité permet de garantir une gestion précise et efficace des documents HTML dans votre application C# avec Aspose.Words.

### FAQ sur le type de contrôle préféré dans un document Word

#### Q : Qu'est-ce que la fonctionnalité « Type de contrôle préféré » dans Aspose.Words pour .NET ?

: La fonctionnalité « Type de contrôle préféré » vous permet de spécifier le type de contrôle préféré pour représenter les éléments HTML lors du chargement d'un document HTML. Cela aide à sélectionner le type de contrôle approprié pour une meilleure représentation et un meilleur traitement du contenu HTML.

#### Q : Comment définir le type de contrôle préféré lors du chargement d'un document HTML ?

 R : Pour définir le type de contrôle préféré, vous devez créer un`HtmlLoadOptions` objet et définir son`PreferredControlType` propriété à la demande`HtmlControlType` . Dans l'exemple fourni,`HtmlControlType.StructuredDocumentTag` est utilisé.

#### Q : Quelle est l’importance de l’utilisation de StructuredDocumentTags (SDT) comme type de contrôle préféré ?

R : Les StructuredDocumentTags (SDT) sont des éléments basés sur XML qui peuvent être utilisés pour représenter du contenu et des contrôles complexes dans un document Word. L'utilisation des SDT comme type de contrôle préféré peut offrir une meilleure compatibilité et représentation du contenu HTML.

#### Q : Comment puis-je m'assurer qu'Aspose.Words utilise le type de contrôle préféré lors du chargement du document HTML ?

 R : En définissant le`PreferredControlType`propriété à`HtmlControlType.StructuredDocumentTag`comme le montre l'exemple de code source, Aspose.Words utilisera les SDT pour représenter les éléments HTML lors du chargement du document.

#### Q : Puis-je utiliser d’autres types de contrôle comme option préférée ?

 R : Oui, à part`HtmlControlType.StructuredDocumentTag` , Aspose.Words for .NET prend en charge d'autres types de contrôle tels que`HtmlControlType.ContentControl` et`HtmlControlType.CustomXmlMarkup`.