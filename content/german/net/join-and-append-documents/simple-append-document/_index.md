---
title: Einfaches Anhängen eines Dokuments
linktitle: Einfaches Anhängen eines Dokuments
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Word-Dokumente mit beibehaltener Formatierung zusammenführen und anhängen.
type: docs
weight: 10
url: /de/net/join-and-append-documents/simple-append-document/
---

Dieses Tutorial führt Sie durch die Verwendung der Funktion „Simple Append Document“ von Aspose.Words für .NET. Mit dieser Funktion können Sie Word-Dokumente ohne zusätzliche Optionen zusammenfügen und anhängen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1. Aspose.Words für .NET installiert. Sie können es von der Aspose-Website herunterladen oder über NuGet installieren.
2. Visual Studio oder eine andere C#-Entwicklungsumgebung.

## Schritt 1: Initialisieren der Dokumentverzeichnisse

 Zuerst müssen Sie den Pfad zu Ihrem Dokumentverzeichnis festlegen. Ändern Sie den Wert des`dataDir` Variable für den Pfad, in dem sich Ihre Dokumente befinden.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie die Quell- und Zieldokumente

Als nächstes müssen Sie die Quell- und Zieldokumente mit dem Aspose.Words laden`Document` Klasse. Aktualisieren Sie die Dateinamen in der`Document` Konstruktor entsprechend Ihren Dokumentnamen.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Schritt 3: Anhängen des Quelldokuments an das Zieldokument

 Nun können Sie das Quelldokument an das Zieldokument anhängen, indem Sie`AppendDocument` Methode der`Document` Klasse. Die`ImportFormatMode.KeepSourceFormatting` Der Parameter stellt sicher, dass die Quellformatierung während des Anfügevorgangs erhalten bleibt.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Schritt 4: Speichern Sie das endgültige Dokument

 Speichern Sie das zusammengeführte Dokument abschließend mit der Funktion „Dokument einfach anhängen“ unter Verwendung des`Save` Methode der`Document` Klasse.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

### Beispielquellcode für Simple Append Document mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Einfaches Anhängen von Dokumenten“ in C# unter Verwendung von Aspose.Words für .NET:

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Hängen Sie das Quelldokument ohne zusätzliche Optionen an das Zieldokument an.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

Das ist es! Sie haben die Funktion „Simple Append Document“ erfolgreich mit Aspose.Words für .NET implementiert. Das endgültige Dokument enthält den zusammengeführten Inhalt unter Beibehaltung der Quellformatierung.