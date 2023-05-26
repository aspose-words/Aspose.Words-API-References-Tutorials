---
title: Nur den Schutz von Formularfeldern zulassen
linktitle: Nur den Schutz von Formularfeldern zulassen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Dokumente schützen und nur die Bearbeitung von Formularfeldern zulassen.
type: docs
weight: 10
url: /de/net/document-protection/allow-only-form-fields-protect/
---

Der Dokumentenschutz ist eine wesentliche Funktion beim Arbeiten mit Dateien in Ihrer C#-Anwendung. Mit der Aspose.Words-Bibliothek für .NET können Sie Ihre Dokumente einfach schützen und nur die Bearbeitung von Formularfeldern zulassen. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch die Verwendung von C#-Quellcode, um nur die Bearbeitung von Formularfeldern mithilfe der Funktion „Nur Formularfelder schützen“ von Aspose.Words für .NET zuzulassen.

## Schritt 1: Festlegen des Dokumentenverzeichnisses

Der erste Schritt besteht darin, das Verzeichnis Ihres Dokuments zu definieren. Sie müssen den Pfad angeben, in dem Sie das geschützte Dokument speichern möchten. Zum Beispiel :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTENVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis ersetzen.

## Schritt 2: Abschnitte und Text einfügen

Als nächstes müssen Sie Abschnitte und Text in Ihr Dokument einfügen. Verwenden Sie die von Aspose.Words bereitgestellte DocumentBuilder-Klasse, um den Inhalt Ihres Dokuments zu erstellen. Hier ist ein einfaches Beispiel:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

In diesem Beispiel erstellen wir ein neues leeres Dokument und fügen dann mit DocumentBuilder eine Textzeile hinzu.

## Schritt 3: Dokumentenschutz aktivieren

 Der Dokumentenschutz funktioniert nur, wenn der Dokumentenschutz aktiviert ist. Sie können den Dokumentenschutz mit aktivieren`Protect` Methode der Document-Klasse. Hier ist wie:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

In diesem Beispiel aktivieren wir den Dokumentenschutz durch Angabe des Schutztyps „

AllowOnlyFormFields` und Festlegen eines Passworts.

## Schritt 4: Nur Formularfelder zulassen

Nachdem der Dokumentenschutz nun aktiviert ist, müssen wir festlegen, dass nur die Bearbeitung von Formularfeldern zulässig ist. Dadurch wird sichergestellt, dass Benutzer nur Teile des Dokuments bearbeiten können, die Formularfelder sind. Hier ist wie:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Ersetzen Sie „Passwort“ unbedingt durch das zuvor festgelegte Passwort.

## Schritt 5: Speichern des geschützten Dokuments

Abschließend können Sie das geschützte Dokument mit speichern`Save` Methode der Document-Klasse. Geben Sie den vollständigen Dateipfad und den gewünschten Dateinamen an. Zum Beispiel :

```csharp
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

Ersetzen Sie „dataDir“ unbedingt durch den Pfad zu Ihrem Dokumentverzeichnis.

### Beispielquellcode für die Funktion „Nur Formularfelder zulassen“ mit Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Fügen Sie zwei Abschnitte mit etwas Text ein.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// Ein Dokumentenschutz funktioniert nur, wenn der Dokumentenschutz aktiviert ist und nur die Bearbeitung in Formularfeldern erlaubt ist.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// Speichern Sie das geschützte Dokument.
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

## Abschluss

In diesem Leitfaden haben wir untersucht, wie Sie die Aspose.Words-Bibliothek für .NET verwenden, um ein Dokument zu schützen und nur die Bearbeitung von Formularfeldern zuzulassen. Wenn Sie die bereitgestellten Schritte befolgen, können Sie diese Funktionalität problemlos in Ihrer C#-Anwendung implementieren. Dokumentenschutz ist unerlässlich, um die Sicherheit und Vertraulichkeit Ihrer Dokumente zu gewährleisten.
