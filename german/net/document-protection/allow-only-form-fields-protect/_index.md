---
title: Nur den Schutz von Formularfeldern im Word-Dokument zulassen
linktitle: Nur den Schutz von Formularfeldern im Word-Dokument zulassen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie Aspose.Words für .NET verwenden, um Word-Dokumente zu schützen und nur die Bearbeitung von Formularfeldern zuzulassen.
type: docs
weight: 10
url: /de/net/document-protection/allow-only-form-fields-protect/
---
Der Dokumentenschutz ist eine wesentliche Funktion bei der Textverarbeitung mit Dateien in Ihrer C#-Anwendung. Mit der Aspose.Words-Bibliothek für .NET können Sie Ihre Dokumente einfach schützen und nur die Bearbeitung von Formularfeldern zulassen. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch die Verwendung von C#-Quellcode, um nur die Bearbeitung von Formularfeldern mithilfe der Funktion „Nur Formularfelder schützen“ von Aspose.Words für .NET zuzulassen.

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

### FAQs zum Schutz nur von Formularfeldern in Word-Dokumenten

#### F: Was ist Dokumentenschutz in Aspose.Words für .NET?

A: Der Dokumentenschutz in Aspose.Words für .NET ist eine Funktion, mit der Sie Ihre Dokumente schützen können, indem Sie bestimmte Aktionen wie Bearbeitung, Formatierung oder Inhaltsänderung einschränken. Es trägt dazu bei, die Integrität und Vertraulichkeit Ihrer Dokumente zu wahren, indem es unbefugte Änderungen verhindert.

#### F: Wie kann ich ein Dokument schützen und zulassen, dass nur Formularfelder mit Aspose.Words für .NET bearbeitet werden?

A: Um ein Dokument zu schützen und nur die Bearbeitung von Formularfeldern mit Aspose.Words für .NET zuzulassen, können Sie die folgenden Schritte ausführen:
1. Definieren Sie den Verzeichnispfad für Ihr Dokument.
2.  Fügen Sie mit dem Abschnitte und Text in Ihr Dokument ein`DocumentBuilder` Klasse.
3.  Aktivieren Sie den Dokumentenschutz mithilfe von`Protect` Methode der`Document` Klasse, Angabe des Schutztyps als`AllowOnlyFormFields` und Bereitstellung eines Passworts.
4.  Speichern Sie das geschützte Dokument mit`Save` Methode der`Document` Klasse.

#### F: Kann ich mit Aspose.Words für .NET Formularfelder in ein geschütztes Dokument einfügen?

A: Ja, Sie können Formularfelder mit Aspose.Words für .NET in ein geschütztes Dokument einfügen. Der Dokumentenschutz mit dem`AllowOnlyFormFields` Mit diesem Typ können Benutzer nur die Formularfelder bearbeiten und gleichzeitig den restlichen Inhalt des Dokuments schützen. Du kannst den ... benutzen`DocumentBuilder` Klasse, um Formularfelder in das Dokument einzufügen, bevor der Schutz aktiviert wird.

#### F: Kann ich den Dokumentschutz von einem geschützten Dokument entfernen?

 A: Ja, Sie können den Dokumentschutz von einem geschützten Dokument mit Aspose.Words für .NET entfernen. Um den Schutz zu entfernen, können Sie die verwenden`Unprotect` Methode der`Document` Klasse und geben Sie das richtige Passwort ein. Dadurch wird der Schutz aufgehoben und das Dokument kann uneingeschränkt bearbeitet werden.

#### F: Ist es möglich, ein Dokument mit mehreren Schutzarten zu schützen?

 A: Nein, mit Aspose.Words für .NET kann jeweils nur ein Schutztyp auf ein Dokument angewendet werden. Allerdings ist die`AllowOnlyFormFields` Der Schutztyp kann die Bearbeitung effektiv auf Formularfelder beschränken und gleichzeitig andere Schutztypen zulassen, z`AllowOnlyComments` oder`AllowOnlyRevisions`kombinierbar mit Formularfeldschutz.

#### F: Kann ich für unterschiedliche Schutzarten in einem Dokument unterschiedliche Passwörter festlegen?

A: Nein, mit Aspose.Words für .NET können Sie unabhängig vom Schutztyp ein einziges Passwort für den Dokumentenschutz festlegen. Das gleiche Passwort wird zum Aktivieren und Deaktivieren des Dokumentenschutzes verwendet.