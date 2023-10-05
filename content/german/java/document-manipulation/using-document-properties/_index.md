---
title: Verwenden von Dokumenteigenschaften in Aspose.Words für Java
linktitle: Dokumenteigenschaften verwenden
second_title: Aspose.Words Java-Dokumentverarbeitungs-API
description: Optimieren Sie die Dokumentenverwaltung mit Aspose.Words für Java. Erfahren Sie in diesem umfassenden Tutorial, wie Sie mit Dokumenteigenschaften arbeiten, benutzerdefinierte Metadaten hinzufügen und vieles mehr.
type: docs
weight: 32
url: /de/java/document-manipulation/using-document-properties/
---

## Einführung in Dokumenteigenschaften

Dokumenteigenschaften sind ein wesentlicher Bestandteil jedes Dokuments. Sie liefern zusätzliche Informationen über das Dokument selbst, wie Titel, Autor, Betreff, Schlüsselwörter und mehr. In Aspose.Words für Java können Sie sowohl integrierte als auch benutzerdefinierte Dokumenteigenschaften bearbeiten.

## Aufzählen von Dokumenteigenschaften

### Integrierte Eigenschaften

Um integrierte Dokumenteigenschaften abzurufen und damit zu arbeiten, können Sie den folgenden Codeausschnitt verwenden:

```java
@Test
public void enumerateProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    System.out.println(MessageFormat.format("1. Document name: {0}", doc.getOriginalFileName()));
    System.out.println("2. Built-in Properties");
    for (DocumentProperty prop : doc.getBuiltInDocumentProperties())
        System.out.println(MessageFormat.format("{0} : {1}", prop.getName(), prop.getValue()));
}
```

Dieser Code zeigt den Namen des Dokuments und integrierte Eigenschaften an, einschließlich Eigenschaften wie „Titel“, „Autor“ und „Schlüsselwörter“.

### Benutzerdefinierte Eigenschaften

Um mit benutzerdefinierten Dokumenteigenschaften zu arbeiten, können Sie den folgenden Codeausschnitt verwenden:

```java
@Test
public void addCustomDocumentProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    CustomDocumentProperties customDocumentProperties = doc.getCustomDocumentProperties();

    if (customDocumentProperties.get("Authorized") != null) return;

    customDocumentProperties.add("Authorized", true);
    customDocumentProperties.add("Authorized By", "John Smith");
    customDocumentProperties.add("Authorized Date", new Date());
    customDocumentProperties.add("Authorized Revision", doc.getBuiltInDocumentProperties().getRevisionNumber());
    customDocumentProperties.add("Authorized Amount", 123.45);
}
```

Dieser Codeausschnitt zeigt, wie Sie benutzerdefinierte Dokumenteigenschaften hinzufügen, einschließlich eines booleschen Werts, einer Zeichenfolge, eines Datums, einer Revisionsnummer und eines numerischen Werts.

## Dokumenteigenschaften entfernen

Um bestimmte Dokumenteigenschaften zu entfernen, können Sie den folgenden Code verwenden:

```java
@Test
public void removeCustomDocumentProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    doc.getCustomDocumentProperties().remove("Authorized Date");
}
```

Dieser Code entfernt die benutzerdefinierte Eigenschaft „Autorisiertes Datum“ aus dem Dokument.

## Link zum Inhalt konfigurieren

In manchen Fällen möchten Sie möglicherweise Links in Ihrem Dokument erstellen. So können Sie es machen:

```java
@Test
public void configuringLinkToContent() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.startBookmark("MyBookmark");
    builder.writeln("Text inside a bookmark.");
    builder.endBookmark("MyBookmark");

    CustomDocumentProperties customProperties = doc.getCustomDocumentProperties();

    // Mit Inhalt verknüpfte Eigenschaft hinzufügen.
    DocumentProperty customProperty = customProperties.addLinkToContent("Bookmark", "MyBookmark");
    customProperty = customProperties.get("Bookmark");
    boolean isLinkedToContent = customProperty.isLinkToContent();
    String linkSource = customProperty.getLinkSource();
    String customPropertyValue = customProperty.getValue().toString();
}
```

Dieser Codeausschnitt zeigt, wie Sie in Ihrem Dokument ein Lesezeichen erstellen und eine benutzerdefinierte Dokumenteigenschaft hinzufügen, die mit diesem Lesezeichen verknüpft ist.

