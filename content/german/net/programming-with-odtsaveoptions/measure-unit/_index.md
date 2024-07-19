---
title: Maßeinheit
linktitle: Maßeinheit
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie die Maßeinheit angeben, wenn Sie ein Word-Dokument mit Aspose.Words für .NET in ODT konvertieren.
type: docs
weight: 10
url: /de/net/programming-with-odtsaveoptions/measure-unit/
---

Wenn Sie ein Word-Dokument in einer C#-Anwendung in das OpenDocument Text (ODT)-Format konvertieren, möchten Sie möglicherweise die Maßeinheit angeben, die für messbare Formatierungs- und Inhaltseigenschaften verwendet wird. Mit der Aspose.Words-Bibliothek für .NET können Sie diese Funktionalität ganz einfach mithilfe der OdtSaveOptions-Speicheroptionen angeben. In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit dem C#-Quellcode von Aspose.Words für .NET ein Word-Dokument in ODT konvertieren, indem Sie die Maßeinheit mithilfe von OdtSaveOptions angeben.

## Die Aspose.Words-Bibliothek verstehen

Bevor Sie sich in den Code vertiefen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten, Konvertieren und Schützen von Word-Dokumenten auf verschiedenen Plattformen, einschließlich .NET. Sie bietet viele Funktionen zum Bearbeiten von Dokumenten, z. B. zum Einfügen von Text, Ändern der Formatierung, Hinzufügen von Abschnitten und vieles mehr.

## Laden des Word-Dokuments

Der erste Schritt besteht darin, das Word-Dokument zu laden, das Sie in ODT konvertieren möchten. Verwenden Sie die Document-Klasse, um das Dokument aus der Quelldatei zu laden. Hier ist ein Beispiel:

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

In diesem Beispiel laden wir das Dokument „Document.docx“, das sich im Dokumentenverzeichnis befindet.

## Konfigurieren von Sicherungsoptionen

Der nächste Schritt besteht darin, die Sicherungsoptionen für die Konvertierung in ODT zu konfigurieren. Verwenden Sie die Klasse OdtSaveOptions und setzen Sie die Eigenschaft MeasureUnit auf den gewünschten Wert. Wenn Sie beispielsweise Zoll als Maßeinheit verwenden möchten, setzen Sie MeasureUnit auf OdtSaveMeasureUnit.Inches. So geht's:

```csharp
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

Wir erstellen ein neues OdtSaveOptions-Objekt und setzen die MeasureUnit-Eigenschaft auf den gewünschten Wert, in unserem Fall OdtSaveMeasureUnit.Inches, um Zoll als Maßeinheit zu verwenden.

## Dokument in ODT konvertieren

Nachdem wir nun die Speicheroptionen konfiguriert haben, können wir mit der Konvertierung des Dokuments in ODT fortfahren. Verwenden Sie die Save-Methode der Document-Klasse, um das konvertierte Dokument im ODT-Format zu speichern, indem Sie Speicheroptionen angeben. Hier ist ein Beispiel:

```csharp
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

In diesem Beispiel speichern wir das konvertierte Dokument mit den angegebenen Speicheroptionen als „WorkingWithOdtSaveOptions.MeasureUnit.odt“.

### Beispielquellcode für OdtSaveOptions mit „Maßeinheit“-Funktionalität unter Verwendung von Aspose.Words für .NET



```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Word-Dokument
Document doc = new Document(dataDir + "Document.docx");

// Konfiguration der Backup-Optionen mit der Funktion „Maßeinheit“
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };

// Konvertieren Sie das Dokument in ODT
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## Abschluss

In dieser Anleitung haben wir erklärt, wie Sie ein Word-Dokument in ODT konvertieren, indem Sie die Maßeinheit mithilfe der Speicheroptionen OdtSaveOptions mit der Aspose.Words-Bibliothek für .NET angeben. Indem Sie die angegebenen Schritte befolgen und den bereitgestellten C#-Quellcode verwenden, können Sie diese Funktion problemlos in Ihrer C#-Anwendung anwenden. Durch die Angabe der Maßeinheit bei der Konvertierung in ODT können Sie die Formatierung und Abmessungen des resultierenden Dokuments entsprechend Ihren spezifischen Anforderungen steuern.