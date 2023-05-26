---
title: Lesen Sie die Eigenschaften von Active XControl
linktitle: Lesen Sie die Eigenschaften von Active XControl
second_title: Aspose.Words für .NET API-Referenz
description: Lesen Sie Eigenschaften von ActiveX-Steuerelementen in einem Word-Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET Eigenschaften von ActiveX-Steuerelementen in einem Word-Dokument lesen. Wir stellen Ihnen den vollständigen Quellcode zur Verfügung und zeigen Ihnen, wie Sie die Markdown-Ausgabe formatieren.

## Schritt 1: Dokumentinitialisierung

 Der erste Schritt besteht darin, das zu initialisieren`Document` Objekt durch Laden des Word-Dokuments, das die ActiveX-Steuerelemente enthält. Unbedingt ersetzen`MyDir` mit dem tatsächlichen Pfad zum Verzeichnis, das das Dokument enthält.

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## Schritt 2: ActiveX-Steuerelemente wiederherstellen

 In diesem Schritt werden wir jeden Schritt durchlaufen`Shape` des Dokuments, um die ActiveX-Steuerelemente abzurufen und ihre Eigenschaften zu lesen.

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

### Beispielquellcode zum Lesen von Active XControl-Eigenschaften mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Lesen von Eigenschaften von ActiveX-Steuerelementen mit Aspose.Words für .NET:

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

