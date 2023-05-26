---
title: Docx zu Rtf
linktitle: Docx zu Rtf
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie Word-Dokumente mit Aspose.Words für .NET vom Docx- in das RTF-Format konvertieren. Schritt-für-Schritt-Anleitung mit Beispielquellcode.
type: docs
weight: 10
url: /de/net/basic-conversions/docx-to-rtf/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET ein Word-Dokument im Docx-Format in RTF konvertieren. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

Stellen Sie zunächst sicher, dass Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und eingerichtet ist. Wenn Sie dies noch nicht getan haben, laden Sie die Bibliothek von der offiziellen Website herunter und installieren Sie sie.

## Schritt 1: Lesen des Dokuments aus Stream

Öffnen Sie zunächst einen Stream, um das Docx-Dokument zu lesen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Stream stream = File.OpenRead(MyDir + "Document.docx");
```

## Schritt 2: Laden des Dokuments

Laden Sie als Nächstes das Dokument aus dem Stream:

```csharp
Document doc = new Document(stream);
```

## Schritt 3: Schließen des Streams

Da das Dokument in den Speicher geladen wird, können Sie den Stream schließen:

```csharp
stream.Close();
```

## Schritt 4: Durchführen von Vorgängen am Dokument

An dieser Stelle können Sie alle gewünschten Vorgänge am Dokument durchführen.

## Schritt 5: Speichern des Dokuments im RTF-Format

Um das Dokument im RTF-Format zu speichern, speichern Sie es in einem Speicherstream:

```csharp
MemoryStream dstStream = new MemoryStream();
doc.Save(dstStream, SaveFormat.Rtf);
```

## Schritt 6: Zurückspulen des Streams

Bevor Sie den Speicherstrom in eine Datei schreiben, spulen Sie seine Position auf Null zurück:

```csharp
dstStream.Position = 0;
```

## Schritt 7: Den Stream in eine Datei schreiben

Schreiben Sie abschließend den Speicherstream in eine RTF-Datei:

```csharp
File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
```

Das ist es! Sie haben mit Aspose.Words für .NET erfolgreich ein Word-Dokument im Docx-Format in RTF konvertiert.

### Beispielquellcode für Docx To Rtf mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Damit Aspose.Words ein Dokument laden kann, reicht der Lesezugriff aus.
	Stream stream = File.OpenRead(MyDir + "Document.docx");

	Document doc = new Document(stream);
	//Sie können den Stream jetzt schließen, er wird nicht mehr benötigt, da sich das Dokument im Speicher befindet.
	stream.Close();

	// ... etwas mit dem Dokument machen.

	// Konvertieren Sie das Dokument in ein anderes Format und speichern Sie es im Stream.
	MemoryStream dstStream = new MemoryStream();
	doc.Save(dstStream, SaveFormat.Rtf);

	// Spulen Sie die Stream-Position auf Null zurück, damit sie für den nächsten Leser bereit ist.
	dstStream.Position = 0;

	File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
	
```

Sie können diesen Code gerne in Ihren eigenen Projekten verwenden und entsprechend Ihren spezifischen Anforderungen modifizieren.