---
title: Ole-Objekt einfügen
linktitle: Ole-Objekt einfügen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein OLE-Objekt in ein Dokument einfügen.
type: docs
weight: 10
url: /de/net/working-with-oleobjects-and-activex/insert-ole-object/
---

Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der veranschaulicht, wie Sie mit Aspose.Words für .NET ein OLE-Objekt einfügen.

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
