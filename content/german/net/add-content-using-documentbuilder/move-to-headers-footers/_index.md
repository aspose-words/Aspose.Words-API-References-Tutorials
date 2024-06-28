---
title: In Word-Dokument zu Kopfzeilen und Fußzeilen verschieben
linktitle: In Word-Dokument zu Kopfzeilen und Fußzeilen verschieben
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie in unserer Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Words für .NET zu Kopf- und Fußzeilen in einem Word-Dokument wechseln. Verbessern Sie Ihre Fähigkeiten zur Dokumentenerstellung.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/move-to-headers-footers/
---
## Einführung

Wenn es um die programmgesteuerte Erstellung und Verwaltung von Word-Dokumenten geht, ist Aspose.Words für .NET ein leistungsstarkes Tool, mit dem Sie viel Zeit und Mühe sparen können. In diesem Artikel erfahren Sie, wie Sie mit Aspose.Words für .NET zu Kopf- und Fußzeilen in einem Word-Dokument wechseln. Diese Funktion ist wichtig, wenn Sie den Kopf- oder Fußzeilenabschnitten Ihres Dokuments bestimmte Inhalte hinzufügen müssen. Unabhängig davon, ob Sie einen Bericht, eine Rechnung oder ein anderes Dokument erstellen, das eine professionelle Note erfordert, ist es von entscheidender Bedeutung, zu verstehen, wie Kopf- und Fußzeilen manipuliert werden.

## Voraussetzungen

Bevor wir uns mit dem Code befassen, stellen wir sicher, dass Sie alles eingerichtet haben:

1. **Aspose.Words for .NET** : Stellen Sie sicher, dass Sie über die Aspose.Words für .NET-Bibliothek verfügen. Sie können es hier herunterladen[Aspose-Veröffentlichungsseite](https://releases.aspose.com/words/net/).
2. **Development Environment**Sie benötigen eine Entwicklungsumgebung wie Visual Studio.
3. **Basic Knowledge of C#**: Das Verständnis der Grundlagen der C#-Programmierung wird Ihnen dabei helfen, weiterzumachen.

## Namespaces importieren

Um zu beginnen, müssen Sie die erforderlichen Namespaces importieren. Dieser Schritt ist entscheidend für den Zugriff auf die von Aspose.Words für .NET bereitgestellten Klassen und Methoden.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
using Aspose.Words.Drawing;
using System;
```

Lassen Sie uns den Prozess in einfache Schritte unterteilen. Jeder Schritt wird klar erklärt, damit Sie besser verstehen, was der Code tut und warum.

## Schritt 1: Initialisieren Sie das Dokument

Der erste Schritt besteht darin, ein neues Dokument und ein DocumentBuilder-Objekt zu initialisieren. Mit der DocumentBuilder-Klasse können Sie das Dokument erstellen und bearbeiten.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 In diesem Schritt erstellen Sie eine neue Instanz von`Document` Klasse und die`DocumentBuilder` Klasse. Der`dataDir` Die Variable wird verwendet, um das Verzeichnis anzugeben, in dem Sie das Dokument speichern möchten.

## Schritt 2: Seiteneinrichtung konfigurieren

Als nächstes müssen wir festlegen, dass die Kopf- und Fußzeilen für die erste, gerade und ungerade Seite unterschiedlich sein sollen.

```csharp
//Geben Sie an, dass die Kopf- und Fußzeilen für die erste, gerade und ungerade Seite unterschiedlich sein sollen.
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;
```

Diese Einstellungen stellen sicher, dass Sie für verschiedene Seitentypen eindeutige Kopf- und Fußzeilen verwenden können.

## Schritt 3: Gehen Sie zur Kopf-/Fußzeile und fügen Sie Inhalt hinzu

Gehen wir nun zu den Kopf- und Fußzeilenabschnitten über und fügen einige Inhalte hinzu.

```csharp
// Erstellen Sie die Header.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");
```

 In diesem Schritt verwenden wir die`MoveToHeaderFooter` -Methode, um zum gewünschten Kopf- oder Fußzeilenabschnitt zu navigieren. Der`Write` Anschließend wird mit der Methode Text zu diesen Abschnitten hinzugefügt.

## Schritt 4: Fügen Sie Inhalte zum Dokumentkörper hinzu

Um die Kopf- und Fußzeilen zu veranschaulichen, fügen wir dem Hauptteil des Dokuments etwas Inhalt hinzu und erstellen ein paar Seiten.

```csharp
// Erstellen Sie zwei Seiten im Dokument.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
```

Hier fügen wir dem Dokument Text hinzu und fügen einen Seitenumbruch ein, um eine zweite Seite zu erstellen.

## Schritt 5: Speichern Sie das Dokument

Speichern Sie abschließend das Dokument im angegebenen Verzeichnis.

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

Diese Codezeile speichert das Dokument mit dem Namen „AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx“ im angegebenen Verzeichnis.

## Abschluss

 Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET problemlos Kopf- und Fußzeilen in einem Word-Dokument bearbeiten. In diesem Tutorial wurden die Grundlagen behandelt, Aspose.Words bietet jedoch eine breite Palette an Funktionalitäten für komplexere Dokumentenmanipulationen. Zögern Sie nicht, das zu erkunden[Dokumentation](https://reference.aspose.com/words/net/) für erweiterte Funktionen.

## FAQs

### Was ist Aspose.Words für .NET?
Aspose.Words für .NET ist eine Bibliothek, die es Entwicklern ermöglicht, Word-Dokumente programmgesteuert mit C# zu erstellen, zu ändern und zu konvertieren.

### Kann ich Bilder zu Kopf- und Fußzeilen hinzufügen?
 Ja, Sie können mit dem Bilder zu Kopf- und Fußzeilen hinzufügen`DocumentBuilder.InsertImage` Methode.

### Ist es möglich, für jeden Abschnitt unterschiedliche Kopf- und Fußzeilen zu haben?
 Absolut! Sie können für jeden Abschnitt eigene Kopf- und Fußzeilen erstellen, indem Sie unterschiedliche einrichten`HeaderFooterType` für jeden Abschnitt.

### Wie erstelle ich komplexere Layouts in Kopf- und Fußzeilen?
Sie können Tabellen, Bilder und verschiedene Formatierungsoptionen von Aspose.Words verwenden, um komplexe Layouts zu erstellen.

### Wo finde ich weitere Beispiele und Tutorials?
 Besuche die[Dokumentation](https://reference.aspose.com/words/net/) und das[Hilfeforum](https://forum.aspose.com/c/words/8) Weitere Beispiele und Community-Unterstützung finden Sie hier.
