---
title: Seitenlayout aktualisieren
linktitle: Seitenlayout aktualisieren
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie das Seitenlayout beim Zusammenfügen und Anhängen von Word-Dokumenten mit Aspose.Words für .NET aktualisieren.
type: docs
weight: 10
url: /de/net/join-and-append-documents/update-page-layout/
---

Dieses Tutorial führt Sie durch den Prozess der Verwendung der Funktion „Seitenlayout aktualisieren“ von Aspose.Words für .NET. Diese Funktion stellt sicher, dass das Seitenlayout beim Zusammenfügen und Anhängen von Word-Dokumenten korrekt aktualisiert wird.

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

## Schritt 3: Aktualisieren Sie das Seitenlayout für das Zieldokument

 Um sicherzustellen, dass das Seitenlayout korrekt aktualisiert wird, bevor das Quelldokument angehängt wird, können Sie das aufrufen`UpdatePageLayout` Methode für das Zieldokument.

```csharp
dstDoc.UpdatePageLayout();
```

## Schritt 4: Hängen Sie das Quelldokument an das Zieldokument an

 Jetzt können Sie das Quelldokument mit an das Zieldokument anhängen`AppendDocument` Methode der`Document` Klasse. Der`ImportFormatMode.KeepSourceFormatting` Der Parameter stellt sicher, dass die Quellformatierung während des Anhängevorgangs erhalten bleibt.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Schritt 5: Aktualisieren Sie das Seitenlayout erneut

 Nachdem Sie das Quelldokument angehängt haben, müssen Sie das aufrufen`UpdatePageLayout`Führen Sie die Methode erneut für das Zieldokument aus, um sicherzustellen, dass alle nach dem Anhängevorgang vorgenommenen Änderungen in der gerenderten Ausgabe widergespiegelt werden.

```csharp
dstDoc.UpdatePageLayout();
```

## Schritt 6: Speichern Sie das endgültige Dokument

 Speichern Sie abschließend das zusammengeführte Dokument mit aktivierter Funktion „Seitenlayout aktualisieren“.`Save` Methode der`Document` Klasse.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### Beispielquellcode für die Aktualisierung des Seitenlayouts mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Seitenlayout aktualisieren“ in C# mit Aspose.Words für .NET:

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Wenn das Zieldokument als PDF, Bild usw. gerendert wird.
	// oder UpdatePageLayout wird vor dem Quelldokument aufgerufen. Ist beigefügt,
	// dann werden alle danach vorgenommenen Änderungen nicht in der gerenderten Ausgabe widergespiegelt
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	// Damit die Änderungen auf die gerenderte Ausgabe aktualisiert werden, muss UpdatePageLayout erneut aufgerufen werden.
	// Wenn es nicht erneut aufgerufen wird, wird das angehängte Dokument nicht in der Ausgabe des nächsten Renderings angezeigt.
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

Das ist es! Sie haben die Funktion „Seitenlayout aktualisieren“ mit Aspose.Words für .NET erfolgreich implementiert. Das endgültige Dokument enthält den zusammengeführten Inhalt mit korrekt aktualisiertem Seitenlayout.