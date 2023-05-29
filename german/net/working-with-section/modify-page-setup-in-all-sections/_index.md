---
title: Ändern Sie die Seiteneinrichtung in allen Abschnitten
linktitle: Ändern Sie die Seiteneinrichtung in allen Abschnitten
second_title: Aspose.Words für .NET API-Referenz
description: In diesem Tutorial erfahren Sie, wie Sie die Seiteneinrichtung in allen Abschnitten eines Word-Dokuments mit Aspose.Words für .NET ändern.
type: docs
weight: 10
url: /de/net/working-with-section/modify-page-setup-in-all-sections/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie die Seiteneinrichtung in allen Abschnitten eines Word-Dokuments mithilfe der Aspose.Words-Bibliothek für .NET ändern. Das Ändern der Seiteneinrichtung kann Einstellungen wie Papiergröße, Ränder, Ausrichtung usw. umfassen. Wir führen Sie Schritt für Schritt, um Ihnen zu helfen, den Code in Ihrem .NET-Projekt zu verstehen und zu implementieren.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Artikel verfügen:
- Grundkenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
 Zuerst müssen Sie den Verzeichnispfad auf den Speicherort Ihres Word-Dokuments festlegen. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad.

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen Sie ein Dokument und fügen Sie Inhalte und Abschnitte hinzu
Als Nächstes erstellen wir ein leeres Dokument, indem wir das instanziieren`Document` Klasse und eine zugehörige`DocumentBuilder` Konstruktor zum Hinzufügen von Inhalten und Abschnitten zum Dokument. In diesem Beispiel fügen wir Inhalte und drei Abschnitte hinzu.

```csharp
// Erstellen Sie ein Dokument
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie Inhalte und Abschnitte hinzu
builder.Writeln("Hello1");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello22");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello3");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello45");
```

## Schritt 3: Bearbeiten Sie die Seiteneinrichtung in allen Abschnitten
 Um die Seiteneinrichtung in allen Abschnitten des Dokuments zu ändern, verwenden wir a`foreach` Schleife, um jeden Abschnitt zu durchlaufen und darauf zuzugreifen`PageSetup` Eigentum. In diesem Beispiel ändern wir die Papiergröße aller Abschnitte, indem wir den Wert auf festlegen`PaperSize.Letter`.

```csharp
foreach(Section section in doc.Sections)
     section.PageSetup.PaperSize = PaperSize.Letter;
```

### Beispielquellcode zum Ändern der Seiteneinrichtung in allen Abschnitten mit Aspose.Words für .NET 

```csharp

// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello1");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello22");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello3");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello45");

// Es ist wichtig zu verstehen, dass ein Dokument viele Abschnitte enthalten kann.
// und jeder Abschnitt hat seine eigene Seiteneinrichtung. In diesem Fall möchten wir sie alle ändern.
foreach (Section section in doc)
	section.PageSetup.PaperSize = PaperSize.Letter;
doc.Save(dataDir + "WorkingWithSection.ModifyPageSetupInAllSections.doc");

```

## Abschluss
In diesem Tutorial haben wir gesehen, wie man mit Aspose.Words für .NET die Seiteneinrichtung in allen Abschnitten eines Word-Dokuments ändert. Wenn Sie die beschriebenen Schritte befolgen, können Sie problemlos auf jeden Abschnitt zugreifen und die Seitenkonfigurationseinstellungen anpassen. Sie können diese Funktion jederzeit an Ihre spezifischen Anforderungen anpassen und nutzen.
