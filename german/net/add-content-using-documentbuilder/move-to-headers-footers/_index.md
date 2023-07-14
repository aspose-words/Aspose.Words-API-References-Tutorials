---
title: Zu Kopfzeilen und Fußzeilen wechseln
linktitle: Zu Kopfzeilen und Fußzeilen wechseln
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie Aspose.Words für .NET zum Navigieren und Ändern von Kopf- und Fußzeilen in Word-Dokumenten verwenden.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/move-to-headers-footers/
---

In diesem Beispiel untersuchen wir die Funktion „In Kopf- und Fußzeilen verschieben“ von Aspose.Words für .NET. Aspose.Words ist eine leistungsstarke Bibliothek zur Dokumentbearbeitung, mit der Entwickler Word-Dokumente programmgesteuert erstellen, ändern und konvertieren können. Mit der Funktion „In Kopf-/Fußzeilen verschieben“ können wir zu verschiedenen Kopf- und Fußzeilen innerhalb eines Dokuments navigieren und ihnen Inhalte hinzufügen.

Lassen Sie uns den Quellcode Schritt für Schritt durchgehen, um zu verstehen, wie Sie die Funktion „In Kopf-/Fußzeilen verschieben“ mit Aspose.Words für .NET verwenden.



## Schritt 1: Initialisieren des Dokuments und des Dokument-Builders

Initialisieren Sie zunächst die Objekte Document und DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Kopf- und Fußzeilen konfigurieren

Geben Sie die Kopf-/Fußzeileneinstellungen für das Dokument an. In diesem Beispiel stellen wir die Kopf- und Fußzeilen für die erste Seite und für ungerade/gerade Seiten unterschiedlich ein:

```csharp
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;
```

## Schritt 3: Kopfzeilen für verschiedene Seiten erstellen

Gehen Sie zu den einzelnen Header-Typen und fügen Sie ihnen Inhalte hinzu. In diesem Beispiel erstellen wir Kopfzeilen für die erste Seite, gerade Seiten und alle anderen Seiten:

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");
```

## Schritt 4: Seiten im Dokument erstellen
Fügen Sie dem Dokument Inhalte hinzu, um mehrere Seiten zu erstellen. Zum Beispiel:

```csharp
// Erstellen Sie zwei Seiten im Dokument.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
```
## Schritt 5: Speichern des Dokuments

Speichern Sie das geänderte Dokument an einem gewünschten Ort:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

Stellen Sie sicher, dass Sie den richtigen Dateipfad und das entsprechende Format angeben (z. B. DOCX).

### Beispielquellcode für „In Kopf-/Fußzeilen verschieben“ mit Aspose.Words für .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Geben Sie an, dass die Kopf- und Fußzeilen für die erste, gerade und ungerade Seite unterschiedlich sein sollen.
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;

// Erstellen Sie die Header.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");

// Erstellen Sie zwei Seiten im Dokument.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```
