---
title: Änderungen akzeptieren
linktitle: Änderungen akzeptieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Revisionen an einem Word-Dokument akzeptieren
type: docs
weight: 10
url: /de/net/working-with-revisions/accept-revisions/
---

In diesem Tutorial zeigen wir Ihnen Schritt für Schritt, wie Sie Revisionen an einem Word-Dokument mithilfe der Funktion „Revisionen akzeptieren“ von Aspose.Words für .NET akzeptieren. Befolgen Sie die nachstehenden Schritte, um den Quellcode zu verstehen und Änderungen am Dokument zu akzeptieren.

## Schritt 1: Dokumentinhalte hinzufügen und bearbeiten

In diesem Beispiel erstellen wir ein Dokument und fügen Inhalt hinzu. Wir verwenden mehrere Absätze, um Änderungen und Überarbeitungen zu veranschaulichen. So geht's:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// Fügen Sie dem ersten Absatz Text hinzu und fügen Sie dann zwei weitere Absätze hinzu.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## Schritt 2: Bewertungen verfolgen und Bewertungen hinzufügen

Wir aktivieren die Revisionsverfolgung und fügen dem Dokument eine Revision hinzu. So geht's:

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Dieser Absatz ist eine Revision und das entsprechende Flag „IsInsertRevision“ ist gesetzt.
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## Schritt 3: Einen Absatz löschen und Revisionen verwalten

Wir löschen einen Absatz und prüfen, ob gespeicherte Revisionen vorhanden sind. So geht's:

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Da wir Revisionen verfolgen, ist der Absatz noch im Dokument vorhanden und hat das Flag „IsDeleteRevision“ gesetzt.
// und wird als Bewertung in Microsoft Word angezeigt, bis wir alle Bewertungen akzeptieren oder ablehnen.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## Schritt 4: Änderungen akzeptieren

Wir akzeptieren alle Änderungen am Dokument. So geht's:

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## Schritt 5: Beenden Sie die Bewertungsverfolgung

Wir werden die Revisionsverfolgung beenden, sodass Änderungen am Dokument nicht mehr als Revisionen angezeigt werden. So geht's:

```csharp
doc.StopTrackRevisions();
```
## Schritt 6: Speichern des Dokuments

 Nach dem Einfügen des Texteingabeformularfelds speichern Sie das Dokument am gewünschten Speicherort mit dem`Save`Methode. Stellen Sie sicher, dass Sie den entsprechenden Dateipfad angeben:

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### Beispielquellcode für „Accept Revisions“ mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Akzeptieren von Änderungen in einem Dokument mit Aspose.Words für .NET:


```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// Fügen Sie dem ersten Absatz Text hinzu und fügen Sie dann zwei weitere Absätze hinzu.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

//Wir haben drei Absätze, von denen keiner als irgendeine Art von Revision registriert ist
// Wenn wir beim Verfolgen von Revisionen Inhalte im Dokument hinzufügen/entfernen,
// Sie werden als solche im Dokument angezeigt und können akzeptiert/abgelehnt werden.
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Dieser Absatz ist eine Revision und das entsprechende Flag „IsInsertRevision“ ist gesetzt.
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

// Holen Sie sich die Absatzsammlung des Dokuments und entfernen Sie einen Absatz.
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Da wir Revisionen verfolgen, existiert der Absatz immer noch im Dokument und hat den Wert "IsDeleteRevision"
// und wird als Revision in Microsoft Word angezeigt, bis wir alle Revisionen akzeptieren oder ablehnen.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// Der Absatz zum Löschen der Revision wird entfernt, sobald wir die Änderungen akzeptieren.
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

// Wenn die Revisionsverfolgung gestoppt wird, wird dieser Text als normaler Text angezeigt.
// Bei Änderungen am Dokument werden Revisionen nicht mitgezählt.
doc.StopTrackRevisions();

// Speichern Sie das Dokument.
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## Abschluss

In diesem Tutorial haben wir gelernt, wie man Revisionen in einem Word-Dokument mit der Funktion „Revisionen akzeptieren“ von Aspose.Words für .NET akzeptiert. Wir haben die Schritte befolgt, um Dokumentinhalte hinzuzufügen und zu bearbeiten, Revisionen zu verfolgen, einen überarbeiteten Absatz zu löschen, alle Änderungen zu akzeptieren und die Revisionsverfolgung zu beenden. Jetzt können Sie dieses Wissen anwenden, um Revisionen in Ihren eigenen Word-Dokumenten mit Aspose.Words für .NET effektiv zu verwalten.

### FAQs

#### F: Wie aktiviere ich die Revisionsverfolgung in Aspose.Words für .NET?

#### Lösung 1:

 A: Um die Revisionsverfolgung in Aspose.Words für .NET zu aktivieren, verwenden Sie die`StartTrackRevisions` Methode der`Document` Objekt und geben Sie den Autorennamen und das Startdatum für die Revisionsverfolgung an.

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### Lösung 2:

 A: Sie können die Revisionsverfolgung auch aktivieren, indem Sie`Document` Konstruktor, der akzeptiert`trackRevisions`Und`author` Parameter.

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### F: Wie akzeptiere ich mit Aspose.Words für .NET alle Änderungen in einem Dokument?

 A: Verwenden Sie die`AcceptAllRevisions` Methode der`Document` Einspruch einlegen, um alle am Dokument vorgenommenen Änderungen zu akzeptieren.

```csharp
doc.AcceptAllRevisions();
```

#### F: Wie speichere ich ein geändertes Dokument mit akzeptierten Revisionen?

 Verwenden Sie die`Save` Methode der`Document` Objekt, um das geänderte Dokument mit akzeptierten Revisionen zu speichern. Geben Sie unbedingt den richtigen Dateipfad an.

```csharp
doc.Save("path/to/the/document.docx");
```

#### F: Wie beende ich die Revisionsverfolgung in Aspose.Words für .NET?

 A: Verwenden Sie die`StopTrackRevisions` Methode der`Document` Objekt, um die Verfolgung von Revisionen zu stoppen.

```csharp
doc.StopTrackRevisions();
```

#### F: Wie lösche ich mit Aspose.Words für .NET einen überarbeiteten Absatz in einem Dokument?

 A: Um einen überarbeiteten Absatz in einem Dokument zu entfernen, können Sie den`Remove` Methode der Absatzsammlung.

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```