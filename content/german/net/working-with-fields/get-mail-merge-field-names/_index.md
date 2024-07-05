---
title: Abrufen von Feldnamen für Seriendruck
linktitle: Abrufen von Feldnamen für Seriendruck
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Serienbrieffeldnamen in Ihre Word-Dokumente erhalten.
type: docs
weight: 10
url: /de/net/working-with-fields/get-mail-merge-field-names/
---

Hier ist eine Schritt-für-Schritt-Anleitung zur Erläuterung des C#-Quellcodes unten, der die Funktion „Get Merge Field Names“ von Aspose.Words für .NET verwendet. Befolgen Sie jeden Schritt sorgfältig, um die gewünschten Ergebnisse zu erzielen.

## Schritt 1: Einrichten des Dokumentverzeichnisses

Im angegebenen Code müssen Sie das Verzeichnis Ihrer Dokumente angeben. Ersetzen Sie den Wert „IHR DOKUMENTVERZEICHNIS“ durch den entsprechenden Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Dokument einlegen

Der erste Schritt besteht darin, das Dokument zu laden, aus dem Sie die Seriendruckfeldnamen erhalten möchten.

```csharp
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");
```

Ersetzen Sie „IHRE DOKUMENTDATEI“ unbedingt durch den Namen Ihrer eigenen Datei.

## Schritt 3: Seriendruckfeldnamen abrufen

 Wir benutzen das`GetFieldNames()` Methode, um ein Array mit den Namen der im Dokument vorhandenen Seriendruckfelder abzurufen.

```csharp
string[] fieldNames = doc.MailMerge.GetFieldNames();
```

 Der`fieldNames` Die Variable enthält jetzt die Namen der Seriendruckfelder.

### Quellcodebeispiel zum Abrufen von Seriendruckfeldnamen mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Legen Sie das Dokument ein.
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");

// Seriendruckfeldnamen abrufen.
string[] fieldNames = doc.MailMerge.GetFieldNames();

// Zeigt die Anzahl der Seriendruckfelder an.
Console.WriteLine("\nDocument contains " + fieldNames.Length + " merge fields.");
```

 In diesem Beispiel haben wir ein Dokument geladen, die Namen der Seriendruckfelder mithilfe der`GetFieldNames()` Methode und zeigt die Anzahl der im Dokument vorhandenen Seriendruckfelder an.

Damit schließen wir unsere Anleitung zur Verwendung der Funktion „Seriendruckfeldnamen abrufen“ mit Aspose.Words für .NET ab.

### FAQs

#### F1: Was ist Serienbrieffunktion in Aspose.Words?

Serienbriefe in Aspose.Words sind ein Prozess, bei dem Daten aus einer externen Quelle (z. B. Excel-Tabelle oder Datenbank) mit einer Word-Vorlage zusammengeführt werden, um personalisierte Dokumente zu erstellen. Dies erleichtert die automatische Erstellung von Briefen, Berichten und anderen ähnlichen Dokumenten.

#### F2: Wie erhalte ich die Liste der in einem Word-Dokument verfügbaren Seriendruckfelder?

Um die Liste der in einem Word-Dokument verfügbaren Seriendruckfelder abzurufen, können Sie die folgenden Schritte ausführen:

1. Importieren Sie die Klassen Document und MailMergeFieldNames aus dem Aspose.Words-Namespace.
2. Erstellen Sie eine Dokumentinstanz, indem Sie Ihr Word-Dokument laden.
3. Verwenden Sie die Methode GetMailMergeFieldNames des Document-Objekts, um die Liste der verfügbaren Seriendruckfelder abzurufen.

Hier ist ein Beispielcode zur Veranschaulichung des Vorgangs:

```csharp
// Importieren Sie die erforderlichen Namespaces
using Aspose.Words;
using Aspose.Words.MailMerging;

// Laden Sie das vorhandene Dokument
Document document = new Document("FilePath");

// Liste der Serienbrieffelder abrufen
MailMergeFieldNames fieldNames = document.MailMerge.GetFieldNames();

// Durch die verfügbaren Serienbrieffelder blättern
foreach (string fieldName in fieldNames)
{
     // Machen Sie etwas mit dem Feldnamen
     Console.WriteLine(fieldName);
}
```
### Häufig gestellte Fragen

#### F: Was ist Serienbrieffunktion in Aspose.Words?

A: Seriendruck in Aspose.Words ist ein Prozess, bei dem Daten aus einer externen Quelle (z. B. Excel-Tabelle oder Datenbank) mit einer Word-Vorlage zusammengeführt werden, um personalisierte Dokumente zu erstellen. Dies erleichtert die automatische Erstellung von Briefen, Berichten und anderen ähnlichen Dokumenten.

#### F: Wie erhalte ich die Liste der in einem Word-Dokument verfügbaren Seriendruckfelder?

A: Um die Liste der in einem Word-Dokument verfügbaren Seriendruckfelder zu erhalten, können Sie die folgenden Schritte ausführen:

1. Importieren Sie die Klassen Document und MailMergeFieldNames aus dem Aspose.Words-Namespace.
2. Erstellen Sie eine Dokumentinstanz, indem Sie Ihr Word-Dokument laden.
3. Verwenden Sie die Methode GetMailMergeFieldNames des Document-Objekts, um die Liste der verfügbaren Seriendruckfelder abzurufen.

#### F: Kann ich Serienbrieffelder aus einer externen Datenquelle wie beispielsweise einer Excel-Tabelle abrufen?

A: Ja, Sie können die Seriendruckfelder aus einer externen Datenquelle wie einer Excel-Tabelle abrufen. Dazu können Sie die Datenbindungsfunktionen von Aspose.Words verwenden, um eine Verbindung mit der Datenquelle herzustellen und die Namen der verfügbaren Felder abzurufen.

#### F: Ist es möglich, Serienbrieffelder nach bestimmten Kriterien zu filtern?

A: Ja, es ist möglich, Serienbrieffelder nach bestimmten Kriterien zu filtern. Sie können reguläre Ausdrücke oder bestimmte Bedingungen verwenden, um Serienbrieffelder zu filtern und nur diejenigen zu erhalten, die Ihren spezifischen Kriterien entsprechen.

#### F: Wie kann ich Serienbrieffelder in Aspose.Words bearbeiten?

A: Um Serienbrieffelder in Aspose.Words zu bearbeiten, können Sie die Methoden und Eigenschaften verwenden, die von den Objekten Document und MailMergeField bereitgestellt werden. Sie können Serienbrieffelder hinzufügen, entfernen oder aktualisieren sowie mit Feldern verknüpfte Werte abrufen und bearbeiten.