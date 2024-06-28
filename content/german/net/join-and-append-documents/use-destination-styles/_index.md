---
title: Verwenden Sie Zielstile
linktitle: Verwenden Sie Zielstile
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie Word-Dokumente zusammenfügen und anhängen und dabei Zieldokumentstile mit Aspose.Words für .NET anwenden.
type: docs
weight: 10
url: /de/net/join-and-append-documents/use-destination-styles/
---

Dieses Tutorial führt Sie durch den Prozess der Verwendung der Funktion „Zielstile verwenden“ von Aspose.Words für .NET. Mit dieser Funktion können Sie Word-Dokumente verbinden und anhängen und dabei die Stile des Zieldokuments anwenden.

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

Als nächstes müssen Sie die Quell- und Zieldokumente mit Aspose.Words laden.`Document` Klasse. Aktualisieren Sie die Dateinamen im`Document` Konstruktor entsprechend Ihren Dokumentnamen.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Schritt 3: Hängen Sie das Quelldokument mit Zielstilen an

 Um das Quelldokument an das Zieldokument anzuhängen und gleichzeitig die Stile des Zieldokuments anzuwenden, können Sie die verwenden`AppendDocument` Methode der`Document` Klasse mit dem`ImportFormatMode.UseDestinationStyles` Parameter.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Schritt 4: Speichern Sie das endgültige Dokument

 Speichern Sie abschließend das zusammengeführte Dokument mit aktivierter Funktion „Zielstile verwenden“ mithilfe von`Save` Methode der`Document` Klasse.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

### Beispielquellcode für die Verwendung von Zielstilen mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Zielstile verwenden“ in C# mit Aspose.Words für .NET:

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Hängen Sie das Quelldokument mit den Stilen des Zieldokuments an.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

Das ist es! Sie haben die Funktion „Zielstile verwenden“ mit Aspose.Words für .NET erfolgreich implementiert. Das endgültige Dokument enthält den zusammengeführten Inhalt mit den angewendeten Stilen des Zieldokuments.