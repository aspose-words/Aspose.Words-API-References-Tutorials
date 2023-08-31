---
title: Felder löschen
linktitle: Felder löschen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Löschen von Zusammenführungsfeldern in Ihren Word-Dokumenten mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-fields/delete-fields/
---

Hier erfahren Sie, wie Sie die Funktion „Felder löschen“ in Aspose verwenden. Words für .NET haben wir unten eine Schritt-für-Schritt-Anleitung erstellt. 

Es ist wichtig, jeden Schritt genau zu befolgen, um die gewünschten Ergebnisse zu erzielen. 

## Schritt 1: Erstellen eines neuen Dokuments

In diesem Codeausschnitt erstellen wir zunächst ein neues leeres Dokument mit der folgenden Zeile: 

```csharp
Document doc = new Document();
```

## Schritt 2: Zusammenführungsfelder entfernen

 Um alle im Dokument vorhandenen Zusammenführungsfelder zu entfernen, verwenden wir die`DeleteFields()` Funktion. 

Dies ist besonders nützlich, wenn Sie nur den statischen Inhalt behalten und alle Zusammenführungsinformationen entfernen möchten. 

### Quellcode-Beispiel zum Löschen von Feldern mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vorhandenes Dokument laden.
Document doc = new Document(dataDir + "YourDocument.docx");

// Zusammenführungsfelder entfernen.
doc.MailMerge.DeleteFields();

// Speichern Sie das geänderte Dokument.
doc.Save(dataDir + "YourDocument_WithoutFields.docx");
```

 In unserem Beispiel laden wir vor dem Aufruf zunächst ein bestehendes Dokument`DeleteFields()`. Abschließend speichern wir das geänderte Dokument unter einem neuen Dateinamen. 

Um Zusammenführungsfelder mithilfe der Funktion „Felder entfernen“ von Aspose.Words für .NET effektiv aus einem Dokument zu entfernen, können Sie sich an diesem Beispiel orientieren. 

Denken Sie immer daran, „IHR DOKUMENTENVERZEICHNIS“ durch Ihren spezifischen Verzeichnispfad zu ersetzen. 

Unser Leitfaden zur Implementierung der Funktion „Felder löschen“ über Aspose.Words für .NET ist damit abgeschlossen.

### FAQs

#### F: Was ist ein Feld in Aspose.Words?

A: Ein Feld in Aspose.Words ist eine Dokumentstruktur, die automatisch generierten Text oder einen berechneten Wert darstellt. Felder werden verwendet, um dynamische Informationen in einem Dokument anzuzeigen, wie z. B. Seitenzahlen, Datumsangaben, Seriendruckfelder usw.

#### F: Wie lösche ich ein Feld in einem Word-Dokument mit Aspose.Words?

A: Um ein Feld in einem Word-Dokument mit Aspose.Words zu löschen, können Sie die folgenden Schritte ausführen:

1. Importieren Sie die Document-Klasse aus dem Aspose.Words-Namespace.
2. Erstellen Sie eine Instanz von Document, indem Sie Ihr vorhandenes Dokument laden.
3. Verwenden Sie die RemoveFields-Methode, um alle Felder aus dem Dokument zu entfernen.

#### F: Kann ich bestimmte Felder löschen, anstatt alle Felder aus einem Dokument zu löschen?

A: Ja, Sie können bestimmte Felder löschen, anstatt alle Felder aus einem Dokument zu löschen. Dazu müssen Sie auf jedes Feld einzeln zugreifen und es mit der Remove-Methode entfernen.

#### F: Wie kann ich prüfen, ob ein Feld in einem Word-Dokument vorhanden ist, bevor ich es lösche?

A: Um zu überprüfen, ob ein Feld in einem Word-Dokument vorhanden ist, bevor Sie es löschen, können Sie die Methode „Contains“ der Fields-Auflistung verwenden, um das angegebene Feld zu finden. Diese Methode gibt einen booleschen Wert zurück, der angibt, ob das Feld vorhanden ist oder nicht.

#### F: Welche Auswirkungen hat das Löschen eines Felds auf den Rest des Dokuments?

A: Wenn Sie ein Feld in einem Word-Dokument löschen, wird das Feld aus dem Dokument entfernt und der mit dem Feld verknüpfte generierte Text oder berechnete Wert wird gelöscht. Dies kann Auswirkungen auf das Dokumentlayout haben, da der vom Feld generierte Inhalt gelöscht wird.