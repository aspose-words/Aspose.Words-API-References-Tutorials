---
title: Entfernen Sie die Kopf- und Fußzeilen der Quelle
linktitle: Entfernen Sie die Kopf- und Fußzeilen der Quelle
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie Kopf- und Fußzeilen entfernen, während Sie Word-Dokumente mit Aspose.Words für .NET verbinden und anhängen.
type: docs
weight: 10
url: /de/net/join-and-append-documents/remove-source-headers-footers/
---

Dieses Tutorial führt Sie durch den Prozess der Verwendung der Funktion „Quellkopfzeilen und Fußzeilen entfernen“ von Aspose.Words für .NET. Mit dieser Funktion können Sie Word-Dokumente verbinden und anhängen und gleichzeitig Kopf- und Fußzeilen aus dem Quelldokument entfernen.

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

## Schritt 3: Entfernen Sie Kopf- und Fußzeilen aus den Abschnitten des Quelldokuments

 Um die Kopf- und Fußzeilen aus jedem Abschnitt im Quelldokument zu entfernen, können Sie mit a die Abschnitte durchlaufen`foreach` Schleife und rufe die auf`ClearHeadersFooters` Methode.

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## Schritt 4: Deaktivieren Sie die Einstellung „LinkToPrevious“ für HeadersFooters

Auch nach dem Löschen der Kopf- und Fußzeilen aus dem Quelldokument besteht die Möglichkeit, dass die Einstellung „LinkToPrevious“ für`HeadersFooters` kann noch eingestellt werden. Um dieses Verhalten zu vermeiden, müssen Sie es explizit auf festlegen`false` für den ersten Abschnitt`HeadersFooters` Eigentum.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Schritt 5: Hängen Sie das Quelldokument an das Zieldokument an

 Jetzt können Sie das Quelldokument mit an das Zieldokument anhängen`AppendDocument` Methode der`Document` Klasse. Der`ImportFormatMode.KeepSourceFormatting` Der Parameter stellt sicher, dass die Quellformatierung während des Anhängevorgangs erhalten bleibt.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Schritt 6: Speichern Sie das endgültige Dokument

 Speichern Sie abschließend das zusammengeführte Dokument mit aktivierter Funktion „Quellkopfzeilen und Fußzeilen entfernen“.`Save` Methode der`Document` Klasse.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

### Beispielquellcode zum Entfernen von Quellkopfzeilen und Fußzeilen mit Aspose.Words für .NET 

Hier ist der vollständige Quellcode für die Funktion „Quellkopfzeilen und Fußzeilen entfernen“ in C# mit Aspose.Words für .NET:


```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Entfernen Sie die Kopf- und Fußzeilen aus jedem Abschnitt im Quelldokument.
	foreach (Section section in srcDoc.Sections)
	{
		section.ClearHeadersFooters();
	}
	// Auch nachdem die Kopf- und Fußzeilen aus dem Quelldokument gelöscht wurden, bleibt die Einstellung „LinkToPrevious“ bestehen
	// für HeadersFooters kann weiterhin gesetzt werden. Dadurch werden die Kopf- und Fußzeilen vom Ziel aus fortgesetzt
	// dokumentieren. Dies sollte auf „false“ gesetzt werden, um dieses Verhalten zu vermeiden.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```
Das ist es! Sie haben die Funktion „Quellkopfzeilen und Fußzeilen entfernen“ mit Aspose.Words für .NET erfolgreich implementiert. Das endgültige Dokument enthält den zusammengeführten Inhalt, wobei die Kopf- und Fußzeilen aus dem Quelldokument entfernt wurden.