---
title: Transformierte Elemente rastern
linktitle: Transformierte Elemente rastern
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie die Rasterung transformierter Elemente bei der Konvertierung in das PCL-Format mit Aspose.Words für .NET deaktivieren.
type: docs
weight: 10
url: /de/net/programming-with-pclsaveoptions/rasterize-transformed-elements/
---

Aspose.Words für .NET ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten und Konvertieren von Word-Dokumenten in einer C#-Anwendung. Zu den von Aspose.Words angebotenen Funktionen gehört die Möglichkeit, transformierte Elemente beim Konvertieren von Dokumenten in verschiedene Formate zu rastern. In dieser Anleitung zeigen wir Ihnen, wie Sie den C#-Quellcode von Aspose.Words für .NET verwenden, um die Rasterung transformierter Elemente beim Konvertieren eines Dokuments in das PCL-Format zu deaktivieren.

## Die Aspose.Words-Bibliothek verstehen

Bevor Sie sich in den Code vertiefen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine beliebte Bibliothek, die die Textverarbeitung mit Word-Dokumenten einfach und effizient macht. Sie bietet eine breite Palette an Funktionen zum Erstellen, Bearbeiten und Konvertieren von Word-Dokumenten, einschließlich Unterstützung für das Rastern transformierter Elemente während der Konvertierung.

## Laden des Word-Dokuments

Der erste Schritt besteht darin, das Word-Dokument zu laden, das Sie in das PCL-Format konvertieren möchten. Verwenden Sie die Document-Klasse, um das Dokument aus der Quelldatei zu laden. Hier ist ein Beispiel:

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

In diesem Beispiel laden wir das Dokument „Rendering.docx“, das sich im Dokumentenverzeichnis befindet.

## Konfigurieren von Sicherungsoptionen

Der nächste Schritt besteht darin, die Speicheroptionen für die Konvertierung in das PCL-Format zu konfigurieren. Verwenden Sie die Klasse PclSaveOptions und setzen Sie die Eigenschaft RasterizeTransformedElements auf „false“. So geht's:

```csharp
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};
```

Wir erstellen ein neues PclSaveOptions-Objekt und setzen die SaveFormat-Eigenschaft auf SaveFormat.Pcl, um anzugeben, dass wir das Dokument im PCL-Format speichern möchten. Als Nächstes setzen wir die RasterizeTransformedElements-Eigenschaft auf false, um die Rasterung transformierter Elemente zu deaktivieren.

## Konvertieren des Dokuments in das PCL-Format

Nachdem wir nun die Speicheroptionen konfiguriert haben, können wir mit der Konvertierung des Dokuments in das PCL-Format fortfahren. Verwenden Sie die Save-Methode der Document-Klasse, um das konvertierte Dokument im PCL-Format zu speichern, indem Sie Speicheroptionen angeben. Hier ist ein Beispiel:

```csharp
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

In diesem Beispiel speichern wir das konvertierte Dokument mit den angegebenen Speicheroptionen als „WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl“.

### Beispielquellcode für die Funktion „Transformierte Elemente rastern“ mit Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Word-Dokument


Document doc = new Document(dataDir + "Rendering.docx");

// Konfigurieren Sie Sicherungsoptionen für die Konvertierung in das PCL-Format
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};

// Konvertieren Sie das Dokument in das PCL-Format
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

## Abschluss

In diesem Handbuch haben wir erläutert, wie Sie mit Aspose.Words für .NET die Rasterung transformierter Elemente deaktivieren, wenn Sie ein Dokument mithilfe des bereitgestellten C#-Quellcodes in das PCL-Format konvertieren. Indem Sie die angegebenen Schritte befolgen, können Sie das Rasterungsverhalten transformierter Elemente beim Konvertieren Ihrer Word-Dokumente in verschiedene Formate problemlos steuern. Aspose.Words bietet enorme Flexibilität und Leistung beim Arbeiten mit den transformierten Elementen, sodass Sie konvertierte Dokumente genau nach Ihren spezifischen Anforderungen erstellen können.