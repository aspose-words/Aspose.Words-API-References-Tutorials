---
title: Lesen Sie die ActiveXControl-Eigenschaften aus der Word-Datei
linktitle: Lesen Sie die ActiveXControl-Eigenschaften aus der Word-Datei
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Lesen Sie Eigenschaften von ActiveX-Steuerelementen in einer Word-Datei mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET Eigenschaften von ActiveX-Steuerelementen in einer Word-Datei lesen. Wir stellen Ihnen den vollständigen Quellcode zur Verfügung und zeigen Ihnen, wie Sie die Markdown-Ausgabe formatieren.

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

## Abschluss

In dieser Anleitung erfahren Sie, wie Sie mit Aspose.Words für .NET Eigenschaften von ActiveX-Steuerelementen in einer Word-Datei lesen. Indem Sie die beschriebenen Schritte befolgen, können Sie das Dokument initialisieren, ActiveX-Steuerelemente abrufen und deren Eigenschaften lesen. Nutzen Sie den bereitgestellten Beispielcode als Ausgangspunkt und passen Sie ihn an Ihre spezifischen Anforderungen an.

Durch das Lesen der Eigenschaften von ActiveX-Steuerelementen können Sie wichtige Informationen aus Ihren Word-Dateien extrahieren, die diese Steuerelemente enthalten. Aspose.Words für .NET bietet leistungsstarke Funktionen für die Textverarbeitung mit ActiveX-Steuerelementen und die Automatisierung Ihrer Dokumentverarbeitung.

### FAQs

#### F: Was ist der erste Schritt, um Eigenschaften von ActiveX-Steuerelementen in einer Word-Datei zu lesen?

 A: Der erste Schritt besteht darin, das zu initialisieren`Document` Objekt durch Laden des Word-Dokuments, das die ActiveX-Steuerelemente enthält. Unbedingt ersetzen`MyDir` mit dem tatsächlichen Pfad zum Verzeichnis, das das Dokument enthält.

#### F: Wie bekomme ich ActiveX-Steuerelemente in das Dokument?

 A: Um ActiveX-Steuerelemente abzurufen, müssen Sie jedes Element durchlaufen`Shape` des Dokuments und prüfen Sie, ob es sich um ein ActiveX-Steuerelement handelt. Benutzen Sie die`OleFormat` Eigentum von`Shape` um auf die zuzugreifen`OleControl` Objekt und rufen Sie die erforderlichen Eigenschaften ab.

#### F: Welche Eigenschaften von ActiveX-Steuerelementen kann ich lesen?

A: Sie können verschiedene Eigenschaften von ActiveX-Steuerelementen lesen, z. B. Beschriftung, Wert, aktivierter oder deaktivierter Status, Typ und dem Steuerelement zugeordnete untergeordnete Knoten.

#### F: Wie kann ich die Gesamtzahl der ActiveX-Steuerelemente im Dokument ermitteln?

 A: Um die Gesamtzahl der ActiveX-Steuerelemente im Dokument zu ermitteln, können Sie Folgendes verwenden`GetChildNodes` Methode der`Document` Objekt, das die angibt`NodeType.Shape` Typ und einschließlich der untergeordneten Knoten.