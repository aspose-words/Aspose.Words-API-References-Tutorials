---
title: Docx in Byte
linktitle: Docx in Byte
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie Word-Dokumente mit Aspose.Words für .NET von Docx in ein Byte-Array konvertieren. Schritt-für-Schritt-Anleitung mit Beispielquellcode.
type: docs
weight: 10
url: /de/net/basic-conversions/docx-to-byte/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET ein Word-Dokument im Docx-Format in ein Byte-Array konvertieren. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

Stellen Sie zunächst sicher, dass Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und eingerichtet ist. Wenn Sie dies noch nicht getan haben, laden Sie die Bibliothek von der offiziellen Website herunter und installieren Sie sie.

## Schritt 1: Initialisieren des MemoryStream

 Erstellen Sie zunächst eine Instanz von`MemoryStream` Klasse zum Speichern des konvertierten Dokuments als Byte-Array:

```csharp
MemoryStream outStream = new MemoryStream();
```

## Schritt 2: Speichern des Dokuments in MemoryStream

 Als nächstes verwenden Sie die`Save` Methode der`Document` Klasse, um das Dokument zu speichern`MemoryStream` im Docx-Format:

```csharp
doc.Save(outStream, SaveFormat.Docx);
```

## Schritt 3: Konvertieren von MemoryStream in ein Byte-Array

 Um die zu konvertieren`MemoryStream` Um das Docx-Dokument in ein Byte-Array umzuwandeln, verwenden Sie das`ToArray` Methode:

```csharp
byte[] docBytes = outStream.ToArray();
```

## Schritt 4: Initialisieren des MemoryStream aus dem Byte-Array

 Initialisieren Sie nun eine neue Instanz von`MemoryStream`Verwenden des im vorherigen Schritt erhaltenen Byte-Arrays:

```csharp
MemoryStream inStream = new MemoryStream(docBytes);
```

## Schritt 5: Dokument aus MemoryStream erstellen

 Erstellen Sie abschließend eine neue`Document` Objekt aus dem`MemoryStream`:

```csharp
Document docFromBytes = new Document(inStream);
```

Das ist es! Sie haben mit Aspose.Words für .NET erfolgreich ein Word-Dokument im Docx-Format in ein Byte-Array konvertiert.

### Beispielquellcode für Docx To Byte mit Aspose.Words für .NET

```csharp

	// MemoryStream outStream = new MemoryStream();
	doc.Save(outStream, SaveFormat.Docx);

	byte[] docBytes = outStream.ToArray();
	MemoryStream inStream = new MemoryStream(docBytes);

	Document docFromBytes = new Document(inStream);
	
```

Sie können diesen Code gerne in Ihren eigenen Projekten verwenden und entsprechend Ihren spezifischen Anforderungen modifizieren.