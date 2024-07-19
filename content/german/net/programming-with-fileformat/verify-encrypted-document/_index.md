---
title: Verschlüsseltes Word-Dokument überprüfen
linktitle: Verschlüsseltes Word-Dokument überprüfen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Überprüfen, ob ein Word-Dokument mit Aspose.Words für .NET verschlüsselt ist.
type: docs
weight: 10
url: /de/net/programming-with-fileformat/verify-encrypted-document/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der Funktion zur Überprüfung verschlüsselter Word-Dokumente mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials werden Sie wissen, wie Sie überprüfen können, ob ein Dokument verschlüsselt ist.

Stellen Sie vor dem Start sicher, dass Sie die Aspose.Words für .NET-Bibliothek in Ihrem Projekt installiert und konfiguriert haben. Sie finden die Bibliothek und Installationsanweisungen auf der Aspose-Website.

## Schritt 1: Dokumentverzeichnis festlegen

 Zunächst müssen Sie den Pfad zum Verzeichnis angeben, in dem sich Ihre Dokumente befinden. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Dateiformat erkennen

 Als nächstes verwenden wir die`DetectFileFormat` Methode der`FileFormatUtil` Klasse zum Erkennen der Dateiformatinformationen. In diesem Beispiel gehen wir davon aus, dass das verschlüsselte Dokument „Encrypted.docx“ heißt und sich im angegebenen Dokumentenverzeichnis befindet.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

## Schritt 3: Überprüfen Sie, ob das Dokument verschlüsselt ist

 Wir benutzen das`IsEncrypted` Eigentum der`FileFormatInfo` Objekt, um zu prüfen, ob das Dokument verschlüsselt ist. Diese Eigenschaft gibt`true` wenn das Dokument verschlüsselt ist, andernfalls wird zurückgegeben`false`. Das Ergebnis zeigen wir in der Konsole an.

```csharp
Console.WriteLine(info.IsEncrypted);
```

Das ist alles! Sie haben erfolgreich überprüft, ob ein Dokument mit Aspose.Words für .NET verschlüsselt ist.

### Beispiel-Quellcode zur Überprüfung verschlüsselter Dokumente mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
	Console.WriteLine(info.IsEncrypted);
            
        
```

## Häufig gestellte Fragen

### F: Welche Schritte sind zum Überprüfen eines verschlüsselten Word-Dokuments erforderlich?

Die Schritte zum Überprüfen eines verschlüsselten Word-Dokuments sind wie folgt:

Definieren Sie das Dokumentverzeichnis.

Erkennen Sie das Dateiformat.

Überprüfen Sie, ob das Dokument verschlüsselt ist.

### F: Wie kann ich das Dokumentverzeichnis festlegen?
 Um das Dokumentenverzeichnis festzulegen, müssen Sie ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad Ihres Dokumentverzeichnisses im folgenden Code:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

### F: Wie erkennt man das Dateiformat?
 Du kannst den ... benutzen`DetectFileFormat` Methode der`FileFormatUtil` Klasse zum Erkennen von Dateiformatinformationen. Im folgenden Beispiel gehen wir davon aus, dass das verschlüsselte Dokument „Encrypted.docx“ heißt und sich im angegebenen Dokumentenverzeichnis befindet:

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

### F: Wie kann ich überprüfen, ob das Dokument verschlüsselt ist?
 Du kannst den ... benutzen`IsEncrypted` Eigentum der`FileFormatInfo` Objekt, um zu prüfen, ob das Dokument verschlüsselt ist. Diese Eigenschaft gibt`true` wenn das Dokument verschlüsselt ist, andernfalls wird zurückgegeben`false`. Das Ergebnis wird in der Konsole angezeigt:

```csharp
Console.WriteLine(info.IsEncrypted);
```

### F: Wie kann ich mit Aspose.Words für .NET überprüfen, ob ein Dokument verschlüsselt ist?
Indem Sie die in diesem Tutorial genannten Schritte befolgen und den bereitgestellten Quellcode ausführen, können Sie mit Aspose.Words für .NET überprüfen, ob ein Dokument verschlüsselt ist.
