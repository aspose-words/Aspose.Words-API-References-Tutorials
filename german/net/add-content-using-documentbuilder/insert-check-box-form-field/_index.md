---
title: Kontrollkästchen-Formularfeld einfügen
linktitle: Kontrollkästchen-Formularfeld einfügen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Kontrollkästchen-Formularfelder in Word-Dokumente einfügen. Schritt für Schritt Anleitung.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/insert-check-box-form-field/
---

In diesem umfassenden Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET ein Kontrollkästchen-Formularfeld in ein Word-Dokument einfügen. Wir führen Sie durch den Prozess und stellen Ihnen die notwendigen C#-Code-Snippets zur Verfügung. Am Ende dieses Leitfadens werden Sie in der Lage sein, Ihren Dokumenten Kontrollkästchen-Formularfelder mit anpassbaren Eigenschaften hinzuzufügen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Aspose.Words für .NET-Bibliothek auf Ihrem System installiert.

## Schritt 1: Erstellen Sie ein neues Dokument und einen neuen DocumentBuilder
Erstellen Sie zunächst ein neues Dokument mit der Document-Klasse und initialisieren Sie ein DocumentBuilder-Objekt:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Fügen Sie ein Kontrollkästchen-Formularfeld ein
Als nächstes verwenden Sie die Methode „InsertCheckBox“ der Klasse „DocumentBuilder“, um ein Kontrollkästchen-Formularfeld einzufügen. Geben Sie die Parameter Name, Prüfstatus, Standardstatus und Größe als Argumente an:

```csharp
builder.InsertCheckBox("CheckBox", true, true, 0);
```

## Schritt 3: Speichern Sie das Dokument
Nachdem Sie das Kontrollkästchen-Formularfeld eingefügt haben, speichern Sie das Dokument mit der Save-Methode der Document-Klasse in einer Datei:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
```

### Beispielquellcode für das Formularfeld „Kontrollkästchen einfügen“ mit Aspose.Words für .NET
Hier ist der vollständige Quellcode zum Einfügen eines Kontrollkästchen-Formularfelds mit Aspose.Words für .NET:

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertCheckBox("CheckBox", true, true, 0);

	doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
	
```

Denken Sie daran, den Code an Ihre spezifischen Anforderungen anzupassen und ihn bei Bedarf um zusätzliche Funktionen zu erweitern.

## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Words für .NET ein Kontrollkästchen-Formularfeld in ein Word-Dokument einfügen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie Ihre Dokumente jetzt mit interaktiven Kontrollkästchen-Formularfeldern erweitern.
