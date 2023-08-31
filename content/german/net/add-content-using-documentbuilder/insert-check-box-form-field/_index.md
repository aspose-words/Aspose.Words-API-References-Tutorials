---
title: Kontrollkästchen-Formularfeld in Word-Dokument einfügen
linktitle: Kontrollkästchen-Formularfeld in Word-Dokument einfügen
second_title: Aspose.Words-Dokumentverarbeitungs-API
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

### FAQs

#### F: Kann ich mehrere Kontrollkästchen-Formularfelder in ein einzelnes Dokument einfügen?

A: Auf jeden Fall! Mit Aspose.Words für .NET können Sie beliebig viele Kontrollkästchen-Formularfelder in ein Word-Dokument einfügen. Wiederholen Sie einfach den Einfügevorgang, um mehrere interaktive Kontrollkästchen hinzuzufügen.

#### F: Kann ich den Anfangszustand (aktiviert oder deaktiviert) des Kontrollkästchen-Formularfelds festlegen?

A: Ja, Sie haben die volle Kontrolle über den Anfangszustand des Kontrollkästchen-Formularfelds. Indem Sie den Parameter „Checked State“ auf „True“ oder „False“ setzen, können Sie festlegen, ob das Kontrollkästchen zunächst aktiviert oder deaktiviert ist.

#### F: Sind Kontrollkästchen-Formularfelder mit anderen Dateiformaten wie PDF kompatibel?

A: Ja, mit Aspose.Words für .NET eingefügte Kontrollkästchen-Formularfelder sind mit verschiedenen Dateiformaten kompatibel, einschließlich DOCX und PDF. Dadurch können Sie Ihre Dokumente in verschiedenen Formaten exportieren und dabei die interaktiven Kontrollkästchen beibehalten.

#### F: Kann ich die Größe des Kontrollkästchen-Formularfelds anpassen?

A: Auf jeden Fall! Sie können die Größe des Kontrollkästchen-Formularfelds mithilfe des Größenparameters in der InsertCheckBox-Methode angeben. Dadurch können Sie die Abmessungen des Kontrollkästchens entsprechend Ihren Designvorlieben steuern.

#### F: Ist Aspose.Words für .NET sowohl für Desktop- als auch für Webanwendungen geeignet?

A: Ja, Aspose.Words für .NET ist eine vielseitige Bibliothek, die sowohl für Desktop- als auch für Webanwendungen geeignet ist. Unabhängig davon, ob Sie eine Windows-Anwendung oder ein webbasiertes System erstellen, können Sie die Bibliothek mühelos integrieren.