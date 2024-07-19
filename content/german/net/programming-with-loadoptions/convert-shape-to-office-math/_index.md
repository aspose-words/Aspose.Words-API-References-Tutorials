---
title: Form in Office-Mathe konvertieren
linktitle: Form in Office-Mathe konvertieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie beim Hochladen von Dokumenten mit Aspose.Words für .NET Formen in mathematische Office-Formeln konvertieren.
type: docs
weight: 10
url: /de/net/programming-with-loadoptions/convert-shape-to-office-math/
---
Wenn Sie in einer C#-Anwendung mit Dokumenten arbeiten, die mathematische Formen enthalten, müssen Sie diese möglicherweise in Office-Mathematikformeln konvertieren, um eine bessere Kompatibilität und Darstellung zu erzielen. Mit der Aspose.Words-Bibliothek für .NET können Sie beim Laden eines Dokuments Formen ganz einfach in Office-Mathematikformeln konvertieren. In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit dem C#-Quellcode von Aspose.Words für .NET ein Dokument laden und dabei Formen mithilfe von LoadOptions in Office-Mathematikformeln konvertieren.

## Die Aspose.Words-Bibliothek verstehen

Bevor Sie sich in den Code vertiefen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten, Konvertieren und Schützen von Word-Dokumenten auf verschiedenen Plattformen, einschließlich .NET. Sie bietet viele Funktionen zum Bearbeiten von Dokumenten, z. B. zum Einfügen von Text, Ändern der Formatierung, Hinzufügen von Abschnitten und vieles mehr.

## Konfigurieren der Ladeoptionen

Der erste Schritt besteht darin, die Ladeoptionen für unser Dokument zu konfigurieren. Verwenden Sie die Klasse LoadOptions, um Ladeparameter anzugeben. In unserem Fall möchten wir die Formen in mathematische Office-Formeln konvertieren, daher müssen wir die Eigenschaft ConvertShapeToOfficeMath auf true setzen. So geht's:

```csharp
LoadOptions loadOptions = new LoadOptions { ConvertShapeToOfficeMath = true };
```

Wir erstellen ein neues LoadOptions-Objekt und setzen die ConvertShapeToOfficeMath-Eigenschaft auf „true“, um die Konvertierung von Formen in mathematische Office-Formeln beim Laden des Dokuments zu ermöglichen.

## Laden von Dokumenten mit Konvertieren von Formen in mathematische Office-Formeln

Nachdem wir nun die Ladeoptionen konfiguriert haben, können wir das Dokument mithilfe der Document-Klasse laden und die Ladeoptionen angeben. Hier ist ein Beispiel:

```csharp
Document doc = new Document(dataDir + "Office math.docx", loadOptions);
```

In diesem Beispiel laden wir das im Dokumentenverzeichnis liegende Dokument „Office math.docx“ mit den angegebenen Ladeoptionen.

## Registrierung des Dokuments

Nachdem Sie das Dokument geladen und die Formen in Office-Mathematikformeln konvertiert haben, können Sie es mit der Save-Methode der Document-Klasse im gewünschten Format speichern. So speichern Sie das Dokument beispielsweise im DOCX-Format:

```csharp
doc.Save(dataDir + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.Docx);
```

Ersetzen Sie „dataDir“ unbedingt durch den Verzeichnispfad zu Ihren Dokumenten.

### Beispielquellcode für LoadOptions mit der Funktion „Form in Office-Mathematik konvertieren“ unter Verwendung von Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Konfiguration der Ladeoptionen mit der „Convert Shape“-Funktionalität

  To Office Math"
LoadOptions loadOptions = new LoadOptions { ConvertShapeToOfficeMath = true };

// Laden Sie das Dokument mit den angegebenen Optionen
Document doc = new Document(dataDir + "Office math.docx", loadOptions);

// Speichern Sie das Dokument im gewünschten Format
doc.Save(dataDir + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.Docx);
```

## Abschluss

In dieser Anleitung haben wir erklärt, wie Sie ein Dokument laden, indem Sie Formen mithilfe der Aspose.Words-Bibliothek für .NET in Office-Mathematikformeln umwandeln. Indem Sie die angegebenen Schritte befolgen und den bereitgestellten C#-Quellcode verwenden, können Sie diese Funktion problemlos in Ihrer C#-Anwendung anwenden. Die Umwandlung von Formen in Office-Mathematikformeln sorgt für bessere Kompatibilität und Darstellung von Dokumenten, die mathematische Elemente enthalten.


### Häufig gestellte Fragen

#### F: Warum müssen Formen in mathematische Office-Formeln konvertiert werden?

A: Das Konvertieren von Formen in mathematische Office-Formeln ist für eine verbesserte Kompatibilität und bessere Darstellung mathematischer Elemente in Word-Dokumenten in einer C#-Anwendung unerlässlich.

#### F: Kann Aspose.Words komplexe mathematische Ausdrücke verarbeiten?

A: Auf jeden Fall! Aspose.Words kann eine breite Palette mathematischer Ausdrücke und Formeln verarbeiten und ist daher ein geeignetes Werkzeug für die Verarbeitung selbst komplexer mathematischer Inhalte.

#### F: Ist Aspose.Words nur auf .NET-Plattformen beschränkt?

A: Aspose.Words ist zwar für .NET optimiert, bietet aber auch Unterstützung für andere Plattformen, darunter Java und Android, was es zu einer vielseitigen Lösung für die Dokumentenverarbeitung macht.

#### F: Kann ich die Ladeoptionen für andere Zwecke anpassen?

A: In der Tat! Aspose.Words bietet verschiedene Ladeoptionen, die an Ihre spezifischen Anforderungen angepasst werden können und so eine nahtlose Integration der Bibliothek in Ihre Anwendung gewährleisten.

#### F: Unterstützt Aspose.Words außer Word auch andere Dokumentformate?

A: Ja, neben Word-Dokumenten unterstützt Aspose.Words eine breite Palette von Formaten wie PDF, HTML, EPUB und mehr und ist damit eine umfassende Lösung zur Dokumentbearbeitung.