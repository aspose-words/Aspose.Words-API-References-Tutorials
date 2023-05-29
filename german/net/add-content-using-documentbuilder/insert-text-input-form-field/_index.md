---
title: Texteingabeformularfeld einfügen
linktitle: Texteingabeformularfeld einfügen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Words für .NET Texteingabeformularfelder in Word-Dokumente einfügen.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/insert-text-input-form-field/
---

In dieser Schritt-für-Schritt-Anleitung erfahren Sie, wie Sie die Funktion „Texteingabeformularfeld einfügen“ in Aspose.Words für .NET verwenden, um Texteingabeformularfelder in Ihren Word-Dokumenten mithilfe von C#-Quellcode hinzuzufügen und zu bearbeiten. Texteingabeformularfelder ermöglichen Benutzern die Eingabe von benutzerdefiniertem Text in ein Dokument und eignen sich daher ideal für die Erstellung interaktiver Formulare und Fragebögen. Wenn Sie die folgenden Anweisungen befolgen, können Sie mühelos Texteingabeformularfelder in Ihre Dokumente einfügen und anpassen. Lass uns anfangen!

## Einführung in die Funktion „Texteingabeformularfeld einfügen“ in Aspose.Words für .NET

Mit der Funktion „Texteingabeformularfeld einfügen“ in Aspose.Words für .NET können Sie Texteingabeformularfelder programmgesteuert zu Ihren Word-Dokumenten hinzufügen. Diese Formularfelder stellen ein interaktives Element dar, in das Benutzer benutzerdefinierten Text oder Daten eingeben können.

## Verständnis der Anforderungen für die Nutzung der Funktion

Bevor Sie mit der Implementierung fortfahren, stellen Sie sicher, dass Sie die folgenden Anforderungen erfüllen:

1. Aspose.Words für .NET-Bibliothek in Ihrem Projekt installiert.
2. Grundkenntnisse der Programmiersprache C#.
3. Ein vorhandenes Word-Dokument oder ein neues Dokument zum Einfügen des Texteingabeformularfelds.

Stellen Sie sicher, dass Sie über diese Voraussetzungen verfügen, um reibungslos vorgehen zu können.

## Schritt-für-Schritt-Anleitung zur Implementierung des Felds „Texteingabeformular einfügen“ mithilfe von C#-Quellcode

Führen Sie die folgenden Schritte aus, um die Funktion „Texteingabeformularfeld einfügen“ mithilfe des bereitgestellten C#-Quellcodes zu implementieren:

### Schritt 1: Initialisieren des Dokuments und des Dokument-Builders

Initialisieren Sie zunächst das Dokument und den Document Builder. Der Document Builder ist ein leistungsstarkes Tool von Aspose.Words für .NET, mit dem wir Word-Dokumente programmgesteuert erstellen und bearbeiten können. Verwenden Sie den folgenden Codeausschnitt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### Schritt 2: Einfügen des Texteingabeformularfelds

 Als nächstes fügen wir das Texteingabeformularfeld mithilfe von in das Dokument ein`InsertTextInput` Methode. Diese Methode akzeptiert verschiedene Parameter, darunter den Namen des Formularfelds, den Typ des Formularfelds (in diesem Fall`TextFormFieldType.Regular`), den Standardwert und die maximale Länge. Hier ist ein Beispiel:

```csharp
builder.InsertTextInput("TextInput", TextFormFieldType.Regular, "", "Hello", 0);
```

Der obige Code fügt ein Texteingabeformularfeld mit dem Namen „TextInput“, dem Standardwert „Hello“ und keiner maximalen Längenbeschränkung ein.

### Schritt 3: Speichern des Dokuments

 Nachdem Sie das Texteingabeformularfeld eingefügt haben, speichern Sie das Dokument mithilfe von am gewünschten Ort`Save` Methode. Stellen Sie sicher, dass Sie den richtigen Dateipfad angeben:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTextInputFormField.docx");
```

Dieser Code speichert das Dokument mit dem eingefügten Texteingabeformularfeld am angegebenen Ort.

### Beispielquellcode für „Texteingabeformularfeld einfügen“ mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertTextInput("TextInput", TextFormFieldType.Regular, "", "Hello", 0);

doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTextInputFormField.docx");
```
