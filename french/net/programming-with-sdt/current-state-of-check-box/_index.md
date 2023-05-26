---
title: Case à cocher État actuel de
linktitle: Case à cocher État actuel de
second_title: Référence de l'API Aspose.Words pour .NET
description: Découvrez comment récupérer et définir l'état actuel d'un contrôle de contenu de case à cocher dans un document Word à l'aide de Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-sdt/current-state-of-check-box/
---

Ce didacticiel explique comment récupérer et définir l'état actuel d'un contrôle de contenu de case à cocher dans un document Word à l'aide de Aspose.Words pour .NET. Vous pouvez cocher ou décocher la case en fonction de son état actuel.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et travail avec des documents Word.

## Étape 1 : Configurer le répertoire de documents
 Commencez par configurer le chemin d'accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel au répertoire où se trouve votre document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : chargez le document et récupérez le contrôle du contenu de la case à cocher
 Chargez le document Word à l'aide du`Document` constructeur, en passant le chemin d'accès au document en tant que paramètre. Ensuite, récupérez le contrôle de contenu de case à cocher souhaité à partir du document. Dans cet exemple, nous supposons que la case à cocher est la première balise de document structuré dans le document.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Étape 3 : cochez ou décochez la case en fonction de son état actuel
 Vérifier si la balise de document structuré récupérée est de type`SdtType.Checkbox` . Si c'est le cas, réglez le`Checked` propriété du contrôle de contenu à`true` pour cocher la case. Sinon, vous pouvez le laisser décoché.

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## Étape 4 : Enregistrer le document
 Enregistrez le document modifié dans le répertoire spécifié à l'aide de la`Save`méthode. Indiquez le nom de fichier souhaité avec l'extension de fichier appropriée. Dans cet exemple, nous enregistrons le document sous "WorkingWithSdt.CurrentStateOfCheckBox.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### Exemple de code source pour l'état actuel de la case à cocher en utilisant Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	// Obtenez le premier contrôle de contenu du document.
	StructuredDocumentTag sdtCheckBox =
		(StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	if (sdtCheckBox.SdtType == SdtType.Checkbox)
		sdtCheckBox.Checked = true;
	doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

C'est ça! Vous avez récupéré et défini avec succès l'état actuel d'un contrôle de contenu de case à cocher dans votre document Word à l'aide de Aspose.Words pour .NET.