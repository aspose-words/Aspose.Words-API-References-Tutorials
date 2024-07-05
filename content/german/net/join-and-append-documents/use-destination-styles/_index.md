---
title: Zielstile verwenden
linktitle: Zielstile verwenden
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie Word-Dokumente zusammenführen und anhängen, während Sie mit Aspose.Words für .NET Zieldokumentstile anwenden.
type: docs
weight: 10
url: /de/net/join-and-append-documents/use-destination-styles/
---

Dieses Tutorial führt Sie durch die Verwendung der Funktion „Zielformatvorlagen verwenden“ von Aspose.Words für .NET. Mit dieser Funktion können Sie Word-Dokumente zusammenfügen und anhängen, während Sie die Formatvorlagen des Zieldokuments anwenden.

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

## Schritt 3: Anhängen des Quelldokuments mit Zielformatvorlagen

 Um das Quelldokument an das Zieldokument anzuhängen und dabei die Stile des Zieldokuments anzuwenden, können Sie das`AppendDocument` Methode der`Document` Klasse mit dem`ImportFormatMode.UseDestinationStyles` Parameter.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Schritt 4: Speichern Sie das endgültige Dokument

 Speichern Sie das zusammengeführte Dokument abschließend mit der Funktion Zielformatvorlagen verwenden, die Sie über den`Save` Methode der`Document` Klasse.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

### Beispielquellcode für „Zielstile verwenden mit Aspose.Words für .NET“

Hier ist der vollständige Quellcode für die Funktion „Zielstile verwenden“ in C# unter Verwendung von Aspose.Words für .NET:

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Hängen Sie das Quelldokument unter Verwendung der Stile des Zieldokuments an.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

Das ist es! Sie haben die Funktion „Zielformatvorlagen verwenden“ erfolgreich mit Aspose.Words für .NET implementiert. Das endgültige Dokument enthält den zusammengeführten Inhalt mit den angewendeten Formatvorlagen des Zieldokuments.