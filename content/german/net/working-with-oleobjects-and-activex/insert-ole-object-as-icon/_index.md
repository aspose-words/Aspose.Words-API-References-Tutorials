---
title: Ole-Objekt als Symbol in Word-Dokument einfügen
linktitle: Ole-Objekt als Symbol in Word-Dokument einfügen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein OLE-Objekt als Symbol in ein Word-Dokument einfügen.
type: docs
weight: 10
url: /de/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der zeigt, wie Sie mit Aspose.Words für .NET ein OLE-Objekt als Symbol in ein Word-Dokument einfügen.

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

## Abschluss

Abschließend haben wir eine Schritt-für-Schritt-Anleitung zum Einfügen eines OLE-Objekts als Symbol in ein Word-Dokument mit Aspose.Words für .NET untersucht.

Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET erfolgreich ein OLE-Objekt als Symbol in Ihre Word-Dokumente einfügen. Stellen Sie sicher, dass Sie die erforderlichen Referenzen importieren und die Anweisungen sorgfältig befolgen, um die gewünschten Ergebnisse zu erzielen.

### FAQs zum Einfügen eines alten Objekts in ein Word-Dokument als Symbol

#### F. Welche Referenzen sind erforderlich, um mit Aspose.Words für .NET ein OLE-Objekt als Symbol in ein Word-Dokument einzufügen?

A: Sie müssen die folgenden Referenzen in Ihr Projekt importieren, um Aspose.Words für .NET verwenden zu können:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### F. Wie erstelle ich ein neues Dokument und einen Dokumentgenerator in Aspose.Words für .NET?

 A: Sie können mit dem ein neues Dokument erstellen`Document` Klasse und einen Dokumentenersteller, der die verwendet`DocumentBuilder`Klasse. Hier ist ein Beispiel :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### F. Wie füge ich ein OLE-Objekt als Symbol in das Dokument ein?

 A: Verwenden Sie den Document Builder`InsertOleObjectAsIcon` Methode zum Einfügen eines OLE-Objekts als Symbol. Geben Sie den OLE-Dateipfad, das Anzeigeflag, den Symbolpfad und den Namen des eingebetteten Objekts an. Hier ist ein Beispiel :

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

#### F. Wie speichere ich das Dokument mit dem als Symbol eingefügten OLE-Objekt?

 A: Verwenden Sie das Dokument`Save`Methode zum Speichern des Dokuments in einer Datei. Hier ist ein Beispiel :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```