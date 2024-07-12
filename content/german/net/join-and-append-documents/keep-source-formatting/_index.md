---
title: Originalformatierung beibehalten
linktitle: Originalformatierung beibehalten
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie Word-Dokumente unter Beibehaltung der Formatierung mit Aspose.Words für .NET zusammenführen. Ideal für Entwickler, die Dokumentzusammenstellungsaufgaben automatisieren möchten.
type: docs
weight: 10
url: /de/net/join-and-append-documents/keep-source-formatting/
---
## Einführung

In diesem Tutorial erfahren Sie, wie Sie Word-Dokumente mit Aspose.Words für .NET zusammenführen und anhängen. Diese leistungsstarke Bibliothek bietet Entwicklern umfangreiche Möglichkeiten zur programmgesteuerten Bearbeitung von Word-Dokumenten. Wir konzentrieren uns auf die Methode, mit der die Quellformatierung beim Zusammenführen von Dokumenten intakt bleibt und die ursprünglichen Stile und Layouts nahtlos erhalten bleiben.

## Voraussetzungen

Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Entwicklungsumgebung: Visual Studio oder jede IDE, die .NET-Entwicklung unterstützt.
-  Aspose.Words für .NET-Bibliothek: Laden Sie die Bibliothek herunter und installieren Sie sie von[Hier](https://releases.aspose.com/words/net/).
- Grundlegende Kenntnisse der C#-Programmierung: Vertrautheit mit der C#-Syntax und Konzepten der objektorientierten Programmierung.

## Namespaces importieren

Importieren Sie zunächst die erforderlichen Namespaces in Ihr C#-Projekt:

```csharp
using Aspose.Words;
```

## Schritt 1: Richten Sie Ihr Projekt ein

Erstellen Sie in Visual Studio eine neue C#-Konsolenanwendung und installieren Sie das NuGet-Paket Aspose.Words. Dieses Paket enthält die Bibliotheken, die zum Arbeiten mit Word-Dokumenten in Ihrem Projekt erforderlich sind.

## Schritt 2: Aspose.Words-Namespace einschließen

Stellen Sie sicher, dass Sie den Aspose.Words-Namespace am Anfang Ihrer C#-Datei einschließen, um auf die Aspose.Words-Klassen und -Methoden zuzugreifen.

## Schritt 3: Dokumentpfade initialisieren

Definieren Sie den Pfad zu Ihrem Dokumentverzeichnis, in dem sich die Quell- und Zieldokumente befinden.

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY_PATH";
```

## Schritt 4: Zieldokument erstellen

Initialisieren Sie eine neue Instanz der Document-Klasse, um ein Zieldokument zu erstellen, in dem der zusammengeführte Inhalt gespeichert wird.

```csharp
Document dstDoc = new Document();
```

## Schritt 5: Quelldokument laden

Erstellen Sie auf ähnliche Weise ein weiteres Dokumentobjekt, um das Quelldokument zu laden, das Sie an das Zieldokument anhängen möchten.

```csharp
Document srcDoc = new Document();
```

## Schritt 6: Quelldokument unter Beibehaltung der Formatierung anhängen

Um das Quelldokument unter Beibehaltung der ursprünglichen Formatierung mit dem Zieldokument zusammenzuführen, verwenden Sie die Methode AppendDocument, wobei „ImportFormatMode“ auf „KeepSourceFormatting“ festgelegt ist.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Schritt 7: Zusammengeführtes Dokument speichern

Speichern Sie abschließend das zusammengeführte Dokument mit der Methode „Save“ im angegebenen Verzeichnis.

```csharp
dstDoc.Save(dataDir + "MergedDocument.docx");
```

## Abschluss

In diesem Tutorial haben wir erläutert, wie Sie Word-Dokumente unter Beibehaltung der ursprünglichen Formatierung mit Aspose.Words für .NET zusammenführen. Dieser Ansatz stellt sicher, dass Stile, Schriftarten und Layouts aus den Quelldokumenten nahtlos in das Zieldokument integriert werden, und bietet eine robuste Lösung für Dokumentzusammenstellungsaufgaben.

## Häufig gestellte Fragen

### Kann ich mit Aspose.Words für .NET mehrere Dokumente in einem Vorgang zusammenführen?
Ja, Sie können mehrere Dokumente zusammenführen, indem Sie jedes Dokument nacheinander an das Zieldokument anhängen.

### Behält Aspose.Words beim Zusammenführen von Dokumenten alle Formatierungsattribute bei?
Aspose.Words unterstützt verschiedene Importmodi; der Modus KeepSourceFormatting stellt sicher, dass die meisten Formatierungsattribute erhalten bleiben.

### Ist Aspose.Words mit .NET Core-Anwendungen kompatibel?
Ja, Aspose.Words unterstützt .NET Core, sodass Sie es plattformübergreifend verwenden können.

### Wie kann ich mit Aspose.Words große Dokumente effizient verarbeiten?
Aspose.Words bietet effiziente APIs für die Arbeit mit großen Dokumenten, einschließlich Funktionen zur Seitennummerierung und Speicherverwaltung.

### Wo finde ich weitere Ressourcen und Support für Aspose.Words?
 Besuche den[Aspose.Words für .NET-Dokumentation](https://reference.aspose.com/words/net/) für detaillierte API-Referenzen, Beispiele und Anleitungen.