---
title: Feld einfügen Keines
linktitle: Feld einfügen Keines
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie AUCUN-Werte in Ihre Word-Dokumente mit Aspose.Words für .NET einfügen.
type: docs
weight: 10
url: /de/net/working-with-fields/insert-field-none/
---

Hier ist eine Schritt-für-Schritt-Anleitung zur Erläuterung des C#-Quellcodes unten, der die Funktion „KEIN Feld einfügen“ von Aspose.Words für .NET verwendet. Befolgen Sie jeden Schritt sorgfältig, um die gewünschten Ergebnisse zu erzielen.

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

## Schritt 3: Einfügen des Feldes NONE

 Wir benutzen das`InsertField()` Methode des DocumentBuilder, um ein NONE-Feld in das Dokument einzufügen.

```csharp
FieldUnknown field = (FieldUnknown)builder.InsertField(FieldType.FieldNone, false);
```

### Quellcodebeispiel zum Einfügen eines NONE-Felds mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie das Dokument und den DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie das Feld KEINE ein.
FieldUnknown field = (FieldUnknown)builder.InsertField(FieldType.FieldNone, false);

doc.Save(dataDir + "InsertionFieldNone.docx");
```

In diesem Beispiel haben wir ein neues Dokument erstellt, einen DocumentBuilder initialisiert und dann ein NONE-Feld eingefügt. Das Dokument wird dann unter einem angegebenen Dateinamen gespeichert.

Damit schließen wir unsere Anleitung zur Verwendung der Funktion „KEIN Feld einfügen“ mit Aspose.Words für .NET ab.

### Häufig gestellte Fragen

#### F: Was wird im Lernprogramm „Textverarbeitung mit Feldern: Feld „Keines“ einfügen“ behandelt?

A: Dieses Tutorial behandelt die Feldmanipulation in Aspose Words für .NET, mit besonderem Schwerpunkt auf dem Einfügen des Felds „Keine“. Felder sind dynamische Elemente in einem Word-Dokument, die zum Anzeigen oder Berechnen von Daten verwendet werden können. Das Tutorial erklärt, wie man das Feld „Keine“ einfügt und richtig verwendet.

#### F: Warum soll ich in Aspose Words das Feld „Keine“ verwenden?

A: Das Feld „Keine“ in Aspose Words ist nützlich, wenn Sie einen Platzhalter oder Marker in ein Dokument einfügen möchten, jedoch ohne einen bestimmten Effekt oder eine Berechnung. Es kann verwendet werden, um Stellen im Dokument zu markieren, an denen Sie später Daten einfügen möchten, oder um spezielle Notizen hinzuzufügen, ohne den restlichen Inhalt zu beeinträchtigen.

#### F: Kann ich das Feld „Keine“ mit zusätzlichen Parametern anpassen?

A: Nein, das Feld „Keine“ akzeptiert keine zusätzlichen Parameter. Es wird hauptsächlich als Markierung oder Platzhalter verwendet und hat keine spezielle Funktion. Sie können jedoch andere Feldtypen in Aspose Words verwenden, um erweiterte Operationen durchzuführen.