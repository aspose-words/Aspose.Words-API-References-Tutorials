---
title: Ole-Objekt mit Ole-Paket in Word einfügen
linktitle: Ole-Objekt mit Ole-Paket in Word einfügen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein OLE-Objekt mit einem OLE-Paket in ein Dokument einfügen.
type: docs
weight: 10
url: /de/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der zeigt, wie Sie mithilfe von Aspose.Words für .NET ein OLE-Objekt mit einem OLE-Paket in Word einfügen.

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

## Abschluss

Abschließend haben wir eine Schritt-für-Schritt-Anleitung zum Einfügen eines OLE-Objekts in ein Word-Dokument mit einem OLE-Paket mithilfe von Aspose.Words für .NET durchlaufen.

Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET erfolgreich OLE-Objekte mit OLE-Paketen in Ihre Word-Dokumente einfügen. Stellen Sie sicher, dass Sie die erforderlichen Referenzen importieren und die Anweisungen sorgfältig befolgen, um die gewünschten Ergebnisse zu erzielen.

### FAQs zum Einfügen eines Ole-Objekts in Word mit einem Ole-Paket

#### F: Welche Anmeldeinformationen muss ich importieren, um Aspose.Words für .NET verwenden zu können?

A: Um Aspose.Words für .NET zu verwenden, müssen Sie die folgenden Referenzen importieren:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

#### F: Wie erstelle ich ein neues Dokument und einen Dokumentengenerator?

 A: Sie können mit dem ein neues Dokument erstellen`Document` Klasse und einen Dokumentenersteller, der die verwendet`DocumentBuilder` Klasse, wie unten gezeigt:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### F: Wie füge ich ein OLE-Objekt mit einem OLE-Paket in das Dokument ein?

 A: Benutzen Sie die`InsertOleObject`Methode des Document Builders (`DocumentBuilder`), um ein OLE-Objekt mit einem OLE-Paket in das Dokument einzufügen. Geben Sie den Datenstrom, den Objekttyp, die Anzeigeoptionen und andere notwendige Einstellungen an. Hier ist ein Beispiel :

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}
```

#### F: Wie speichere ich das Dokument?

 A: Verwenden Sie das Dokument`Save` Methode zum Speichern des Dokuments in einer Datei. Hier ist ein Beispiel :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

#### F: Können Sie ein vollständiges Beispiel für das Einfügen eines OLE-Objekts in ein OLE-Paket mit Aspose.Words für .NET bereitstellen?

A: Hier ist ein vollständiger Beispielcode zum Einfügen eines OLE-Objekts mit einem OLE-Paket mithilfe von Aspose.Words für .NET. Stellen Sie sicher, dass Sie die erforderlichen Referenzen importieren und die zuvor beschriebenen Schritte befolgen, um diesen Code in Ihr Projekt zu integrieren:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Damit ist unser Tutorial zum Einfügen eines OLE-Objekts mit einem OLE-Paket in ein Word-Dokument mit Aspose.Words für .NET abgeschlossen. Importieren Sie gerne die notwendigen Referenzen und befolgen Sie die beschriebenen Schritte, um diesen Code in Ihr Projekt zu integrieren. Wenn Sie weitere Fragen haben, zögern Sie bitte nicht, uns zu kontaktieren.