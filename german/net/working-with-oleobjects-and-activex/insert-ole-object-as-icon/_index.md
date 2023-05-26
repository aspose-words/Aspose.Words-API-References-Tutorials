---
title: Ole-Objekt als Symbol einfügen
linktitle: Ole-Objekt als Symbol einfügen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein OLE-Objekt als Symbol einfügen.
type: docs
weight: 10
url: /de/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der veranschaulicht, wie Sie mit Aspose.Words für .NET ein OLE-Objekt als Symbol einfügen.

## Schritt 1: Importieren Sie die erforderlichen Referenzen
Bevor Sie beginnen, stellen Sie sicher, dass Sie die erforderlichen Referenzen zur Verwendung von Aspose.Words für .NET in Ihr Projekt importiert haben. Dazu gehört das Importieren der Aspose.Words-Bibliothek und das Hinzufügen der erforderlichen Namespaces zu Ihrer Quelldatei.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Schritt 2: Erstellen Sie ein neues Dokument und einen Dokumentengenerator
 In diesem Schritt erstellen wir ein neues Dokument mit`Document` Klasse und einen Dokumentenersteller, der die verwendet`DocumentBuilder` Klasse.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Fügen Sie ein OLE-Objekt als Symbol ein
 Verwenden Sie den Document Builder`InsertOleObjectAsIcon` Methode zum Einfügen eines OLE-Objekts als Symbol in das Dokument. Geben Sie den OLE-Dateipfad, das Anzeigeflag, den Symbolpfad und den Namen des eingebetteten Objekts an.

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## Schritt 4: Speichern Sie das Dokument
 Verwenden Sie das Dokument`Save` Methode zum Speichern des Dokuments in einer Datei.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

### Beispielquellcode zum Einfügen eines OLE-Objekts als Symbol mit Aspose.Words für .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

Dies ist ein vollständiges Codebeispiel zum Einfügen eines OLE-Objekts als Symbol mit Aspose.Words für .NET. Stellen Sie sicher, dass Sie die erforderlichen Referenzen importieren und die zuvor beschriebenen Schritte befolgen, um diesen Code in Ihr Projekt zu integrieren.
