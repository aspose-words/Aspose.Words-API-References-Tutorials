---
title: Feld-Update-Kultur
linktitle: Feld-Update-Kultur
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Feldkultur in Ihren Word-Dokumenten aktualisieren.
type: docs
weight: 10
url: /de/net/working-with-fields/field-update-culture/
---

Hier ist eine Schritt-für-Schritt-Anleitung zur Erläuterung des C#-Quellcodes unten, der die Funktion „Field Culture Update“ von Aspose.Words für .NET verwendet. Befolgen Sie jeden Schritt sorgfältig, um die gewünschten Ergebnisse zu erzielen.

## Schritt 1: Einrichten des Dokumentverzeichnisses

Im angegebenen Code müssen Sie das Verzeichnis Ihrer Dokumente angeben. Ersetzen Sie den Wert „IHR DOKUMENTVERZEICHNIS“ durch den entsprechenden Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen des Dokuments und des Dokumentgenerators

Wir beginnen mit der Erstellung eines neuen Dokuments und eines Dokumentgenerators.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Einfügen des Zeitfeldes

 Wir benutzen das`InsertField()`Methode, um ein Zeitfeld in das Dokument einzufügen.

```csharp
builder. InsertField(FieldType.FieldTime, true);
```

Dadurch wird ein Zeitfeld in das Dokument eingefügt.

## Schritt 4: Konfigurieren der Feldaktualisierungskultur

Wir konfigurieren die Feldoptionen, um anzugeben, dass die Feldaktualisierungskultur auf dem Feldcode basieren soll.

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();
```

Diese Optionen bestimmen die Kultur, die zum Aktualisieren von Feldern verwendet wird.

### Beispiel-Quellcode zum Aktualisieren der Feldkultur mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie das Dokument und den Dokumentgenerator.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie das Zeitfeld ein.
builder. InsertField(FieldType.FieldTime, true);

// Konfigurieren Sie die Feldaktualisierungskultur.
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();

// Speichern Sie das Dokument.
doc.Save(dataDir + "UpdateCultureChamps.pdf");
```

In diesem Beispiel haben wir ein neues Dokument erstellt, ein Zeitfeld eingefügt und die Feldaktualisierungskultur konfiguriert. Anschließend haben wir das Dokument unter einem angegebenen Dateinamen gespeichert.

Damit schließen wir unsere Anleitung zur Verwendung der Funktion „Feldkultur aktualisieren“ mit Aspose.Words für .NET ab.

### Häufig gestellte Fragen

#### F: Was ist die Feldaktualisierungskultur in Aspose.Words?

A: Die Feldaktualisierungskultur in Aspose.Words bezieht sich auf die Kultur, die zum Formatieren und Aktualisieren von Feldwerten in einem Word-Dokument verwendet wird. Die Kultur bestimmt, wie Zahlen, Daten und andere Daten in Feldern dargestellt werden, wenn sie aktualisiert werden.

#### F: Wie lege ich mit Aspose.Words die Aktualisierungskultur für Felder in einem Word-Dokument fest?

A: Um die Aktualisierungskultur für Felder in einem Word-Dokument mit Aspose.Words festzulegen, können Sie die folgenden Schritte ausführen:

1. Importieren Sie die Document-Klasse aus dem Aspose.Words-Namespace.
2. Erstellen Sie eine Instanz von Document, indem Sie Ihr vorhandenes Dokument laden.
3. Verwenden Sie die Eigenschaft Document.UpdateFieldsCultureInfo, um die Aktualisierungskultur für Felder festzulegen.

#### F: Welche Kulturen werden zum Aktualisieren von Feldern in Aspose.Words unterstützt?

A: Aspose.Words unterstützt verschiedene Kulturen zum Aktualisieren von Feldern. Sie können jede vom Betriebssystem unterstützte Kultur angeben. Zum Beispiel „en-US“ für amerikanisches Englisch, „fr-FR“ für Französisch, „de-DE“ für Deutsch usw.

#### F: Ist es möglich, eine bestimmte Kultur für ein einzelnes Feld statt für das gesamte Dokument festzulegen?

A: Ja, es ist möglich, eine bestimmte Kultur für ein einzelnes Feld statt für das gesamte Dokument festzulegen. In Aspose.Words hat jedes Feld eine Format-Eigenschaft, mit der die für dieses Feld spezifische Formatierungskultur festgelegt werden kann. Auf diese Weise können Sie steuern, wie dieses Feld unabhängig von anderen Feldern im Dokument angezeigt und aktualisiert wird.

#### F: Wie kann ich die aktuell definierte Feldaktualisierungskultur in einem Word-Dokument überprüfen?

A: Um die aktuell definierte Feldaktualisierungskultur in einem Word-Dokument zu überprüfen, können Sie die Eigenschaft Document.UpdateFieldsCultureInfo verwenden. Diese Eigenschaft gibt das CultureInfo-Objekt zurück, das die Kultur darstellt, die aktuell zum Festlegen von Feldaktualisierungen verwendet wird.