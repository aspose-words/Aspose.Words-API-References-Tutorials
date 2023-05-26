---
title: Schriftart vom Zielcomputer verwenden
linktitle: Schriftart vom Zielcomputer verwenden
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Word-Dokument mithilfe der Schriftarten des Zielcomputers in festes HTML konvertieren.
type: docs
weight: 10
url: /de/net/programming-with-htmlfixedsaveoptions/use-font-from-target-machine/
---

Beim Konvertieren eines Word-Dokuments in festes HTML in einer C#-Anwendung möchten Sie möglicherweise die Schriftarten des Zielcomputers verwenden, um sicherzustellen, dass das gerenderte HTML das ursprüngliche Aussehen und den ursprünglichen Stil des Dokuments beibehält. Mit der Aspose.Words-Bibliothek für .NET können Sie diese Funktionalität mithilfe der Speicheroptionen von HtmlFixedSaveOptions problemlos angeben. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch die Verwendung des C#-Quellcodes von Aspose.Words für .NET, um ein Word-Dokument mithilfe der Schriftarten des Zielcomputers mithilfe von HtmlFixedSaveOptions in festes HTML zu konvertieren.

## Grundlegendes zur Aspose.Words-Bibliothek

Bevor Sie in den Code eintauchen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten, Konvertieren und Schützen von Word-Dokumenten auf verschiedenen Plattformen, einschließlich .NET. Es bietet viele Funktionen zum Bearbeiten von Dokumenten, wie zum Beispiel das Einfügen von Text, das Ändern von Formatierungen, das Hinzufügen von Abschnitten und vieles mehr.

## Laden des Word-Dokuments

Der erste Schritt besteht darin, das Word-Dokument zu laden, das Sie in festes HTML konvertieren möchten. Verwenden Sie die Document-Klasse, um das Dokument aus der Quelldatei zu laden. Hier ist ein Beispiel :

```csharp
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");
```

In diesem Beispiel laden wir das Dokument „Aufzählungspunkte mit alternativer Schriftart.docx“, das sich im Dokumentenverzeichnis befindet.

## Backup-Optionen konfigurieren

Der nächste Schritt besteht darin, die Speicheroptionen für die Konvertierung in festes HTML zu konfigurieren. Verwenden Sie die Klasse „HtmlFixedSaveOptions“ und legen Sie die Eigenschaft „UseTargetMachineFonts“ auf „true“ fest, um Aspose.Words anzuweisen, Schriftarten vom Zielcomputer zu verwenden. So geht's:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };
```

Wir erstellen ein neues HtmlFixedSaveOptions-Objekt und setzen die UseTargetMachineFonts-Eigenschaft auf „true“, um beim Konvertieren die Schriftarten des Zielcomputers zu verwenden.

## Die Konvertierung von HTML-Dokumenten wurde korrigiert

Nachdem wir nun die Speicheroptionen konfiguriert haben, können wir mit der Konvertierung des Dokuments in festes HTML fortfahren. Verwenden Sie die Save-Methode der Document-Klasse, um das konvertierte Dokument im festen HTML-Format zu speichern, indem Sie Speicheroptionen angeben. Hier ist ein Beispiel :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

In diesem Beispiel speichern wir das konvertierte Dokument unter Verwendung der angegebenen Speicheroptionen als „WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html“.

### Beispielquellcode für HtmlFixedSaveOptions mit der Funktion „Schriftarten vom Zielcomputer verwenden“ unter Verwendung von Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Laden Sie das Word-Dokument
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");

// Konfigurieren Sie Sicherungsoptionen mit der Funktion „Schriftarten vom Zielcomputer verwenden“.
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };

// Konvertieren Sie das Dokument in festes HTML
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

## Abschluss

In dieser Anleitung haben wir erklärt, wie Sie ein Word-Dokument mithilfe der Schriftarten des Zielcomputers mit der Aspose.Words-Bibliothek für .NET in festes HTML konvertieren. Indem Sie die bereitgestellten Schritte befolgen und den bereitgestellten C#-Quellcode verwenden, können Sie diese Funktionalität problemlos in Ihrer C#-Anwendung anwenden. Die Konvertierung in festes HTML mit den Schriftarten des Zielrechners garantiert eine originalgetreue und konsistente Darstellung des Dokuments im HTML-Format.
