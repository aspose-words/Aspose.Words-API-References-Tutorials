---
title: Schreiben Sie alle CSS-Regeln in eine einzige Datei
linktitle: Schreiben Sie alle CSS-Regeln in eine einzige Datei
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Word-Dokument in festes HTML konvertieren, indem Sie alle CSS-Regeln in eine einzige Datei schreiben.
type: docs
weight: 10
url: /de/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---

Wenn Sie ein Word-Dokument in einer C#-Anwendung in festes HTML konvertieren, möchten Sie möglicherweise alle CSS-Regeln in einer einzigen Datei konsolidieren, um die Organisation und Portabilität zu verbessern. Mit der Aspose.Words-Bibliothek für .NET können Sie diese Funktionalität mithilfe der Speicheroptionen von HtmlFixedSaveOptions problemlos angeben. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch die Verwendung von Aspose.Words für .NET C#-Quellcode zum Konvertieren eines Word-Dokuments in festes HTML, indem wir alle CSS-Regeln mithilfe der Speicheroptionen HtmlFixedSaveOptions in eine einzige Datei schreiben.

## Grundlegendes zur Aspose.Words-Bibliothek

Bevor Sie in den Code eintauchen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten, Konvertieren und Schützen von Word-Dokumenten auf verschiedenen Plattformen, einschließlich .NET. Es bietet viele Funktionen zum Bearbeiten von Dokumenten, wie zum Beispiel das Einfügen von Text, das Ändern von Formatierungen, das Hinzufügen von Abschnitten und vieles mehr.

## Laden des Word-Dokuments

Der erste Schritt besteht darin, das Word-Dokument zu laden, das Sie in festes HTML konvertieren möchten. Verwenden Sie die Document-Klasse, um das Dokument aus der Quelldatei zu laden. Hier ist ein Beispiel :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

In diesem Beispiel laden wir das Dokument „Document.docx“, das sich im Dokumentenverzeichnis befindet.

## Backup-Optionen konfigurieren

Der nächste Schritt besteht darin, die Speicheroptionen für die Konvertierung in festes HTML zu konfigurieren. Verwenden Sie die Klasse „HtmlFixedSaveOptions“ und legen Sie die Eigenschaft „SaveFontFaceCssSeparately“ auf „false“ fest, um alle CSS-Regeln in eine einzige Datei zu schreiben. So geht's:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };
```

Wir erstellen ein neues HtmlFixedSaveOptions-Objekt und setzen die SaveFontFaceCssSeparately-Eigenschaft auf false, um alle CSS-Regeln in eine einzige Datei zu schreiben.

## Die Konvertierung von HTML-Dokumenten wurde korrigiert

Nachdem wir nun die Speicheroptionen konfiguriert haben, können wir mit der Konvertierung des Dokuments in festes HTML fortfahren. Verwenden Sie die Save-Methode der Document-Klasse, um das konvertierte Dokument im festen HTML-Format zu speichern, indem Sie Speicheroptionen angeben. Hier ist ein Beispiel :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

In diesem Beispiel speichern wir das konvertierte Dokument unter Verwendung der angegebenen Speicheroptionen als „WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html“.

### Beispielquellcode für HtmlFixedSaveOptions mit der Funktion „Alle CSS-Regeln in eine Datei schreiben“ unter Verwendung von Aspose.Words für .NET

```csharp
// Zugriffspfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Word-Dokument
Document doc = new Document(dataDir + "Document.docx");

// Konfigurieren Sie Sicherungsoptionen mit der Funktion „Alle CSS-Regeln in eine Datei schreiben“.
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };

// Konvertieren Sie das Dokument in festes HTML
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## Abschluss

In dieser Anleitung haben wir beschrieben, wie Sie ein Word-Dokument in festes HTML konvertieren, indem Sie alle CSS-Regeln mithilfe von HtmlFixedSaveOptions mit der Aspose.Words-Bibliothek für .NET in eine einzige Datei schreiben. Indem Sie die bereitgestellten Schritte befolgen und den bereitgestellten C#-Quellcode verwenden, können Sie diese Funktionalität problemlos in Ihrer C#-Anwendung anwenden. Das Schreiben aller CSS-Regeln in einer einzigen Datei erleichtert die Organisation und Verwaltung des bei der Dokumentkonvertierung generierten HTML-Codes.