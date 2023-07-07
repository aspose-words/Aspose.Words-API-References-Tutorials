---
title: Lire les propriétés XControl actives à partir d'un fichier Word
linktitle: Lire les propriétés XControl actives à partir d'un fichier Word
second_title: Référence de l'API Aspose.Words pour .NET
description: Lire les propriétés des contrôles ActiveX dans un fichier Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

Dans ce guide étape par étape, nous vous montrerons comment lire les propriétés des contrôles ActiveX dans un fichier Word à l'aide de Aspose.Words pour .NET. Nous vous fournirons le code source complet et vous montrerons comment formater la sortie Markdown.

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

## Conclusion

Ce guide vous a montré comment lire les propriétés des contrôles ActiveX dans un fichier Word à l'aide de Aspose.Words pour .NET. En suivant les étapes décrites, vous pouvez initialiser le document, récupérer les contrôles ActiveX et lire leurs propriétés. Utilisez l'exemple de code fourni comme point de départ et personnalisez-le selon vos besoins spécifiques.

La lecture des propriétés des contrôles ActiveX vous permet d'extraire des informations importantes de vos fichiers Word contenant ces contrôles. Aspose.Words pour .NET offre des fonctionnalités puissantes pour travailler avec les contrôles ActiveX et automatiser le traitement de votre document.

### FAQ

#### Q : Quelle est la première étape pour lire les propriétés des contrôles ActiveX dans un fichier Word ?

 R : La première étape consiste à initialiser le`Document` objet en chargeant le document Word contenant les contrôles ActiveX. Assurez-vous de remplacer`MyDir` avec le chemin d'accès réel au répertoire contenant le document.

#### Q : Comment intégrer les contrôles ActiveX dans le document ?

 R : Pour récupérer les contrôles ActiveX, vous devez parcourir chaque`Shape` du document et vérifiez s'il s'agit d'un contrôle ActiveX. Utilisez le`OleFormat` propriété de`Shape` pour accéder à la`OleControl` objet et récupérez les propriétés nécessaires.

#### Q : Quelles propriétés des contrôles ActiveX puis-je lire ?

R : Vous pouvez lire diverses propriétés des contrôles ActiveX, telles que la légende, la valeur, l'état activé ou désactivé, le type et les nœuds enfants associés au contrôle.

#### Q : Comment puis-je obtenir le nombre total de contrôles ActiveX dans le document ?

 R : Pour obtenir le nombre total de contrôles ActiveX dans le document, vous pouvez utiliser le`GetChildNodes` méthode de la`Document` objet spécifiant le`NodeType.Shape` type et incluant les nœuds enfants.