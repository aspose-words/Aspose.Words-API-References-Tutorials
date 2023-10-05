---
title: Ole-Objekt mit Stream als Symbol einfügen
linktitle: Ole-Objekt mit Stream als Symbol einfügen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein OLE-Objekt als Symbol mithilfe eines Streams einfügen.
type: docs
weight: 10
url: /de/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der zeigt, wie Sie mit Aspose.Words für .NET ein OLE-Objekt als Symbol mithilfe eines Streams einfügen.

## Schritt 1: Importieren Sie die erforderlichen Referenzen
Bevor Sie beginnen, stellen Sie sicher, dass Sie die erforderlichen Referenzen zur Verwendung von Aspose.Words für .NET in Ihr Projekt importiert haben. Dazu gehört das Importieren der Aspose.Words-Bibliothek und das Hinzufügen der erforderlichen Namespaces zu Ihrer Quelldatei.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## Schritt 2: Erstellen Sie ein neues Dokument und einen Dokumentengenerator
 In diesem Schritt erstellen wir ein neues Dokument mit`Document` Klasse und einen Dokumentenersteller, der die verwendet`DocumentBuilder` Klasse.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Fügen Sie ein OLE-Objekt als Symbol aus einem Stream ein
 Verwenden Sie den Document Builder`InsertOleObjectAsIcon` Methode zum Einfügen eines OLE-Objekts als Symbol aus einem Stream in das Dokument. Geben Sie den Datenstrom, den Objekttyp, den Symbolpfad und den Namen des eingebetteten Objekts an.

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

## Schritt 4: Speichern Sie das Dokument
 Verwenden Sie das Dokument`Save` Methode zum Speichern des Dokuments in einer Datei.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

### Beispielquellcode zum Einfügen eines OLE-Objekts als Symbol mithilfe eines Streams mit Aspose.Words für .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

Dies ist ein vollständiges Codebeispiel zum Einfügen eines OLE-Objekts als Symbol mithilfe eines Streams mit Aspose.Words für .NET. Stellen Sie sicher, dass Sie die erforderlichen Referenzen importieren und die zuvor beschriebenen Schritte befolgen, um diesen Code in Ihr Projekt zu integrieren.

## Abschluss

In der obigen Schritt-für-Schritt-Anleitung wird erläutert, wie Sie mithilfe eines Flows mit Aspose.Words für .NET ein OLE-Objekt als Symbol in ein Word-Dokument einfügen. Wenn Sie die beschriebenen Schritte befolgen, können Sie diese Funktionalität in Ihr Projekt integrieren. Stellen Sie sicher, dass Sie die erforderlichen Referenzen importieren, ein neues Dokument und einen neuen Dokumentgenerator erstellen, das OLE-Objekt als Symbol aus dem Stream einfügen und dann das Dokument speichern. Nutzen Sie den bereitgestellten Beispielcode als Ausgangspunkt und passen Sie ihn an Ihre Bedürfnisse an.

### FAQs

#### F. Wie importiere ich die notwendigen Referenzen, um Aspose.Words für .NET zu verwenden?

A. Um die erforderlichen Referenzen zu importieren, müssen Sie die folgenden Schritte ausführen:

 Fügen Sie Folgendes hinzu`using` Anweisungen am Anfang Ihrer Quelldatei:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```
Stellen Sie sicher, dass Sie die Aspose.Words-Bibliothek zu Ihrem Projekt hinzugefügt haben.

#### F. Wie erstelle ich ein neues Dokument und einen Dokument-Builder mit Aspose.Words für .NET?

A. Um ein neues Dokument und einen Dokumentengenerator zu erstellen, können Sie die folgenden Schritte ausführen:

 Benutzen Sie die`Document` Klasse zum Erstellen eines neuen Dokuments:

```csharp
Document doc = new Document();
```
 Benutzen Sie die`DocumentBuilder`-Klasse zum Erstellen eines Dokument-Builders, der dem zuvor erstellten Dokument zugeordnet ist:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### F. Wie füge ich mit Aspose.Words für .NET ein OLE-Objekt als Symbol aus einem Stream ein?

A. Um ein OLE-Objekt als Symbol aus einem Stream einzufügen, können Sie die folgenden Schritte ausführen:

 Benutzen Sie die`InsertOleObjectAsIcon` Methode des Dokumentengenerators zum Einfügen des OLE-Objekts:

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
  builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

#### F. Wie speichere ich das Dokument in einer Datei?

A.  Um das Dokument in einer Datei zu speichern, können Sie die verwenden`Save` Methode des Dokuments, die den Zielpfad angibt:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

#### F. Wie bette ich den Code zum Einfügen eines OLE-Objekts als Symbol aus einem Stream in mein Projekt ein?

A. Um den Code zum Einfügen eines OLE-Objekts als Symbol aus einem Stream in Ihr Projekt einzubetten, gehen Sie folgendermaßen vor:
-  Importieren Sie die erforderlichen Referenzen, indem Sie die entsprechenden hinzufügen`using` Aussagen.
-  Erstellen Sie ein neues Dokument und einen Dokument-Builder mit dem`Document` Und`DocumentBuilder` Klassen.
- Verwenden Sie den Code zum Einfügen des OLE-Objekts als Symbol aus einem Stream.
-  Speichern Sie das Dokument mit`Save` Methode mit dem entsprechenden Zielpfad.

Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET erfolgreich ein OLE-Objekt als Symbol aus einem Stream einfügen. Befolgen Sie unbedingt die Anweisungen und importieren Sie die erforderlichen Referenzen, um die gewünschten Ergebnisse zu erzielen.