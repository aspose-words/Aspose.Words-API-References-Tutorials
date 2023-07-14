---
title: Mit Codierung laden
linktitle: Mit Codierung laden
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Dokument mit einer bestimmten Kodierung laden.
type: docs
weight: 10
url: /de/net/programming-with-loadoptions/load-with-encoding/
---
Bei der Textverarbeitung mit Textdokumenten in einer C#-Anwendung ist es wichtig, diese durch Angabe der richtigen Kodierung korrekt laden zu können. Mit der Aspose.Words-Bibliothek für .NET können Sie mithilfe der LoadOptions-Ladeoptionen ganz einfach Textdokumente mit der gewünschten Kodierung laden. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch die Verwendung des Aspose.Words für .NET C#-Quellcodes zum Laden eines Textdokuments mit der angegebenen Codierung mithilfe der LoadOptions-Ladeoptionen.

## Grundlegendes zur Aspose.Words-Bibliothek

Bevor Sie in den Code eintauchen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten, Konvertieren und Schützen von Word-Dokumenten auf verschiedenen Plattformen, einschließlich .NET. Es bietet viele Funktionen zum Bearbeiten von Dokumenten, wie zum Beispiel das Einfügen von Text, das Ändern von Formatierungen, das Hinzufügen von Abschnitten und vieles mehr.

## Ladeoptionen konfigurieren

Der erste Schritt besteht darin, die Ladeoptionen für unser Textdokument zu konfigurieren. Verwenden Sie die LoadOptions-Klasse, um Ladeparameter anzugeben. In unserem Fall müssen wir die Eigenschaft „Encoding“ auf die gewünschte Kodierung festlegen, zum Beispiel „Encoding.UTF7“ für die UTF-7-Kodierung. So geht's:

```csharp
LoadOptions loadOptions = new LoadOptions { Encoding = Encoding.UTF7 };
```

Wir erstellen ein neues LoadOptions-Objekt und setzen die Encoding-Eigenschaft auf Encoding.UTF7, um die UTF-7-Codierung anzugeben.

## Dokument mit angegebener Kodierung wird geladen

Nachdem wir nun die Ladeoptionen konfiguriert haben, können wir das Dokument mithilfe der Document-Klasse laden und die Ladeoptionen angeben. Hier ist ein Beispiel :

```csharp
Document doc = new Document(dataDir + "Encoded in UTF-7.txt", loadOptions);
```

In diesem Beispiel laden wir das Dokument „Encoded in UTF-7.txt“, das sich im Dokumentenverzeichnis befindet, mit den angegebenen Ladeoptionen.

### Beispielquellcode für LoadOptions mit „Load With Encoding“-Funktionalität unter Verwendung von Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladeoptionen mit der gewünschten Kodierung konfigurieren (UTF-7)
LoadOptions loadOptions = new LoadOptions { Encoding = Encoding.UTF7 };

// Laden Sie das Dokument mit der angegebenen Kodierung
Document doc = new Document(dataDir + "Encoded in UTF-7.txt", loadOptions);
```

## Abschluss

In dieser Anleitung haben wir erklärt, wie man mithilfe der Aspose.Words-Bibliothek für .NET ein Textdokument mit einer bestimmten Kodierung lädt. Indem Sie die bereitgestellten Schritte befolgen und den bereitgestellten C#-Quellcode verwenden, können Sie diese Funktionalität problemlos in Ihrer C#-Anwendung anwenden. Durch das Laden von Textdokumenten mit der richtigen Codierung wird sichergestellt, dass der Inhalt Ihrer Anwendung korrekt und genau gelesen wird.