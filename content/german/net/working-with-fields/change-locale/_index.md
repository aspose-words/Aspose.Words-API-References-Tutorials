---
title: Gebietsschema ändern
linktitle: Gebietsschema ändern
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET das Gebietsschema für die Datums- und Zahlenformatierung in Word-Dokumenten ändern.
type: docs
weight: 10
url: /de/net/working-with-fields/change-locale/
---

In diesem Tutorial führen wir Sie durch den Prozess zum Ändern des Gebietsschemas in Word-Dokumenten mit Aspose.Words für .NET. Durch Ändern des Gebietsschemas können Sie die Formatierung von Daten und Zahlen während Seriendruckvorgängen steuern. Wir stellen Ihnen den erforderlichen C#-Quellcode und schrittweise Anweisungen zur Verfügung, um dies zu erreichen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Auf Ihrem System ist die Bibliothek Aspose.Words für .NET installiert.

## Schritt 1: Erstellen Sie ein Dokument und einen DocumentBuilder
Erstellen Sie zunächst eine Instanz der Document-Klasse und ein DocumentBuilder-Objekt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Feld einfügen
Fügen Sie als Nächstes mit der Methode InsertField ein Seriendruckfeld in das Dokument ein:

```csharp
builder.InsertField("MERGEFIELD Date");
```

Im obigen Code fügen wir ein Seriendruckfeld mit dem Namen „Datum“ in das Dokument ein.

## Schritt 3: Ändern Sie das Gebietsschema
Um das Gebietsschema für die Datums- und Zahlenformatierung zu ändern, können Sie die aktuelle Kultur des Threads ändern. In diesem Beispiel setzen wir das Gebietsschema auf Deutsch („de-DE“):

```csharp
CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");
```

Im obigen Code speichern wir die aktuelle Kultur und stellen dann die Kultur des aktuellen Threads auf Deutsch ein.

## Schritt 4: Serienbrief erstellen
Führen Sie einen Serienbriefvorgang durch und geben Sie den Datumswert für das Feld „Datum“ ein:

```csharp
doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });
```

In diesem Codeausschnitt führen wir den Serienbriefvorgang aus und geben als Wert für das Feld „Datum“ das aktuelle Datum an.

## Schritt 5: Wiederherstellen des ursprünglichen Gebietsschemas
Stellen Sie nach Abschluss des Seriendrucks die ursprüngliche Kultur für den Thread wieder her:

```csharp
Thread.CurrentThread.CurrentCulture = currentCulture;
```

Im obigen Code stellen wir die ursprüngliche Kultur des Threads wieder her.

## Schritt 6: Speichern Sie das Dokument
Speichern Sie das geänderte Dokument mit der Save-Methode der Document-Klasse in einer Datei:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

### Beispiel-Quellcode zum Ändern des Gebietsschemas mit Aspose.Words für .NET
Hier ist der vollständige Quellcode zum Ändern des Gebietsschemas in Word-Dokumenten mit Aspose.Words für .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField("MERGEFIELD Date");

CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");

doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });

Thread.CurrentThread.CurrentCulture = currentCulture;

doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

## Abschluss
Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie das Gebietsschema in Word-Dokumenten mit Aspose.Words für .NET ändern. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie jetzt die Formatierung von Daten und Zahlen während Seriendruckvorgängen steuern. Passen Sie das Gebietsschema entsprechend Ihren Anforderungen an, um eine genaue und konsistente Formatierung in Ihren Dokumenten sicherzustellen.

### Häufig gestellte Fragen

#### F: Ist Aspose.Words mit verschiedenen Versionen von Microsoft Word kompatibel?

A: Ja, Aspose.Words ist mit verschiedenen Versionen von Microsoft Word kompatibel, darunter Word 2003, Word 2007, Word 2010, Word 2013, Word 2016 und Word 2019.

#### F: Unterstützt Aspose.Words komplexe Feldstrukturen?

A: Absolut! Aspose.Words bietet umfassende Unterstützung für komplexe Feldstrukturen, einschließlich verschachtelter Felder, Berechnungen und bedingter Ausdrücke. Sie können diese leistungsstarke API verwenden, um mit jeder Art von Feldstruktur zu arbeiten.

#### F: Unterstützt Aspose.Words Feldaktualisierungsvorgänge?

A: Ja, Aspose.Words ermöglicht Ihnen die planmäßige Aktualisierung von Feldern. Mithilfe der API können Sie Feldwerte problemlos aktualisieren, Berechnungen aktualisieren und andere feldbezogene Vorgänge ausführen.

#### F: Ist es möglich, Felder mit Aspose.Words in einfachen Text umzuwandeln?

A: Natürlich! Aspose.Words bietet Methoden, um Felder in Klartext umzuwandeln. Dies kann nützlich sein, wenn Sie den Inhalt ohne Formatierung oder feldbezogene Funktionen extrahieren müssen.

#### F: Ist es möglich, mit Aspose.Words Word-Dokumente mit dynamischen Feldern zu erstellen?

A: Absolut! Aspose.Words bietet robuste Funktionen zum Generieren von Word-Dokumenten mit dynamischen Feldern. Sie können Vorlagen mit vordefinierten Feldern erstellen und diese dynamisch mit Daten füllen, was eine flexible und effiziente Lösung für die Dokumentgenerierung bietet.