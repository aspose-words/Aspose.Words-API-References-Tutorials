---
title: Kombinationsfeld-Formularfeld einfügen
linktitle: Kombinationsfeld-Formularfeld einfügen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Kombinationsfeld-Formularfelder in Word-Dokumente einfügen. Schritt für Schritt Anleitung.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/insert-combo-box-form-field/
---

In diesem umfassenden Beispiel erfahren Sie, wie Sie mit Aspose.Words für .NET ein Kombinationsfeld-Formularfeld in ein Word-Dokument einfügen. Wir führen Sie durch den Prozess und stellen Ihnen die notwendigen C#-Code-Snippets zur Verfügung. Am Ende dieser Anleitung werden Sie in der Lage sein, Ihren Dokumenten Kombinationsfeld-Formularfelder mit anpassbaren Eigenschaften hinzuzufügen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Aspose.Words für .NET-Bibliothek auf Ihrem System installiert.

## Schritt 1: Erstellen Sie ein neues Dokument und einen neuen DocumentBuilder
Erstellen Sie zunächst ein neues Dokument mit der Document-Klasse und initialisieren Sie ein DocumentBuilder-Objekt:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Kombinationsfeldelemente definieren
Als nächstes definieren Sie ein Array von Elementen für das Kombinationsfeld-Formularfeld:

```csharp
string[] items = { "One", "Two", "Three" };
```

## Schritt 3: Fügen Sie ein Kombinationsfeld-Formularfeld ein
Verwenden Sie die InsertComboBox-Methode der DocumentBuilder-Klasse, um ein Kombinationsfeld-Formularfeld einzufügen. Geben Sie den Namen, das Elementarray und den ausgewählten Index als Parameter an:

```csharp
builder.InsertComboBox("DropDown", items, 0);
```

## Schritt 4: Speichern Sie das Dokument
Nachdem Sie das Kombinationsfeld-Formularfeld eingefügt haben, speichern Sie das Dokument mit der Save-Methode der Document-Klasse in einer Datei:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertComboBoxFormField.docx");
```

### Beispielquellcode für das Formularfeld „Kombinationsfeld einfügen“ mit Aspose.Words für .NET
Hier ist der vollständige Quellcode zum Einfügen eines Kombinationsfeld-Formularfelds mit Aspose.Words für .NET:

```csharp

	string[] items = { "One", "Two", "Three" };

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertComboBox("DropDown", items, 0);

	doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertComboBoxFormField.docx");
	
```

Denken Sie daran, den Code an Ihre spezifischen Anforderungen anzupassen und ihn bei Bedarf um zusätzliche Funktionen zu erweitern.

## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Words für .NET ein Kombinationsfeld-Formularfeld in ein Word-Dokument einfügen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie Ihre Dokumente jetzt mit interaktiven Kombinationsfeld-Formularfeldern erweitern.
