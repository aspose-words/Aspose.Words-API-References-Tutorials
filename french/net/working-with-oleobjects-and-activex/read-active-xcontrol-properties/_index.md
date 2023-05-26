---
title: Lire les propriétés XControl actives
linktitle: Lire les propriétés XControl actives
second_title: Référence de l'API Aspose.Words pour .NET
description: Lire les propriétés des contrôles ActiveX dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

Dans ce guide étape par étape, nous vous montrerons comment lire les propriétés des contrôles ActiveX dans un document Word à l'aide de Aspose.Words pour .NET. Nous vous fournirons le code source complet et vous montrerons comment formater la sortie Markdown.

## Étape 1 : Initialisation du document

 La première étape consiste à initialiser le`Document` objet en chargeant le document Word contenant les contrôles ActiveX. Assurez-vous de remplacer`MyDir` avec le chemin d'accès réel au répertoire contenant le document.

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## Étape 2 : Récupérer les contrôles ActiveX

 Dans cette étape, nous allons parcourir chaque`Shape` du document pour récupérer les contrôles ActiveX et lire leurs propriétés.

```csharp
string properties = "";
foreach(Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
     if (shape.OleFormat is null) break;

     OleControl oleControl = shape.OleFormat.OleControl;
     if (oleControl.IsForms2OleControl)
     {
         Forms2OleControl checkBox = (Forms2OleControl)oleControl;
         properties = properties + "\nCaption: " + checkBox.Caption;
         properties = properties + "\nValue: " + checkBox.Value;
         properties = properties + "\nEnabled: " + checkBox.Enabled;
         properties = properties + "\nType: " + checkBox.Type;
         if (checkBox. ChildNodes != null)
         {
             properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
         }

         properties += "\n";
     }
}

properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
Console.WriteLine("\n" + properties);
```

### Exemple de code source pour Lire les propriétés Active XControl à l'aide de Aspose.Words pour .NET

Voici le code source complet pour lire les propriétés des contrôles ActiveX à l'aide d'Aspose.Words pour .NET :

```csharp
	Document doc = new Document(MyDir + "ActiveX controls.docx");

	string properties = "";
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
	{
		if (shape.OleFormat is null) break;

		OleControl oleControl = shape.OleFormat.OleControl;
		if (oleControl.IsForms2OleControl)
		{
			Forms2OleControl checkBox = (Forms2OleControl) oleControl;
			properties = properties + "\nCaption: " + checkBox.Caption;
			properties = properties + "\nValue: " + checkBox.Value;
			properties = properties + "\nEnabled: " + checkBox.Enabled;
			properties = properties + "\nType: " + checkBox.Type;
			if (checkBox.ChildNodes != null)
			{
				properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
			}

			properties += "\n";
		}
	}

	properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
	Console.WriteLine("\n" + properties);
```

