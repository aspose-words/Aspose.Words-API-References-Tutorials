---
title: Listen-Keep-Quellformatierung
linktitle: Listen-Keep-Quellformatierung
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie die Listenformatierung beibehalten, während Sie Word-Dokumente mit Aspose.Words für .NET verbinden und anhängen.
type: docs
weight: 10
url: /de/net/join-and-append-documents/list-keep-source-formatting/
---

Dieses Tutorial führt Sie durch die Verwendung der Funktion „List Keep Source Formatting“ von Aspose.Words für .NET. Mit dieser Funktion können Sie Word-Dokumente zusammenfügen und anhängen, während die Quellformatierung von Listen erhalten bleibt.

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
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Schritt 3: Stellen Sie das Quelldokument auf kontinuierlichen Fluss ein

 Um sicherzustellen, dass der Inhalt des Quelldokuments kontinuierlich an das Zieldokument angehängt wird, müssen Sie die`SectionStart` Eigenschaft des ersten Abschnitts im Quelldokument, um`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Schritt 4: Anhängen des Quelldokuments an das Zieldokument

 Nun können Sie das Quelldokument an das Zieldokument anhängen, indem Sie`AppendDocument` Methode der`Document` Klasse. Die`ImportFormatMode.KeepSourceFormatting`Der Parameter stellt sicher, dass die Quellformatierung, einschließlich der Formatierung von Listen, während des Anfügevorgangs erhalten bleibt.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Schritt 5: Speichern Sie das endgültige Dokument

 Speichern Sie das zusammengeführte Dokument abschließend mit der Funktion „Liste Quellformatierung beibehalten“ über den`Save` Methode der`Document` Klasse.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

### Beispielquellcode für die List Keep Source-Formatierung mit Aspose.Words für .NET 

Hier ist der vollständige Quellcode für die Funktion „List Keep Source Formatting“ in C# unter Verwendung von Aspose.Words für .NET:

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Fügen Sie den Inhalt des Dokuments an, damit dieser kontinuierlich fließt.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

Das ist es! Sie haben die Funktion „Liste mit Quellformatierung beibehalten“ erfolgreich mit Aspose.Words für .NET implementiert. Das endgültige Dokument enthält den zusammengeführten Inhalt, wobei die Listenformatierung des Quelldokuments beibehalten wird.