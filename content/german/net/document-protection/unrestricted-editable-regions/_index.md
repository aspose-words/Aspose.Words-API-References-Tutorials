---
title: Unbegrenzt bearbeitbare Bereiche im Word-Dokument
linktitle: Unbegrenzt bearbeitbare Bereiche im Word-Dokument
second_title: Aspose.Words-Dokumentverarbeitungs-API
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

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET uneingeschränkt bearbeitbare Bereiche in einem Word-Dokument erstellt. Indem Sie die bereitgestellten Schritte befolgen, können Sie bestimmte Bereiche innerhalb des Dokuments definieren, in denen Benutzer den Inhalt frei bearbeiten können, während der Rest des Dokuments schreibgeschützt bleibt. Aspose.Words für .NET bietet leistungsstarke Funktionen zum Schutz und zur Anpassung von Dokumenten und gibt Ihnen die Kontrolle über die Bearbeitungsmöglichkeiten Ihrer Word-Dokumente.

### FAQs zu uneingeschränkt bearbeitbaren Bereichen in Word-Dokumenten

#### F: Was sind uneingeschränkt bearbeitbare Bereiche in Aspose.Words für .NET?

A: Unbeschränkt bearbeitbare Bereiche in Aspose.Words für .NET sind Bereiche innerhalb eines Word-Dokuments, in denen Inhalte ohne Einschränkungen bearbeitet werden können, selbst wenn der Rest des Dokuments schreibgeschützt ist. Diese Bereiche bieten eine Möglichkeit, bestimmte Teile des Dokuments zu definieren, die Benutzer ändern können, während der allgemeine Dokumentschutz erhalten bleibt.

#### F: Wie kann ich mit Aspose.Words für .NET uneingeschränkt bearbeitbare Bereiche erstellen?

A: Um mit Aspose.Words für .NET uneingeschränkt bearbeitbare Bereiche in einem Word-Dokument zu erstellen, können Sie die folgenden Schritte ausführen:
1.  Laden Sie das vorhandene Dokument mit`Document` Klasse.
2.  Stellen Sie den Dokumentschutz mithilfe von auf schreibgeschützt ein`Protect` Methode der`Document` Objekt.
3.  Benutzen Sie die`DocumentBuilder` Klasse zum Erstellen eines bearbeitbaren Bereichs durch Hinzufügen einer`EditableRangeStart` Objekt und ein`EditableRangeEnd` Objekt.
4.  Fügen Sie mithilfe von Inhalte innerhalb des bearbeitbaren Bereichs hinzu`DocumentBuilder`.
5.  Speichern Sie das geänderte Dokument mit`Save` Methode der`Document` Objekt.

#### F: Kann ich in einem Word-Dokument mehrere uneingeschränkt bearbeitbare Bereiche haben?

A: Ja, Sie können in einem Word-Dokument mehrere uneingeschränkt bearbeitbare Bereiche haben. Um dies zu erreichen, können Sie mehrere Sätze erstellen`EditableRangeStart` Und`EditableRangeEnd` Objekte mit der`DocumentBuilder` Klasse. Jeder Objektsatz definiert einen separaten bearbeitbaren Bereich, in dem Benutzer den Inhalt ohne Einschränkungen ändern können.

#### F: Kann ich bearbeitbare Bereiche ineinander verschachteln?

 A: Nein, Sie können mit Aspose.Words für .NET keine bearbeitbaren Bereiche ineinander verschachteln. Jeder bearbeitbare Bereich, der durch eine definiert ist`EditableRangeStart` Und`EditableRangeEnd` Das Paar sollte unabhängig sein und sich nicht überlappen oder in einem anderen bearbeitbaren Bereich verschachtelt sein. Verschachtelte bearbeitbare Bereiche werden nicht unterstützt.

#### F: Kann ich den Leseschutz aus dem Dokument innerhalb eines bearbeitbaren Bereichs entfernen?

A: Nein, Sie können den Leseschutz des Dokuments innerhalb eines bearbeitbaren Bereichs nicht entfernen. Der Leseschutz wird auf das gesamte Dokument angewendet und kann nicht selektiv innerhalb bestimmter bearbeitbarer Bereiche entfernt werden. Der Zweck der bearbeitbaren Bereiche besteht darin, die Änderung von Inhalten zu ermöglichen und gleichzeitig das gesamte Dokument schreibgeschützt zu halten.