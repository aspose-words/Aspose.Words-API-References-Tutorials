---
title: Schriftart vom Zielcomputer verwenden
linktitle: Schriftart vom Zielcomputer verwenden
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Word-Dokument unter Verwendung der Schriftarten des Zielcomputers in festes HTML konvertieren.
type: docs
weight: 10
url: /de/net/programming-with-htmlfixedsaveoptions/use-font-from-target-machine/
---

Wenn Sie ein Word-Dokument in einer C#-Anwendung in festes HTML konvertieren, möchten Sie möglicherweise die Schriftarten des Zielcomputers verwenden, um sicherzustellen, dass das gerenderte HTML das ursprüngliche Aussehen und den Stil des Dokuments beibehält. Mit der Aspose.Words-Bibliothek für .NET können Sie diese Funktionalität ganz einfach mithilfe der Speicheroptionen HtmlFixedSaveOptions angeben. In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie den C#-Quellcode von Aspose.Words für .NET verwenden, um ein Word-Dokument mithilfe der Schriftarten des Zielcomputers und der HtmlFixedSaveOptions in festes HTML zu konvertieren.

## Die Aspose.Words-Bibliothek verstehen

Bevor Sie sich in den Code vertiefen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten, Konvertieren und Schützen von Word-Dokumenten auf verschiedenen Plattformen, einschließlich .NET. Sie bietet viele Funktionen zum Bearbeiten von Dokumenten, z. B. zum Einfügen von Text, Ändern der Formatierung, Hinzufügen von Abschnitten und vieles mehr.

## Laden des Word-Dokuments

Der erste Schritt besteht darin, das Word-Dokument zu laden, das Sie in festes HTML konvertieren möchten. Verwenden Sie die Document-Klasse, um das Dokument aus der Quelldatei zu laden. Hier ist ein Beispiel:

```csharp
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");
```

In diesem Beispiel laden wir das Dokument „Aufzählungspunkte mit alternativer Schriftart.docx“, das sich im Verzeichnis „Dokumente“ befindet.

## Konfigurieren von Sicherungsoptionen

Der nächste Schritt besteht darin, die Speicheroptionen für die Konvertierung in festes HTML zu konfigurieren. Verwenden Sie die Klasse HtmlFixedSaveOptions und setzen Sie die Eigenschaft UseTargetMachineFonts auf true, um Aspose.Words anzuweisen, Schriftarten vom Zielcomputer zu verwenden. So geht's:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };
```

Wir erstellen ein neues HtmlFixedSaveOptions-Objekt und setzen die UseTargetMachineFonts-Eigenschaft auf „true“, um beim Konvertieren die Schriftarten des Zielcomputers zu verwenden.

## Konvertierung von HTML-Dokumenten behoben

Nachdem wir nun die Speicheroptionen konfiguriert haben, können wir mit der Konvertierung des Dokuments in festes HTML fortfahren. Verwenden Sie die Save-Methode der Document-Klasse, um das konvertierte Dokument im festen HTML-Format zu speichern, indem Sie Speicheroptionen angeben. Hier ist ein Beispiel:

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

In diesem Beispiel speichern wir das konvertierte Dokument mit den angegebenen Speicheroptionen als „WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html“.

### Beispielquellcode für HtmlFixedSaveOptions mit der Funktion „Schriftarten vom Zielcomputer verwenden“ unter Verwendung von Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Word-Dokument
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");

// Konfigurieren Sie Sicherungsoptionen mit der Funktion „Schriftarten vom Zielcomputer verwenden“
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };

// Dokument in festes HTML konvertieren
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

## Abschluss

In dieser Anleitung haben wir erklärt, wie Sie mit der Aspose.Words-Bibliothek für .NET ein Word-Dokument unter Verwendung der Schriftarten des Zielcomputers in festes HTML konvertieren. Indem Sie die angegebenen Schritte befolgen und den bereitgestellten C#-Quellcode verwenden, können Sie diese Funktionalität problemlos in Ihrer C#-Anwendung anwenden. Die Konvertierung in festes HTML mit den Schriftarten des Zielcomputers garantiert eine originalgetreue und konsistente Darstellung des Dokuments in einem HTML-Format.
