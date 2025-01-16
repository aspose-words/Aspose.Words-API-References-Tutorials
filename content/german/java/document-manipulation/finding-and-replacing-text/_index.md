---
title: Suchen und Ersetzen von Text in Aspose.Words für Java
linktitle: Suchen und Ersetzen von Text
second_title: Aspose.Words Java-API zur Dokumentverarbeitung
description: Erfahren Sie, wie Sie mit Aspose.Words für Java Text in Word-Dokumenten suchen und ersetzen. Schritt-für-Schritt-Anleitung mit Codebeispielen. Verbessern Sie Ihre Fähigkeiten zur Bearbeitung von Java-Dokumenten.
type: docs
weight: 15
url: /de/java/document-manipulation/finding-and-replacing-text/
---

## Einführung in das Suchen und Ersetzen von Text in Aspose.Words für Java

Aspose.Words für Java ist eine leistungsstarke Java-API, mit der Sie programmgesteuert mit Word-Dokumenten arbeiten können. Eine der häufigsten Aufgaben beim Umgang mit Word-Dokumenten ist das Suchen und Ersetzen von Text. Ob Sie Platzhalter in Vorlagen aktualisieren oder komplexere Textmanipulationen durchführen müssen, Aspose.Words für Java kann Ihnen helfen, Ihre Ziele effizient zu erreichen.

## Voraussetzungen

Bevor wir uns mit den Details zum Suchen und Ersetzen von Text befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Java-Entwicklungsumgebung
- Aspose.Words für Java-Bibliothek
- Ein Beispiel-Word-Dokument zum Arbeiten

 Sie können die Aspose.Words für Java-Bibliothek herunterladen von[Hier](https://releases.aspose.com/words/java/).

## Suchen und Ersetzen von einfachem Text

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

// Erstellen eines DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);

// Suchen und Ersetzen von Text
builder.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// Speichern des geänderten Dokuments
doc.save("modified-document.docx");
```

 In diesem Beispiel laden wir ein Word-Dokument, erstellen eine`DocumentBuilder` und verwenden Sie die`replace` Methode zum Suchen und Ersetzen von „altem Text“ durch „neuen Text“ im Dokument.

## Verwenden regulärer Ausdrücke

Reguläre Ausdrücke bieten leistungsstarke Mustervergleichsfunktionen für die Textsuche und -ersetzung. Aspose.Words für Java unterstützt reguläre Ausdrücke für erweiterte Such- und Ersetzungsvorgänge.

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

// Erstellen eines DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);

// Verwenden Sie reguläre Ausdrücke zum Suchen und Ersetzen von Text
Pattern regex = Pattern.compile("your-pattern");
builder.getRange().replace(regex, "replacement-text", new FindReplaceOptions());

// Speichern des geänderten Dokuments
doc.save("modified-document.docx");
```

In diesem Beispiel verwenden wir ein reguläres Ausdrucksmuster, um Text im Dokument zu suchen und zu ersetzen.

## Text in Feldern ignorieren

Sie können Aspose.Words so konfigurieren, dass Text in Feldern beim Ausführen von Such- und Ersetzungsvorgängen ignoriert wird.

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

// Erstellen Sie eine FindReplaceOptions-Instanz und setzen Sie IgnoreFields auf true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreFields(true);

// Verwenden Sie Optionen beim Ersetzen von Text
doc.getRange().replace("text-to-replace", "new-text", options);

// Speichern des geänderten Dokuments
doc.save("modified-document.docx");
```

Dies ist nützlich, wenn Sie Text in Feldern, wie z. B. Seriendruckfeldern, vom Ersetzen ausschließen möchten.

## Text in gelöschten Revisionen ignorieren

Sie können Aspose.Words so konfigurieren, dass Text in gelöschten Revisionen bei Such- und Ersetzungsvorgängen ignoriert wird.

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

// Erstellen Sie eine FindReplaceOptions-Instanz und setzen Sie IgnoreDeleted auf true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreDeleted(true);

// Verwenden Sie Optionen beim Ersetzen von Text
doc.getRange().replace("text-to-replace", "new-text", options);

// Speichern des geänderten Dokuments
doc.save("modified-document.docx");
```

Dadurch können Sie Text, der in der Änderungsverfolgung zum Löschen markiert wurde, vom Ersetzen ausschließen.

## Ignorieren von Text in Einfügerevisionen

Sie können Aspose.Words so konfigurieren, dass Text in Einfügerevisionen bei Such- und Ersetzungsvorgängen ignoriert wird.

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

// Erstellen Sie eine FindReplaceOptions-Instanz und setzen Sie IgnoreInserted auf true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreInserted(true);

// Verwenden Sie Optionen beim Ersetzen von Text
doc.getRange().replace("text-to-replace", "new-text", options);

// Speichern des geänderten Dokuments
doc.save("modified-document.docx");
```

Auf diese Weise können Sie Text, der in den nachverfolgten Änderungen als eingefügt markiert wurde, vom Ersetzen ausschließen.

## Ersetzen von Text durch HTML

Sie können Aspose.Words für Java verwenden, um Text durch HTML-Inhalte zu ersetzen.

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

// Erstellen Sie eine FindReplaceOptions-Instanz mit einem benutzerdefinierten Ersetzungs-Callback
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceWithHtmlEvaluator(options));

// Verwenden Sie Optionen beim Ersetzen von Text
doc.getRange().replace("text-to-replace", "new-html-content", options);

// Speichern des geänderten Dokuments
doc.save("modified-document.docx");
```

 In diesem Beispiel verwenden wir eine benutzerdefinierte`ReplaceWithHtmlEvaluator` um Text durch HTML-Inhalt zu ersetzen.

## Ersetzen von Text in Kopf- und Fußzeilen

Sie können Text in Kopf- und Fußzeilen Ihres Word-Dokuments suchen und ersetzen.

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

// Holen Sie sich die Sammlung von Kopf- und Fußzeilen
HeaderFooterCollection headersFooters = doc.getFirstSection().getHeadersFooters();

// Wählen Sie den Kopf- oder Fußzeilentyp aus, in dem Sie Text ersetzen möchten (z. B. HeaderFooterType.FOOTER_PRIMARY).
HeaderFooter footer = headersFooters.getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);

