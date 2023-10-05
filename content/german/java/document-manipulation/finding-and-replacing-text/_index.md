---
title: Suchen und Ersetzen von Text in Aspose.Words für Java
linktitle: Text suchen und ersetzen
second_title: Aspose.Words Java-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für Java Text in Word-Dokumenten suchen und ersetzen. Schritt-für-Schritt-Anleitung mit Codebeispielen. Verbessern Sie Ihre Fähigkeiten im Umgang mit Java-Dokumenten.
type: docs
weight: 15
url: /de/java/document-manipulation/finding-and-replacing-text/
---

## Einführung in das Suchen und Ersetzen von Text in Aspose.Words für Java

Aspose.Words für Java ist eine leistungsstarke Java-API, mit der Sie programmgesteuert mit Word-Dokumenten arbeiten können. Eine der häufigsten Aufgaben beim Umgang mit Word-Dokumenten ist das Suchen und Ersetzen von Text. Ganz gleich, ob Sie Platzhalter in Vorlagen aktualisieren oder komplexere Textmanipulationen durchführen müssen, Aspose.Words für Java kann Ihnen dabei helfen, Ihre Ziele effizient zu erreichen.

## Voraussetzungen

Bevor wir uns mit den Details zum Suchen und Ersetzen von Text befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Java-Entwicklungsumgebung
- Aspose.Words für Java-Bibliothek
- Ein Beispiel-Word-Dokument zum Arbeiten

 Sie können die Aspose.Words für Java-Bibliothek von herunterladen[Hier](https://releases.aspose.com/words/java/).

## Einfachen Text suchen und ersetzen

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

// Erstellen Sie einen DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);

// Suchen und ersetzen Sie Text
builder.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// Speichern Sie das geänderte Dokument
doc.save("modified-document.docx");
```

 In diesem Beispiel laden wir ein Word-Dokument und erstellen ein`DocumentBuilder` , und verwenden Sie die`replace` Methode zum Suchen und Ersetzen von „altem Text“ durch „neuen Text“ im Dokument.

## Verwendung regulärer Ausdrücke

Reguläre Ausdrücke bieten leistungsstarke Mustervergleichsfunktionen für die Textsuche und -ersetzung. Aspose.Words für Java unterstützt reguläre Ausdrücke für erweiterte Such- und Ersetzungsvorgänge.

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

// Erstellen Sie einen DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);

// Verwenden Sie reguläre Ausdrücke zum Suchen und Ersetzen von Text
Pattern regex = Pattern.compile("your-pattern");
builder.getRange().replace(regex, "replacement-text", new FindReplaceOptions());

// Speichern Sie das geänderte Dokument
doc.save("modified-document.docx");
```

In diesem Beispiel verwenden wir ein reguläres Ausdrucksmuster, um Text im Dokument zu suchen und zu ersetzen.

## Text in Feldern ignorieren

Sie können Aspose.Words so konfigurieren, dass Text in Feldern beim Durchführen von Such- und Ersetzungsvorgängen ignoriert wird.

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

// Erstellen Sie eine FindReplaceOptions-Instanz und setzen Sie IgnoreFields auf true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreFields(true);

// Verwenden Sie beim Ersetzen von Text Optionen
doc.getRange().replace("text-to-replace", "new-text", options);

// Speichern Sie das geänderte Dokument
doc.save("modified-document.docx");
```

Dies ist nützlich, wenn Sie Text in Feldern, z. B. Briefvorlagenfeldern, vom Ersetzen ausschließen möchten.

## Ignorieren von Text in Löschrevisionen

Sie können Aspose.Words so konfigurieren, dass Text in Löschrevisionen bei Such- und Ersetzungsvorgängen ignoriert wird.

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

// Erstellen Sie eine FindReplaceOptions-Instanz und setzen Sie IgnoreDeleted auf true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreDeleted(true);

// Verwenden Sie beim Ersetzen von Text Optionen
doc.getRange().replace("text-to-replace", "new-text", options);

// Speichern Sie das geänderte Dokument
doc.save("modified-document.docx");
```

Dadurch können Sie Text, der in den nachverfolgten Änderungen zum Löschen markiert wurde, vom Ersetzen ausschließen.

## Text innerhalb von Einfügungsrevisionen wird ignoriert

Sie können Aspose.Words so konfigurieren, dass Text in Einfügerevisionen bei Such- und Ersetzungsvorgängen ignoriert wird.

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

// Erstellen Sie eine FindReplaceOptions-Instanz und setzen Sie IgnoreInserted auf true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreInserted(true);

// Verwenden Sie beim Ersetzen von Text Optionen
doc.getRange().replace("text-to-replace", "new-text", options);

// Speichern Sie das geänderte Dokument
doc.save("modified-document.docx");
```

Dadurch können Sie Text, der als in nachverfolgte Änderungen eingefügt markiert wurde, vom Ersetzen ausschließen.

## Text durch HTML ersetzen

Sie können Aspose.Words für Java verwenden, um Text durch HTML-Inhalte zu ersetzen.

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

// Erstellen Sie eine FindReplaceOptions-Instanz mit einem benutzerdefinierten Ersetzungsrückruf
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceWithHtmlEvaluator(options));

// Verwenden Sie beim Ersetzen von Text Optionen
doc.getRange().replace("text-to-replace", "new-html-content", options);

// Speichern Sie das geänderte Dokument
doc.save("modified-document.docx");
```

 In diesem Beispiel verwenden wir eine benutzerdefinierte`ReplaceWithHtmlEvaluator` um Text durch HTML-Inhalt zu ersetzen.

## Text in Kopf- und Fußzeilen ersetzen

Sie können Text in Kopf- und Fußzeilen Ihres Word-Dokuments suchen und ersetzen.

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

// Rufen Sie die Sammlung von Kopf- und Fußzeilen ab
HeaderFooterCollection headersFooters = doc.getFirstSection().getHeadersFooters();

// Wählen Sie den Kopf- oder Fußzeilentyp aus, in dem Sie den Text ersetzen möchten (z. B. HeaderFooterType.FOOTER_PRIMARY).
HeaderFooter footer = headersFooters.getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);

