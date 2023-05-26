---
title: Gebietsschema ändern
linktitle: Gebietsschema ändern
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET das Gebietsschema für die Datums- und Zahlenformatierung in Word-Dokumenten ändern.
type: docs
weight: 10
url: /de/net/working-with-fields/change-locale/
---

In diesem Tutorial führen wir Sie durch den Prozess der Änderung des Gebietsschemas in Word-Dokumenten mit Aspose.Words für .NET. Durch Ändern des Gebietsschemas können Sie die Formatierung von Datums- und Zahlenangaben bei Serienbriefvorgängen steuern. Wir stellen Ihnen den notwendigen C#-Quellcode und eine Schritt-für-Schritt-Anleitung zur Verfügung, um dies zu erreichen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Aspose.Words für .NET-Bibliothek auf Ihrem System installiert.

## Schritt 1: Erstellen Sie ein Dokument und einen DocumentBuilder
Erstellen Sie zunächst eine Instanz der Document-Klasse und ein DocumentBuilder-Objekt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Fügen Sie ein Feld ein
Als nächstes fügen Sie mithilfe der InsertField-Methode ein Zusammenführungsfeld in das Dokument ein:

```csharp
builder.InsertField("MERGEFIELD Date");
```

Im obigen Code fügen wir ein Zusammenführungsfeld mit dem Namen „Datum“ in das Dokument ein.

## Schritt 3: Ändern Sie das Gebietsschema
Um das Gebietsschema für die Datums- und Zahlenformatierung zu ändern, können Sie die aktuelle Kultur des Threads ändern. In diesem Beispiel stellen wir das Gebietsschema auf Deutsch („de-DE“) ein:

```csharp
CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");
```

Im obigen Code speichern wir die aktuelle Kultur und setzen dann die Kultur des aktuellen Threads auf Deutsch.

## Schritt 4: Führen Sie den Serienbrief durch
Führen Sie einen Seriendruckvorgang durch und geben Sie den Datumswert für das Feld „Datum“ ein:

```csharp
doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });
```

In diesem Codeausschnitt führen wir den Seriendruckvorgang aus und geben das aktuelle Datum als Wert für das Feld „Datum“ an.

## Schritt 5: Stellen Sie das ursprüngliche Gebietsschema wieder her
Nachdem der Seriendruck abgeschlossen ist, stellen Sie die ursprüngliche Kultur für den Thread wieder her:

```csharp
Thread.CurrentThread.CurrentCulture = currentCulture;
```

Im obigen Code stellen wir die ursprüngliche Kultur des Threads wieder her.

## Schritt 6: Speichern Sie das Dokument
Speichern Sie das geänderte Dokument mit der Save-Methode der Document-Klasse in einer Datei:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

### Beispielquellcode zum Ändern des Gebietsschemas mit Aspose.Words für .NET
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
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Words für .NET das Gebietsschema in Word-Dokumenten ändern. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie jetzt die Formatierung von Datums- und Zahlenangaben bei Seriendruckvorgängen steuern. Passen Sie das Gebietsschema entsprechend Ihren Anforderungen an, um eine genaue und konsistente Formatierung in Ihren Dokumenten sicherzustellen.
