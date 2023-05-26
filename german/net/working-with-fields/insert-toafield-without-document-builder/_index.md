---
title: TOA-Feld ohne Document Builder einfügen
linktitle: TOA-Feld ohne Document Builder einfügen
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Einfügen eines TOA-Felds ohne Document Builder mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-fields/insert-toafield-without-document-builder/
---

Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der die Funktion „TOA Field Insertion“ von Aspose.Words für .NET verwendet. Befolgen Sie jeden Schritt sorgfältig, um die gewünschten Ergebnisse zu erzielen.

## Schritt 1: Einrichten des Dokumentenverzeichnisses

Im bereitgestellten Code müssen Sie das Verzeichnis Ihrer Dokumente angeben. Ersetzen Sie den Wert „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Dokument und Absatz erstellen

Wir beginnen mit der Erstellung eines neuen Dokuments und der Initialisierung eines Absatzes.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Schritt 3: Einfügen des TA-Feldes

Wir verwenden die FieldTA-Klasse, um ein TA-Feld in den Absatz einzufügen.

```csharp
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";
```

## Schritt 4: Hinzufügen des Absatzes zum Hauptteil des Dokuments

Wir fügen den Absatz, der das TA-Feld enthält, zum Hauptteil des Dokuments hinzu.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Schritt 5: Erstellen des Absatzes für das TOA-Feld

Wir erstellen einen neuen Absatz für das TOA-Feld.

```csharp
para = new Paragraph(doc);
```

## Schritt 6: Einfügen des TOA-Feldes

Wir verwenden die FieldToa-Klasse, um ein TOA-Feld in den Absatz einzufügen.

```csharp
FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
```

## Schritt 7: Hinzufügen des Absatzes zum Hauptteil des Dokuments

Wir fügen den Absatz, der das TOA-Feld enthält, zum Hauptteil des Dokuments hinzu.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Schritt 8: TOA-Feld aktualisieren

 Abschließend nennen wir die`Update()` Methode zum Aktualisieren des TOA-Felds.

```csharp
fieldToa.Update();
```

### Quellcode-Beispiel für das Einfügen von TOA-Feldern ohne Document Builder mit Aspose.Words für .NET

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
