---
title: Active XControl-Eigenschaften aus Word-Datei lesen
linktitle: Active XControl-Eigenschaften aus Word-Datei lesen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Lesen Sie Eigenschaften von ActiveX-Steuerelementen in einer Word-Datei mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET Eigenschaften von ActiveX-Steuerelementen in einer Word-Datei lesen. Wir stellen Ihnen den vollständigen Quellcode zur Verfügung und zeigen Ihnen, wie Sie die Markdown-Ausgabe formatieren.

## Schritt 1: Dokumentinitialisierung

 Der erste Schritt besteht in der Initialisierung des`Document` Objekt, indem Sie das Word-Dokument mit den ActiveX-Steuerelementen laden. Ersetzen Sie unbedingt`MyDir` durch den tatsächlichen Pfad zum Verzeichnis, das das Dokument enthält.

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## Schritt 2: ActiveX-Steuerelemente wiederherstellen

 In diesem Schritt durchlaufen wir jeden`Shape` des Dokuments, um die ActiveX-Steuerelemente abzurufen und ihre Eigenschaften zu lesen.

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

Hier ist der vollständige Quellcode zum Lesen der Eigenschaften von ActiveX-Steuerelementen mit Aspose.Words für .NET:

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

In dieser Anleitung wurde gezeigt, wie Sie mit Aspose.Words für .NET Eigenschaften von ActiveX-Steuerelementen in einer Word-Datei lesen. Indem Sie die beschriebenen Schritte befolgen, können Sie das Dokument initialisieren, ActiveX-Steuerelemente abrufen und deren Eigenschaften lesen. Verwenden Sie den bereitgestellten Beispielcode als Ausgangspunkt und passen Sie ihn an Ihre spezifischen Anforderungen an.

Durch das Lesen der Eigenschaften von ActiveX-Steuerelementen können Sie wichtige Informationen aus Ihren Word-Dateien extrahieren, die diese Steuerelemente enthalten. Aspose.Words für .NET bietet leistungsstarke Funktionen für die Textverarbeitung mit ActiveX-Steuerelementen und die Automatisierung Ihrer Dokumentverarbeitung.

### FAQs

#### F: Was ist der erste Schritt zum Lesen der Eigenschaften von ActiveX-Steuerelementen in einer Word-Datei?

 A: Der erste Schritt besteht in der Initialisierung des`Document` Objekt, indem Sie das Word-Dokument mit den ActiveX-Steuerelementen laden. Ersetzen Sie unbedingt`MyDir` durch den tatsächlichen Pfad zum Verzeichnis, das das Dokument enthält.

#### F: Wie bekomme ich ActiveX-Steuerelemente in das Dokument?

 A: Um ActiveX-Steuerelemente abzurufen, müssen Sie jedes`Shape` des Dokuments und prüfen Sie, ob es sich um ein ActiveX-Steuerelement handelt. Verwenden Sie die`OleFormat` Eigentum von`Shape` für den Zugriff auf die`OleControl` -Objekt und rufen Sie die erforderlichen Eigenschaften ab.

#### F: Welche Eigenschaften von ActiveX-Steuerelementen kann ich lesen?

A: Sie können verschiedene Eigenschaften von ActiveX-Steuerelementen lesen, z. B. Überschrift, Wert, aktivierter oder deaktivierter Status, Typ und mit dem Steuerelement verknüpfte untergeordnete Knoten.

#### F: Wie kann ich die Gesamtzahl der ActiveX-Steuerelemente im Dokument ermitteln?

 A: Um die Gesamtzahl der ActiveX-Steuerelemente im Dokument zu ermitteln, können Sie den`GetChildNodes` Methode der`Document` Objekt, das die`NodeType.Shape` Typ und einschließlich der untergeordneten Knoten.