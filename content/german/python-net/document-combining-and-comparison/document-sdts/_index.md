---
title: Verwendung strukturierter Dokument-Tags (SDTs) für strukturierte Daten
linktitle: Verwendung strukturierter Dokument-Tags (SDTs) für strukturierte Daten
second_title: Aspose.Words Python-Dokumentenverwaltungs-API
description: Nutzen Sie die Möglichkeiten strukturierter Dokument-Tags (SDTs) zum Organisieren von Inhalten. Erfahren Sie, wie Sie Aspose.Words für Python zum Implementieren von SDTs verwenden.
type: docs
weight: 13
url: /de/python-net/document-combining-and-comparison/document-sdts/
---

## Einführung in strukturierte Dokument-Tags (SDTs)

Strukturierte Dokument-Tags, oft auch als Inhaltssteuerelemente bezeichnet, sind Elemente innerhalb eines Dokuments, die dem darin enthaltenen Inhalt Struktur verleihen. Sie ermöglichen eine konsistente Formatierung und ermöglichen die programmgesteuerte Bearbeitung von Inhalten. SDTs können verschiedene Arten von Inhalten umfassen, z. B. einfachen Text, Rich-Text, Bilder, Kontrollkästchen und mehr.

## Vorteile der Verwendung von SDTs

Die Verwendung von SDTs bietet mehrere Vorteile, darunter:

- Konsistenz: SDTs stellen sicher, dass Inhalte einem standardisierten Format folgen und verhindern so Formatierungsinkonsistenzen.
- Automatisierung: Mit SDTs können Sie die Dokumentenerstellung automatisieren und so die Erstellung von Vorlagen und Berichten erleichtern.
- Datenvalidierung: SDTs können Datenvalidierungsregeln durchsetzen, Fehler reduzieren und die Datenintegrität wahren.
- Dynamischer Inhalt: SDTs ermöglichen das Einfügen dynamischer Inhalte, die automatisch aktualisiert werden, wie z. B. Datums- und Zeitstempel.
- Einfache Zusammenarbeit: Mitarbeiter können sich auf den Inhalt konzentrieren, ohne die Struktur des Dokuments zu ändern.

## Erste Schritte mit Aspose.Words für Python

Bevor wir uns mit der Verwendung von SDTs befassen, beginnen wir mit Aspose.Words für Python. Aspose.Words ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, Word-Dokumente programmgesteuert zu erstellen, zu ändern und zu konvertieren. Führen Sie zunächst die folgenden Schritte aus:

1. Installation: Installieren Sie Aspose.Words für Python mit pip:
   
   ```python
   pip install aspose-words
   ```

2. Importieren der Bibliothek: Importieren Sie die Aspose.Words-Bibliothek in Ihr Python-Skript:

   ```python
   import aspose.words
   ```

3. Laden eines Dokuments: Laden Sie ein vorhandenes Word-Dokument mit Aspose.Words:

   ```python
   doc = aspose.words.Document("sample.docx")
   ```

## Erstellen und Hinzufügen von SDTs zu einem Dokument

Das Hinzufügen von SDTs zu einem Dokument erfordert ein paar einfache Schritte:

1.  SDT erstellen: Verwenden Sie die`StructuredDocumentTag` Klasse zum Erstellen einer SDT-Instanz.

   ```python
   sdt = aspose.words.StructuredDocumentTag(doc, aspose.words.SdtType.PLAIN_TEXT)
   ```

2. Inhalt festlegen: Legen Sie den Inhalt des SDT fest:

   ```python
   sdt.get_first_child().remove_all_children()
   sdt.get_first_child().append_child(aspose.words.Run(doc, "Structured Content"))
   ```

3. Zum Dokument hinzufügen: Fügen Sie das SDT zur Knotensammlung auf Blockebene des Dokuments hinzu:

   ```python
   doc.get_first_section().get_body().append_child(sdt)
   ```

## Arbeiten mit SDT-Inhaltssteuerelementen

SDT-Inhaltssteuerelemente ermöglichen Benutzern die Interaktion mit dem Dokument. Sehen wir uns einige gängige Inhaltssteuerelemente an:

1. Nur-Text-Steuerung:

   ```python
   sdt = aspose.words.StructuredDocumentTag(doc, aspose.words.SdtType.PLAIN_TEXT)
   sdt.get_first_child().append_child(aspose.words.Run(doc, "Enter your name: "))
   ```