// Erstellen Sie eine FindReplaceOptions-Instanz und wenden Sie sie auf den Bereich der Fußzeile an.
FindReplaceOptions options = new FindReplaceOptions();
footer.getRange().replace("text-to-replace", "new-text", options);

// Speichern des geänderten Dokuments
doc.save("modified-document.docx");
```

Damit können Sie Textersetzungen gezielt in Kopf- und Fußzeilen vornehmen.

## Änderungen für Kopf- und Fußzeilenaufträge anzeigen

Sie können Aspose.Words verwenden, um Änderungen an der Reihenfolge von Kopf- und Fußzeilen in Ihrem Dokument anzuzeigen.

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

// Holen Sie sich den ersten Abschnitt
Section firstPageSection = doc.getFirstSection();

//Erstellen Sie eine FindReplaceOptions-Instanz und wenden Sie sie auf den Bereich des Dokuments an
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceLog());

// Ersetzen von Text, der die Reihenfolge von Kopf- und Fußzeilen beeinflusst
doc.getRange().replace(Pattern.compile("(header|footer)"), "", options);

// Speichern des geänderten Dokuments
doc.save("modified-document.docx");
```

Auf diese Weise können Sie Änderungen in Bezug auf die Reihenfolge von Kopf- und Fußzeilen in Ihrem Dokument visualisieren.

## Ersetzen von Text durch Felder

Sie können Text mit Aspose.Words für Java durch Felder ersetzen.

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

// Erstellen Sie eine FindReplaceOptions-Instanz und legen Sie einen benutzerdefinierten Ersetzungs-Callback für Felder fest
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceTextWithFieldHandler(FieldType.FIELD_MERGE_FIELD));

// Verwenden Sie Optionen beim Ersetzen von Text
doc.getRange().replace(Pattern.compile("PlaceHolder(\\d+)"), "", options);

// Speichern des geänderten Dokuments
doc.save("modified-document.docx");
```

 In diesem Beispiel ersetzen wir Text durch Felder und geben den Feldtyp an (z. B.`FieldType.FIELD_MERGE_FIELD`).

## Ersetzen durch einen Evaluator

Sie können einen benutzerdefinierten Evaluator verwenden, um den Ersetzungstext dynamisch zu bestimmen.

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

// Erstellen Sie eine FindReplaceOptions-Instanz und legen Sie einen benutzerdefinierten Ersetzungs-Callback fest
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new MyReplaceEvaluator());

// Verwenden Sie Optionen beim Ersetzen von Text
doc.getRange().replace(Pattern.compile("[s|m]ad"), "", options);

// Speichern des geänderten Dokuments
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

// Speichern des geänderten Dokuments
doc.save("modified-document.docx");
```

In diesem Beispiel verwenden wir ein reguläres Ausdrucksmuster, um Text im Dokument zu suchen und zu ersetzen.

## Erkennen und Ersetzen von Ersetzungsmustern

Mit Aspose.Words für Java können Sie Ersetzungen innerhalb von Ersetzungsmustern erkennen und vornehmen.

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

