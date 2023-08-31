---
title: Modifier les contrôles de contenu
linktitle: Modifier les contrôles de contenu
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment modifier le texte, les listes déroulantes et les images dans les contrôles de contenu d'un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-sdt/modify-content-controls/
---

Ce didacticiel explique comment modifier différents types de contrôles de contenu dans un document Word à l'aide d'Aspose.Words pour .NET. Vous pouvez mettre à jour le texte, la valeur sélectionnée d'une liste déroulante ou remplacer une image dans les contrôles de contenu.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et du traitement de mots avec des documents Word.

## Étape 1 : configurer le répertoire de documents
 Commencez par configurer le chemin d’accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers le répertoire où se trouve votre document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : charger le document et parcourir les contrôles de contenu
 Chargez le document Word à l'aide du`Document`constructeur, en passant le chemin d'accès au document en paramètre. Parcourez toutes les balises de document structuré du document à l'aide d'un`foreach` boucle.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // Effectuer des actions en fonction du type de contrôle de contenu
}
```

## Étape 3 : Modifier le contrôle du contenu en texte brut
 Pour les contrôles de contenu de type`SdtType.PlainText`, supprimez tous les enfants existants, créez un nouveau paragraphe et ajoutez une séquence avec le texte souhaité.

```csharp
case SdtType.PlainText:
{
    sdt.RemoveAllChildren();
    Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
    Run run = new Run(doc, "new text goes here");
    para.AppendChild(run);
    break;
}
```

## Étape 4 : Modifier le contrôle du contenu de la liste déroulante
 Pour les contrôles de contenu de type`SdtType.DropDownList` , mettez à jour la valeur sélectionnée en la définissant sur un paramètre spécifique`SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## Étape 5 : Modifier le contrôle du contenu de l'image
 Pour les contrôles de contenu de type`SdtType.Picture`, récupérez la forme dans le contrôle de contenu et remplacez son image par une nouvelle.

```csharp
case SdtType.Picture:
{
    Shape shape = (Shape)sdt.GetChild(NodeType.Shape, 0, true);
    if (shape.HasImage)
    {
        shape.ImageData.SetImage(ImagesDir + "Watermark.png");
    }
    break;
}
```

## Étape 6 : Enregistrez le document modifié
 Enregistrez le document modifié dans le répertoire spécifié à l'aide du`Save` méthode. Fournissez le nom de fichier souhaité avec l'extension de fichier appropriée. Dans cet exemple, nous enregistrons le document sous le nom « WorkingWithSdt.ModifyContentControls.docx ».

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

### Exemple de code source pour modifier les contrôles de contenu à l'aide d'Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
	{
		switch (sdt.SdtType)
		{
			case SdtType.PlainText:
			{
				sdt.RemoveAllChildren();
				Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
				Run run = new Run(doc, "new text goes here");
				para.AppendChild(run);
				break;
			}
			case SdtType.DropDownList:
			{
				SdtListItem secondItem = sdt.ListItems[2];
				sdt.ListItems.SelectedValue = secondItem;
				break;
			}
			case SdtType.Picture:
			{
				Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
				if (shape.HasImage)
				{
					shape.ImageData.SetImage(ImagesDir + "Watermark.png");
				}
				break;
			}
		}
	}
	doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");

```

C'est ça! Vous avez modifié avec succès différents types de contrôles de contenu dans votre document Word à l'aide d'Aspose.Words pour .NET.