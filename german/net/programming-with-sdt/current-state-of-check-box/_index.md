---
title: Kontrollkästchen „Aktueller Status“.
linktitle: Kontrollkästchen „Aktueller Status“.
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET den aktuellen Status eines Kontrollkästchen-Inhaltssteuerelements in einem Word-Dokument abrufen und festlegen.
type: docs
weight: 10
url: /de/net/programming-with-sdt/current-state-of-check-box/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET den aktuellen Status eines Kontrollkästchen-Inhaltssteuerelements in einem Word-Dokument abrufen und festlegen. Sie können das Kontrollkästchen je nach aktuellem Status aktivieren oder deaktivieren.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und der Arbeit mit Word-Dokumenten.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein
 Beginnen Sie mit der Einrichtung des Pfads zu Ihrem Dokumentenverzeichnis. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu dem Verzeichnis, in dem sich Ihr Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument und rufen Sie das Kontrollkästchen-Inhaltssteuerelement ab
 Laden Sie das Word-Dokument mit`Document` Konstruktor, der den Pfad zum Dokument als Parameter übergibt. Rufen Sie dann das gewünschte Kontrollkästcheninhaltssteuerelement aus dem Dokument ab. In diesem Beispiel gehen wir davon aus, dass das Kontrollkästchen das erste strukturierte Dokument-Tag im Dokument ist.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Schritt 3: Aktivieren oder deaktivieren Sie das Kontrollkästchen je nach aktuellem Status
 Überprüfen Sie, ob das abgerufene Tag des strukturierten Dokuments vom Typ ist`SdtType.Checkbox` . Wenn ja, stellen Sie die ein`Checked` Eigenschaft des Inhaltssteuerelements`true` um das Kästchen anzukreuzen. Andernfalls können Sie es deaktiviert lassen.

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## Schritt 4: Speichern Sie das Dokument
 Speichern Sie das geänderte Dokument mit im angegebenen Verzeichnis`Save`Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithSdt.CurrentStateOfCheckBox.docx“.

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### Beispielquellcode für den aktuellen Status des Kontrollkästchens mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	// Holen Sie sich das erste Inhaltssteuerelement aus dem Dokument.
	StructuredDocumentTag sdtCheckBox =
		(StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	if (sdtCheckBox.SdtType == SdtType.Checkbox)
		sdtCheckBox.Checked = true;
	doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

Das ist es! Sie haben den aktuellen Status eines Kontrollkästchen-Inhaltssteuerelements in Ihrem Word-Dokument mit Aspose.Words für .NET erfolgreich abgerufen und festgelegt.