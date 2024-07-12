---
title: OLE-Objekt mit OLE-Paket in Word einfügen
linktitle: OLE-Objekt mit OLE-Paket in Word einfügen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein OLE-Objekt mit einem OLE-Paket in ein Dokument einfügen.
type: docs
weight: 10
url: /de/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

Hier ist eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der zeigt, wie mithilfe von Aspose.Words für .NET ein OLE-Objekt mit einem OLE-Paket in Word eingefügt wird.

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

## Schritt 3: Einfügen eines OLE-Objekts mit einem OLE-Paket
 Nutzen Sie den Dokumentgenerator`InsertOleObject` Methode, um ein OLE-Objekt mit einem OLE-Paket in das Dokument einzufügen. Geben Sie den Datenstrom, den Objekttyp, die Anzeigeoptionen und andere erforderliche Einstellungen an.

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
 Verwenden Sie die`Save` Methode, um das Dokument in einer Datei zu speichern.

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

Dies ist ein vollständiges Codebeispiel zum Einfügen eines OLE-Objekts mit einem OLE-Paket mit Aspose.Words für .NET. Achten Sie darauf, die erforderlichen Referenzen zu importieren, und befolgen Sie die zuvor beschriebenen Schritte, um diesen Code in Ihr Projekt zu integrieren.

## Abschluss

Abschließend haben wir eine Schritt-für-Schritt-Anleitung zum Einfügen eines OLE-Objekts in ein Word-Dokument mit einem OLE-Paket unter Verwendung von Aspose.Words für .NET durchgearbeitet.

Wenn Sie diese Schritte befolgen, können Sie mithilfe von Aspose.Words für .NET erfolgreich OLE-Objekte mit OLE-Paketen in Ihre Word-Dokumente einfügen. Achten Sie darauf, die erforderlichen Referenzen zu importieren, und befolgen Sie die Anweisungen sorgfältig, um die gewünschten Ergebnisse zu erzielen.

### FAQs zum Einfügen eines OLE-Objekts in Word mit einem OLE-Paket

#### F: Welche Anmeldeinformationen muss ich importieren, um Aspose.Words für .NET zu verwenden?

A: Um Aspose.Words für .NET zu verwenden, müssen Sie die folgenden Referenzen importieren:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

#### F: Wie erstelle ich ein neues Dokument und einen Dokumentgenerator?

 A: Sie können ein neues Dokument erstellen, indem Sie`Document` Klasse und einen Dokumentgenerator mit der`DocumentBuilder` Klasse, wie unten gezeigt:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### F: Wie fügt man ein OLE-Objekt mit einem OLE-Paket in das Dokument ein?

 A: Verwenden Sie die`InsertOleObject`Methode des Dokument-Builders (`DocumentBuilder`), um ein OLE-Objekt mit einem OLE-Paket in das Dokument einzufügen. Geben Sie den Datenstrom, den Objekttyp, die Anzeigeoptionen und andere erforderliche Einstellungen an. Hier ist ein Beispiel:

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

 A: Verwenden Sie das Dokument`Save` Methode, um das Dokument in einer Datei zu speichern. Hier ist ein Beispiel:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

#### F: Können Sie ein vollständiges Beispiel für das Einfügen eines OLE-Objekts mit einem OLE-Paket mit Aspose.Words für .NET bereitstellen?

A: Hier ist ein vollständiger Beispielcode zum Einfügen eines OLE-Objekts mit einem OLE-Paket unter Verwendung von Aspose.Words für .NET. Achten Sie darauf, die erforderlichen Referenzen zu importieren und befolgen Sie die zuvor beschriebenen Schritte, um diesen Code in Ihr Projekt zu integrieren:

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

Damit ist unser Tutorial zum Einfügen eines OLE-Objekts mit einem OLE-Paket in ein Word-Dokument mithilfe von Aspose.Words für .NET abgeschlossen. Importieren Sie die erforderlichen Referenzen und befolgen Sie die beschriebenen Schritte, um diesen Code in Ihr Projekt zu integrieren. Wenn Sie weitere Fragen haben, zögern Sie bitte nicht, uns zu kontaktieren.