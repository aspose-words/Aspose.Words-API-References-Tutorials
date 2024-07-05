---
title: Unbeschränkt bearbeitbare Bereiche im Word-Dokument
linktitle: Unbeschränkt bearbeitbare Bereiche im Word-Dokument
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET uneingeschränkt bearbeitbare Bereiche in einem Word-Dokument erstellen.
type: docs
weight: 10
url: /de/net/document-protection/unrestricted-editable-regions/
---
In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der Funktion für uneingeschränkt bearbeitbare Bereiche von Aspose.Words für .NET. Mit dieser Funktion können Sie Bereiche in einem Word-Dokument definieren, in denen Inhalte ohne Einschränkung bearbeitet werden können, auch wenn der Rest des Dokuments schreibgeschützt ist. Befolgen Sie die folgenden Schritte:

## Schritt 1: Dokument laden und Schutz einrichten

Beginnen Sie mit dem Laden des vorhandenen Dokuments:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
doc.Protect(ProtectionType.ReadOnly, "MyPassword");
```

Schützen Sie das Dokument, indem Sie den Schreibschutztyp und das Kennwort festlegen.

## Schritt 2: Editierbaren Bereich erstellen

Beginnen Sie mit der Erstellung eines bearbeitbaren Bereichs mithilfe der Objekte EditableRangeStart und EditableRangeEnd:

```csharp
EditableRangeStart edRangeStart = builder.StartEditableRange();
// Für den gerade erstellten EditableRangeStart wird ein EditableRange-Objekt erstellt.
EditableRange editableRange = edRangeStart.EditableRange;

// Platzieren Sie etwas innerhalb des bearbeitbaren Bereichs.
builder.Writeln("Paragraph inside first editable range");

// Ein editierbarer Bereich ist wohlgeformt, wenn er einen Anfang und ein Ende hat.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

```

## Schritt 3: Inhalte außerhalb der bearbeitbaren Bereiche hinzufügen

Sie können Inhalte außerhalb der bearbeitbaren Bereiche hinzufügen, die schreibgeschützt bleiben:

```csharp
builder.Writeln("This paragraph is outside of all editable areas and cannot be edited.");
```

## Schritt 4: Speichern Sie das Dokument

Speichern Sie abschließend das geänderte Dokument:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
```

Geben Sie unbedingt den richtigen Pfad und Dateinamen an, um das Dokument mit bearbeitbaren Bereichen zu speichern.

### Beispielquellcode für uneingeschränkt editierbare Regionen mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für uneingeschränkt editierbare Bereiche mit Aspose.Words für .NET:

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Laden Sie ein Dokument hoch und machen Sie es schreibgeschützt.
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

doc.Protect(ProtectionType.ReadOnly, "MyPassword");

builder.Writeln("Hello world! Since we have set the document's protection level to read-only, " + "we cannot edit this paragraph without the password.");

// Starten Sie einen bearbeitbaren Bereich.
EditableRangeStart edRangeStart = builder.StartEditableRange();
// Für den gerade erstellten EditableRangeStart wird ein EditableRange-Objekt erstellt.
EditableRange editableRange = edRangeStart.EditableRange;

// Platzieren Sie etwas innerhalb des bearbeitbaren Bereichs.
builder.Writeln("Paragraph inside first editable range");

// Ein editierbarer Bereich ist wohlgeformt, wenn er einen Anfang und ein Ende hat.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");

```
Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET ganz einfach uneingeschränkt bearbeitbare Bereiche in Ihrem Word-Dokument erstellen.

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET uneingeschränkt bearbeitbare Bereiche in einem Word-Dokument erstellt. Indem Sie die angegebenen Schritte befolgen, können Sie bestimmte Bereiche innerhalb des Dokuments definieren, in denen Benutzer den Inhalt frei bearbeiten können, während der Rest des Dokuments schreibgeschützt bleibt. Aspose.Words für .NET bietet leistungsstarke Funktionen zum Schutz und zur Anpassung von Dokumenten und gibt Ihnen Kontrolle über die Bearbeitungsmöglichkeiten Ihrer Word-Dokumente.

### FAQs zu uneingeschränkt bearbeitbaren Bereichen in Word-Dokumenten

#### F: Was sind uneingeschränkt editierbare Bereiche in Aspose.Words für .NET?

A: Unbeschränkt bearbeitbare Bereiche in Aspose.Words für .NET sind Bereiche innerhalb eines Word-Dokuments, in denen Inhalte ohne Einschränkungen bearbeitet werden können, selbst wenn der Rest des Dokuments schreibgeschützt ist. Diese Bereiche bieten eine Möglichkeit, bestimmte Teile des Dokuments zu definieren, die Benutzer ändern können, während der allgemeine Dokumentschutz erhalten bleibt.

#### F: Wie kann ich mit Aspose.Words für .NET uneingeschränkt bearbeitbare Bereiche erstellen?

A: Um mit Aspose.Words für .NET uneingeschränkt bearbeitbare Bereiche in einem Word-Dokument zu erstellen, können Sie die folgenden Schritte ausführen:
1.  Laden Sie das vorhandene Dokument mit dem`Document` Klasse.
2.  Setzen Sie den Dokumentschutz auf schreibgeschützt mit dem`Protect` Methode der`Document` Objekt.
3.  Verwenden Sie die`DocumentBuilder` Klasse, um einen editierbaren Bereich zu erstellen, indem Sie ein`EditableRangeStart` Objekt und ein`EditableRangeEnd` Objekt.
4.  Fügen Sie Inhalt innerhalb des editierbaren Bereichs hinzu, indem Sie die`DocumentBuilder`.
5.  Speichern Sie das geänderte Dokument mit dem`Save` Methode der`Document` Objekt.

#### F: Kann ich in einem Word-Dokument mehrere uneingeschränkt bearbeitbare Bereiche haben?

A: Ja, Sie können mehrere uneingeschränkt bearbeitbare Bereiche in einem Word-Dokument haben. Um dies zu erreichen, können Sie mehrere Sätze von`EditableRangeStart` Und`EditableRangeEnd` Objekte mit dem`DocumentBuilder` Klasse. Jeder Objektsatz definiert einen separaten bearbeitbaren Bereich, in dem Benutzer den Inhalt ohne Einschränkungen ändern können.

#### F: Kann ich bearbeitbare Bereiche ineinander verschachteln?

 A: Nein, Sie können editierbare Bereiche nicht ineinander verschachteln, wenn Sie Aspose.Words für .NET verwenden. Jeder editierbare Bereich, der durch ein`EditableRangeStart` Und`EditableRangeEnd` Paar sollte unabhängig sein und darf sich nicht überlappen oder in einem anderen bearbeitbaren Bereich verschachtelt sein. Verschachtelte bearbeitbare Bereiche werden nicht unterstützt.

#### F: Kann ich den schreibgeschützten Schutz des Dokuments innerhalb eines bearbeitbaren Bereichs entfernen?

A: Nein, Sie können den Nur-Lese-Schutz des Dokuments innerhalb eines bearbeitbaren Bereichs nicht entfernen. Der Nur-Lese-Schutz wird auf das gesamte Dokument angewendet und kann nicht selektiv innerhalb bestimmter bearbeitbarer Bereiche entfernt werden. Der Zweck der bearbeitbaren Bereiche besteht darin, Inhaltsänderungen zu ermöglichen, während das gesamte Dokument schreibgeschützt bleibt.