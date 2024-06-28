---
title: Mit Lesezeichen versehene Inhalte im Word-Dokument ausblenden anzeigen
linktitle: Mit Lesezeichen versehene Inhalte im Word-Dokument ausblenden anzeigen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie in dieser umfassenden Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Words für .NET mit Lesezeichen versehene Inhalte in Word-Dokumenten dynamisch ein- oder ausblenden.
type: docs
weight: 10
url: /de/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

## Einführung

Hallo! Wollten Sie schon immer die Sichtbarkeit bestimmter Inhalte in einem Word-Dokument anhand bestimmter Bedingungen steuern? Mit Aspose.Words für .NET können Sie mit nur wenigen Codezeilen mit Lesezeichen versehene Inhalte dynamisch ein- oder ausblenden. In diesem Tutorial werde ich Sie Schritt für Schritt durch den Prozess führen und sicherstellen, dass Sie jeden Teil des Codes verstehen. Am Ende werden Sie ein Profi im Bearbeiten von Lesezeichen in Word-Dokumenten sein. Lass uns anfangen!

## Voraussetzungen

Bevor wir uns mit dem Tutorial befassen, stellen wir sicher, dass Sie alles haben, was Sie brauchen:

1. Grundkenntnisse in C#: Sie sollten mit der Syntax und den Konzepten von C# vertraut sein.
2.  Aspose.Words für .NET: Laden Sie es herunter[Hier](https://releases.aspose.com/words/net/) . Wenn Sie noch nicht zum Kauf bereit sind, können Sie mit einem beginnen[Kostenlose Testphase](https://releases.aspose.com/).
3. Visual Studio: Jede neuere Version funktioniert, es wird jedoch empfohlen, die neueste Version zu verwenden.
4. .NET Framework: Stellen Sie sicher, dass es auf Ihrem Computer installiert ist.

Bereit anzufangen? Großartig! Beginnen wir mit dem Importieren der erforderlichen Namespaces.

## Namespaces importieren

Um Aspose.Words für .NET verwenden zu können, müssen wir die erforderlichen Namespaces importieren. Dieser Schritt stellt sicher, dass wir Zugriff auf alle Klassen und Methoden haben, die wir verwenden werden.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Diese Namespaces sind für die Arbeit mit Word-Dokumenten und die Bearbeitung ihres Inhalts von entscheidender Bedeutung.

## Schritt 1: Einrichten des Dokuments

Lassen Sie uns zunächst ein neues Word-Dokument und einen Dokument-Builder erstellen. Der Document Builder hilft uns, Inhalte innerhalb des Dokuments einfach hinzuzufügen und zu bearbeiten.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

In diesem Schritt initialisieren wir ein neues Dokument und einen Document Builder. Dadurch wird unsere Umgebung für weitere Vorgänge vorbereitet.

## Schritt 2: Mit Lesezeichen versehene Inhalte hinzufügen

Als Nächstes fügen wir dem Dokument etwas Inhalt hinzu und erstellen ein Lesezeichen darum herum. Dieses Lesezeichen hilft uns, den Inhalt zu identifizieren und zu bearbeiten.

```csharp
builder.Write("This is some text before the bookmark.");
builder.StartBookmark("MyBookmark");
builder.Write("This is the bookmarked content.");
builder.EndBookmark("MyBookmark");
builder.Write("This is some text after the bookmark.");
```

 Hier fügen wir Text vor und nach dem mit Lesezeichen versehenen Inhalt hinzu. Der`StartBookmark` Und`EndBookmark` Methoden definieren die Grenzen des Lesezeichens.

## Schritt 3: Einfügen eines bedingten Feldes

Um die Sichtbarkeit des mit Lesezeichen versehenen Inhalts zu steuern, verwenden wir ein bedingtes Feld. In diesem Feld wird eine Bedingung geprüft und der Inhalt entsprechend angezeigt oder ausgeblendet.

```csharp
builder.MoveToDocumentEnd();
Field field = builder.InsertField("IF \"", null);
builder.MoveTo(field.Start.NextSibling);
builder.InsertField("MERGEFIELD MyBookmark", null);
builder.Write("\" = \"true\" \"Visible\" \"Hidden\"");
```

In diesem Schritt fügen wir ein IF-Feld ein, das den Wert des Lesezeichens überprüft. Wenn der Wert „wahr“ ist, wird „Sichtbar“ angezeigt; andernfalls wird „Ausgeblendet“ angezeigt.

## Schritt 4: Knoten neu anordnen

Als Nächstes müssen wir die Knoten neu anordnen, um sicherzustellen, dass die bedingte Logik korrekt auf den mit Lesezeichen versehenen Inhalt angewendet wird.

```csharp
Bookmark bm = doc.Range.Bookmarks["MyBookmark"];
Node currentNode = field.Start;
bool flag = true;

while (currentNode != null && flag)
{
    if (currentNode.NodeType == NodeType.Run && currentNode.ToString(SaveFormat.Text).Trim() == "\"")
        flag = false;

    Node nextNode = currentNode.NextSibling;
    bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
    currentNode = nextNode;
}

Node endNode = bm.BookmarkEnd;
flag = true;

while (currentNode != null && flag)
{
    if (currentNode.NodeType == NodeType.FieldEnd)
        flag = false;

    Node nextNode = currentNode.NextSibling;
    bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
    endNode = currentNode;
    currentNode = nextNode;
}
```

Hier verschieben wir Knoten, um sicherzustellen, dass die Bedingung den mit Lesezeichen versehenen Inhalt ordnungsgemäß umfasst.

## Schritt 5: Serienbrief ausführen

Abschließend führen wir einen Serienbrief durch, um den Wert des Lesezeichens festzulegen und zu bestimmen, ob der Inhalt angezeigt oder ausgeblendet werden soll.

```csharp
doc.MailMerge.Execute(new[] { "MyBookmark" }, new object[] { "true" });
```

Dieser Schritt setzt den Lesezeichenwert auf „true“, wodurch der Inhalt basierend auf unserer Bedingung sichtbar wird.

## Schritt 6: Speichern des Dokuments

Nach all den Manipulationen besteht der letzte Schritt darin, das geänderte Dokument zu speichern.

```csharp
doc.Save("ShowHideBookmarkedContent.docx");
```

Hier speichern wir das Dokument mit einem beschreibenden Dateinamen, um die Änderungen anzuzeigen.

## Abschluss

 Und das ist es! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Words für .NET mit Lesezeichen versehene Inhalte in einem Word-Dokument ein- oder ausblenden. In diesem Tutorial wurde das Erstellen eines Dokuments, das Hinzufügen von Lesezeichen, das Einfügen von Bedingungsfeldern, das Neuanordnen von Knoten und das Ausführen eines Seriendrucks behandelt. Aspose.Words bietet eine Fülle von Funktionen, also zögern Sie nicht, diese zu erkunden[API-Dokumentation](https://reference.aspose.com/words/net/) für erweiterte Funktionen.

## FAQs

### 1. Was ist Aspose.Words für .NET?

Aspose.Words für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, Word-Dokumente programmgesteuert zu erstellen, zu ändern und zu konvertieren. Es wird häufig für Aufgaben zur Dokumentenautomatisierung verwendet.

### 2. Kann ich Aspose.Words für .NET kostenlos nutzen?

 Sie können Aspose.Words für .NET mit a ausprobieren[Kostenlose Testphase](https://releases.aspose.com/). Für die langfristige Nutzung müssen Sie eine Lizenz erwerben.

### 3. Wie ändere ich andere Eigenschaften eines Lesezeichens?

 Mit Aspose.Words können Sie verschiedene Eigenschaften eines Lesezeichens bearbeiten, z. B. seinen Text und seine Position. Siehe die[API-Dokumentation](https://reference.aspose.com/words/net/) für detaillierte Anweisungen.

### 4. Wie erhalte ich Unterstützung für Aspose.Words für .NET?

Sie können Unterstützung erhalten, indem Sie die besuchen[Aspose-Supportforum](https://forum.aspose.com/c/words/8).

### 5. Kann ich mit Aspose.Words für .NET andere Arten von Inhalten bearbeiten?

Ja, Aspose.Words für .NET unterstützt verschiedene Arten der Inhaltsbearbeitung, einschließlich Text, Bilder, Tabellen und mehr.