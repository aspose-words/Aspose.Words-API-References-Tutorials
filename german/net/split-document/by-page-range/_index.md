---
title: Nach Seitenbereich
linktitle: Nach Seitenbereich
second_title: Aspose.Words für .NET API-Referenz
description: Einfaches Extrahieren nach Seitenbereich aus einem Word-Dokument mit Aspose.Words für .NET. Schritt-für-Schritt-Anleitung.
type: docs
weight: 10
url: /de/net/split-document/by-page-range/
---

## Einführung
In diesem Tutorial führen wir Sie Schritt für Schritt durch das Verständnis und die Verwendung der „By Page Range“-Funktionalität von Aspose.Words für .NET. Mit dieser Funktion können Sie einen bestimmten Teil eines großen Word-Dokuments mithilfe eines bestimmten Seitenbereichs extrahieren. Wir stellen Ihnen den vollständigen Quellcode und die Markdown-Ausgabeformate zur Verfügung, damit Sie ihn später leichter verstehen und verwenden können.

## Anforderungen
Bevor Sie beginnen, stellen Sie sicher, dass Folgendes vorhanden ist:

1. Aspose.Words für .NET ist auf Ihrem Entwicklungscomputer installiert.
2. Eine große Word-Datei, aus der Sie einen bestimmten Teil extrahieren möchten.

Nachdem wir nun die Anforderungen abgedeckt haben, können wir mit den Schritten zur Verwendung der Funktion „Nach Seitenbereich“ fortfahren.

## Schritt 1: Initialisierung und Laden des Dokuments
Nachdem Sie Ihre Entwicklungsumgebung eingerichtet haben, müssen Sie das Word-Dokument, aus dem Sie einen bestimmten Teil extrahieren möchten, initialisieren und laden. Hier ist der zu verwendende Code:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "Name_of_large_document.docx");
```

Stellen Sie sicher, dass Sie „IHR_DOCUMENTS_VERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis und „Name_des_großen_Dokuments.docx“ durch den Namen Ihrer großen Word-Datei ersetzen.

## Schritt 2: Extrahieren des Teils des Dokuments
 Nachdem wir das Dokument geladen haben, können wir den spezifischen Teil mithilfe von extrahieren`ExtractPages` Funktion mit dem gewünschten Seitenbereich. So geht's:

```csharp
Document extractedPages = doc.ExtractPages(3, 6);
```

In diesem Beispiel extrahieren wir die Seiten 3–6 aus dem Originaldokument. Sie können die Seitenzahlen Ihren Bedürfnissen entsprechend anpassen.

## Schritt 3: Speichern Sie den extrahierten Teil
Sobald wir die gewünschten Seiten extrahiert haben, können wir sie in einem neuen Word-Dokument speichern. Hier ist wie:

```csharp
extractedPages.Save(dataDir + "Document_Extraits.ParRangeDePages.docx");
```

Ersetzen Sie unbedingt „Document_Extraits.ParPlageDePages.docx“ durch den gewünschten Namen für Ihre Ausgabedatei.

### Beispielquellcode für „By Page Range“ mit Aspose.Words für .NET

```csharp

            // Der Pfad zum Dokumentenverzeichnis.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(MyDir + "Big document.docx");
            
            // Holen Sie sich einen Teil des Dokuments.
            Document extractedPages = doc.ExtractPages(3, 6);
            extractedPages.Save(dataDir + "SplitDocument.ByPageRange.docx");
            
        
```

## Abschluss
Herzlichen Glückwunsch! Sie haben gelernt, wie Sie „By Page Range“ von Aspose.Words für .NET verwenden. Jetzt können Sie mithilfe eines bestimmten Seitenbereichs ganz einfach bestimmte Teile eines großen Word-Dokuments extrahieren. Experimentieren Sie ruhig noch mehr mit den anderen leistungsstarken Funktionen von Aspose. .Wörter, die Ihren spezifischen Bedürfnissen entsprechen.

