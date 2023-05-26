---
title: Verschlüsseltes Dokument überprüfen
linktitle: Verschlüsseltes Dokument überprüfen
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zur Überprüfung, ob ein Dokument mit Aspose.Words für .NET verschlüsselt ist.
type: docs
weight: 10
url: /de/net/programming-with-fileformat/verify-encrypted-document/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der Funktion zur Überprüfung verschlüsselter Dokumente mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials erfahren Sie, wie Sie überprüfen, ob ein Dokument verschlüsselt ist.

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

 Wir benutzen das`IsEncrypted` Eigentum der`FileFormatInfo` Objekt, um zu prüfen, ob das Dokument verschlüsselt ist. Diese Eigenschaft wird zurückgegeben`true` wenn das Dokument verschlüsselt ist, andernfalls wird es zurückgegeben`false`. Das Ergebnis zeigen wir in der Konsole an.

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