// Erstellen Sie eine FindReplaceOptions-Instanz mit UseSubstitutions auf true
FindReplaceOptions options = new FindReplaceOptions();
options.setUseSubstitutions(true);

// Verwenden Sie Optionen, wenn Sie Text durch ein Muster ersetzen
doc.getRange().replace(Pattern.compile("([A-z]+) give money to ([A-z]+)"), "$2 take money from $1", options);

// Speichern des geänderten Dokuments
doc.save("modified-document.docx");
```

Auf diese Weise können Sie innerhalb der Ersetzungsmuster Ersetzungen für erweiterte Ersetzungen durchführen.

## Ersetzen durch eine Zeichenfolge

Sie können Text mit Aspose.Words für Java durch eine einfache Zeichenfolge ersetzen.

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

// Ersetzen Sie Text durch eine Zeichenfolge
doc.getRange().replace("text-to-replace", "new-string", new FindReplaceOptions());

// Speichern des geänderten Dokuments
doc.save("modified-document.docx");
```

In diesem Beispiel ersetzen wir im Dokument „zu ersetzender Text“ durch „neue Zeichenfolge“.

## Legacy-Reihenfolge verwenden

Sie können beim Ausführen von Such- und Ersetzungsvorgängen die alte Reihenfolge verwenden.

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

// Erstellen Sie eine FindReplaceOptions-Instanz und setzen Sie UseLegacyOrder auf true
FindReplaceOptions options = new FindReplaceOptions();
options.setUseLegacyOrder(true);

// Verwenden Sie Optionen beim Ersetzen von Text
doc.getRange().replace(Pattern.compile("\\[(.*?)\\]"), "", options);

// Speichern des geänderten Dokuments
doc.save("modified-document.docx");
```

Auf diese Weise können Sie die alte Reihenfolge für Such- und Ersetzungsvorgänge verwenden.

## Ersetzen von Text in einer Tabelle

Sie können Text in Tabellen in Ihrem Word-Dokument suchen und ersetzen.

```java
// Laden Sie das Dokument
Document doc = new Document("your-document.docx");

// Holen Sie sich eine bestimmte Tabelle (z. B. die erste Tabelle)
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);

//Verwenden Sie FindReplaceOptions zum Ersetzen von Text in der Tabelle
table.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// Speichern des geänderten Dokuments
doc.save("modified-document.docx");
```

Damit ist es möglich, Textersetzungen gezielt innerhalb von Tabellen vorzunehmen.

## Abschluss

Aspose.Words für Java bietet umfassende Funktionen zum Suchen und Ersetzen von Text in Word-Dokumenten. Ob Sie einfache Textersetzungen oder erweiterte Operationen mit regulären Ausdrücken, Feldmanipulationen oder benutzerdefinierten Evaluatoren durchführen müssen, Aspose.Words für Java bietet alles. Sehen Sie sich unbedingt die umfangreiche Dokumentation und die Beispiele von Aspose an, um das volle Potenzial dieser leistungsstarken Java-Bibliothek auszuschöpfen.

## Häufig gestellte Fragen

### Wie lade ich Aspose.Words für Java herunter?

 Sie können Aspose.Words für Java von der Website herunterladen, indem Sie[dieser Link](https://releases.aspose.com/words/java/).

### Kann ich reguläre Ausdrücke zum Textersetzen verwenden?

Ja, Sie können reguläre Ausdrücke zum Ersetzen von Text in Aspose.Words für Java verwenden. Dadurch können Sie erweiterte und flexiblere Such- und Ersetzungsvorgänge durchführen.

### Wie kann ich Text in Feldern beim Ersetzen ignorieren?

Um Text in Feldern beim Ersetzen zu ignorieren, können Sie die`IgnoreFields` Eigentum der`FindReplaceOptions` Zu`true`. Dadurch wird sichergestellt, dass Text in Feldern, wie z. B. Seriendruckfeldern, vom Ersetzen ausgeschlossen wird.

### Kann ich Text in Kopf- und Fußzeilen ersetzen?

 Ja, Sie können Text in Kopf- und Fußzeilen Ihres Word-Dokuments ersetzen. Rufen Sie einfach die entsprechende Kopf- oder Fußzeile auf und verwenden Sie die`replace` Methode mit der gewünschten`FindReplaceOptions`.

### Wofür ist die Option UseLegacyOrder?

 Der`UseLegacyOrder` Option in`FindReplaceOptions` ermöglicht Ihnen, bei Such- und Ersetzungsvorgängen die alte Reihenfolge zu verwenden. Dies kann in bestimmten Szenarien nützlich sein, in denen das alte Reihenfolgeverhalten erwünscht ist.