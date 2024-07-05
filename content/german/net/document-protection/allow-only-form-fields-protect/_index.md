---
title: Nur Formularfelder im Word-Dokument schützen lassen
linktitle: Nur Formularfelder im Word-Dokument schützen lassen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie Aspose.Words für .NET verwenden, um Word-Dokumente zu schützen und nur die Bearbeitung von Formularfeldern zuzulassen.
type: docs
weight: 10
url: /de/net/document-protection/allow-only-form-fields-protect/
---
Der Dokumentenschutz ist eine wesentliche Funktion bei der Textverarbeitung mit Dateien in Ihrer C#-Anwendung. Mit der Aspose.Words-Bibliothek für .NET können Sie Ihre Dokumente einfach schützen und nur die Bearbeitung von Formularfeldern zulassen. In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mithilfe des C#-Quellcodes nur die Bearbeitung von Formularfeldern zulassen, indem Sie die Funktion „Nur Formularfelder schützen“ von Aspose.Words für .NET verwenden.

## Schritt 1: Festlegen des Dokumentverzeichnisses

Der erste Schritt besteht darin, das Verzeichnis Ihres Dokuments zu definieren. Sie müssen den Pfad angeben, in dem Sie das geschützte Dokument speichern möchten. Beispiel:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 2: Abschnitte und Text einfügen

Als Nächstes müssen Sie Abschnitte und Text in Ihr Dokument einfügen. Verwenden Sie die von Aspose.Words bereitgestellte DocumentBuilder-Klasse, um den Inhalt Ihres Dokuments zu erstellen. Hier ist ein einfaches Beispiel:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

In diesem Beispiel erstellen wir ein neues leeres Dokument und verwenden dann DocumentBuilder, um eine Textzeile hinzuzufügen.

## Schritt 3: Dokumentenschutz aktivieren

 Der Dokumentenschutz funktioniert nur, wenn der Dokumentenschutz aktiviert ist. Sie können den Dokumentenschutz aktivieren, indem Sie`Protect` Methode der Document-Klasse. So geht's:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

In diesem Beispiel aktivieren wir den Dokumentenschutz durch die Angabe des Schutztyps `

AllowOnlyFormFields‘ und Festlegen eines Passworts.

## Schritt 4: Nur Formularfelder zulassen

Nachdem der Dokumentschutz aktiviert ist, müssen wir festlegen, dass nur die Bearbeitung von Formularfeldern zulässig ist. Dadurch wird sichergestellt, dass Benutzer nur Teile des Dokuments bearbeiten können, bei denen es sich um Formularfelder handelt. So geht's:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Ersetzen Sie „Passwort“ unbedingt durch das zuvor festgelegte Passwort.

## Schritt 5: Speichern des geschützten Dokuments

 Abschließend können Sie das geschützte Dokument mit dem`Save` Methode der Document-Klasse. Geben Sie den vollständigen Dateipfad und den gewünschten Dateinamen an. Beispiel:

```csharp
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

Ersetzen Sie „dataDir“ unbedingt durch den Pfad zu Ihrem Dokumentverzeichnis.

### Beispielquellcode für die Funktion „Nur Formularfelder schützen“ mit Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Fügen Sie zwei Abschnitte mit etwas Text ein.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// Ein Dokumentenschutz funktioniert nur, wenn der Dokumentenschutz eingeschaltet ist und nur das Bearbeiten in Formularfeldern erlaubt ist.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// Speichern Sie das geschützte Dokument.
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

## Abschluss

In diesem Handbuch haben wir untersucht, wie Sie mit der Aspose.Words-Bibliothek für .NET ein Dokument schützen und nur die Bearbeitung von Formularfeldern zulassen. Indem Sie die angegebenen Schritte befolgen, können Sie diese Funktion problemlos in Ihre C#-Anwendung implementieren. Der Dokumentenschutz ist unerlässlich, um die Sicherheit und Vertraulichkeit Ihrer Dokumente zu gewährleisten.

### FAQs zum Thema „Nur Formularfelder in Word-Dokument schützen“

#### F: Was ist Dokumentenschutz in Aspose.Words für .NET?

A: Der Dokumentenschutz in Aspose.Words für .NET ist eine Funktion, mit der Sie Ihre Dokumente sichern können, indem Sie bestimmte Aktionen wie Bearbeiten, Formatieren oder Inhaltsänderungen einschränken. Es trägt dazu bei, die Integrität und Vertraulichkeit Ihrer Dokumente zu wahren, indem es unbefugte Änderungen verhindert.

#### F: Wie kann ich mit Aspose.Words für .NET ein Dokument schützen und nur die Bearbeitung von Formularfeldern zulassen?

A: Um ein Dokument zu schützen und nur die Bearbeitung von Formularfeldern mit Aspose.Words für .NET zuzulassen, können Sie die folgenden Schritte ausführen:
1. Definieren Sie den Verzeichnispfad für Ihr Dokument.
2.  Fügen Sie Abschnitte und Text in Ihr Dokument ein, indem Sie den`DocumentBuilder` Klasse.
3.  Aktivieren Sie den Dokumentenschutz über die`Protect` Methode der`Document` Klasse, wobei der Schutztyp angegeben wird als`AllowOnlyFormFields` und die Eingabe eines Passwortes.
4.  Speichern Sie das geschützte Dokument mit dem`Save` Methode der`Document` Klasse.

#### F: Kann ich mit Aspose.Words für .NET Formularfelder in ein geschütztes Dokument einfügen?

A: Ja, Sie können Formularfelder in ein geschütztes Dokument mit Aspose.Words für .NET einfügen. Der Dokumentschutz mit dem`AllowOnlyFormFields` ermöglicht es Benutzern, nur die Formularfelder zu bearbeiten und den restlichen Inhalt des Dokuments zu schützen. Sie können den`DocumentBuilder` Klasse, um Formularfelder in das Dokument einzufügen, bevor der Schutz aktiviert wird.

#### F: Kann ich den Dokumentenschutz von einem geschützten Dokument entfernen?

 A: Ja, Sie können den Dokumentschutz von einem geschützten Dokument mit Aspose.Words für .NET entfernen. Um den Schutz zu entfernen, können Sie den`Unprotect` Methode der`Document` Klasse und geben Sie das richtige Passwort ein. Dadurch wird der Schutz aufgehoben und das Dokument kann uneingeschränkt bearbeitet werden.

#### F: Ist es möglich, ein Dokument mit mehreren Schutzarten zu schützen?

 A: Nein, Aspose.Words für .NET erlaubt nur die Anwendung eines Schutztyps auf ein Dokument gleichzeitig. Allerdings`AllowOnlyFormFields` Schutztyp kann die Bearbeitung von Formularfeldern effektiv einschränken und gleichzeitig andere Schutztypen zulassen, wie z. B.`AllowOnlyComments` oder`AllowOnlyRevisions`zu kombinieren mit Formularfeldschutz.

#### F: Kann ich für unterschiedliche Schutzarten in einem Dokument unterschiedliche Passwörter festlegen?

A: Nein, Aspose.Words für .NET ermöglicht Ihnen, unabhängig vom Schutztyp ein einzelnes Kennwort für den Dokumentenschutz festzulegen. Zum Aktivieren und Deaktivieren des Dokumentenschutzes wird dasselbe Kennwort verwendet.