2. Kontrollkästchen:

   ```python
   sdt = aspose.words.StructuredDocumentTag(doc, aspose.words.SdtType.CHECKBOX)
   sdt.checkbox = True
   sdt.get_first_child().append_child(aspose.words.Run(doc, "Check to agree: "))
   ```

## Programmgesteuertes Navigieren und Bearbeiten von SDTs

Das programmgesteuerte Navigieren und Bearbeiten von SDTs ermöglicht eine dynamische Dokumentgenerierung. So können Sie es erreichen:

1. Zugriff auf SDTs:

   ```python
   sdt_collection = doc.get_child_nodes(aspose.words.NodeType.STRUCTURED_DOCUMENT_TAG, True)
   ```

2. Aktualisieren des SDT-Inhalts:

   ```python
   for sdt in sdt_collection:
       if sdt.sdt_type == aspose.words.SdtType.PLAIN_TEXT:
           sdt.get_first_child().remove_all_children()
           sdt.get_first_child().append_child(aspose.words.Run(doc, "New Content"))
   ```

## Verwendung von SDTs für die Dokumentenautomatisierung

SDTs können für Dokumentautomatisierungsszenarien genutzt werden. Sie können beispielsweise Rechnungsvorlagen mit SDTs für variable Felder wie Kundennamen, Beträge und Daten erstellen. Füllen Sie diese Felder dann programmgesteuert basierend auf Daten aus einer Datenbank aus.

## Anpassen des Erscheinungsbilds und Verhaltens von SDT

SDTs bieten verschiedene Anpassungsoptionen, z. B. das Ändern von Schriftarten, Farben und Verhalten. Sie können beispielsweise Platzhaltertext festlegen, um Benutzer beim Ausfüllen von SDTs zu unterstützen.

## Fortgeschrittene Techniken mit SDTs

Fortgeschrittene Techniken umfassen verschachtelte SDTs, benutzerdefinierte XML-Datenbindung und die Verarbeitung von mit SDTs verbundenen Ereignissen. Diese Techniken ermöglichen komplizierte Dokumentstrukturen und interaktivere Benutzererlebnisse.

## Best Practices für die Verwendung von SDTs

Befolgen Sie diese Best Practices bei der Verwendung von SDTs:

- Verwenden Sie SDTs konsistent für ähnliche Inhalte in allen Dokumenten.
- Planen Sie vor der Implementierung die Struktur Ihres Dokuments und Ihrer SDTs.
- Testen Sie das Dokument gründlich, insbesondere wenn Sie die Inhaltsfüllung automatisieren.

## Fallstudie: Erstellen einer dynamischen Berichtsvorlage

Betrachten wir eine Fallstudie, in der wir mithilfe von SDTs eine dynamische Berichtsvorlage erstellen. Wir erstellen Platzhalter für einen Berichtstitel, den Namen des Autors und den Inhalt. Anschließend füllen wir diese Platzhalter programmgesteuert mit relevanten Daten.

## Abschluss

Strukturierte Dokument-Tags bieten eine effektive Möglichkeit, strukturierte Daten in Dokumenten zu verwalten. Durch die Nutzung von Aspose.Words für Python können Entwickler problemlos dynamische und automatisierte Dokumentlösungen erstellen. SDTs ermöglichen Benutzern die Interaktion mit Dokumenten unter Wahrung der Konsistenz und Integrität.

## FAQs

### Wie greife ich auf die Inhalte innerhalb eines SDT zu?

 Um auf den Inhalt innerhalb eines SDT zuzugreifen, können Sie die verwenden`get_text()`Methode der Inhaltskontrolle des SDT. Dadurch wird der im SDT enthaltene Text abgerufen.

### Kann ich SDTs in Excel- oder PowerPoint-Dokumenten verwenden?

Nein, SDTs gelten speziell für Word-Dokumente und sind in Excel oder PowerPoint nicht verfügbar.

### Sind SDTs mit älteren Versionen von Microsoft Word kompatibel?

SDTs sind mit Microsoft Word 2010 und späteren Versionen kompatibel. In früheren Versionen funktionieren sie möglicherweise nicht wie vorgesehen.

### Kann ich benutzerdefinierte SDT-Typen erstellen?

Ab sofort unterstützt Microsoft Word einen vordefinierten Satz von SDT-Typen. Benutzerdefinierte SDT-Typen können nicht erstellt werden.

### Wie kann ich ein SDT aus einem Dokument entfernen?

Sie können eine SDT aus einem Dokument entfernen, indem Sie die SDT auswählen und die Taste „Entf“ drücken oder die entsprechende Methode in der Aspose.Words-API verwenden.