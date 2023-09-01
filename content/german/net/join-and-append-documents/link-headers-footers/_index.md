---
title: Kopf- und Fußzeilen verknüpfen
linktitle: Kopf- und Fußzeilen verknüpfen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie Kopf- und Fußzeilen verknüpfen, während Sie Word-Dokumente mit Aspose.Words für .NET verbinden und anhängen.
type: docs
weight: 10
url: /de/net/join-and-append-documents/link-headers-footers/
---

Dieses Tutorial führt Sie durch den Prozess der Verwendung der Funktion „Link Headers Footers“ von Aspose.Words für .NET. Mit dieser Funktion können Sie mehrere Word-Dokumente zusammenfügen und anhängen und gleichzeitig die Kopf- und Fußzeilen des Quelldokuments mit dem vorherigen Abschnitt im Zieldokument verknüpfen.

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

## Schritt 3: Legen Sie fest, dass das angehängte Dokument auf einer neuen Seite angezeigt wird

Um sicherzustellen, dass der Inhalt des Quelldokuments auf einer neuen Seite im Zieldokument angezeigt wird, müssen Sie Folgendes festlegen`SectionStart` Eigenschaft des ersten Abschnitts im Quelldokument`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Schritt 4: Kopf- und Fußzeilen mit dem vorherigen Abschnitt verknüpfen

 Um die Kopf- und Fußzeilen des Quelldokuments mit dem vorherigen Abschnitt im Zieldokument zu verknüpfen, können Sie die verwenden`LinkToPrevious` Methode der`HeadersFooters` Sammlung. Im Vorbeigehen`true` Als Parameter überschreiben Sie alle vorhandenen Kopf- und Fußzeilen im Quelldokument.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
```

## Schritt 5: Hängen Sie das Quelldokument an das Zieldokument an

 Jetzt können Sie das Quelldokument mit an das Zieldokument anhängen`AppendDocument` Methode der`Document` Klasse. Der`ImportFormatMode.KeepSourceFormatting` Der Parameter stellt sicher, dass die Quellformatierung während des Anhängevorgangs erhalten bleibt.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Schritt 6: Speichern Sie das endgültige Dokument

 Speichern Sie abschließend das zusammengeführte Dokument mit den verknüpften Kopf- und Fußzeilen mithilfe von`Save` Methode der`Document` Klasse.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

### Beispielquellcode für Link-Kopfzeilen und Fußzeilen mit Aspose.Words für .NET 

Hier ist der vollständige Quellcode für die Funktion „Link Headers Footers“ in C# mit Aspose.Words für .NET:


```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Legen Sie fest, dass das angehängte Dokument auf einer neuen Seite angezeigt wird.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Verknüpfen Sie die Kopf- und Fußzeilen im Quelldokument mit dem vorherigen Abschnitt.
	// Dadurch werden alle bereits im Quelldokument vorhandenen Kopf- und Fußzeilen überschrieben.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

Das ist es! Sie haben die Funktion „Link Headers Footers“ mit Aspose.Words für .NET erfolgreich implementiert. Das endgültige Dokument enthält den zusammengeführten Inhalt mit den Kopf- und Fußzeilen des Quelldokuments, die mit dem vorherigen Abschnitt im Zieldokument verknüpft sind.