---
title: Ole-Objekt mit Stream als Symbol einfügen
linktitle: Ole-Objekt mit Stream als Symbol einfügen
second_title: Aspose.Words für .NET API-Referenz
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