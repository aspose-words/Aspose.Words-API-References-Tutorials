---
title: OLE-Objekt als Symbol in Word-Dokument einfügen
linktitle: OLE-Objekt als Symbol in Word-Dokument einfügen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein OLE-Objekt als Symbol in ein Word-Dokument einfügen.
type: docs
weight: 10
url: /de/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

Hier ist eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der zeigt, wie mit Aspose.Words für .NET ein OLE-Objekt als Symbol in ein Word-Dokument eingefügt wird.

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

## Schritt 3: Einfügen eines OLE-Objekts als Symbol
 Verwenden Sie den Document Builder`InsertOleObjectAsIcon`Methode, um ein OLE-Objekt als Symbol in das Dokument einzufügen. Geben Sie den OLE-Dateipfad, das Anzeigeflag, den Symbolpfad und den Namen des eingebetteten Objekts an.

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## Schritt 4: Speichern Sie das Dokument
 Verwenden Sie die`Save` Methode, um das Dokument in einer Datei zu speichern.

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

Dies ist ein vollständiges Codebeispiel zum Einfügen eines OLE-Objekts als Symbol mit Aspose.Words für .NET. Achten Sie darauf, die erforderlichen Referenzen zu importieren, und befolgen Sie die zuvor beschriebenen Schritte, um diesen Code in Ihr Projekt zu integrieren.

## Abschluss

Abschließend haben wir eine Schritt-für-Schritt-Anleitung zum Einfügen eines OLE-Objekts als Symbol in ein Word-Dokument mit Aspose.Words für .NET untersucht.

Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET erfolgreich ein OLE-Objekt als Symbol in Ihre Word-Dokumente einfügen. Achten Sie darauf, die erforderlichen Referenzen zu importieren, und befolgen Sie die Anweisungen sorgfältig, um die gewünschten Ergebnisse zu erzielen.

### FAQs zum Einfügen eines OLE-Objekts in ein Word-Dokument als Symbol

#### F. Welche Referenzen werden benötigt, um mit Aspose.Words für .NET ein OLE-Objekt als Symbol in ein Word-Dokument einzufügen?

A: Sie müssen die folgenden Referenzen in Ihr Projekt importieren, um Aspose.Words für .NET zu verwenden:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### F. Wie erstelle ich in Aspose.Words für .NET ein neues Dokument und einen Dokumentgenerator?

 A: Sie können ein neues Dokument erstellen, indem Sie`Document` Klasse und einen Dokumentgenerator mit der`DocumentBuilder` Klasse. Hier ist ein Beispiel:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### F. Wie fügt man ein OLE-Objekt als Symbol in das Dokument ein?

 A: Verwenden Sie den Document Builder`InsertOleObjectAsIcon` Methode zum Einfügen eines OLE-Objekts als Symbol. Geben Sie den OLE-Dateipfad, die Anzeigeflagge, den Symbolpfad und den Namen des eingebetteten Objekts an. Hier ist ein Beispiel:

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

#### F. Wie speichere ich das Dokument mit dem als Symbol eingefügten OLE-Objekt?

 A: Verwenden Sie das Dokument`Save` Methode, um das Dokument in einer Datei zu speichern. Hier ist ein Beispiel:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```