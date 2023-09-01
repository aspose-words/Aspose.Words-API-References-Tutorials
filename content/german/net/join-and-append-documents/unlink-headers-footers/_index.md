---
title: Verknüpfung von Kopf- und Fußzeilen aufheben
linktitle: Verknüpfung von Kopf- und Fußzeilen aufheben
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Word-Dokumente verbinden und anhängen und gleichzeitig die Verknüpfung von Kopf- und Fußzeilen aufheben.
type: docs
weight: 10
url: /de/net/join-and-append-documents/unlink-headers-footers/
---

Dieses Tutorial führt Sie durch den Prozess der Verwendung der Funktion „Verknüpfung von Kopf- und Fußzeilen aufheben“ von Aspose.Words für .NET. Mit dieser Funktion können Sie Word-Dokumente verbinden und anhängen und gleichzeitig die Verknüpfung von Kopf- und Fußzeilen mit dem Quelldokument aufheben.

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

## Schritt 3: Heben Sie die Verknüpfung von Kopf- und Fußzeilen im Quelldokument auf

 Um die Verknüpfung der Kopf- und Fußzeilen im Quelldokument mit der Fortsetzung der Kopf- und Fußzeilen des Zieldokuments aufzuheben, müssen Sie Folgendes festlegen`LinkToPrevious` Eigentum der`HeadersFooters` Sammlung im ersten Abschnitt des Quelldokuments an`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Schritt 4: Hängen Sie das Quelldokument an das Zieldokument an

 Jetzt können Sie das Quelldokument mit an das Zieldokument anhängen`AppendDocument` Methode der`Document` Klasse. Der`ImportFormatMode.KeepSourceFormatting` Der Parameter stellt sicher, dass die Quellformatierung während des Anhängevorgangs erhalten bleibt.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Schritt 5: Speichern Sie das endgültige Dokument

 Speichern Sie abschließend das zusammengeführte Dokument mit aktivierter Funktion „Verknüpfung von Kopf- und Fußzeilen aufheben“ mithilfe von`Save` Methode der`Document` Klasse.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

### Beispielquellcode für Unlink Headers Footers mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Unlink Headers Footers“ in C# mit Aspose.Words für .NET:

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Um dies zu verhindern, heben Sie die Verknüpfung der Kopf- und Fußzeilen im Quelldokument auf
	// daran gehindert, die Kopf- und Fußzeilen des Zieldokuments fortzusetzen.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

Das ist es! Sie haben die Funktion „Verknüpfung von Kopf- und Fußzeilen aufheben“ mit Aspose.Words für .NET erfolgreich implementiert. Das endgültige Dokument enthält den zusammengeführten Inhalt, wobei die Kopf- und Fußzeilen des Quelldokuments nicht mit dem Zieldokument verknüpft sind.