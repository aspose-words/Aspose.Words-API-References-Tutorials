---
title: Dokument mit Builder einfügen
linktitle: Dokument mit Builder einfügen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie zwei Word-Dokumente mit Aspose.Words für .NET zusammenführen. Schritt-für-Schritt-Anleitung zum Einfügen eines Dokuments mit DocumentBuilder und Beibehalten der Formatierung.
type: docs
weight: 10
url: /de/net/join-and-append-documents/insert-document-with-builder/
---
## Einführung

Sie haben also zwei Word-Dokumente und möchten diese zu einem zusammenführen. Sie fragen sich vielleicht: „Gibt es eine einfache Möglichkeit, dies programmgesteuert zu tun?“ Auf jeden Fall! Heute werde ich Sie durch den Vorgang des Einfügens eines Dokuments in ein anderes mithilfe der Aspose.Words-Bibliothek für .NET führen. Diese Methode ist äußerst praktisch, insbesondere wenn Sie mit großen Dokumenten arbeiten oder den Vorgang automatisieren müssen. Lassen Sie uns direkt loslegen!

## Voraussetzungen

Bevor wir beginnen, stellen wir sicher, dass Sie alles haben, was Sie brauchen:

1.  Aspose.Words für .NET: Falls noch nicht geschehen, können Sie es hier herunterladen:[Hier](https://releases.aspose.com/words/net/).
2. Entwicklungsumgebung: Stellen Sie sicher, dass Sie Visual Studio oder eine andere geeignete IDE installiert haben.
3. Grundkenntnisse in C#: Ein wenig Vertrautheit mit C# wird Ihnen sehr weiterhelfen.

## Namespaces importieren

Zunächst müssen Sie die erforderlichen Namespaces importieren, um auf die Funktionen der Aspose.Words-Bibliothek zugreifen zu können. So können Sie das tun:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Nachdem wir nun die Voraussetzungen geschaffen haben, wollen wir den Prozess Schritt für Schritt durchgehen.

## Schritt 1: Einrichten Ihres Dokumentverzeichnisses

Bevor wir mit dem Codieren beginnen, müssen Sie den Pfad zu Ihrem Dokumentverzeichnis festlegen. Hier werden Ihre Quell- und Zieldokumente gespeichert.

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad, in dem sich Ihre Dokumente befinden. So kann das Programm Ihre Dateien leichter finden.

## Schritt 2: Laden der Quell- und Zieldokumente

Als nächstes müssen wir die Dokumente laden, mit denen wir arbeiten möchten. In diesem Beispiel haben wir ein Quelldokument und ein Zieldokument.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

 Hier verwenden wir die`Document` Klasse aus der Aspose.Words-Bibliothek, um unsere Dokumente zu laden. Stellen Sie sicher, dass die Dateinamen mit denen in Ihrem Verzeichnis übereinstimmen.

## Schritt 3: Erstellen eines DocumentBuilder-Objekts

Der`DocumentBuilder` Klasse ist ein leistungsstarkes Tool in der Aspose.Words-Bibliothek. Es ermöglicht uns, im Dokument zu navigieren und es zu bearbeiten.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

 In diesem Schritt haben wir eine`DocumentBuilder` Objekt für unser Zieldokument. Dies hilft uns, Inhalt in das Dokument einzufügen.

## Schritt 4: Zum Ende des Dokuments wechseln

Wir müssen den Builder-Cursor an das Ende des Zieldokuments bewegen, bevor wir das Quelldokument einfügen.

```csharp
builder.MoveToDocumentEnd();
```

Dadurch wird sichergestellt, dass das Quelldokument am Ende des Zieldokuments eingefügt wird.

## Schritt 5: Einen Seitenumbruch einfügen

Um die Übersichtlichkeit zu wahren, fügen wir vor dem Einfügen des Quelldokuments einen Seitenumbruch ein. Dadurch beginnt der Inhalt des Quelldokuments auf einer neuen Seite.

```csharp
builder.InsertBreak(BreakType.PageBreak);
```

Ein Seitenumbruch stellt sicher, dass der Inhalt des Quelldokuments auf einer neuen Seite beginnt, wodurch das zusammengeführte Dokument professionell aussieht.

## Schritt 6: Einfügen des Quelldokuments

Jetzt kommt der spannende Teil – das eigentliche Einfügen des Quelldokuments in das Zieldokument.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

 Mit dem`InsertDocument` Methode können wir das gesamte Quelldokument in das Zieldokument einfügen. Die`ImportFormatMode.KeepSourceFormatting` stellt sicher, dass die Formatierung des Quelldokuments erhalten bleibt.

## Schritt 7: Zusammengeführtes Dokument speichern

Zum Schluss speichern wir das zusammengeführte Dokument. Dadurch werden Quell- und Zieldokument in einer Datei kombiniert.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

Mit dem Speichern des Dokuments schließen wir den Vorgang des Zusammenführens der beiden Dokumente ab. Ihr neues Dokument ist nun fertig und im angegebenen Verzeichnis gespeichert.

## Abschluss

Und da haben Sie es! Sie haben erfolgreich ein Dokument mit Aspose.Words für .NET in ein anderes eingefügt. Diese Methode ist nicht nur effizient, sondern bewahrt auch die Formatierung beider Dokumente und gewährleistet so eine nahtlose Zusammenführung. Egal, ob Sie an einem einmaligen Projekt arbeiten oder die Dokumentverarbeitung automatisieren müssen, Aspose.Words für .NET ist die Lösung für Sie.

## Häufig gestellte Fragen

### Was ist Aspose.Words für .NET?  
Aspose.Words für .NET ist eine leistungsstarke Bibliothek, mit der Entwickler Word-Dokumente programmgesteuert erstellen, bearbeiten, konvertieren und bearbeiten können.

### Kann ich die Formatierung des Quelldokuments beibehalten?  
 Ja, mit`ImportFormatMode.KeepSourceFormatting`bleibt die Formatierung des Quelldokuments beim Einfügen in das Zieldokument erhalten.

### Benötige ich eine Lizenz, um Aspose.Words für .NET zu verwenden?  
 Ja, Aspose.Words für .NET erfordert eine Lizenz für die volle Funktionalität. Sie erhalten eine[vorläufige Lizenz](https://purchase.aspose.com/temporary-license/) zur Auswertung.

### Kann ich diesen Prozess automatisieren?  
Auf jeden Fall! Die beschriebene Methode kann in größere Anwendungen integriert werden, um Dokumentverarbeitungsaufgaben zu automatisieren.

### Wo finde ich weitere Ressourcen und Unterstützung?  
 Weitere Informationen finden Sie im[Dokumentation](https://reference.aspose.com/words/net/) , oder besuchen Sie die[Support-Forum](https://forum.aspose.com/c/words/8) um Hilfe.