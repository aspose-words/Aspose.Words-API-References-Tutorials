---
title: Form in Office-Mathe umwandeln
linktitle: Form in Office-Mathe umwandeln
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie beim Hochladen von Dokumenten mit Aspose.Words für .NET Formen in Office-Matheformeln konvertieren.
type: docs
weight: 10
url: /de/net/programming-with-loadoptions/convert-shape-to-office-math/
---

Wenn Sie in einer C#-Anwendung mit Dokumenten arbeiten, die mathematische Formen enthalten, müssen Sie diese möglicherweise zur besseren Kompatibilität und Darstellung in Office-Matheformeln konvertieren. Mit der Aspose.Words-Bibliothek für .NET können Sie beim Laden eines Dokuments problemlos Formen in Office-Matheformeln konvertieren. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch die Verwendung des Aspose.Words für .NET C#-Quellcodes zum Laden eines Dokuments mit der Konvertierung von Formen in Office-Matheformeln mithilfe von LoadOptions.

## Grundlegendes zur Aspose.Words-Bibliothek

Bevor Sie in den Code eintauchen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten, Konvertieren und Schützen von Word-Dokumenten auf verschiedenen Plattformen, einschließlich .NET. Es bietet viele Funktionen zum Bearbeiten von Dokumenten, wie zum Beispiel das Einfügen von Text, das Ändern von Formatierungen, das Hinzufügen von Abschnitten und vieles mehr.

## Ladeoptionen konfigurieren

Der erste Schritt besteht darin, die Ladeoptionen für unser Dokument zu konfigurieren. Verwenden Sie die LoadOptions-Klasse, um Ladeparameter anzugeben. In unserem Fall möchten wir die Formen in Office-Matheformeln konvertieren, daher müssen wir die Eigenschaft „ConvertShapeToOfficeMath“ auf „true“ setzen. So geht's:

```csharp
LoadOptions loadOptions = new LoadOptions { ConvertShapeToOfficeMath = true };
```

Wir erstellen ein neues LoadOptions-Objekt und setzen die ConvertShapeToOfficeMath-Eigenschaft auf true, um beim Laden des Dokuments die Konvertierung von Formen in Office-Matheformeln zu ermöglichen.

## Laden von Dokumenten mit Konvertieren von Formen in Office-Matheformeln

Nachdem wir nun die Ladeoptionen konfiguriert haben, können wir das Dokument mithilfe der Document-Klasse laden und die Ladeoptionen angeben. Hier ist ein Beispiel :

```csharp
Document doc = new Document(dataDir + "Office math.docx", loadOptions);
```

In diesem Beispiel laden wir das Dokument „Office math.docx“, das sich im Dokumentenverzeichnis befindet, mit den angegebenen Ladeoptionen.

## Registrierung des Dokuments

Nachdem Sie das Dokument mit der Konvertierung von Formen in Office-Matheformeln geladen haben, können Sie es mit der Save-Methode der Document-Klasse im gewünschten Format speichern. Um das Dokument beispielsweise im .docx-Format zu speichern:

```csharp
doc.Save(dataDir + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.Docx);
```

Ersetzen Sie „dataDir“ unbedingt durch den Verzeichnispfad zu Ihren Dokumenten.

### Beispielquellcode für LoadOptions mit der Funktionalität „Convert Shape To Office Math“ unter Verwendung von Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Konfiguration der Ladeoptionen mit der „Convert Shape“-Funktionalität

  To Office Math"
LoadOptions loadOptions = new LoadOptions { ConvertShapeToOfficeMath = true };

// Laden Sie das Dokument mit den angegebenen Optionen
Document doc = new Document(dataDir + "Office math.docx", loadOptions);

//Speichern Sie das Dokument im gewünschten Format
doc.Save(dataDir + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.Docx);
```

## Abschluss

In dieser Anleitung haben wir erklärt, wie man ein Dokument mit der Konvertierung von Formen in Office-Matheformeln mithilfe der Aspose.Words-Bibliothek für .NET lädt. Indem Sie die bereitgestellten Schritte befolgen und den bereitgestellten C#-Quellcode verwenden, können Sie diese Funktionalität problemlos in Ihrer C#-Anwendung anwenden. Das Konvertieren von Formen in Office-Matheformeln sorgt für eine bessere Kompatibilität und Darstellung von Dokumenten, die mathematische Elemente enthalten.
