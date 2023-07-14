---
title: Lade Chm
linktitle: Lade Chm
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie CHM-Dateien mit Aspose.Words für .NET laden.
type: docs
weight: 10
url: /de/net/programming-with-loadoptions/load-chm/
---

Bei Textverarbeitung mit HTML-Hilfedateien (CHM) in einer C#-Anwendung ist es wichtig, sie korrekt laden zu können. Mit der Aspose.Words-Bibliothek für .NET können Sie CHM-Dateien mithilfe der entsprechenden Ladeoptionen problemlos laden. In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie Aspose.Words für .NET C#-Quellcode verwenden, um eine CHM-Datei mithilfe der LoadOptions-Ladeoptionen zu laden.

## Grundlegendes zur Aspose.Words-Bibliothek

Bevor Sie in den Code eintauchen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten, Konvertieren und Schützen von Word-Dokumenten auf verschiedenen Plattformen, einschließlich .NET. Es bietet viele Funktionen zum Bearbeiten von Dokumenten, wie zum Beispiel das Einfügen von Text, das Ändern von Formatierungen, das Hinzufügen von Abschnitten und vieles mehr.

## Ladeoptionen konfigurieren

Der erste Schritt besteht darin, die Ladeoptionen für unsere CHM-Datei zu konfigurieren. Verwenden Sie die LoadOptions-Klasse, um Ladeparameter anzugeben. In unserem Fall müssen wir die Eigenschaft „Encoding“ auf die entsprechende Kodierung für CHM-Dateien einstellen, normalerweise „windows-1251“. So geht's:

```csharp
LoadOptions loadOptions = new LoadOptions { Encoding = Encoding. GetEncoding("windows-1251") };
```

Wir erstellen ein neues LoadOptions-Objekt und setzen die Encoding-Eigenschaft auf „Windows-1251“-Kodierung für CHM-Dateien.

## CHM-Datei wird geladen

Nachdem wir nun die Ladeoptionen konfiguriert haben, können wir die CHM-Datei mithilfe der Document-Klasse laden und die Ladeoptionen angeben. Hier ist ein Beispiel :

```csharp
Document doc = new Document(dataDir + "HTML help.chm", loadOptions);
```

In diesem Beispiel laden wir die CHM-Datei „HTML help.chm“, die sich im Dokumentenverzeichnis befindet, mit den angegebenen Ladeoptionen.

### Beispielquellcode für LoadOptions mit „Load Chm“-Funktionalität unter Verwendung von Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Konfiguration der Ladeoptionen mit der Funktion „Load Chm“.
LoadOptions loadOptions = new LoadOptions { Encoding = Encoding. GetEncoding("windows-1251") };

// Laden Sie die CHM-Datei mit den angegebenen Optionen
Document doc = new Document(dataDir + "HTML help.chm", loadOptions);
```

## Abschluss

In dieser Anleitung haben wir erklärt, wie man eine CHM-Datei mit der Aspose.Words-Bibliothek für .NET lädt. Indem Sie die bereitgestellten Schritte befolgen und den bereitgestellten C#-Quellcode verwenden, können Sie diese Funktionalität problemlos in Ihrer C#-Anwendung anwenden. Das korrekte Laden von CHM-Dateien ist wichtig, um sie mit Aspose.Words effizient bearbeiten und konvertieren zu können.