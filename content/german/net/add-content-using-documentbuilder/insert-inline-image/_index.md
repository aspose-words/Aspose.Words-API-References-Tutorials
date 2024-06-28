---
title: Inline-Bild in Word-Dokument einfügen
linktitle: Inline-Bild in Word-Dokument einfügen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Inline-Bilder in Word-Dokumente einfügen. Schritt-für-Schritt-Anleitung mit Codebeispielen und FAQs enthalten.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/insert-inline-image/
---
## Einführung

Im Bereich der Dokumentverarbeitung mit .NET-Anwendungen gilt Aspose.Words als robuste Lösung für die programmgesteuerte Bearbeitung von Word-Dokumenten. Eines der Hauptmerkmale ist die Möglichkeit, mühelos Inline-Bilder einzufügen und so die visuelle Attraktivität und Funktionalität Ihrer Dokumente zu verbessern. In diesem Tutorial erfahren Sie, wie Sie Aspose.Words für .NET nutzen können, um Bilder nahtlos in Ihre Word-Dokumente einzubetten.

## Voraussetzungen

Bevor Sie sich mit dem Einfügen von Inline-Bildern mit Aspose.Words für .NET befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Visual Studio-Umgebung: Visual Studio muss installiert und bereit sein, .NET-Anwendungen zu erstellen und zu kompilieren.
2.  Aspose.Words for .NET-Bibliothek: Laden Sie die Aspose.Words for .NET-Bibliothek herunter und installieren Sie sie von[Hier](https://releases.aspose.com/words/net/).
3. Grundlegendes Verständnis von C#: Vertrautheit mit den Grundlagen der Programmiersprache C# ist für die Implementierung der Codefragmente von Vorteil.

Lassen Sie uns nun die Schritte zum Importieren der erforderlichen Namespaces und zum Einfügen eines Inline-Bilds mit Aspose.Words für .NET durchgehen.

## Namespaces importieren

Zunächst müssen Sie die erforderlichen Namespaces in Ihren C#-Code importieren, um auf die Funktionalitäten von Aspose.Words für .NET zuzugreifen:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

Diese Namespaces bieten Zugriff auf Klassen und Methoden, die zum Bearbeiten von Word-Dokumenten und zum Umgang mit Bildern erforderlich sind.

## Schritt 1: Erstellen Sie ein neues Dokument

 Beginnen Sie mit der Initialisierung einer neuen Instanz von`Document` Klasse und a`DocumentBuilder` um die Dokumenterstellung zu erleichtern.

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Fügen Sie das Inline-Bild ein

 Benutzen Sie die`InsertImage` Methode der`DocumentBuilder` Klasse, um ein Bild an der aktuellen Position in das Dokument einzufügen.

```csharp
string imagePath = "PATH_TO_YOUR_IMAGE_FILE";
builder.InsertImage(imagePath);
```

 Ersetzen`"PATH_TO_YOUR_IMAGE_FILE"` mit dem tatsächlichen Pfad zu Ihrer Bilddatei. Bei dieser Methode wird das Bild nahtlos in das Dokument integriert.

## Schritt 3: Speichern Sie das Dokument

 Speichern Sie das Dokument abschließend mit dem an Ihrem gewünschten Ort`Save` Methode der`Document` Klasse.

```csharp
doc.Save(dataDir + "InsertInlineImage.docx");
```

Dieser Schritt stellt sicher, dass das Dokument, das das Inline-Bild enthält, unter dem angegebenen Dateinamen gespeichert wird.

## Abschluss

Zusammenfassend lässt sich sagen, dass die Integration von Inline-Bildern in Word-Dokumente mit Aspose.Words für .NET ein unkomplizierter Prozess ist, der die Visualisierung und Funktionalität von Dokumenten verbessert. Wenn Sie die oben beschriebenen Schritte befolgen, können Sie Bilder in Ihren Dokumenten effizient programmgesteuert bearbeiten und dabei die Leistungsfähigkeit von Aspose.Words nutzen.

## FAQs

### Kann ich mit Aspose.Words für .NET mehrere Bilder in ein einzelnes Word-Dokument einfügen?
 Ja, Sie können mehrere Bilder einfügen, indem Sie Ihre Bilddateien durchlaufen und aufrufen`builder.InsertImage` für jedes Bild.

### Unterstützt Aspose.Words für .NET das Einfügen von Bildern mit transparentem Hintergrund?
Ja, Aspose.Words für .NET unterstützt das Einfügen von Bildern mit transparentem Hintergrund, wobei die Transparenz des Bildes im Dokument erhalten bleibt.

### Wie kann ich die Größe eines mit Aspose.Words für .NET eingefügten Inline-Bildes ändern?
 Sie können die Größe eines Bildes ändern, indem Sie die Breiten- und Höheneigenschaften des Bildes festlegen`Shape` Objekt zurückgegeben von`builder.InsertImage`.

### Ist es möglich, mit Aspose.Words für .NET ein Inline-Bild an einer bestimmten Stelle im Dokument zu positionieren?
 Ja, Sie können die Position eines Inline-Bildes vor dem Aufruf mithilfe der Cursorposition des Document Builders angeben`builder.InsertImage`.

### Kann ich mit Aspose.Words für .NET Bilder aus URLs in ein Word-Dokument einbetten?
Ja, Sie können Bilder von URLs mit .NET-Bibliotheken herunterladen und sie dann mit Aspose.Words für .NET in ein Word-Dokument einfügen.