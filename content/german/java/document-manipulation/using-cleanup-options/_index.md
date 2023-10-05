---
title: Verwenden von Bereinigungsoptionen in Aspose.Words für Java
linktitle: Bereinigungsoptionen verwenden
second_title: Aspose.Words Java-Dokumentverarbeitungs-API
description: Verbessern Sie die Klarheit von Dokumenten mit Aspose.Words für Java-Bereinigungsoptionen. Erfahren Sie, wie Sie leere Absätze, ungenutzte Bereiche und mehr entfernen.
type: docs
weight: 10
url: /de/java/document-manipulation/using-cleanup-options/
---

## Einführung in die Verwendung von Bereinigungsoptionen in Aspose.Words für Java

In diesem Tutorial erfahren Sie, wie Sie die Bereinigungsoptionen in Aspose.Words für Java verwenden, um Dokumente während des Seriendruckvorgangs zu bearbeiten und zu bereinigen. Mit den Bereinigungsoptionen können Sie verschiedene Aspekte der Dokumentbereinigung steuern, z. B. das Entfernen leerer Absätze, nicht verwendeter Bereiche und mehr.

## Voraussetzungen

 Bevor wir beginnen, stellen Sie sicher, dass Sie die Aspose.Words for Java-Bibliothek in Ihr Projekt integriert haben. Sie können es herunterladen unter[Hier](https://releases.aspose.com/words/java/).

## Schritt 1: Leere Absätze entfernen

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie Zusammenführungsfelder ein
FieldMergeField mergeFieldOption1 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_1");
mergeFieldOption1.setFieldName("Option_1");
builder.write(" ? ");
FieldMergeField mergeFieldOption2 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_2");
mergeFieldOption2.setFieldName("Option_2");

// Bereinigungsoptionen festlegen
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS);

// Aktivieren Sie Bereinigungsabsätze mit Satzzeichen
doc.getMailMerge().setCleanupParagraphsWithPunctuationMarks(true);

// Serienbrief ausführen
doc.getMailMerge().execute(new String[] { "Option_1", "Option_2" }, new Object[] { null, null });

// Speichern Sie das Dokument
doc.save("WorkingWithCleanupOptions.CleanupParagraphsWithPunctuationMarks.docx");
```

In diesem Beispiel erstellen wir ein neues Dokument, fügen Zusammenführungsfelder ein und legen die Bereinigungsoptionen fest, um leere Absätze zu entfernen. Darüber hinaus ermöglichen wir das Entfernen von Absätzen mit Satzzeichen. Nach der Ausführung des Seriendrucks wird das Dokument mit der angegebenen Bereinigung gespeichert.

## Schritt 2: Nicht zusammengeführte Regionen entfernen

```java
Document doc = new Document("Your Directory Path" + "Mail merge destination - Northwind suppliers.docx");
DataSet data = new DataSet();

// Legen Sie Bereinigungsoptionen fest, um nicht verwendete Regionen zu entfernen
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS);

// Serienbrief mit Regionen ausführen
doc.getMailMerge().executeWithRegions(data);

// Speichern Sie das Dokument
doc.save("WorkingWithCleanupOptions.RemoveUnmergedRegions.docx");
```

In diesem Beispiel öffnen wir ein vorhandenes Dokument mit Zusammenführungsbereichen, legen die Bereinigungsoptionen fest, um nicht verwendete Bereiche zu entfernen, und führen dann den Serienbrief mit leeren Daten aus. Durch diesen Vorgang werden die nicht verwendeten Bereiche automatisch aus dem Dokument entfernt.

## Schritt 3: Leere Felder entfernen

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Legen Sie Bereinigungsoptionen fest, um leere Felder zu entfernen
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_FIELDS);

// Serienbrief ausführen
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Speichern Sie das Dokument
doc.save("WorkingWithCleanupOptions.RemoveEmptyFields.docx");
```

In diesem Beispiel öffnen wir ein Dokument mit Serienbrieffeldern, legen die Bereinigungsoptionen fest, um leere Felder zu entfernen, und führen den Serienbrief mit Daten aus. Nach der Zusammenführung werden alle leeren Felder aus dem Dokument entfernt.

## Schritt 4: Nicht verwendete Felder entfernen

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Legen Sie Bereinigungsoptionen fest, um nicht verwendete Felder zu entfernen
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS);

// Serienbrief ausführen
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Speichern Sie das Dokument
doc.save("WorkingWithCleanupOptions.RemoveUnusedFields.docx");
```

In diesem Beispiel öffnen wir ein Dokument mit Seriendruckfeldern, legen die Bereinigungsoptionen fest, um nicht verwendete Felder zu entfernen, und führen den Serienbrief mit Daten aus. Nach der Zusammenführung werden alle nicht verwendeten Felder aus dem Dokument entfernt.

## Schritt 5: Enthaltende Felder entfernen

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Legen Sie Bereinigungsoptionen fest, um enthaltende Felder zu entfernen
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS);

// Serienbrief ausführen
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Speichern Sie das Dokument
doc.save("WorkingWithCleanupOptions.RemoveContainingFields.docx");
```

In diesem Beispiel öffnen wir ein Dokument mit Serienbrieffeldern, legen die Bereinigungsoptionen fest, um enthaltende Felder zu entfernen, und führen den Serienbrief mit Daten aus. Nach der Zusammenführung werden die Felder selbst aus dem Dokument entfernt.

