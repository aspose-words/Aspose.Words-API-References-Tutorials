---
title: Verknüpfung von Kopf- und Fußzeilen aufheben
linktitle: Verknüpfung von Kopf- und Fußzeilen aufheben
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Word-Dokumente zusammenfügen und anhängen und dabei die Verknüpfung von Kopf- und Fußzeilen aufheben.
type: docs
weight: 10
url: /de/net/join-and-append-documents/unlink-headers-footers/
---

Dieses Tutorial führt Sie durch die Verwendung der Funktion „Kopf- und Fußzeilenverknüpfung aufheben“ von Aspose.Words für .NET. Mit dieser Funktion können Sie Word-Dokumente zusammenfügen und anhängen, während Sie die Verknüpfung von Kopf- und Fußzeilen mit dem Quelldokument aufheben.

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

## Schritt 3: Verknüpfung von Kopf- und Fußzeilen im Quelldokument aufheben

 Um die Verknüpfung der Kopf- und Fußzeilen im Quelldokument mit den Kopf- und Fußzeilen des Zieldokuments aufzuheben, müssen Sie die`LinkToPrevious` Eigentum der`HeadersFooters` Sammlung im ersten Abschnitt des Quelldokuments, um`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Schritt 4: Anhängen des Quelldokuments an das Zieldokument

 Nun können Sie das Quelldokument an das Zieldokument anhängen, indem Sie`AppendDocument` Methode der`Document` Klasse. Die`ImportFormatMode.KeepSourceFormatting` Der Parameter stellt sicher, dass die Quellformatierung während des Anfügevorgangs erhalten bleibt.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Schritt 5: Speichern Sie das endgültige Dokument

 Speichern Sie das zusammengeführte Dokument abschließend mit der Funktion Kopf- und Fußzeilenverknüpfung aufheben, indem Sie auf`Save` Methode der`Document` Klasse.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

### Beispielquellcode zum Aufheben der Verknüpfung von Kopf- und Fußzeilen mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Kopf- und Fußzeilen trennen“ in C# unter Verwendung von Aspose.Words für .NET:

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Um dies zu verhindern, entfernen Sie die Verknüpfungen zwischen Kopf- und Fußzeilen im Quelldokument.
	// daran, die Kopf- und Fußzeilen des Zieldokuments fortzusetzen.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

Das ist es! Sie haben die Funktion „Kopf- und Fußzeilen trennen“ erfolgreich mit Aspose.Words für .NET implementiert. Das endgültige Dokument enthält den zusammengeführten Inhalt mit den Kopf- und Fußzeilen des Quelldokuments, die vom Zieldokument getrennt sind.