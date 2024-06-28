---
title: Akzeptieren Sie Bewertungen
linktitle: Akzeptieren Sie Bewertungen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Überarbeitungen an einem Word-Dokument akzeptieren
type: docs
weight: 10
url: /de/net/working-with-revisions/accept-revisions/
---

In diesem Tutorial führen wir Sie durch das Akzeptieren von Revisionen an einem Word-Dokument mithilfe der Funktion „Revisionen akzeptieren“ von Aspose.Words für .NET. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und Änderungen am Dokument zu akzeptieren.

## Schritt 1: Dokumentinhalt hinzufügen und bearbeiten

In diesem Beispiel erstellen wir ein Dokument und fügen Inhalte hinzu. Wir verwenden mehrere Absätze, um Änderungen und Überarbeitungen zu veranschaulichen. Hier ist wie:

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

## Schritt 2: Verfolgen Sie Bewertungen und fügen Sie Bewertungen hinzu

Wir aktivieren die Revisionsverfolgung und fügen dem Dokument eine Revision hinzu. Hier ist wie:

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Bei diesem Absatz handelt es sich um eine Überarbeitung und das entsprechende Flag „IsInsertRevision“ ist gesetzt.
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## Schritt 3: Löschen Sie einen Absatz und verwalten Sie Überarbeitungen

Wir löschen einen Absatz und suchen nach gespeicherten Überarbeitungen. Hier ist wie:

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Während wir Revisionen verfolgen, ist der Absatz noch im Dokument vorhanden und das Flag „IsDeleteRevision“ ist gesetzt
// und wird als Rezension in Microsoft Word angezeigt, bis wir alle Rezensionen akzeptieren oder ablehnen.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## Schritt 4: Änderungen akzeptieren

Wir akzeptieren alle Änderungen am Dokument. Hier ist wie:

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## Schritt 5: Beenden Sie die Verfolgung von Bewertungen

Wir werden die Nachverfolgung von Überarbeitungen einstellen, sodass Änderungen am Dokument nicht mehr als Überarbeitungen angezeigt werden. Hier ist wie:

```csharp
doc.StopTrackRevisions();
```
## Schritt 6: Speichern des Dokuments

 Nachdem Sie das Texteingabeformularfeld eingefügt haben, speichern Sie das Dokument mithilfe von am gewünschten Ort`Save` Methode. Stellen Sie sicher, dass Sie den richtigen Dateipfad angeben:

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### Beispielquellcode für Accept Revisions mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Akzeptieren von Änderungen in einem Dokument mit Aspose.Words für .NET:


```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// Fügen Sie dem ersten Absatz Text hinzu und fügen Sie dann zwei weitere Absätze hinzu.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

//Wir haben drei Absätze, von denen keiner als irgendeine Art von Überarbeitung registriert ist
// Wenn wir beim Verfolgen von Überarbeitungen Inhalte im Dokument hinzufügen/entfernen,
// sie werden als solche im Dokument angezeigt und können angenommen/abgelehnt werden.
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Bei diesem Absatz handelt es sich um eine Überarbeitung und das entsprechende Flag „IsInsertRevision“ ist gesetzt.
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

// Rufen Sie die Absatzsammlung des Dokuments ab und entfernen Sie einen Absatz.
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Da wir Revisionen verfolgen, ist der Absatz immer noch im Dokument vorhanden und es ist „IsDeleteRevision“ festgelegt
// und wird als Revision in Microsoft Word angezeigt, bis wir alle Revisionen akzeptieren oder ablehnen.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// Der gelöschte Revisionsabsatz wird entfernt, sobald wir die Änderungen akzeptieren.
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

// Wenn Sie die Verfolgung von Revisionen stoppen, wird dieser Text als normaler Text angezeigt.
// Revisionen werden bei einer Änderung des Dokuments nicht gezählt.
doc.StopTrackRevisions();

// Speichern Sie das Dokument.
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## Abschluss

In diesem Tutorial haben wir gelernt, wie man Revisionen in einem Word-Dokument mit der Funktion „Revisionen akzeptieren“ von Aspose.Words für .NET akzeptiert. Wir haben die Schritte befolgt, um Dokumentinhalte hinzuzufügen und zu bearbeiten, Überarbeitungen zu verfolgen, einen überarbeiteten Absatz zu löschen, alle Änderungen zu akzeptieren und die Nachverfolgung von Überarbeitungen zu beenden. Jetzt können Sie dieses Wissen anwenden, um Überarbeitungen in Ihren eigenen Word-Dokumenten mit Aspose.Words für .NET effektiv zu verwalten.

### FAQs

#### F: Wie aktiviere ich die Revisionsverfolgung in Aspose.Words für .NET?

#### Lösung 1:

 A: Um die Revisionsverfolgung in Aspose.Words für .NET zu aktivieren, verwenden Sie die`StartTrackRevisions` Methode der`Document` Objekt und geben Sie den Namen des Autors und das Startdatum für die Revisionsverfolgung an.

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### Lösung 2:

 A: Sie können die Revisionsverfolgung auch mit aktivieren`Document` Konstruktor, der akzeptiert`trackRevisions` Und`author` Parameter.

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### F: Wie übernehme ich alle Änderungen in einem Dokument mit Aspose.Words für .NET?

 A: Benutzen Sie die`AcceptAllRevisions` Methode der`Document` Einspruch gegen alle am Dokument vorgenommenen Änderungen einlegen.

```csharp
doc.AcceptAllRevisions();
```

#### F: Wie speichere ich ein geändertes Dokument mit akzeptierten Revisionen?

 Benutzen Sie die`Save` Methode der`Document` -Objekt, um das geänderte Dokument mit akzeptierten Revisionen zu speichern. Stellen Sie sicher, dass Sie den richtigen Dateipfad angeben.

```csharp
doc.Save("path/to/the/document.docx");
```

#### F: Wie kann ich die Nachverfolgung von Revisionen in Aspose.Words für .NET beenden?

 A: Benutzen Sie die`StopTrackRevisions` Methode der`Document` Objekt, um die Nachverfolgung von Revisionen zu stoppen.

```csharp
doc.StopTrackRevisions();
```

#### F: Wie lösche ich einen überarbeiteten Absatz in einem Dokument mit Aspose.Words für .NET?

 A: Um einen überarbeiteten Absatz in einem Dokument zu entfernen, können Sie den verwenden`Remove` Methode der Absatzsammlung.

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```