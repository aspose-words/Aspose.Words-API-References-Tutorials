---
title: Fußzeilen entfernen
linktitle: Fußzeilen entfernen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ganz einfach Fußzeilen aus Word-Dokumenten entfernen. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für den effizienten Umgang mit DOCX-Dateien.
type: docs
weight: 10
url: /de/net/remove-content/remove-footers/
---
Wenn es um die Arbeit mit Word-Dokumenten in Ihrer .NET-Anwendung geht, ist Aspose.Words ein leistungsstarkes und vielseitiges Tool, mit dem Sie DOCX-Dateien einfach bearbeiten können. In diesem Artikel werden wir eine spezielle Funktion von Aspose.Words untersuchen: das Entfernen von Fußzeilen.

## Aspose.Words für .NET verstehen

Aspose.Words für .NET ist eine leistungsstarke Klassenbibliothek zum Erstellen, Ändern, Konvertieren und Bearbeiten von Word-Dokumenten in .NET-Anwendungen. Es bietet eine Vielzahl von Funktionen, darunter die Verwaltung von Kopf- und Fußzeilen, Bildern, Textformatierungen und mehr.

## Zweck des Entfernens von Fußzeilen in Aspose.Words

Es kann vorkommen, dass Sie Fußzeilen aus einem Word-Dokument entfernen möchten. Dies kann verschiedene Gründe haben, beispielsweise die Notwendigkeit, vertrauliche Informationen zu löschen, das Dokument für eine andere Verwendung anzupassen oder einfach unerwünschte Elemente zu entfernen. Aspose.Words erleichtert diese Aufgabe erheblich, indem es Ihnen eine einfache und effiziente Möglichkeit bietet, Fußzeilen aus Ihren Dokumenten zu entfernen.

## Schritt 1: Legen Sie den Dokumentverzeichnispfad fest

Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihr Dokumentverzeichnis in der Variablen „dataDir“ festgelegt haben. Dadurch können Sie den genauen Speicherort Ihrer DOCX-Datei angeben.

```csharp
string dataDir = "PATH_TO_YOUR_DOCUMENT_DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument

Der erste Schritt besteht darin, das Dokument in ein Objekt vom Typ Document zu laden. Dadurch können Sie auf den Inhalt des Dokuments zugreifen und ihn bearbeiten.

```csharp
Document doc = new Document(dataDir + "Name_of_document.docx");
```

Ersetzen Sie „Name_of_document.docx“ unbedingt durch den tatsächlichen Namen Ihres Dokuments.

## Schritt 3: Durchlaufen Sie die Abschnitte

Ein Word-Dokument kann mehrere Abschnitte enthalten und jeder Abschnitt kann seine eigenen Fußzeilen haben. Wir müssen jeden Abschnitt des Dokuments durchgehen, um zu den Fußzeilen zu gelangen.

```csharp
foreach (Section section in doc)
{
     // Code zum Entfernen von Fußzeilen
}
```

## Schritt 4: Fußzeilen entfernen

Nachdem wir nun zu einem bestimmten Abschnitt navigiert sind, können wir die Fußzeilen aus diesem Abschnitt entfernen. In Aspose.Words gibt es verschiedene Arten möglicher Fußzeilen, z. B. „FooterFirst“ (für die erste Seite), „FooterPrimary“ (für ungerade Seiten) und „FooterEven“ (für gerade Seiten). Wir müssen alle diese Arten von Fußzeilen überprüfen und entfernen.

```csharp
HeaderFooter footer = section.HeadersFooters[HeaderFooterType.Footer

First];
footer?.Remove();

footer = section.HeadersFooters[HeaderFooterType.FooterPrimary];
footer?.Remove();

footer = section.HeadersFooters[HeaderFooterType.FooterEven];
footer?.Remove();
```

## Schritt 5: Speichern Sie das geänderte Dokument

Sobald wir mit dem Entfernen der Fußzeilen fertig sind, können wir das bearbeitete Dokument in einer separaten Datei speichern.

```csharp
doc.Save(dataDir + "Name_of_modified_document.docx");
```

Vergessen Sie nicht, den Namen und Speicherort der geänderten Datei in „Name_of_modified_document.docx“ anzugeben.

### Beispielquellcode zum Entfernen von Fußzeilen mit Aspose.Words für .NET 
```csharp

// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document(dataDir + "Header and footer types.docx");

foreach (Section section in doc)
{
	// In einem Abschnitt sind bis zu drei verschiedene Fußzeilen möglich (für erste, gerade und ungerade Seiten)
	// Wir prüfen und löschen sie alle.
	HeaderFooter footer = section.HeadersFooters[HeaderFooterType.FooterFirst];
	footer?.Remove();

	// Die primäre Fußzeile ist die Fußzeile, die für ungerade Seiten verwendet wird.
	footer = section.HeadersFooters[HeaderFooterType.FooterPrimary];
	footer?.Remove();

	footer = section.HeadersFooters[HeaderFooterType.FooterEven];
	footer?.Remove();
}

doc.Save(dataDir + "RemoveContent.RemoveFooters.docx");
            
        
```

## Abschluss

In diesem Artikel haben wir untersucht, wie Sie mit Aspose.Words für .NET Fußzeilen aus einem Word-Dokument entfernen. Wenn Sie die bereitgestellten Schritte befolgen, können Sie Ihre Dokumente einfach bearbeiten und unerwünschte Fußzeilen entfernen. Aspose.Words bietet eine leistungsstarke und praktische Lösung für die Arbeit mit Word-Dokumenten in Ihrer .NET-Anwendung.

