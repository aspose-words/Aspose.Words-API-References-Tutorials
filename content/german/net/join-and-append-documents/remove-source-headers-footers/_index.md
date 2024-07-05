---
title: Quellkopfzeilen und -fußzeilen entfernen
linktitle: Quellkopfzeilen und -fußzeilen entfernen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie Kopf- und Fußzeilen entfernen, während Sie Word-Dokumente mit Aspose.Words für .NET verbinden und anhängen.
type: docs
weight: 10
url: /de/net/join-and-append-documents/remove-source-headers-footers/
---

Dieses Tutorial führt Sie durch die Verwendung der Funktion „Quellkopfzeilen und -fußzeilen entfernen“ von Aspose.Words für .NET. Mit dieser Funktion können Sie Word-Dokumente zusammenfügen und anhängen, während Sie Kopf- und Fußzeilen aus dem Quelldokument entfernen.

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

## Schritt 3: Kopf- und Fußzeilen aus den Abschnitten des Quelldokuments entfernen

 Um die Kopf- und Fußzeilen aus jedem Abschnitt im Quelldokument zu entfernen, können Sie die Abschnitte mithilfe eines`foreach` Schleife und rufe die`ClearHeadersFooters` Methode.

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## Schritt 4: Deaktivieren Sie die Einstellung „LinkToPrevious“ für Header/Footer

Auch nach dem Löschen der Kopf- und Fußzeilen aus dem Quelldokument besteht die Möglichkeit, dass die Einstellung "LinkToPrevious" für`HeadersFooters` kann noch gesetzt werden. Um dieses Verhalten zu vermeiden, müssen Sie es explizit auf`false` für den ersten Abschnitt`HeadersFooters` Eigentum.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Schritt 5: Anhängen des Quelldokuments an das Zieldokument

 Nun können Sie das Quelldokument an das Zieldokument anhängen, indem Sie`AppendDocument` Methode der`Document` Klasse. Die`ImportFormatMode.KeepSourceFormatting` Der Parameter stellt sicher, dass die Quellformatierung während des Anfügevorgangs erhalten bleibt.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Schritt 6: Speichern Sie das endgültige Dokument

 Speichern Sie das zusammengeführte Dokument abschließend mit der Funktion „Quelltext-Kopfzeilen/-Fußzeilen entfernen“ über den`Save` Methode der`Document` Klasse.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

### Beispielquellcode zum Entfernen von Quellkopf- und -fußzeilen mit Aspose.Words für .NET 

Hier ist der vollständige Quellcode für die Funktion „Quelltext-Kopf- und Fußzeilen entfernen“ in C# unter Verwendung von Aspose.Words für .NET:


```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Entfernen Sie die Kopf- und Fußzeilen aus allen Abschnitten im Quelldokument.
	foreach (Section section in srcDoc.Sections)
	{
		section.ClearHeadersFooters();
	}
	// Auch wenn die Kopf- und Fußzeilen aus dem Quelldokument gelöscht wurden, bleibt die Einstellung "LinkToPrevious"
	// für HeadersFooters können weiterhin gesetzt werden. Dies führt dazu, dass die Kopf- und Fußzeilen vom Ziel aus fortgesetzt werden
	// Dokument. Um dieses Verhalten zu vermeiden, sollte dies auf „false“ gesetzt werden.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```
Das ist es! Sie haben die Funktion „Quellkopf- und -fußzeilen entfernen“ erfolgreich mit Aspose.Words für .NET implementiert. Das endgültige Dokument enthält den zusammengeführten Inhalt mit den aus dem Quelldokument entfernten Kopf- und Fußzeilen.