// Erstellen Sie eine FindReplaceOptions-Instanz und wenden Sie sie auf den Bereich der Fußzeile an
FindReplaceOptions options = new FindReplaceOptions();
footer.getRange().replace("text-to-replace", "new-text", options);

// Speichern Sie das geänderte Dokument
doc.save("modified-document.docx");
```

Dadurch können Sie Textersetzungen gezielt in Kopf- und Fußzeilen durchführen.

## Änderungen für Kopf- und Fußzeilenreihenfolgen werden angezeigt

Sie können Aspose.Words verwenden, um Änderungen für Kopf- und Fußzeilenreihenfolgen in Ihrem Dokument anzuzeigen.

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

// Holen Sie sich den ersten Abschnitt
Section firstPageSection = doc.getFirstSection();

// Erstellen Sie eine FindReplaceOptions-Instanz und wenden Sie sie auf den Bereich des Dokuments an
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceLog());

//Ersetzen Sie Text, der sich auf die Reihenfolge von Kopf- und Fußzeilen auswirkt
doc.getRange().replace(Pattern.compile("(header|footer)"), "", options);

// Speichern Sie das geänderte Dokument
doc.save("modified-document.docx");
```

Dadurch können Sie Änderungen im Zusammenhang mit der Kopf- und Fußzeilenreihenfolge in Ihrem Dokument visualisieren.

## Text durch Felder ersetzen

Mit Aspose.Words für Java können Sie Text durch Felder ersetzen.

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

// Erstellen Sie eine FindReplaceOptions-Instanz und legen Sie einen benutzerdefinierten Ersetzungsrückruf für Felder fest
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceTextWithFieldHandler(FieldType.FIELD_MERGE_FIELD));

// Verwenden Sie beim Ersetzen von Text Optionen
doc.getRange().replace(Pattern.compile("PlaceHolder(\\d+)"), "", options);

// Speichern Sie das geänderte Dokument
doc.save("modified-document.docx");
```

 In diesem Beispiel ersetzen wir Text durch Felder und geben den Feldtyp an (z. B.`FieldType.FIELD_MERGE_FIELD`).

## Ersetzen durch einen Evaluator

Sie können einen benutzerdefinierten Evaluator verwenden, um den Ersetzungstext dynamisch zu ermitteln.

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

// Erstellen Sie eine FindReplaceOptions-Instanz und legen Sie einen benutzerdefinierten Ersetzungsrückruf fest
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new MyReplaceEvaluator());

// Verwenden Sie beim Ersetzen von Text Optionen
doc.getRange().replace(Pattern.compile("[s|m]ad"), "", options);

// Speichern Sie das geänderte Dokument
doc.save("modified-document.docx");
```

In diesem Beispiel verwenden wir einen benutzerdefinierten Evaluator (`MyReplaceEvaluator`), um Text zu ersetzen.

## Ersetzen durch Regex

Mit Aspose.Words für Java können Sie Text durch reguläre Ausdrücke ersetzen.

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

// Verwenden Sie reguläre Ausdrücke zum Suchen und Ersetzen von Text
doc.getRange().replace(Pattern.compile("[s|m]ad"), "bad", new FindReplaceOptions());

