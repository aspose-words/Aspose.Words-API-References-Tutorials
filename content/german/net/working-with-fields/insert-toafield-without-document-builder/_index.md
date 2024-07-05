---
title: TOA-Feld ohne Document Builder einfügen
linktitle: TOA-Feld ohne Document Builder einfügen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Einfügen eines TOA-Felds ohne Document Builder mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-fields/insert-toafield-without-document-builder/
---

Hier ist eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der die Funktion „TOA Field Insertion“ von Aspose.Words für .NET verwendet. Befolgen Sie jeden Schritt sorgfältig, um die gewünschten Ergebnisse zu erzielen.

## Schritt 1: Einrichten des Dokumentverzeichnisses

Im angegebenen Code müssen Sie das Verzeichnis Ihrer Dokumente angeben. Ersetzen Sie den Wert „IHR DOKUMENTVERZEICHNIS“ durch den entsprechenden Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen des Dokuments und des Absatzes

Wir beginnen mit der Erstellung eines neuen Dokuments und der Initialisierung eines Absatzes.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Schritt 3: Einfügen des TA-Feldes

Wir verwenden die Klasse FieldTA, um ein TA-Feld in den Absatz einzufügen.

```csharp
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";
```

## Schritt 4: Hinzufügen des Absatzes zum Hauptteil des Dokuments

Wir fügen den Absatz, der das TA-Feld enthält, dem Hauptteil des Dokuments hinzu.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Schritt 5: Absatz für das TOA-Feld erstellen

Wir erstellen einen neuen Absatz für das TOA-Feld.

```csharp
para = new Paragraph(doc);
```

## Schritt 6: Einfügen des TOA-Feldes

Wir verwenden die Klasse FieldToa, um ein TOA-Feld in den Absatz einzufügen.

```csharp
FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
```

## Schritt 7: Hinzufügen des Absatzes zum Hauptteil des Dokuments

Wir fügen den Absatz, der das TOA-Feld enthält, dem Hauptteil des Dokuments hinzu.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Schritt 8: TOA-Feld aktualisieren

 Schließlich nennen wir die`Update()` Methode zum Aktualisieren des TOA-Felds.

```csharp
fieldToa.Update();
```

### Quellcodebeispiel für TOA-Feldeinfügung ohne Document Builder mit Aspose.Words für .NET

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Wir möchten TA- und TOA-Felder wie folgt einfügen:
// { TA \c 1 \l "Wert 0" }
// { TOA \c 1 }

FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);

para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);

fieldToa.Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

### Häufig gestellte Fragen

#### F: Wie kann ich das Erscheinungsbild des in das Word-Dokument eingefügten TOA-Felds mit Aspose.Words für .NET anpassen?

A: Sie können das Erscheinungsbild des eingefügten TOA-Feldes anpassen, indem Sie die Eigenschaften des`FieldTOA` Objekt, um Formatierungsoptionen anzugeben.

#### F: Kann ich mit Aspose.Words für .NET mehrere TOA-Felder in ein einzelnes Word-Dokument einfügen?

A: Ja, Sie können mit Aspose.Words für .NET mehrere TOA-Felder in ein einzelnes Word-Dokument einfügen. Wiederholen Sie einfach die Einfügeschritte für jedes Feld.

#### F: Wie kann ich überprüfen, ob ein TOA-Feld mit Aspose.Words für .NET erfolgreich in ein Word-Dokument eingefügt wurde?

A: Um zu überprüfen, ob ein TOA-Feld erfolgreich eingefügt wurde, können Sie den Dokumentinhalt durchsuchen und nach TOA-Feldinstanzen suchen.

#### F: Hat das Einfügen eines TOA-Felds ohne Verwendung von DocumentBuilder Auswirkungen auf die Formatierung von Word-Dokumenten mit Aspose.Words für .NET?

A: Das Einfügen eines TOA-Felds ohne Verwendung von DocumentBuilder wirkt sich nicht direkt auf die Formatierung des Word-Dokuments aus. Die Formatierungsoptionen des TOA-Felds können sich jedoch auf die Gesamtformatierung des Dokuments auswirken.