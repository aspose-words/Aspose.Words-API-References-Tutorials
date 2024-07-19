---
title: Eigentümerdokument
linktitle: Eigentümerdokument
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie das Eigentümerdokument in Aspose.Words für .NET verwenden.
type: docs
weight: 10
url: /de/net/working-with-node/owner-document/
---

Hier ist eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, die veranschaulicht, wie proprietäre Dokumentfunktionen mit Aspose.Words für .NET verwendet werden.

## Schritt 1: Importieren Sie die erforderlichen Referenzen
Stellen Sie vor dem Beginn sicher, dass Sie die erforderlichen Referenzen importiert haben, um Aspose.Words für .NET in Ihrem Projekt zu verwenden. Dazu gehört das Importieren der Aspose.Words-Bibliothek und das Hinzufügen der erforderlichen Namespaces zu Ihrer Quelldatei.

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
using Aspose.Words.Paragraphs;
```

## Schritt 2: Neues Dokument erstellen
 In diesem Schritt erstellen wir ein neues Dokument mit dem`Document` Klasse.

```csharp
Document doc = new Document();
```

## Schritt 3: Erstellen Sie einen Knoten mit dem Eigentümerdokument
 Wenn Sie einen neuen Knoten beliebigen Typs erstellen, müssen Sie das Dokument an den Konstruktor übergeben. In diesem Beispiel erstellen wir einen neuen Absatzknoten mit dem Dokument`doc`.

```csharp
Paragraph para = new Paragraph(doc);
```

## Schritt 4: Überprüfen Sie den übergeordneten Knoten und das Eigentümerdokument
Nachdem wir nun den Absatzknoten erstellt haben, können wir prüfen, ob er einen übergeordneten Knoten hat und ob das übergeordnete Dokument dasselbe ist wie`doc`.

```csharp
Console.WriteLine("The paragraph has no parent node: " + (para.ParentNode == null));
Console.WriteLine("The documents of the two nodes are identical: " + (para.Document == doc));
```

## Schritt 5: Knoteneigenschaften mit Dokumentdaten ändern
Die Beziehung zwischen einem Knoten und einem Dokument ermöglicht den Zugriff auf und die Änderung von Eigenschaften, die sich auf dokumentspezifische Daten beziehen, wie z. B. Stile oder Listen. In diesem Beispiel legen wir den Namen des Absatzstils auf „Überschrift 1“ fest.

```csharp
para.ParagraphFormat.StyleName = "Heading 1";
```

## Schritt 6: Fügen Sie den Absatz zum Dokument hinzu
Jetzt können wir den Absatzknoten zum Hauptabschnitt des Dokuments hinzufügen.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Schritt 7: Überprüfen des übergeordneten Knotens nach dem Hinzufügen
Nachdem wir den Absatz zum Dokument hinzugefügt haben, prüfen wir erneut, ob er jetzt einen übergeordneten Knoten hat.

```csharp
Console.WriteLine("The paragraph has a parent node: " + (para.ParentNode != null));
```

### Beispielquellcode für Eigentümerdokument mit Aspose.Words für .NET

```csharp
Document doc = new Document();

// Zum Erstellen eines neuen Knotens beliebigen Typs ist die Übergabe eines Dokuments an den Konstruktor erforderlich.
Paragraph para = new Paragraph(doc);

// Der neue Absatzknoten hat noch keinen übergeordneten Knoten.
Console.WriteLine("Paragraph has no parent node: " + (para.ParentNode == null));

// Aber der Absatzknoten kennt sein Dokument.
Console.WriteLine("Both nodes' documents are the same: " + (para.Document == doc));

// Die Tatsache, dass ein Knoten immer zu einem Dokument gehört, ermöglicht uns den Zugriff und die Änderung
// Eigenschaften, die auf die dokumentweiten Daten verweisen, wie etwa Stile oder Listen.
para.ParagraphFormat.StyleName = "Heading 1";

// Fügen Sie nun den Absatz zum Haupttext des ersten Abschnitts hinzu.
doc.FirstSection.Body.AppendChild(para);

// Der Absatzknoten ist jetzt ein untergeordnetes Element des Body-Knotens.
Console.WriteLine("Paragraph has a parent node: " + (para.ParentNode != null));
```

### Häufig gestellte Fragen

#### F: Was ist ein proprietäres Dokument in Node.js?

A: Ein Besitzerdokument in Node.js ist das XML-Dokument, zu dem ein bestimmter Knoten gehört. Es stellt die Instanz des XML-Dokuments dar, das den Knoten enthält.

#### F: Wie erhalte ich das Eigentümerdokument eines Knotens?

 A: Um das Besitzerdokument eines Knotens in Node.js zu erhalten, können Sie das`ownerDocument` Eigenschaft des Knotens. Diese Eigenschaft gibt das XML-Dokument zurück, dem der Knoten gehört.

#### F: Wofür wird das proprietäre Dokument verwendet?

A: Das Besitzerdokument wird verwendet, um den globalen Kontext eines Knotens in einem XML-Dokument darzustellen. Es bietet Zugriff auf andere Knoten im Dokument und ermöglicht die Ausführung von Vorgängen an ihnen.

#### F: Können wir das Besitzerdokument eines Knotens ändern?

A: In den meisten Fällen wird der Dokumentbesitzer eines Knotens bei der Erstellung des Knotens festgelegt und kann nicht direkt geändert werden. Das Besitzerdokument ist eine schreibgeschützte Eigenschaft.

#### F: Wie greife ich auf die Knoten eines Eigentümerdokuments zu?

A: Um auf Knoten in einem proprietären Dokument zuzugreifen, können Sie die Methoden und Eigenschaften verwenden, die von der XML-API bereitgestellt werden, die in Ihrer Node.js-Umgebung verwendet wird. Sie können beispielsweise Methoden wie`getElementsByTagName` oder`querySelector` um bestimmte Knoten im Dokument auszuwählen.