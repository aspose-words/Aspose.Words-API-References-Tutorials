---
title: Fügen Sie FieldIncludeText ohne Document Builder ein
linktitle: Fügen Sie FieldIncludeText ohne Document Builder ein
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein FieldIncludeText-Feld in Ihre Word-Dokumente einfügen.
type: docs
weight: 10
url: /de/net/working-with-fields/insert-field-include-text-without-document-builder/
---

Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der die Funktionalität „Ein FieldIncludeText-Feld einfügen“ von Aspose.Words für .NET verwendet. Stellen Sie sicher, dass Sie jeden Schritt sorgfältig befolgen, um die gewünschten Ergebnisse zu erzielen.

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

## Schritt 3: Einfügen des FieldIncludeText-Felds

 Wir benutzen das`AppendField()` Methode zum Einfügen eines FieldIncludeText-Felds in den Absatz.

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

Anschließend konfigurieren wir die Eigenschaften des FieldIncludeText-Felds, indem wir den Namen des Lesezeichens und den Namen der Quelldatei angeben.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

Als nächstes fügen wir den Absatz zum Hauptteil des Dokuments hinzu.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

 Abschließend nennen wir die`Update()` Methode zum Aktualisieren des Felds.

```csharp
fieldIncludeText.Update();
```

### Beispiel des Quellcodes zum Einfügen eines FieldIncludeText-Felds mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie das Dokument und den Absatz.
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Fügen Sie das FieldIncludeText-Feld ein.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

In diesem Beispiel haben wir ein neues Dokument erstellt, einen Absatz initialisiert, ein FieldIncludeTexten eingefügt, das den Namen des Lesezeichens und den Namen der Quelldatei angibt, und das Dokument unter einem angegebenen Dateinamen gespeichert.

Damit ist unser Leitfaden zur Verwendung der Funktion „Einen FieldIncludeText einfügen“ mit Aspose.Words für .NET abgeschlossen.