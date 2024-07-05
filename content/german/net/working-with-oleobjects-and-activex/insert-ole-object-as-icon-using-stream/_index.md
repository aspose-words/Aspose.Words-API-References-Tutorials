---
title: OLE-Objekt als Symbol mit Stream einfügen
linktitle: OLE-Objekt als Symbol mit Stream einfügen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET mithilfe eines Streams ein OLE-Objekt als Symbol einfügen.
type: docs
weight: 10
url: /de/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

Hier ist eine Schritt-für-Schritt-Anleitung zur Erklärung des folgenden C#-Quellcodes, der zeigt, wie mithilfe eines Streams mit Aspose.Words für .NET ein OLE-Objekt als Symbol eingefügt wird.

## Schritt 1: Importieren Sie die erforderlichen Referenzen
Stellen Sie vor dem Beginn sicher, dass Sie die erforderlichen Referenzen importiert haben, um Aspose.Words für .NET in Ihrem Projekt zu verwenden. Dazu gehört das Importieren der Aspose.Words-Bibliothek und das Hinzufügen der erforderlichen Namespaces zu Ihrer Quelldatei.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## Schritt 2: Neues Dokument und Dokumentgenerator erstellen
 In diesem Schritt erstellen wir ein neues Dokument mit dem`Document` Klasse und einen Dokumentgenerator mit der`DocumentBuilder` Klasse.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Einfügen eines OLE-Objekts als Symbol aus einem Stream
 Verwenden Sie den Document Builder`InsertOleObjectAsIcon` Methode, um ein OLE-Objekt als Symbol aus einem Stream in das Dokument einzufügen. Geben Sie den Datenstream, den Objekttyp, den Symbolpfad und den Namen des eingebetteten Objekts an.

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

## Schritt 4: Speichern Sie das Dokument
 Verwenden Sie die`Save` Methode, um das Dokument in einer Datei zu speichern.

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

Dies ist ein vollständiges Codebeispiel zum Einfügen eines OLE-Objekts als Symbol mithilfe eines Streams mit Aspose.Words für .NET. Achten Sie darauf, die erforderlichen Referenzen zu importieren, und befolgen Sie die zuvor beschriebenen Schritte, um diesen Code in Ihr Projekt zu integrieren.

## Abschluss

Die obige Schritt-für-Schritt-Anleitung erklärt, wie Sie mithilfe eines Flows mit Aspose.Words für .NET ein OLE-Objekt als Symbol in ein Word-Dokument einfügen. Wenn Sie die beschriebenen Schritte befolgen, können Sie diese Funktionalität in Ihr Projekt integrieren. Achten Sie darauf, die erforderlichen Referenzen zu importieren, ein neues Dokument und einen Dokumentgenerator zu erstellen, das OLE-Objekt als Symbol aus dem Stream einzufügen und dann das Dokument zu speichern. Verwenden Sie den bereitgestellten Beispielcode als Ausgangspunkt und passen Sie ihn an Ihre Bedürfnisse an.

### Häufig gestellte Fragen

#### F. Wie importiere ich die erforderlichen Referenzen, um Aspose.Words für .NET zu verwenden?

A. Um die notwendigen Referenzen zu importieren, müssen Sie die folgenden Schritte ausführen:

 Fügen Sie Folgendes hinzu`using` -Anweisungen oben in Ihrer Quelldatei:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```
Stellen Sie sicher, dass Sie die Aspose.Words-Bibliothek zu Ihrem Projekt hinzugefügt haben.

#### F. Wie erstelle ich mit Aspose.Words für .NET ein neues Dokument und einen neuen Dokument-Generator?

A. Um ein neues Dokument und einen Dokumentgenerator zu erstellen, können Sie die folgenden Schritte ausführen:

 Verwenden Sie die`Document` Klasse zum Erstellen eines neuen Dokuments:

```csharp
Document doc = new Document();
```
 Verwenden Sie die`DocumentBuilder`Klasse zum Erstellen eines Dokument-Generators, der mit dem zuvor erstellten Dokument verknüpft ist:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### F: Wie fügt man mit Aspose.Words für .NET ein OLE-Objekt als Symbol aus einem Stream ein?

A. Um ein OLE-Objekt als Symbol aus einem Stream einzufügen, können Sie die folgenden Schritte ausführen:

 Verwenden Sie die`InsertOleObjectAsIcon` Methode des Dokumentgenerators zum Einfügen des OLE-Objekts:

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
  builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

#### F. Wie speichere ich das Dokument in einer Datei?

A.  Um das Dokument in einer Datei zu speichern, können Sie den`Save` Methode des Dokuments, die den Zielpfad angibt:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

#### F: Wie bettet ich den Code zum Einfügen eines OLE-Objekts als Symbol aus einem Stream in mein Projekt ein?

A. Um den Code zum Einfügen eines OLE-Objekts als Symbol aus einem Stream in Ihr Projekt einzubetten, führen Sie die folgenden Schritte aus:
-  Importieren Sie die notwendigen Referenzen durch Hinzufügen der entsprechenden`using` Aussagen.
-  Erstellen Sie ein neues Dokument und einen Dokumentgenerator mit dem`Document` Und`DocumentBuilder` Klassen.
- Verwenden Sie den Code zum Einfügen des OLE-Objekts als Symbol aus einem Stream.
-  Speichern Sie das Dokument mit dem`Save` Methode mit dem entsprechenden Zielpfad.

Wenn Sie diese Schritte befolgen, können Sie mithilfe von Aspose.Words für .NET erfolgreich ein OLE-Objekt als Symbol aus einem Stream einfügen. Befolgen Sie unbedingt die Anweisungen und importieren Sie die erforderlichen Referenzen, um die gewünschten Ergebnisse zu erzielen.