---
title: Feld einfügen
linktitle: Feld einfügen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Feld in Ihre Word-Dokumente einfügen. Personalisieren Sie Ihre Dokumente mit dynamischen Feldern.
type: docs
weight: 10
url: /de/net/working-with-fields/insert-field/
---

Hier ist eine Schritt-für-Schritt-Anleitung zur Erläuterung des C#-Quellcodes unten, der die Funktion „Feld einfügen“ von Aspose.Words für .NET verwendet. Befolgen Sie jeden Schritt sorgfältig, um die gewünschten Ergebnisse zu erzielen.

## Schritt 1: Einrichten des Dokumentverzeichnisses

Im angegebenen Code müssen Sie das Verzeichnis Ihrer Dokumente angeben. Ersetzen Sie den Wert „IHR DOKUMENTVERZEICHNIS“ durch den entsprechenden Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen des Dokuments und des DocumentBuilder

Wir beginnen mit der Erstellung eines neuen Dokuments und der Initialisierung eines DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Einfügen des Feldes

 Wir benutzen das`InsertField()` Methode des DocumentBuilder, um ein Feld in das Dokument einzufügen. In diesem Beispiel fügen wir ein Seriendruckfeld (MERGEFIELD) mit dem Feldnamen „MyFieldName“ und dem Seriendruckformat ein.

```csharp
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");
```

### Beispiel des Quellcodes zum Einfügen eines Feldes mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie das Dokument und den DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie das Feld ein.
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");

doc.Save(dataDir + "InsertionField.docx");
```

In diesem Beispiel haben wir ein neues Dokument erstellt, einen DocumentBuilder initialisiert und dann ein Seriendruckfeld mit dem Feldnamen „MyFieldName“ und Seriendruckformat eingefügt. Das Dokument wird dann unter einem angegebenen Dateinamen gespeichert.

Damit schließen wir unsere Anleitung zur Verwendung der Funktion „Feld einfügen“ mit Aspose.Words für .NET ab.

### Häufig gestellte Fragen

#### F: Was ist ein Feld in Word?

A: Ein Feld in Word ist ein Element, mit dem Sie dynamische Daten in ein Dokument einfügen und bearbeiten können. Es kann verwendet werden, um variable Informationen wie Daten, Seitenzahlen, Tabellen, mathematische Formeln usw. anzuzeigen.

#### F: Wie fügt man ein Feld in ein Word-Dokument ein?

A: Um ein Feld in ein Word-Dokument einzufügen, können Sie diese Schritte befolgen:

1. Platzieren Sie den Cursor an der Stelle, an der Sie das Feld einfügen möchten.
2. Gehen Sie in der Multifunktionsleiste auf die Registerkarte „Einfügen“.
3. Klicken Sie in der Gruppe „Text“ auf die Schaltfläche „Feld“, um das Dialogfeld „Felder“ zu öffnen.
4. Wählen Sie aus der Dropdownliste den Feldtyp aus, den Sie einfügen möchten.
5. Konfigurieren Sie die Feldoptionen nach Bedarf.
6. Klicken Sie auf die Schaltfläche „OK“, um das Feld in Ihr Dokument einzufügen.

#### F: Welche Feldtypen werden in Word häufig verwendet?

A: Word bietet eine Vielzahl von Feldtypen, die Sie in Ihren Dokumenten verwenden können. Hier sind einige der am häufigsten verwendeten Feldtypen:

- Datum und Uhrzeit: Zeigt das aktuelle Datum und die Uhrzeit an.
- Seitenzahl: zeigt die aktuelle Seitenzahl an.
- Inhaltsverzeichnis: Generiert automatisch ein Inhaltsverzeichnis basierend auf den Stilen Ihrer Titel.
- Berechnung: Führt mathematische Berechnungen mithilfe von Formeln durch.
- Fülltext: Generiert zufälligen Text zum Füllen Ihres Dokuments.

#### F: Kann ich das Erscheinungsbild von Feldern in Word anpassen?

A: Ja, Sie können das Erscheinungsbild von Feldern in Word mithilfe der verfügbaren Formatierungsoptionen anpassen. Sie können beispielsweise Schriftart, Größe, Farbe und Stil des Texts in einem Feld ändern. Sie können auch Formatierungseffekte wie Fettdruck, Kursivdruck und Unterstreichung anwenden.
  