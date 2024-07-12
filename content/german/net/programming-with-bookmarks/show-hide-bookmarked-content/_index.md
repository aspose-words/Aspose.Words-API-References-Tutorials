---
title: Mit Lesezeichen versehenen Inhalt im Word-Dokument ein- und ausblenden
linktitle: Mit Lesezeichen versehenen Inhalt im Word-Dokument ein- und ausblenden
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie in dieser umfassenden Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Words für .NET mit Lesezeichen versehene Inhalte in Word-Dokumenten dynamisch anzeigen oder ausblenden.
type: docs
weight: 10
url: /de/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

## Einführung

Hallo! Wollten Sie schon immer die Sichtbarkeit bestimmter Inhalte in einem Word-Dokument basierend auf bestimmten Bedingungen steuern? Mit Aspose.Words für .NET können Sie mit Lesezeichen versehene Inhalte mit nur wenigen Codezeilen dynamisch ein- oder ausblenden. In diesem Tutorial führe ich Sie Schritt für Schritt durch den Vorgang und stelle sicher, dass Sie jeden Teil des Codes verstehen. Am Ende sind Sie ein Profi im Bearbeiten von Lesezeichen in Word-Dokumenten. Lassen Sie uns anfangen!

## Voraussetzungen

Bevor wir mit dem Tutorial beginnen, stellen wir sicher, dass Sie alles haben, was Sie brauchen:

1. Grundkenntnisse in C#: Sie sollten mit der Syntax und den Konzepten von C# vertraut sein.
2.  Aspose.Words für .NET: Laden Sie es herunter[Hier](https://releases.aspose.com/words/net/) Wenn Sie noch nicht zum Kauf bereit sind, können Sie mit einem[Kostenlose Testphase](https://releases.aspose.com/).
3. Visual Studio: Jede aktuelle Version funktioniert, es wird jedoch empfohlen, die neueste Version zu verwenden.
4. .NET Framework: Stellen Sie sicher, dass es auf Ihrem Computer installiert ist.

Bereit, loszulegen? Großartig! Beginnen wir mit dem Importieren der erforderlichen Namespaces.

## Namespaces importieren

Um Aspose.Words für .NET zu verwenden, müssen wir die erforderlichen Namespaces importieren. Dieser Schritt stellt sicher, dass wir Zugriff auf alle Klassen und Methoden haben, die wir verwenden werden.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Diese Namespaces sind für die Arbeit mit Word-Dokumenten und die Bearbeitung ihres Inhalts von entscheidender Bedeutung.

## Schritt 1: Einrichten des Dokuments

Erstellen wir zunächst ein neues Word-Dokument und einen Dokumentgenerator. Mit dem Dokumentgenerator können wir problemlos Inhalte im Dokument hinzufügen und bearbeiten.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

In diesem Schritt initialisieren wir ein neues Dokument und einen Dokumentgenerator. Damit richten wir unsere Umgebung für weitere Vorgänge ein.

## Schritt 2: Mit Lesezeichen versehenen Inhalt hinzufügen

Als Nächstes fügen wir dem Dokument Inhalt hinzu und erstellen ein Lesezeichen darum. Mit diesem Lesezeichen können wir den Inhalt leichter identifizieren und bearbeiten.

```csharp
builder.Write("This is some text before the bookmark.");
builder.StartBookmark("MyBookmark");
builder.Write("This is the bookmarked content.");
builder.EndBookmark("MyBookmark");
builder.Write("This is some text after the bookmark.");
```

 Hier fügen wir vor und nach dem mit Lesezeichen versehenen Inhalt etwas Text hinzu.`StartBookmark`Und`EndBookmark` Methoden definieren die Grenzen des Lesezeichens.

## Schritt 3: Einfügen eines bedingten Felds

Um die Sichtbarkeit des mit Lesezeichen versehenen Inhalts zu steuern, verwenden wir ein bedingtes Feld. Dieses Feld überprüft eine Bedingung und zeigt den Inhalt entsprechend an oder verbirgt ihn.

```csharp
builder.MoveToDocumentEnd();
Field field = builder.InsertField("IF \"", null);
builder.MoveTo(field.Start.NextSibling);
builder.InsertField("MERGEFIELD MyBookmark", null);
builder.Write("\" = \"true\" \"Visible\" \"Hidden\"");
```

In diesem Schritt fügen wir ein WENN-Feld ein, das den Wert des Lesezeichens überprüft. Wenn der Wert „true“ ist, wird „Sichtbar“ angezeigt, andernfalls „Versteckt“.

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

Hier verschieben wir Knoten, um sicherzustellen, dass die Bedingung den mit Lesezeichen versehenen Inhalt richtig umfasst.

## Schritt 5: Serienbrief ausführen

Abschließend führen wir einen Serienbrief aus, um den Wert des Lesezeichens festzulegen und zu bestimmen, ob der Inhalt angezeigt oder ausgeblendet werden soll.

```csharp
doc.MailMerge.Execute(new[] { "MyBookmark" }, new object[] { "true" });
```

Dieser Schritt setzt den Lesezeichenwert auf „true“, wodurch der Inhalt basierend auf unserer Bedingung sichtbar wird.

## Schritt 6: Speichern des Dokuments

Nach allen Manipulationen besteht der letzte Schritt darin, das geänderte Dokument zu speichern.

```csharp
doc.Save("ShowHideBookmarkedContent.docx");
```

Dabei speichern wir das Dokument unter einem aussagekräftigen Dateinamen, um die Änderungen kenntlich zu machen.

## Abschluss

 Und das ist es! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Words für .NET mit Lesezeichen versehene Inhalte in einem Word-Dokument anzeigen oder ausblenden können. In diesem Tutorial wurde das Erstellen eines Dokuments, das Hinzufügen von Lesezeichen, das Einfügen bedingter Felder, das Neuanordnen von Knoten und das Ausführen eines Seriendrucks behandelt. Aspose.Words bietet eine Fülle von Funktionen. Zögern Sie also nicht, die[API-Dokumentation](https://reference.aspose.com/words/net/) für erweiterte Funktionen.

## FAQs

### 1. Was ist Aspose.Words für .NET?

Aspose.Words für .NET ist eine leistungsstarke Bibliothek, mit der Entwickler Word-Dokumente programmgesteuert erstellen, ändern und konvertieren können. Sie wird häufig für Aufgaben zur Dokumentautomatisierung verwendet.

### 2. Kann ich Aspose.Words für .NET kostenlos nutzen?

 Sie können Aspose.Words für .NET mit einem[Kostenlose Testphase](https://releases.aspose.com/)Für die langfristige Nutzung müssen Sie eine Lizenz erwerben.

### 3. Wie ändere ich andere Eigenschaften eines Lesezeichens?

 Mit Aspose.Words können Sie verschiedene Eigenschaften eines Lesezeichens bearbeiten, z. B. dessen Text und Position. Weitere Informationen finden Sie im[API-Dokumentation](https://reference.aspose.com/words/net/) für detaillierte Anweisungen.

### 4. Wie erhalte ich Unterstützung für Aspose.Words für .NET?

Sie erhalten Unterstützung unter[Aspose-Supportforum](https://forum.aspose.com/c/words/8).

### 5. Kann ich mit Aspose.Words für .NET andere Arten von Inhalten bearbeiten?

Ja, Aspose.Words für .NET unterstützt verschiedene Arten der Inhaltsmanipulation, einschließlich Text, Bilder, Tabellen und mehr.