---
title: Aktueller Status des Kontrollkästchens
linktitle: Aktueller Status des Kontrollkästchens
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET den aktuellen Status eines Kontrollkästchen-Inhaltssteuerelements in einem Word-Dokument abrufen und festlegen.
type: docs
weight: 10
url: /de/net/programming-with-sdt/current-state-of-check-box/
---

In diesem Tutorial wird erläutert, wie Sie den aktuellen Status eines Kontrollkästchen-Inhaltssteuerelements in einem Word-Dokument mithilfe von Aspose.Words für .NET abrufen und festlegen. Sie können das Kontrollkästchen basierend auf seinem aktuellen Status aktivieren oder deaktivieren.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Einrichten des Dokumentverzeichnisses
 Beginnen Sie mit der Einrichtung des Pfades zu Ihrem Dokumentverzeichnis. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zum Verzeichnis, in dem sich Ihr Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument und rufen Sie das Kontrollkästchen-Inhaltssteuerelement ab.
 Laden Sie das Word-Dokument mit dem`Document` Konstruktor, wobei der Pfad zum Dokument als Parameter übergeben wird. Rufen Sie dann das gewünschte Kontrollkästchen-Inhaltssteuerelement aus dem Dokument ab. In diesem Beispiel gehen wir davon aus, dass das Kontrollkästchen das erste strukturierte Dokument-Tag im Dokument ist.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Schritt 3: Aktivieren oder deaktivieren Sie das Kontrollkästchen basierend auf seinem aktuellen Status
 Überprüfen Sie, ob das abgerufene strukturierte Dokument-Tag vom Typ ist`SdtType.Checkbox` . Wenn dies der Fall ist, stellen Sie die`Checked` Eigenschaft des Inhaltssteuerelements auf`true` , um das Kontrollkästchen zu aktivieren. Andernfalls können Sie es deaktiviert lassen.

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## Schritt 4: Speichern Sie das Dokument
 Speichern Sie das geänderte Dokument im angegebenen Verzeichnis mit dem`Save`Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithSdt.CurrentStateOfCheckBox.docx“.

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### Beispielquellcode für „Current State Of Check Box“ mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	// Holen Sie sich das erste Inhaltssteuerelement aus dem Dokument.
	StructuredDocumentTag sdtCheckBox =
		(StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	if (sdtCheckBox.SdtType == SdtType.Checkbox)
		sdtCheckBox.Checked = true;
	doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

Das ist es! Sie haben den aktuellen Status eines Kontrollkästchen-Inhaltssteuerelements in Ihrem Word-Dokument erfolgreich mit Aspose.Words für .NET abgerufen und festgelegt.