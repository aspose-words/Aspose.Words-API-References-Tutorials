---
title: Feld einfügen
linktitle: Feld einfügen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Feld in Ihre Word-Dokumente einfügen. Personalisieren Sie Ihre Dokumente mit dynamischen Feldern.
type: docs
weight: 10
url: /de/net/working-with-fields/insert-field/
---

Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der die Funktion „Ein Feld einfügen“ von Aspose.Words für .NET verwendet. Stellen Sie sicher, dass Sie jeden Schritt sorgfältig befolgen, um die gewünschten Ergebnisse zu erzielen.

## Schritt 1: Einrichten des Dokumentenverzeichnisses

Im bereitgestellten Code müssen Sie das Verzeichnis Ihrer Dokumente angeben. Ersetzen Sie den Wert „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen des Dokuments und DocumentBuilder

Wir beginnen mit der Erstellung eines neuen Dokuments und der Initialisierung eines DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Einfügen des Feldes

 Wir benutzen das`InsertField()` Methode des DocumentBuilders, um ein Feld in das Dokument einzufügen. In diesem Beispiel fügen wir ein Zusammenführungsfeld (MERGEFIELD) mit dem Feldnamen „MyFieldName“ und dem Zusammenführungsformat ein.

```csharp
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");
```

### Beispiel des Quellcodes zum Einfügen eines Feldes mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie das Dokument und den DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie das Feld ein.
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");

doc.Save(dataDir + "InsertionField.docx");
```

In diesem Beispiel haben wir ein neues Dokument erstellt, einen DocumentBuilder initialisiert und dann ein Zusammenführungsfeld mit dem Feldnamen „MyFieldName“ und dem Zusammenführungsformat eingefügt. Das Dokument wird dann unter einem angegebenen Dateinamen gespeichert.

Damit ist unser Leitfaden zur Verwendung der Funktion „Ein Feld einfügen“ mit Aspose.Words für .NET abgeschlossen.

### FAQs

#### F: Was ist ein Feld in Word?

A: Ein Feld in Word ist ein Element, mit dem Sie dynamische Daten in ein Dokument einfügen und bearbeiten können. Es kann zur Anzeige variabler Informationen wie Datumsangaben, Seitenzahlen, Tabellen, mathematische Formeln usw. verwendet werden.

#### F: Wie füge ich ein Feld in ein Word-Dokument ein?

A: Um ein Feld in ein Word-Dokument einzufügen, können Sie die folgenden Schritte ausführen:

1. Platzieren Sie Ihren Cursor an der Stelle, an der Sie das Feld einfügen möchten.
2. Gehen Sie im Menüband auf die Registerkarte „Einfügen“.
3. Klicken Sie in der Gruppe „Text“ auf die Schaltfläche „Feld“, um das Felddialogfeld zu öffnen.
4. Wählen Sie aus der Dropdown-Liste den Feldtyp aus, den Sie einfügen möchten.
5. Konfigurieren Sie die Feldoptionen nach Bedarf.
6. Klicken Sie auf die Schaltfläche „OK“, um das Feld in Ihr Dokument einzufügen.

#### F: Welche Feldtypen werden in Word häufig verwendet?

A: Word bietet eine Vielzahl von Feldtypen, die Sie in Ihren Dokumenten verwenden können. Hier sind einige der am häufigsten verwendeten Feldtypen:

- Datum und Uhrzeit: Zeigt das aktuelle Datum und die aktuelle Uhrzeit an.
- Seitenzahl: Zeigt die aktuelle Seitenzahl an.
- Inhaltsverzeichnis: Erstellt automatisch ein Inhaltsverzeichnis basierend auf den Stilen Ihrer Titel.
- Berechnung: Führt mathematische Berechnungen mithilfe von Formeln durch.
- Fülltext: Erzeugt zufälligen Text zum Füllen Ihres Dokuments.

#### F: Kann ich das Erscheinungsbild von Feldern in Word anpassen?

A: Ja, Sie können das Erscheinungsbild von Feldern in Word mithilfe der verfügbaren Formatierungsoptionen anpassen. Sie können beispielsweise Schriftart, Größe, Farbe und Stil des Texts in einem Feld ändern. Sie können auch Formatierungseffekte wie Fett, Kursiv und Unterstrichen anwenden.
  