// Speichern Sie das geänderte Dokument
doc.save("modified-document.docx");
```

In diesem Beispiel verwenden wir ein reguläres Ausdrucksmuster, um Text im Dokument zu suchen und zu ersetzen.

## Erkennen und Ersetzen innerhalb von Ersetzungsmustern

Mit Aspose.Words für Java können Sie Ersetzungen innerhalb von Ersetzungsmustern erkennen und vornehmen.

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

//Erstellen Sie eine FindReplaceOptions-Instanz, wobei UseSubstitutions auf „true“ gesetzt ist
FindReplaceOptions options = new FindReplaceOptions();
options.setUseSubstitutions(true);

// Verwenden Sie Optionen, wenn Sie Text durch ein Muster ersetzen
doc.getRange().replace(Pattern.compile("([A-z]+) give money to ([A-z]+)"), "$2 take money from $1", options);

// Speichern Sie das geänderte Dokument
doc.save("modified-document.docx");
```

Dadurch können Sie innerhalb der Ersetzungsmuster Ersetzungen für komplexere Ersetzungen durchführen.

## Ersetzen durch einen String

Mit Aspose.Words für Java können Sie Text durch eine einfache Zeichenfolge ersetzen.

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

// Ersetzen Sie Text durch eine Zeichenfolge
doc.getRange().replace("text-to-replace", "new-string", new FindReplaceOptions());

// Speichern Sie das geänderte Dokument
doc.save("modified-document.docx");
```

In diesem Beispiel ersetzen wir „text-to-replace“ durch „new-string“ innerhalb des Dokuments.

## Verwendung der Legacy-Reihenfolge

Sie können beim Durchführen von Such- und Ersetzungsvorgängen die Legacy-Reihenfolge verwenden.

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

// Erstellen Sie eine FindReplaceOptions-Instanz und setzen Sie UseLegacyOrder auf true
FindReplaceOptions options = new FindReplaceOptions();
options.setUseLegacyOrder(true);

// Verwenden Sie beim Ersetzen von Text Optionen
doc.getRange().replace(Pattern.compile("\\[(.*?)\\]"), "", options);

// Speichern Sie das geänderte Dokument
doc.save("modified-document.docx");
```

Dadurch können Sie die Legacy-Reihenfolge für Such- und Ersetzungsvorgänge verwenden.

## Text in einer Tabelle ersetzen

Sie können Text in Tabellen in Ihrem Word-Dokument suchen und ersetzen.

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

// Holen Sie sich eine bestimmte Tabelle (z. B. die erste Tabelle)
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);

// Verwenden Sie FindReplaceOptions zum Ersetzen von Text in der Tabelle
table.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// Speichern Sie das geänderte Dokument
doc.save("modified-document.docx");
```

Dadurch können Sie Textersetzungen gezielt innerhalb von Tabellen durchführen.

## Abschluss

Aspose.Words für Java bietet umfassende Funktionen zum Suchen und Ersetzen von Text in Word-Dokumenten. Ganz gleich, ob Sie einfache Textersetzungen oder komplexere Vorgänge mit regulären Ausdrücken, Feldmanipulationen oder benutzerdefinierten Evaluatoren durchführen müssen, Aspose.Words für Java ist für Sie da. Schauen Sie sich unbedingt die umfangreiche Dokumentation und die Beispiele von Aspose an, um das volle Potenzial dieser leistungsstarken Java-Bibliothek auszuschöpfen.

## FAQs

### Wie lade ich Aspose.Words für Java herunter?

 Sie können Aspose.Words für Java von der Website herunterladen, indem Sie hier klicken[dieser Link](https://releases.aspose.com/words/java/).

### Kann ich reguläre Ausdrücke zum Ersetzen von Text verwenden?

Ja, Sie können reguläre Ausdrücke zum Ersetzen von Text in Aspose.Words für Java verwenden. Dadurch können Sie erweiterte und flexiblere Such- und Ersetzungsvorgänge durchführen.

### Wie kann ich Text in Feldern beim Ersetzen ignorieren?

 Um Text in Feldern beim Ersetzen zu ignorieren, können Sie festlegen`IgnoreFields` Eigentum der`FindReplaceOptions` Zu`true`Dadurch wird sichergestellt, dass Text in Feldern, z. B. Briefvorlagenfeldern, von der Ersetzung ausgeschlossen wird.

### Kann ich Text in Kopf- und Fußzeilen ersetzen?

 Ja, Sie können Text in Kopf- und Fußzeilen Ihres Word-Dokuments ersetzen. Greifen Sie einfach auf die entsprechende Kopf- oder Fußzeile zu und verwenden Sie die`replace` Methode mit der gewünschten`FindReplaceOptions`.

### Wozu dient die UseLegacyOrder-Option?

 Der`UseLegacyOrder` Option in`FindReplaceOptions` ermöglicht Ihnen die Verwendung der Legacy-Reihenfolge beim Durchführen von Such- und Ersetzungsvorgängen. Dies kann in bestimmten Szenarien nützlich sein, in denen ein Legacy-Auftragsverhalten gewünscht ist.