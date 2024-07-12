---
title: Schreiben Sie alle CSS-Regeln in eine einzige Datei
linktitle: Schreiben Sie alle CSS-Regeln in eine einzige Datei
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie ein Word-Dokument in festes HTML konvertieren, indem Sie mit Aspose.Words für .NET alle CSS-Regeln in eine einzige Datei schreiben.
type: docs
weight: 10
url: /de/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---

Wenn Sie ein Word-Dokument in einer C#-Anwendung in festes HTML konvertieren, möchten Sie möglicherweise alle CSS-Regeln in einer einzigen Datei zusammenfassen, um eine bessere Organisation und Portabilität zu gewährleisten. Mit der Aspose.Words-Bibliothek für .NET können Sie diese Funktionalität mithilfe der Speicheroptionen HtmlFixedSaveOptions ganz einfach angeben. In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit dem C#-Quellcode von Aspose.Words für .NET ein Word-Dokument in festes HTML konvertieren, indem Sie alle CSS-Regeln mithilfe der Speicheroptionen HtmlFixedSaveOptions in eine einzige Datei schreiben.

## Die Aspose.Words-Bibliothek verstehen

Bevor Sie sich in den Code vertiefen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten, Konvertieren und Schützen von Word-Dokumenten auf verschiedenen Plattformen, einschließlich .NET. Sie bietet viele Funktionen zum Bearbeiten von Dokumenten, z. B. zum Einfügen von Text, Ändern der Formatierung, Hinzufügen von Abschnitten und vieles mehr.

## Laden des Word-Dokuments

Der erste Schritt besteht darin, das Word-Dokument zu laden, das Sie in festes HTML konvertieren möchten. Verwenden Sie die Document-Klasse, um das Dokument aus der Quelldatei zu laden. Hier ist ein Beispiel:

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

In diesem Beispiel laden wir das Dokument „Document.docx“, das sich im Dokumentenverzeichnis befindet.

## Konfigurieren von Sicherungsoptionen

Der nächste Schritt besteht darin, die Speicheroptionen für die Konvertierung in festes HTML zu konfigurieren. Verwenden Sie die Klasse HtmlFixedSaveOptions und setzen Sie die Eigenschaft SaveFontFaceCssSeparately auf „false“, um alle CSS-Regeln in eine einzige Datei zu schreiben. So geht's:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };
```

Wir erstellen ein neues HtmlFixedSaveOptions-Objekt und setzen die Eigenschaft SaveFontFaceCssSeparately auf „false“, um alle CSS-Regeln in eine einzige Datei zu schreiben.

## Konvertierung von HTML-Dokumenten behoben

Nachdem wir nun die Speicheroptionen konfiguriert haben, können wir mit der Konvertierung des Dokuments in festes HTML fortfahren. Verwenden Sie die Save-Methode der Document-Klasse, um das konvertierte Dokument im festen HTML-Format zu speichern, indem Sie Speicheroptionen angeben. Hier ist ein Beispiel:

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

In diesem Beispiel speichern wir das konvertierte Dokument mit den angegebenen Speicheroptionen als „WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html“.

### Beispiel-Quellcode für HtmlFixedSaveOptions mit der Funktion „Alle CSS-Regeln in eine Datei schreiben“ unter Verwendung von Aspose.Words für .NET

```csharp
// Zugriffspfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Word-Dokument
Document doc = new Document(dataDir + "Document.docx");

// Konfigurieren Sie Sicherungsoptionen mit der Funktion „Alle CSS-Regeln in eine Datei schreiben“
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };

// Dokument in festes HTML konvertieren
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## Abschluss

In dieser Anleitung haben wir erläutert, wie Sie ein Word-Dokument in festes HTML konvertieren, indem Sie alle CSS-Regeln mithilfe von HtmlFixedSaveOptions mit der Aspose.Words-Bibliothek für .NET in eine einzige Datei schreiben. Indem Sie die angegebenen Schritte befolgen und den bereitgestellten C#-Quellcode verwenden, können Sie diese Funktionalität problemlos in Ihrer C#-Anwendung anwenden. Das Schreiben aller CSS-Regeln in einer einzigen Datei erleichtert die Organisation und Verwaltung des während der Dokumentkonvertierung generierten HTML-Codes.