## Konvertieren zwischen Maßeinheiten

In Aspose.Words für Java können Sie Maßeinheiten einfach umrechnen. Hier ist ein Beispiel dafür:

```java
@Test
public void convertBetweenMeasurementUnits() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    PageSetup pageSetup = builder.getPageSetup();

    // Legen Sie die Ränder in Zoll fest.
    pageSetup.setTopMargin(ConvertUtil.inchToPoint(1.0));
    pageSetup.setBottomMargin(ConvertUtil.inchToPoint(1.0));
    pageSetup.setLeftMargin(ConvertUtil.inchToPoint(1.5));
    pageSetup.setRightMargin(ConvertUtil.inchToPoint(1.5));
    pageSetup.setHeaderDistance(ConvertUtil.inchToPoint(0.2));
    pageSetup.setFooterDistance(ConvertUtil.inchToPoint(0.2));
}
```

Dieser Codeausschnitt legt verschiedene Ränder und Abstände in Zoll fest, indem er sie in Punkte umwandelt.

## Verwendung von Steuerzeichen

Steuerzeichen können beim Umgang mit Text hilfreich sein. So ersetzen Sie ein Steuerzeichen in Ihrem Text:

```java
@Test
public void useControlCharacters()
{
    final String TEXT = "test\r";

    // Ersetzen Sie das Steuerzeichen „\r“ durch „\r\n“.
    String replace = TEXT.replace(ControlChar.CR, ControlChar.CR_LF);
}
```

In diesem Beispiel ersetzen wir den Wagenrücklauf (`\r`) mit einem Wagenrücklauf gefolgt von einem Zeilenvorschub (`\r\n`).

## Abschluss

Dokumenteigenschaften spielen eine wichtige Rolle bei der effektiven Verwaltung und Organisation Ihrer Dokumente in Aspose.Words für Java. Unabhängig davon, ob Sie mit integrierten Eigenschaften, benutzerdefinierten Eigenschaften oder der Verwendung von Steuerzeichen arbeiten, steht Ihnen eine Reihe von Tools zur Verfügung, mit denen Sie Ihre Funktionen zur Dokumentenverwaltung erweitern können.

## FAQs

### Wie greife ich auf integrierte Dokumenteigenschaften zu?

 Um auf integrierte Dokumenteigenschaften in Aspose.Words für Java zuzugreifen, können Sie die verwenden`getBuiltInDocumentProperties` Methode auf der`Document` Objekt. Diese Methode gibt eine Sammlung integrierter Eigenschaften zurück, die Sie durchlaufen können.

### Kann ich einem Dokument benutzerdefinierte Dokumenteigenschaften hinzufügen?

 Ja, Sie können einem Dokument mithilfe von benutzerdefinierte Dokumenteigenschaften hinzufügen`CustomDocumentProperties` Sammlung. Sie können benutzerdefinierte Eigenschaften mit verschiedenen Datentypen definieren, einschließlich Zeichenfolgen, booleschen Werten, Datumsangaben und numerischen Werten.

### Wie kann ich eine bestimmte benutzerdefinierte Dokumenteigenschaft entfernen?

 Um eine bestimmte benutzerdefinierte Dokumenteigenschaft zu entfernen, können Sie die verwenden`remove` Methode auf der`CustomDocumentProperties`-Sammlung und übergibt dabei den Namen der Eigenschaft, die Sie entfernen möchten, als Parameter.

### Was ist der Zweck der Verlinkung auf Inhalte innerhalb eines Dokuments?

Durch die Verknüpfung mit Inhalten innerhalb eines Dokuments können Sie dynamische Verweise auf bestimmte Teile des Dokuments erstellen. Dies kann nützlich sein, um interaktive Dokumente oder Querverweise zwischen Abschnitten zu erstellen.

### Wie kann ich in Aspose.Words für Java zwischen verschiedenen Maßeinheiten konvertieren?

 Sie können in Aspose.Words für Java zwischen verschiedenen Maßeinheiten konvertieren, indem Sie die verwenden`ConvertUtil` Klasse. Es bietet Methoden zum Umrechnen von Einheiten wie Zoll in Punkt, Punkt in Zentimeter und mehr.