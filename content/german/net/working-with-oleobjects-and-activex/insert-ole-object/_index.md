---
title: OLE-Objekt in Word-Dokument einfügen
linktitle: OLE-Objekt in Word-Dokument einfügen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein OLE-Objekt in ein Word-Dokument einfügen.
type: docs
weight: 10
url: /de/net/working-with-oleobjects-and-activex/insert-ole-object/
---

Hier ist eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der zeigt, wie mit Aspose.Words für .NET ein OLE-Objekt in ein Word-Dokument eingefügt wird.

## Schritt 1: Importieren Sie die erforderlichen Referenzen
Stellen Sie vor dem Beginn sicher, dass Sie die erforderlichen Referenzen importiert haben, um Aspose.Words für .NET in Ihrem Projekt zu verwenden. Dazu gehört das Importieren der Aspose.Words-Bibliothek und das Hinzufügen der erforderlichen Namespaces zu Ihrer Quelldatei.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Schritt 2: Neues Dokument und Dokumentgenerator erstellen
 In diesem Schritt erstellen wir ein neues Dokument mit dem`Document` Klasse und einen Dokumentgenerator mit der`DocumentBuilder` Klasse.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Einfügen eines OLE-Objekts
 Verwenden Sie den Document Builder`InsertOleObject` Methode zum Einfügen eines OLE-Objekts in das Dokument. Geben Sie die OLE-Objekt-URL, den Objekttyp, die Anzeigeoptionen und andere erforderliche Einstellungen an.

```csharp
builder. InsertOleObject("http://www.aspose.com", "html-Datei", true, true, null);
```

## Schritt 4: Speichern Sie das Dokument
 Verwenden Sie die`Save` Methode, um das Dokument in einer Datei zu speichern.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

### Beispielquellcode zum Einfügen eines OLE-Objekts mit Aspose.Words für .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "html-Datei", true, true, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

Dies ist ein vollständiges Codebeispiel zum Einfügen eines OLE-Objekts mit Aspose.Words für .NET. Achten Sie darauf, die erforderlichen Referenzen zu importieren, und befolgen Sie die zuvor beschriebenen Schritte, um diesen Code in Ihr Projekt zu integrieren.

## Abschluss

Zusammenfassend lässt sich sagen, dass das Einfügen von OLE-Objekten in ein Word-Dokument eine leistungsstarke Funktion von Aspose.Words für .NET ist. Mit dieser Bibliothek können Sie OLE-Objekte wie HTML-Dateien, Excel-Tabellen, PowerPoint-Präsentationen usw. problemlos in Ihre Word-Dokumente einbetten.

In diesem Artikel haben wir eine Schritt-für-Schritt-Anleitung durchgearbeitet, um den Quellcode in C# zu erklären, der zeigt, wie man ein OLE-Objekt in ein Word-Dokument einfügt. Wir haben die notwendigen Referenzen, das Erstellen eines neuen Dokuments und eines Dokumentgenerators sowie die Schritte zum Einfügen eines OLE-Objekts und Speichern des Dokuments behandelt.

### FAQs zum Einfügen eines OLE-Objekts in ein Word-Dokument

#### F: Welche Anmeldeinformationen muss ich importieren, um Aspose.Words für .NET zu verwenden?

A: Um Aspose.Words für .NET zu verwenden, müssen Sie die folgenden Referenzen importieren:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### F: Wie erstelle ich ein neues Dokument und einen Dokumentgenerator?

 A: Sie können ein neues Dokument erstellen, indem Sie`Document` Klasse und einen Dokumentgenerator mit der`DocumentBuilder` Klasse, wie unten gezeigt:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### F: Wie fügt man ein OLE-Objekt in das Dokument ein?

 A: Verwenden Sie die`InsertOleObject`Methode des Dokument-Builders (`DocumentBuilder`), um ein OLE-Objekt in das Dokument einzufügen. Geben Sie die URL des OLE-Objekts, den Objekttyp, die Anzeigeoptionen und andere erforderliche Einstellungen an. Hier ist ein Beispiel:

```csharp
builder. InsertOleObject("http://www.aspose.com", "html-Datei", true, true, null);
```

#### F: Wie speichere ich das Dokument?

 A: Verwenden Sie das Dokument`Save` Methode, um das Dokument in einer Datei zu speichern. Hier ist ein Beispiel:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

#### F: Können Sie ein vollständiges Beispiel für das Einfügen eines OLE-Objekts mit Aspose.Words für .NET bereitstellen?

A: Hier ist ein vollständiger Beispielcode zum Einfügen eines OLE-Objekts mit Aspose.Words für .NET. Achten Sie darauf, die erforderlichen Referenzen zu importieren und befolgen Sie die zuvor beschriebenen Schritte, um diesen Code in Ihr Projekt zu integrieren:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "html-Datei", true, true, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```
