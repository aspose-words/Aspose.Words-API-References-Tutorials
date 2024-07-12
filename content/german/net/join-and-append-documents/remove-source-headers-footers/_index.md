---
title: Quellkopfzeilen und -fußzeilen entfernen
linktitle: Quellkopfzeilen und -fußzeilen entfernen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Kopf- und Fußzeilen in Word-Dokumenten entfernen. Vereinfachen Sie Ihre Dokumentenverwaltung mit unserer Schritt-für-Schritt-Anleitung.
type: docs
weight: 10
url: /de/net/join-and-append-documents/remove-source-headers-footers/
---
## Einführung

In dieser umfassenden Anleitung erfahren Sie, wie Sie mithilfe von Aspose.Words für .NET Kopf- und Fußzeilen effektiv aus einem Word-Dokument entfernen können. Kopf- und Fußzeilen werden häufig für Seitennummerierungen, Dokumenttitel oder andere sich wiederholende Inhalte in Word-Dokumenten verwendet. Ganz gleich, ob Sie Dokumente zusammenführen oder die Formatierung bereinigen, die Beherrschung dieses Prozesses kann Ihre Dokumentenverwaltungsaufgaben rationalisieren. Lassen Sie uns den schrittweisen Prozess erkunden, um dies mithilfe von Aspose.Words für .NET zu erreichen.

## Voraussetzungen

Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Entwicklungsumgebung: Visual Studio oder eine andere .NET-Entwicklungsumgebung muss installiert sein.
2.  Aspose.Words für .NET: Stellen Sie sicher, dass Sie Aspose.Words für .NET heruntergeladen und installiert haben. Wenn nicht, können Sie es hier herunterladen:[Hier](https://releases.aspose.com/words/net/).
3. Grundkenntnisse: Vertrautheit mit der C#-Programmierung und den Grundlagen des .NET-Frameworks.

## Namespaces importieren

Bevor Sie mit dem Codieren beginnen, stellen Sie sicher, dass Sie die erforderlichen Namespaces in Ihre C#-Datei importieren:

```csharp
using Aspose.Words;
```

## Schritt 1: Laden Sie das Quelldokument

 Zuerst müssen Sie das Quelldokument laden, aus dem Sie Kopf- und Fußzeilen entfernen möchten. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis, in dem sich das Quelldokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Document source.docx");
```

## Schritt 2: Zieldokument erstellen oder laden

 Wenn Sie noch kein Zieldokument erstellt haben, in dem Sie den geänderten Inhalt platzieren möchten, können Sie ein neues`Document` Objekt oder laden Sie ein vorhandenes.

```csharp
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Schritt 3: Kopf- und Fußzeilen aus Abschnitten löschen

Iterieren Sie durch jeden Abschnitt im Quelldokument (`srcDoc`) und löschen Sie dessen Kopf- und Fußzeilen.

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## Schritt 4: LinkToPrevious-Einstellung verwalten

Um zu verhindern, dass Kopf- und Fußzeilen im Zieldokument fortgeführt werden (`dstDoc` ), stellen Sie sicher, dass die`LinkToPrevious` Die Einstellung für Kopf- und Fußzeilen ist auf`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Schritt 5: Geändertes Dokument an Zieldokument anhängen

Zum Schluss fügen Sie den geänderten Inhalt aus dem Quelldokument an (`srcDoc`) zum Zieldokument (`dstDoc`) unter Beibehaltung der Quellformatierung.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Schritt 6: Speichern Sie das resultierende Dokument

Speichern Sie das endgültige Dokument mit entfernten Kopf- und Fußzeilen in dem von Ihnen angegebenen Verzeichnis.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

## Abschluss

Das Entfernen von Kopf- und Fußzeilen aus einem Word-Dokument mit Aspose.Words für .NET ist ein unkomplizierter Vorgang, der die Dokumentenverwaltung erheblich erleichtern kann. Indem Sie die oben beschriebenen Schritte befolgen, können Sie Dokumente effizient bereinigen und ihnen ein elegantes, professionelles Erscheinungsbild verleihen.

## Häufig gestellte Fragen

### Kann ich Kopf- und Fußzeilen nur aus bestimmten Abschnitten entfernen?
Ja, Sie können Abschnitte durchlaufen und Kopf- und Fußzeilen nach Bedarf selektiv löschen.

### Unterstützt Aspose.Words für .NET das Entfernen von Kopf- und Fußzeilen in mehreren Dokumenten?
Natürlich können Sie mit Aspose.Words für .NET Kopf- und Fußzeilen in mehreren Dokumenten bearbeiten.

###  Was passiert, wenn ich vergesse,`LinkToPrevious` to `false`?
Kopf- und Fußzeilen des Quelldokuments werden möglicherweise im Zieldokument übernommen.

### Kann ich Kopf- und Fußzeilen programmgesteuert entfernen, ohne andere Formatierungen zu beeinträchtigen?
Ja, mit Aspose.Words für .NET können Sie Kopf- und Fußzeilen entfernen und gleichzeitig die restliche Formatierung des Dokuments beibehalten.

### Wo finde ich weitere Ressourcen und Support für Aspose.Words für .NET?
 Besuche den[Aspose.Words für .NET-Dokumentation](https://reference.aspose.com/words/net/) für detaillierte API-Referenzen und Beispiele.
