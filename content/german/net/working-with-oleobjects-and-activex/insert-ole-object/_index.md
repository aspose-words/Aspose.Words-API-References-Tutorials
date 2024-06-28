---
title: Ole-Objekt in Word-Dokument einfügen
linktitle: Ole-Objekt in Word-Dokument einfügen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein OLE-Objekt in ein Word-Dokument einfügen.
type: docs
weight: 10
url: /de/net/working-with-oleobjects-and-activex/insert-ole-object/
---

Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der veranschaulicht, wie Sie mit Aspose.Words für .NET ein OLE-Objekt in ein Word-Dokument einfügen.

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

## Schritt 3: Fügen Sie ein OLE-Objekt ein
 Verwenden Sie den Document Builder`InsertOleObject` Methode zum Einfügen eines OLE-Objekts in das Dokument. Geben Sie die OLE-Objekt-URL, den Objekttyp, die Anzeigeoptionen und andere erforderliche Einstellungen an.

```csharp
builder. InsertOleObject("http://www.aspose.com“, „htmlfile“, true, true, null);
```

## Schritt 4: Speichern Sie das Dokument
 Verwenden Sie das Dokument`Save` Methode zum Speichern des Dokuments in einer Datei.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

### Beispielquellcode zum Einfügen eines OLE-Objekts mit Aspose.Words für .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com“, „htmlfile“, true, true, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

Dies ist ein vollständiges Codebeispiel zum Einfügen eines OLE-Objekts mit Aspose.Words für .NET. Stellen Sie sicher, dass Sie die erforderlichen Referenzen importieren und die zuvor beschriebenen Schritte befolgen, um diesen Code in Ihr Projekt zu integrieren.

## Abschluss

Zusammenfassend lässt sich sagen, dass das Einfügen von OLE-Objekten in ein Word-Dokument eine leistungsstarke Funktion ist, die Aspose.Words für .NET bietet. Mithilfe dieser Bibliothek können Sie ganz einfach OLE-Objekte wie HTML-Dateien, Excel-Tabellen, PowerPoint-Präsentationen usw. in Ihre Word-Dokumente einbetten.

In diesem Artikel haben wir eine Schritt-für-Schritt-Anleitung durchgearbeitet, um den Quellcode in C# zu erklären, der zeigt, wie man ein OLE-Objekt in ein Word-Dokument einfügt. Wir haben die notwendigen Referenzen, das Erstellen eines neuen Dokuments und eines Dokumentgenerators sowie die Schritte zum Einfügen eines OLE-Objekts und Speichern des Dokuments behandelt.

### FAQs zum Einfügen eines OLE-Objekts in ein Word-Dokument

#### F: Welche Anmeldeinformationen muss ich importieren, um Aspose.Words für .NET verwenden zu können?

A: Um Aspose.Words für .NET zu verwenden, müssen Sie die folgenden Referenzen importieren:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### F: Wie erstelle ich ein neues Dokument und einen Dokumentengenerator?

 A: Sie können mit dem ein neues Dokument erstellen`Document` Klasse und einen Dokumentenersteller, der die verwendet`DocumentBuilder` Klasse, wie unten gezeigt:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### F: Wie füge ich ein OLE-Objekt in das Dokument ein?

 A: Benutzen Sie die`InsertOleObject`Methode des Document Builders (`DocumentBuilder`), um ein OLE-Objekt in das Dokument einzufügen. Geben Sie die OLE-Objekt-URL, den Objekttyp, die Anzeigeoptionen und andere erforderliche Einstellungen an. Hier ist ein Beispiel :

```csharp
builder. InsertOleObject("http://www.aspose.com“, „htmlfile“, true, true, null);
```

#### F: Wie speichere ich das Dokument?

 A: Verwenden Sie das Dokument`Save` Methode zum Speichern des Dokuments in einer Datei. Hier ist ein Beispiel :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

#### F: Können Sie ein vollständiges Beispiel für das Einfügen eines OLE-Objekts mit Aspose.Words für .NET bereitstellen?

A: Hier ist ein vollständiger Beispielcode zum Einfügen eines OLE-Objekts mit Aspose.Words für .NET. Stellen Sie sicher, dass Sie die erforderlichen Referenzen importieren und die zuvor beschriebenen Schritte befolgen, um diesen Code in Ihr Projekt zu integrieren:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com“, „htmlfile“, true, true, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```
