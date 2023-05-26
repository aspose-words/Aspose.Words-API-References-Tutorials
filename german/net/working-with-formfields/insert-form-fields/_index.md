---
title: Formularfelder einfügen
linktitle: Formularfelder einfügen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Dropdown-Formularfelder in Word-Dokumente einfügen.
type: docs
weight: 10
url: /de/net/working-with-formfields/insert-form-fields/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET Formularfelder, insbesondere ein Dropdown-Formularfeld, in ein Word-Dokument einfügen. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

Stellen Sie zunächst sicher, dass Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und eingerichtet ist. Wenn Sie dies noch nicht getan haben, laden Sie die Bibliothek von der offiziellen Website herunter und installieren Sie sie.

## Schritt 1: Initialisieren der Document- und DocumentBuilder-Objekte

 Initialisieren Sie zunächst die`Document` Und`DocumentBuilder` Objekte:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Einfügen eines Dropdown-Formularfelds

 Geben Sie als Nächstes die Optionen für das Dropdown-Formularfeld an und fügen Sie es mithilfe von in das Dokument ein`InsertComboBox` Methode der`DocumentBuilder`Objekt. In diesem Beispiel fügen wir ein Dropdown-Formularfeld namens „DropDown“ mit drei Optionen ein: „Eins“, „Zwei“ und „Drei“:

```csharp
string[] items = { "One", "Two", "Three" };
builder.InsertComboBox("DropDown", items, 0);
```

## Schritt 3: Speichern des Dokuments

Speichern Sie abschließend das Dokument:

```csharp
doc.Save("OutputDocument.docx");
```

Das ist es! Sie haben mit Aspose.Words für .NET erfolgreich ein Dropdown-Formularfeld in ein Word-Dokument eingefügt.

### Beispielquellcode für das Einfügen von Formularfeldern mit Aspose.Words für .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

string[] items = { "One", "Two", "Three" };
builder.InsertComboBox("DropDown", items, 0);

doc.Save("OutputDocument.docx");
```

Sie können diesen Code gerne in Ihren eigenen Projekten verwenden und entsprechend Ihren spezifischen Anforderungen modifizieren.