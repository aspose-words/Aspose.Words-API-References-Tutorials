---
title: Einfaches Dokument anhängen
linktitle: Einfaches Dokument anhängen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Word-Dokumente mit beibehaltener Formatierung zusammenfügen und anhängen.
type: docs
weight: 10
url: /de/net/join-and-append-documents/simple-append-document/
---

Dieses Tutorial führt Sie durch den Prozess der Verwendung der Funktion „Einfaches Dokument anhängen“ von Aspose.Words für .NET. Mit dieser Funktion können Sie Word-Dokumente ohne zusätzliche Optionen zusammenfügen und anhängen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1. Aspose.Words für .NET installiert. Sie können es von der Aspose-Website herunterladen oder über NuGet installieren.
2. Visual Studio oder eine andere C#-Entwicklungsumgebung.

## Schritt 1: Initialisieren Sie die Dokumentverzeichnisse

 Zuerst müssen Sie den Pfad zu Ihrem Dokumentverzeichnis festlegen. Ändern Sie den Wert von`dataDir` Variable für den Pfad, in dem sich Ihre Dokumente befinden.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie die Quell- und Zieldokumente

 Als nächstes müssen Sie die Quell- und Zieldokumente mit Aspose.Words laden`Document` Klasse. Aktualisieren Sie die Dateinamen im`Document` Konstruktor entsprechend Ihren Dokumentnamen.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Schritt 3: Hängen Sie das Quelldokument an das Zieldokument an

 Jetzt können Sie das Quelldokument mit an das Zieldokument anhängen`AppendDocument` Methode der`Document` Klasse. Der`ImportFormatMode.KeepSourceFormatting` Der Parameter stellt sicher, dass die Quellformatierung während des Anhängevorgangs erhalten bleibt.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Schritt 4: Speichern Sie das endgültige Dokument

 Speichern Sie abschließend das zusammengeführte Dokument mit der Funktion „Einfaches Dokument anhängen“ mithilfe von`Save` Methode der`Document` Klasse.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

### Beispielquellcode für Simple Append Document mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Simple Append Document“ in C# mit Aspose.Words für .NET:

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Hängen Sie das Quelldokument ohne zusätzliche Optionen an das Zieldokument an.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

Das ist es! Sie haben die Funktion „Einfaches Dokument anhängen“ mit Aspose.Words für .NET erfolgreich implementiert. Das endgültige Dokument enthält den zusammengeführten Inhalt unter Beibehaltung der Quellformatierung.