## Schritt 6: Leere Tabellenzeilen entfernen

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Legen Sie Bereinigungsoptionen fest, um leere Tabellenzeilen zu entfernen
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS);

// Serienbrief ausführen
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Speichern Sie das Dokument
doc.save("WorkingWithCleanupOptions.RemoveEmptyTableRows.docx");
```

In diesem Beispiel öffnen wir ein Dokument mit einer Tabelle und Serienbrieffeldern, legen die Bereinigungsoptionen fest, um leere Tabellenzeilen zu entfernen, und führen den Serienbrief mit Daten aus. Nach der Zusammenführung werden alle leeren Tabellenzeilen aus dem Dokument entfernt.

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie Bereinigungsoptionen in Aspose.Words für Java verwenden, um Dokumente während des Seriendruckvorgangs zu bearbeiten und zu bereinigen. Diese Optionen bieten eine detaillierte Kontrolle über die Dokumentenbereinigung, sodass Sie ganz einfach ausgefeilte und individuelle Dokumente erstellen können.

## FAQs

### Welche Bereinigungsoptionen gibt es in Aspose.Words für Java?

Bei den Bereinigungsoptionen in Aspose.Words für Java handelt es sich um Einstellungen, mit denen Sie verschiedene Aspekte der Dokumentenbereinigung während des Serienbriefprozesses steuern können. Sie ermöglichen es Ihnen, unnötige Elemente wie leere Absätze, ungenutzte Bereiche und mehr zu entfernen und so sicherzustellen, dass Ihr endgültiges Dokument gut strukturiert und ausgefeilt ist.

### Wie kann ich leere Absätze aus meinem Dokument entfernen?

 Um leere Absätze mit Aspose.Words für Java aus Ihrem Dokument zu entfernen, können Sie Folgendes festlegen`MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS` Option auf wahr. Dadurch werden Absätze ohne Inhalt automatisch entfernt, was zu einem übersichtlicheren Dokument führt.

###  Was ist der Zweck des`REMOVE_UNUSED_REGIONS` cleanup option?

 Der`MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS` Die Option wird verwendet, um Bereiche in einem Dokument zu entfernen, die während des Seriendruckvorgangs keine entsprechenden Daten haben. Es hilft, Ihr Dokument aufgeräumt zu halten, indem es ungenutzte Platzhalter entfernt.

### Kann ich mit Aspose.Words für Java leere Tabellenzeilen aus einem Dokument entfernen?

 Ja, Sie können leere Tabellenzeilen aus einem Dokument entfernen, indem Sie das festlegen`MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS`Bereinigungsoption auf true setzen. Dadurch werden automatisch alle Tabellenzeilen gelöscht, die keine Daten enthalten, wodurch eine gut strukturierte Tabelle in Ihrem Dokument gewährleistet wird.

###  Was passiert, wenn ich das einstelle?`REMOVE_CONTAINING_FIELDS` option?

 Einstellen der`MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS` Mit dieser Option wird während des Seriendruckvorgangs das gesamte Serienbrieffeld, einschließlich des enthaltenden Absatzes, aus dem Dokument entfernt. Dies ist nützlich, wenn Sie Briefvorlagenfelder und den zugehörigen Text entfernen möchten.

### Wie kann ich nicht verwendete Zusammenführungsfelder aus meinem Dokument entfernen?

 Um nicht verwendete Zusammenführungsfelder aus einem Dokument zu entfernen, können Sie Folgendes festlegen`MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS` Option auf wahr. Dadurch werden automatisch Serienbrieffelder entfernt, die während des Seriendrucks nicht ausgefüllt werden, was zu einem saubereren Dokument führt.

###  Was ist der Unterschied zwischen`REMOVE_EMPTY_FIELDS` and `REMOVE_UNUSED_FIELDS` cleanup options?

 Der`REMOVE_EMPTY_FIELDS` Mit dieser Option werden Briefvorlagenfelder entfernt, die keine Daten enthalten oder während des Seriendruckvorgangs leer sind. Andererseits ist die`REMOVE_UNUSED_FIELDS`Diese Option entfernt Zusammenführungsfelder, die während der Zusammenführung nicht mit Daten gefüllt werden. Die Wahl zwischen ihnen hängt davon ab, ob Sie Felder ohne Inhalt oder solche, die im jeweiligen Zusammenführungsvorgang nicht verwendet werden, entfernen möchten.

### Wie kann ich das Entfernen von Absätzen mit Satzzeichen aktivieren?

 Um das Entfernen von Absätzen mit Satzzeichen zu ermöglichen, können Sie Folgendes festlegen`cleanupParagraphsWithPunctuationMarks` Setzen Sie die Option auf „true“ und geben Sie die Satzzeichen an, die bei der Bereinigung berücksichtigt werden sollen. Dadurch können Sie ein verfeinertes Dokument erstellen, indem Sie unnötige Absätze, die nur aus Satzzeichen bestehen, entfernen.

### Kann ich die Bereinigungsoptionen in Aspose.Words für Java anpassen?

Ja, Sie können die Bereinigungsoptionen an Ihre spezifischen Bedürfnisse anpassen. Sie können auswählen, welche Bereinigungsoptionen Sie anwenden möchten, und diese gemäß Ihren Dokumentenbereinigungsanforderungen konfigurieren, um sicherzustellen, dass Ihr endgültiges Dokument Ihren gewünschten Standards entspricht.