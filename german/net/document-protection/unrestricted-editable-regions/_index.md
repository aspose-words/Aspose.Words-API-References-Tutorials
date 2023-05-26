---
title: Unbegrenzt bearbeitbare Bereiche
linktitle: Unbegrenzt bearbeitbare Bereiche
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET uneingeschränkt bearbeitbare Bereiche in einem Word-Dokument erstellen.
type: docs
weight: 10
url: /de/net/document-protection/unrestricted-editable-regions/
---

In diesem Tutorial führen wir Sie durch die Schritte zur Nutzung der Funktion „uneingeschränkt bearbeitbare Bereiche“ von Aspose.Words für .NET. Mit dieser Funktion können Sie Bereiche in einem Word-Dokument definieren, in denen Inhalte uneingeschränkt bearbeitet werden können, auch wenn der Rest des Dokuments schreibgeschützt ist. Folgen Sie den unteren Schritten:

## Schritt 1: Dokument laden und Schutz einstellen

Laden Sie zunächst das vorhandene Dokument:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
doc.Protect(ProtectionType.ReadOnly, "MyPassword");
```

Schützen Sie das Dokument, indem Sie den schreibgeschützten Schutztyp und das Kennwort festlegen

## Schritt 2: Einen bearbeitbaren Bereich erstellen

Erstellen Sie zunächst einen bearbeitbaren Bereich mit den Objekten EditableRangeStart und EditableRangeEnd:

```csharp
EditableRangeStart edRangeStart = builder.StartEditableRange();
// Für den soeben erstellten EditableRangeStart wird ein EditableRange-Objekt erstellt.
EditableRange editableRange = edRangeStart.EditableRange;

// Platzieren Sie etwas innerhalb des bearbeitbaren Bereichs.
builder.Writeln("Paragraph inside first editable range");

// Ein bearbeitbarer Bereich ist wohlgeformt, wenn er einen Anfang und ein Ende hat.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

```

## Schritt 3: Fügen Sie Inhalte außerhalb der bearbeitbaren Bereiche hinzu

Sie können Inhalte außerhalb der bearbeitbaren Bereiche hinzufügen, die dann schreibgeschützt bleiben:

```csharp
builder.Writeln("This paragraph is outside of all editable areas and cannot be edited.");
```

## Schritt 4: Speichern Sie das Dokument

Speichern Sie abschließend das geänderte Dokument:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen angeben, um das Dokument mit bearbeitbaren Bereichen zu speichern.

### Beispielquellcode für uneingeschränkt bearbeitbare Regionen mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für uneingeschränkt bearbeitbare Bereiche mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Laden Sie ein Dokument hoch und machen Sie es schreibgeschützt.
	Document doc = new Document(MyDir + "Document.docx");
	DocumentBuilder builder = new DocumentBuilder(doc);

	doc.Protect(ProtectionType.ReadOnly, "MyPassword");

	builder.Writeln("Hello world! Since we have set the document's protection level to read-only, " + "we cannot edit this paragraph without the password.");

	// Starten Sie einen bearbeitbaren Bereich.
	EditableRangeStart edRangeStart = builder.StartEditableRange();
	// Für den soeben erstellten EditableRangeStart wird ein EditableRange-Objekt erstellt.
	EditableRange editableRange = edRangeStart.EditableRange;

	// Platzieren Sie etwas innerhalb des bearbeitbaren Bereichs.
	builder.Writeln("Paragraph inside first editable range");

	// Ein bearbeitbarer Bereich ist wohlgeformt, wenn er einen Anfang und ein Ende hat.
	EditableRangeEnd edRangeEnd = builder.EndEditableRange();

	builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

	doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");

```
Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET ganz einfach uneingeschränkt bearbeitbare Bereiche in Ihrem Word-Dokument erstellen.


