---
title: Dokument beim Ersetzen einfügen
linktitle: Dokument beim Ersetzen einfügen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Dokument beim Ersetzen einfügen.
type: docs
weight: 10
url: /de/net/clone-and-combine-documents/insert-document-at-replace/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie beim Ersetzen mithilfe der Funktion „Dokument beim Ersetzen einfügen“ von Aspose.Words für .NET ein Dokument in ein anderes Dokument einfügen. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und das Einfügen des Dokuments durchzuführen.

## Schritt 1: Laden des Hauptdokuments

Geben Sie zunächst das Verzeichnis für Ihre Dokumente an und laden Sie das Hauptdokument in ein Document-Objekt. Hier ist wie:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Schritt 2: Such- und Ersetzungsoptionen konfigurieren

Jetzt konfigurieren wir die Such- und Ersetzungsoptionen, indem wir die Suchrichtung und den Ersetzungsrückruf angeben, um ein Dokument in ein anderes Dokument einzufügen. Hier ist wie:

```csharp
// Konfigurieren Sie Such- und Ersetzungsoptionen.
FindReplaceOptions options = new FindReplaceOptions
{
Direction = FindReplaceDirection.Backward,
ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

## Schritt 3: Aufruf der Ersetzungsmethode

Wir rufen nun die Methode „replace“ auf, um mithilfe der konfigurierten Optionen den angegebenen Text zu suchen und durch eine leere Zeichenfolge zu ersetzen. Hier ist wie:

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

### Beispielquellcode für „Dokument beim Ersetzen einfügen“ mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Dokument einfügen“ beim Ersetzen von Aspose.Words für .NET:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

// Legen Sie Such- und Ersetzungsoptionen fest.
FindReplaceOptions options = new FindReplaceOptions
{
	Direction = FindReplaceDirection.Backward, 
	ReplacingCallback = new InsertDocumentAtReplaceHandler()
};

// Rufen Sie die Ersetzungsmethode auf.
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

## Abschluss

In diesem Tutorial haben wir untersucht, wie man ein Dokument während des Ersetzens mithilfe der Funktion „Dokument beim Ersetzen einfügen“ von Aspose.Words für .NET in ein anderes Dokument einfügt. Durch die Konfiguration der Such- und Ersetzungsoptionen und die Bereitstellung der erforderlichen Daten können Sie Dokumente dynamisch zusammenstellen, indem Sie bestimmte Platzhalter durch den Inhalt anderer Dokumentvorlagen oder Abschnitte ersetzen. Aspose.Words für .NET bietet eine leistungsstarke und flexible Möglichkeit zur Verwaltung komplexer Dokumentbearbeitungsaufgaben und macht es zu einem wertvollen Werkzeug zur Automatisierung von Dokumenterstellungs- und Inhaltseinfügungsszenarien.

### FAQs

#### F: Welchen Zweck hat das Einfügen eines Dokuments in ein anderes Dokument beim Ersetzen?

A: Wenn Sie beim Ersetzen ein Dokument in ein anderes Dokument einfügen, können Sie einen bestimmten Platzhalter dynamisch durch den Inhalt eines separaten Dokuments ersetzen. Diese Funktion ist besonders nützlich, wenn Sie ein größeres Dokument zusammenstellen möchten, indem Sie verschiedene vordefinierte Dokumentvorlagen oder Abschnitte in bestimmten Platzhaltern kombinieren.

#### F: Wie füge ich beim Ersetzen mit Aspose.Words für .NET ein Dokument in ein anderes Dokument ein?

A: Um ein Dokument während des Ersetzens mit Aspose.Words für .NET in ein anderes Dokument einzufügen, führen Sie die folgenden Schritte aus:
1. Laden Sie das Hauptdokument, das die Platzhalter enthält, in ein Document-Objekt.
2. Konfigurieren Sie die Such- und Ersetzungsoptionen, einschließlich der Suchrichtung und des Ersetzungsrückrufs, um das Einfügen des Dokuments zu verarbeiten.
3. Rufen Sie die Ersetzungsmethode mit dem entsprechenden Suchmuster auf und ersetzen Sie die Platzhalter mithilfe der konfigurierten Optionen durch eine leere Zeichenfolge.

#### F: Kann ich das Einfügeverhalten beim Ersetzen anpassen?

A: Ja, Sie können das Einfügeverhalten während des Ersetzens anpassen, indem Sie einen benutzerdefinierten ReplacementCallback implementieren. Durch die Vererbung von der IReplacingCallback-Schnittstelle können Sie steuern, wie die Dokumente basierend auf Ihren spezifischen Anforderungen beim Ersetzen der Platzhalter eingefügt und zusammengeführt werden.

#### F: Kann ich mehrere Platzhalter durch unterschiedliche Dokumente ersetzen?

A: Ja, Sie können mehrere Platzhalter durch unterschiedliche Dokumente ersetzen, indem Sie für jeden Platzhalter die entsprechenden Suchmuster angeben und die entsprechenden einzufügenden Dokumente angeben.