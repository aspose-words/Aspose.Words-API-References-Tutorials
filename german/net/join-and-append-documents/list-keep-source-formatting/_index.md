---
title: Liste Quellformatierung beibehalten
linktitle: Liste Quellformatierung beibehalten
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie die Listenformatierung beim Zusammenfügen und Anhängen von Word-Dokumenten mit Aspose.Words für .NET beibehalten.
type: docs
weight: 10
url: /de/net/join-and-append-documents/list-keep-source-formatting/
---

Dieses Tutorial führt Sie durch den Prozess der Verwendung der Funktion „List Keep Source Formatting“ von Aspose.Words für .NET. Mit dieser Funktion können Sie Word-Dokumente zusammenfügen und anhängen und dabei die Quellformatierung der Listen beibehalten.

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
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Schritt 3: Stellen Sie das Quelldokument auf „Kontinuierlicher Fluss“ ein

 Um sicherzustellen, dass der Inhalt des Quelldokuments kontinuierlich fließt, wenn er an das Zieldokument angehängt wird, müssen Sie Folgendes festlegen`SectionStart` Eigenschaft des ersten Abschnitts im Quelldokument`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Schritt 4: Hängen Sie das Quelldokument an das Zieldokument an

 Jetzt können Sie das Quelldokument mit an das Zieldokument anhängen`AppendDocument` Methode der`Document` Klasse. Der`ImportFormatMode.KeepSourceFormatting`Der Parameter stellt sicher, dass die Quellformatierung, einschließlich der Formatierung von Listen, während des Anhängevorgangs erhalten bleibt.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Schritt 5: Speichern Sie das endgültige Dokument

 Speichern Sie abschließend das zusammengeführte Dokument mit aktivierter Funktion „Quellenformatierung beibehalten“ mithilfe von`Save` Methode der`Document` Klasse.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

### Beispielquellcode für List Keep Source Formatting mit Aspose.Words für .NET 

Hier ist der vollständige Quellcode für die Funktion „List Keep Source Formatting“ in C# mit Aspose.Words für .NET:

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Hängen Sie den Inhalt des Dokuments an, damit es kontinuierlich fließt.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

Das ist es! Sie haben die Funktion „List Keep Source Formatting“ mit Aspose.Words für .NET erfolgreich implementiert. Das endgültige Dokument enthält den zusammengeführten Inhalt, wobei die Listenformatierung des Quelldokuments erhalten bleibt.