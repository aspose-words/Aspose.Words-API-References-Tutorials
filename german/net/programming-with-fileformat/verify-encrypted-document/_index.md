---
title: Überprüfen Sie das verschlüsselte Word-Dokument
linktitle: Überprüfen Sie das verschlüsselte Word-Dokument
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zur Überprüfung, ob ein Word-Dokument mit Aspose.Words für .NET verschlüsselt ist.
type: docs
weight: 10
url: /de/net/programming-with-fileformat/verify-encrypted-document/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der Funktion zur Überprüfung verschlüsselter Word-Dokumente mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials erfahren Sie, wie Sie überprüfen, ob ein Dokument verschlüsselt ist.

Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aspose.Words für .NET-Bibliothek in Ihrem Projekt installiert und konfiguriert haben. Die Bibliothek und Installationsanweisungen finden Sie auf der Aspose-Website.

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

 Zunächst müssen Sie den Pfad zu dem Verzeichnis definieren, in dem sich Ihre Dokumente befinden. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Dateiformat erkennen

 Als nächstes verwenden wir die`DetectFileFormat` Methode der`FileFormatUtil` Klasse zum Erkennen der Dateiformatinformationen. In diesem Beispiel gehen wir davon aus, dass das verschlüsselte Dokument „Encrypted.docx“ heißt und sich im angegebenen Dokumentenverzeichnis befindet.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

## Schritt 3: Überprüfen Sie, ob das Dokument verschlüsselt ist

 Wir benutzen das`IsEncrypted`Eigentum der`FileFormatInfo` Objekt, um zu prüfen, ob das Dokument verschlüsselt ist. Diese Eigenschaft wird zurückgegeben`true` wenn das Dokument verschlüsselt ist, andernfalls wird es zurückgegeben`false`. Das Ergebnis zeigen wir in der Konsole an.

```csharp
Console.WriteLine(info.IsEncrypted);
```

Das ist alles ! Sie haben mit Aspose.Words für .NET erfolgreich überprüft, ob ein Dokument verschlüsselt ist.

### Beispielquellcode zur Überprüfung verschlüsselter Dokumente mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
	Console.WriteLine(info.IsEncrypted);
            
        
```

## Häufig gestellte Fragen

### F: Welche Schritte sind erforderlich, um ein verschlüsseltes Word-Dokument zu überprüfen?

Die Schritte zum Überprüfen eines verschlüsselten Word-Dokuments sind wie folgt:

Definieren Sie das Dokumentenverzeichnis.

Erkennen Sie das Dateiformat.

Überprüfen Sie, ob das Dokument verschlüsselt ist.

### F: Wie kann ich das Dokumentenverzeichnis festlegen?
 Um das Dokumentenverzeichnis festzulegen, müssen Sie ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad Ihres Dokumentenverzeichnisses im folgenden Code:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

### F: Wie erkennt man das Dateiformat?
 Du kannst den ... benutzen`DetectFileFormat` Methode der`FileFormatUtil` Klasse zum Erkennen von Dateiformatinformationen. Im folgenden Beispiel gehen wir davon aus, dass das verschlüsselte Dokument „Encrypted.docx“ heißt und sich im angegebenen Dokumentenverzeichnis befindet:

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

### F: Wie kann ich überprüfen, ob das Dokument verschlüsselt ist?
 Du kannst den ... benutzen`IsEncrypted`Eigentum der`FileFormatInfo` Objekt, um zu prüfen, ob das Dokument verschlüsselt ist. Diese Eigenschaft wird zurückgegeben`true` wenn das Dokument verschlüsselt ist, andernfalls wird es zurückgegeben`false`. Das Ergebnis wird in der Konsole angezeigt:

```csharp
Console.WriteLine(info.IsEncrypted);
```

### F: Wie kann ich mit Aspose.Words für .NET überprüfen, ob ein Dokument verschlüsselt ist?
Indem Sie die in diesem Tutorial genannten Schritte befolgen und den bereitgestellten Quellcode ausführen, können Sie mit Aspose.Words für .NET überprüfen, ob ein Dokument verschlüsselt ist.
