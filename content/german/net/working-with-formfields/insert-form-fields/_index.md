---
title: Formularfelder einfügen
linktitle: Formularfelder einfügen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Dropdown-Formularfelder in Word-Dokumente einfügen.
type: docs
weight: 10
url: /de/net/working-with-formfields/insert-form-fields/
---

In diesem Schritt-für-Schritt-Tutorial zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET Formularfelder, insbesondere ein Dropdown-Formularfeld, in ein Word-Dokument einfügen. Wir erklären den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

 Stellen Sie zunächst sicher, dass Sie Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und eingerichtet haben. Wenn Sie dies noch nicht getan haben, laden Sie die Bibliothek herunter und installieren Sie sie von[[Originaltext von Aspose.Releases]https://releases.aspose.com/words/net/.

## Schritt 1: Initialisieren der Document- und DocumentBuilder-Objekte

 Initialisieren Sie zunächst den`Document` Und`DocumentBuilder` Objekte:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Einfügen eines Dropdown-Formularfelds

 Geben Sie als nächstes die Optionen für das Dropdown-Formularfeld an und fügen Sie es mit dem`InsertComboBox` Methode der`DocumentBuilder` Objekt. In diesem Beispiel fügen wir ein Dropdown-Formularfeld namens „DropDown“ mit drei Optionen ein: „Eins“, „Zwei“ und „Drei“:

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

### Beispielquellcode zum Einfügen von Formularfeldern mit Aspose.Words für .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

string[] items = { "One", "Two", "Three" };
builder.InsertComboBox("DropDown", items, 0);

doc.Save("OutputDocument.docx");
```

Sie können diesen Code gerne in Ihren eigenen Projekten verwenden und ihn entsprechend Ihren spezifischen Anforderungen ändern.

### Häufig gestellte Fragen

#### F: Wie kann ich in Aspose.Words ein Formularfeld vom Typ „Text“ einfügen?

 A: Um ein Textformularfeld in Aspose.Words einzufügen, können Sie das`FormField` Klasse und legen Sie deren`Type`Eigentum an`FormFieldType.Text`. Sie können auch andere Eigenschaften wie Name, Bezeichnung und Optionen anpassen.

#### F: Ist es möglich, in einem Dokument ein Formularfeld vom Typ „Kontrollkästchen“ zu erstellen?

 A: Ja, es ist möglich, ein Kontrollkästchen-Formularfeld in einem Aspose.Words-Dokument zu erstellen. Sie können das`FormField` Klasse und legen Sie deren`Type`Eigentum an`FormFieldType.CheckBox` , um ein Kontrollkästchen zu erstellen. Anschließend können Sie die Eigenschaften des Kontrollkästchens nach Bedarf anpassen.

#### F: Wie kann ich einem Dokument ein Dropdown-Formularfeld hinzufügen?

 A: Um ein Dropdown-Formularfeld in ein Aspose.Words-Dokument einzufügen, verwenden Sie die`FormField` Klasse und legen Sie deren`Type`Eigentum an`FormFieldType.DropDown` Sie können dann die Dropdown-Optionen mit dem`DropDownItems` Eigentum.

#### F: Kann ich in Aspose.Words einen Standardwert für ein Formularfeld festlegen?

A: Ja, Sie können einen Standardwert für ein Formularfeld in Aspose.Words festlegen. Verwenden Sie die`FormField.Result` -Eigenschaft, um den Anfangswert des Formularfelds festzulegen.

#### F: Wie kann ich in Formularfeldern in Aspose.Words eingegebene Daten abrufen?

 A: Um Daten abzurufen, die in Formularfeldern in Aspose.Words eingegeben wurden, können Sie das`FormField.Result` Eigenschaft, die den vom Benutzer eingegebenen Wert enthält. Sie können auf diese Eigenschaft für jedes Formularfeld in Ihrem Dokument zugreifen.