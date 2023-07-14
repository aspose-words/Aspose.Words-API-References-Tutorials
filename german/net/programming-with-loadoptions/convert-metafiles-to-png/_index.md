---
title: Konvertieren Sie Metadateien in PNG
linktitle: Konvertieren Sie Metadateien in PNG
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie beim Hochladen von Dokumenten mit Aspose.Words für .NET Metadateien in PNG-Bilder konvertieren.
type: docs
weight: 10
url: /de/net/programming-with-loadoptions/convert-metafiles-to-png/
---
Bei der Textverarbeitung mit Dokumenten in einer C#-Anwendung kann es für eine bessere Kompatibilität und genaue Wiedergabe erforderlich sein, Metadateien in PNG-Bilder zu konvertieren. Mit der Aspose.Words-Bibliothek für .NET können Sie Metadateien beim Laden eines Dokuments problemlos in PNG konvertieren. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch die Verwendung von Aspose.Words für .NET C#-Quellcode zum Laden eines Dokuments mit Konvertierung von Metadateien in PNG mithilfe der LoadOptions-Ladeoptionen.

## Grundlegendes zur Aspose.Words-Bibliothek

Bevor Sie in den Code eintauchen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten, Konvertieren und Schützen von Word-Dokumenten auf verschiedenen Plattformen, einschließlich .NET. Es bietet viele Funktionen zum Bearbeiten von Dokumenten, wie zum Beispiel das Einfügen von Text, das Ändern von Formatierungen, das Hinzufügen von Abschnitten und vieles mehr.

## Schritt 1: Definieren des Dokumentenverzeichnisses

Der erste Schritt besteht darin, das Verzeichnis zu definieren, in dem sich Ihre Dokumente befinden. Sie müssen den vollständigen Verzeichnispfad angeben. Zum Beispiel :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTENVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis ersetzen.

## Schritt 2: Ladeoptionen konfigurieren

Jetzt konfigurieren wir die Ladeoptionen für unser Dokument. Verwenden Sie die LoadOptions-Klasse, um Ladeparameter anzugeben. Zum Beispiel :

```csharp
LoadOptions loadOptions = new LoadOptions { ConvertMetafilesToPng = true };
```

In diesem Beispiel erstellen wir ein neues LoadOptions-Objekt und setzen die ConvertMetafilesToPng-Eigenschaft auf „true“, um die Konvertierung von Metadateien in PNG beim Laden des Dokuments zu ermöglichen.

## Schritt 3: Laden des Dokuments mit Konvertierung der Metadateien in PNG

Nachdem wir nun die Ladeoptionen konfiguriert haben, können wir das Dokument mithilfe der Document-Klasse laden und die Ladeoptionen angeben. Zum Beispiel :

```csharp
Document doc = new Document(dataDir + "WMF with image.docx", loadOptions);
```

In diesem Beispiel laden wir das Dokument „WMF with image.docx“, das sich im Dokumentenverzeichnis befindet, mit den angegebenen Ladeoptionen.

## Beispielquellcode für die LoadOptions mit der Funktion „Metadateien in PNG konvertieren“ unter Verwendung von Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Konfigurieren Sie Ladeoptionen mit der Funktion „Metadateien in PNG konvertieren“.
LoadOptions loadOptions = new LoadOptions { ConvertMetafilesToPng = true };

// Laden Sie das Dokument mit den angegebenen Optionen
Document doc = new Document(dataDir + "WMF with image.docx", loadOptions);
```

## Abschluss

In dieser Anleitung haben wir erklärt, wie man ein Dokument mit der Konvertierung von Metadateien in PNG-Bilder mithilfe der Aspose.Words-Bibliothek für .NET lädt. Indem Sie die bereitgestellten Schritte befolgen und den bereitgestellten C#-Quellcode verwenden, können Sie diese Funktionalität problemlos in Ihrer C#-Anwendung anwenden. Die Konvertierung von Metadateien in PNG sorgt für eine bessere Kompatibilität und eine genaue Darstellung von Dokumenten.
