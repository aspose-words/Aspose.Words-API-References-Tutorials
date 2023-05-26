---
title: Ole-Objekt mit Ole-Paket einfügen
linktitle: Ole-Objekt mit Ole-Paket einfügen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein OLE-Objekt mit einem OLE-Paket in ein Dokument einfügen.
type: docs
weight: 10
url: /de/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der veranschaulicht, wie Sie mithilfe von Aspose.Words für .NET ein OLE-Objekt in ein OLE-Paket einfügen.

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

## Schritt 3: Fügen Sie ein OLE-Objekt mit einem OLE-Paket ein
 Nutzen Sie den Dokumentengenerator`InsertOleObject` Methode zum Einfügen eines OLE-Objekts mit einem OLE-Paket in das Dokument. Geben Sie den Datenstrom, den Objekttyp, die Anzeigeoptionen und andere notwendige Einstellungen an.

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}
```

## Schritt 4: Speichern Sie das Dokument
 Verwenden Sie das Dokument`Save` Methode zum Speichern des Dokuments in einer Datei.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

### Beispielquellcode zum Einfügen eines OLE-Objekts mit einem OLE-Paket mit Aspose.Words für .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Dies ist ein vollständiges Codebeispiel zum Einfügen eines OLE-Objekts mit einem OLE-Paket mit Aspose.Words für .NET. Stellen Sie sicher, dass Sie die erforderlichen Referenzen importieren und die zuvor beschriebenen Schritte befolgen, um diesen Code in Ihr Projekt zu integrieren.