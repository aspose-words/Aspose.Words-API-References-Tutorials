---
title: Seitenlayout aktualisieren
linktitle: Seitenlayout aktualisieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie das Seitenlayout beim Zusammenführen und Anhängen von Word-Dokumenten mit Aspose.Words für .NET aktualisieren.
type: docs
weight: 10
url: /de/net/join-and-append-documents/update-page-layout/
---

Dieses Tutorial führt Sie durch den Prozess der Verwendung der Funktion „Seitenlayout aktualisieren“ von Aspose.Words für .NET. Diese Funktion stellt sicher, dass das Seitenlayout beim Zusammenfügen und Anhängen von Word-Dokumenten korrekt aktualisiert wird.

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

## Schritt 3: Seitenlayout für das Zieldokument aktualisieren

 Um sicherzustellen, dass das Seitenlayout vor dem Anhängen des Quelldokuments korrekt aktualisiert wird, können Sie den`UpdatePageLayout` Methode im Zieldokument.

```csharp
dstDoc.UpdatePageLayout();
```

## Schritt 4: Anhängen des Quelldokuments an das Zieldokument

 Nun können Sie das Quelldokument an das Zieldokument anhängen, indem Sie`AppendDocument` Methode der`Document` Klasse. Die`ImportFormatMode.KeepSourceFormatting` Der Parameter stellt sicher, dass die Quellformatierung während des Anfügevorgangs erhalten bleibt.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Schritt 5: Seitenlayout erneut aktualisieren

 Nach dem Anhängen des Quelldokuments müssen Sie den`UpdatePageLayout`Methode im Zieldokument erneut, um sicherzustellen, dass alle nach dem Anfügevorgang vorgenommenen Änderungen in der gerenderten Ausgabe widergespiegelt werden.

```csharp
dstDoc.UpdatePageLayout();
```

## Schritt 6: Speichern Sie das endgültige Dokument

 Speichern Sie das zusammengeführte Dokument abschließend mit der Funktion Seitenlayout aktualisieren, die Sie über den`Save` Methode der`Document` Klasse.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### Beispielquellcode zum Aktualisieren des Seitenlayouts mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Seitenlayout aktualisieren“ in C# mit Aspose.Words für .NET:

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Wenn das Zieldokument im PDF-, Bild- usw.-Format gerendert wird.
	// oder UpdatePageLayout wird vor dem Quelldokument aufgerufen. Wird angehängt,
	// dann werden alle danach vorgenommenen Änderungen nicht in der gerenderten Ausgabe widergespiegelt
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	// Damit die Änderungen in der gerenderten Ausgabe aktualisiert werden, muss UpdatePageLayout erneut aufgerufen werden.
	// Wenn es nicht erneut aufgerufen wird, erscheint das angehängte Dokument nicht in der Ausgabe des nächsten Renderings.
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

Das ist es! Sie haben die Funktion „Seitenlayout aktualisieren“ erfolgreich mit Aspose.Words für .NET implementiert. Das endgültige Dokument enthält den zusammengeführten Inhalt mit dem korrekt aktualisierten Seitenlayout.