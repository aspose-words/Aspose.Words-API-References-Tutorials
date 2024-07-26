---
title: Tabulatorzeichen pro Ebene für Listeneinrückung verwenden
linktitle: Tabulatorzeichen pro Ebene für Listeneinrückung verwenden
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie die Funktion zum Einrücken von Listen mit Tabulatorzeichen in Aspose.Words für .NET verwenden. Sparen Sie Zeit und verbessern Sie Ihren Workflow mit dieser leistungsstarken Funktion.
type: docs
weight: 10
url: /de/net/programming-with-txtsaveoptions/use-tab-character-per-level-for-list-indentation/
---

In diesem Tutorial untersuchen wir den C#-Quellcode für die Funktion „Ein Tabulatorzeichen pro Ebene für Listeneinrückung verwenden“ mit Aspose.Words für .NET. Mit dieser Funktion können Sie Tabulatorzeichen zum Einrücken von Listen auf jeder Ebene anwenden, was Ihnen mehr Flexibilität und Kontrolle über das Erscheinungsbild Ihrer Dokumente bietet.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung mit Aspose.Words für .NET eingerichtet haben. Stellen Sie sicher, dass Sie die erforderlichen Referenzen hinzugefügt und die entsprechenden Namespaces importiert haben.

## Schritt 2: Erstellen des Dokuments und des Generators

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 In diesem Schritt erstellen wir ein neues`Document` Objekt und ein zugehöriges`DocumentBuilder` Objekt. Diese Objekte ermöglichen uns die Bearbeitung und Generierung unseres Dokuments.

## Schritt 3: Erstellen einer Liste mit drei Einrückungsebenen

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

In diesem Schritt wenden wir das Standardformat der Listennummern an, indem wir`ApplyNumberDefault()` Methode des Listenformatierers. Als nächstes fügen wir unserer Liste drei Elemente hinzu, indem wir die`Writeln()`Und`Write()` Methoden. Wir verwenden die`ListIndent()` Methode, um die Einrückung auf jeder Ebene zu erhöhen.

## Schritt 4: Aufzeichnungsoptionen konfigurieren

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 1;
saveOptions.ListIndentation.Character = '\t';
```

 In diesem Schritt konfigurieren wir die Optionen zum Speichern des Dokuments. Wir erstellen ein neues`TxtSaveOptions` Objekt und setzen Sie den`ListIndentation.Count` -Eigenschaft auf 1, um die Anzahl der Tabulatorzeichen pro Einrückungsebene festzulegen. Wir setzen auch die`ListIndentation.Character` -Eigenschaft auf „\t“, um anzugeben, dass wir Tabulatorzeichen verwenden möchten.

## Schritt 5: Speichern Sie das Dokument

```csharp
doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
```

 In diesem letzten Schritt speichern wir das Dokument mit den angegebenen Speicheroptionen. Wir verwenden die`Save()` Methode des Dokuments, die den vollständigen Pfad der Ausgabedatei und die Speicheroptionen übergibt.


Jetzt können Sie den Quellcode ausführen, um ein Dokument mit Listeneinrückung mithilfe von Tabulatorzeichen zu generieren. Die Ausgabedatei wird im angegebenen Verzeichnis unter dem Namen „WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt“ gespeichert.

### Beispielcodequelle für die Funktion „Ein Tabulatorzeichen pro Ebene für Listeneinrückung verwenden“ mit Aspose.Words für .NET:

```csharp

// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Erstellen Sie eine Liste mit drei Einrückungsebenen
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");

TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 1;
saveOptions.ListIndentation.Character = '\t';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);

```

Nachdem Sie nun Ihr Dokument mit Listeneinrückung mithilfe von Tabulatorzeichen erstellt haben, können Sie Markdown verwenden, um den Inhalt Ihres Artikels zu formatieren. Achten Sie darauf, geeignete Formatierungs-Tags zu verwenden, um Titel, Untertitel und enthaltenen Quellcode hervorzuheben.

### Häufig gestellte Fragen

#### F: Was ist die Funktion „Ein Tabulatorzeichen pro Ebene für Listeneinrückung verwenden“ in Aspose.Words für .NET?
Die Funktion „Ein Tabulatorzeichen pro Ebene für Listeneinrückung verwenden“ von Aspose.Words für .NET ermöglicht die Anwendung von Tabulatorzeichen für Listeneinrückungen auf jeder Ebene. Dies bietet mehr Flexibilität und Kontrolle über das Erscheinungsbild Ihrer Dokumente.

#### F: Wie kann ich diese Funktion mit Aspose.Words für .NET verwenden?
Um diese Funktion mit Aspose.Words für .NET zu verwenden, können Sie diese Schritte ausführen:

Richten Sie Ihre Entwicklungsumgebung ein, indem Sie die erforderlichen Referenzen hinzufügen und die entsprechenden Namespaces importieren.

 Erstelle eine neue`Document` Objekt und ein zugehöriges`DocumentBuilder` Objekt.

 Verwenden Sie die`DocumentBuilder`zum Erstellen einer Liste mit mehreren Einrückungsebenen mit den Methoden`ApplyNumberDefault()` um das Standardlistennummernformat anzuwenden,`Writeln()`Und`Write()` um Elemente zur Liste hinzuzufügen, und`ListIndent()` um die Einrückung auf jeder Ebene zu erhöhen.

 Konfigurieren Sie die Speicheroptionen durch die Erstellung eines`TxtSaveOptions` Objekt und Festlegen der Eigenschaften`ListIndentation.Count` auf die Anzahl der Tabulatorzeichen pro Ebene und`ListIndentation.Character` Zu`'\t'` um die Tabulatorzeichen zu verwenden.

 Speichern Sie das Dokument mit dem`Save()` Methode des Dokuments, die den vollständigen Pfad der Ausgabedatei und die Speicheroptionen angibt.

#### F: Ist es möglich, die Anzahl der Tabulatorzeichen pro Ebene für die Listeneinrückung anzupassen?
 Ja, Sie können die Anzahl der Tabulatorzeichen pro Ebene für die Listeneinrückung anpassen, indem Sie den Wert des`ListIndentation.Count` Eigentum in der`TxtSaveOptions` Klasse. Sie können die Anzahl der Tabulatorzeichen für jede Einrückungsebene angeben.

#### F: Welche anderen Zeichen kann ich mit Aspose.Words für .NET zur Listeneinrückung verwenden?
Neben Tabulatorzeichen können Sie mit Aspose.Words für .NET auch andere Zeichen für die Listeneinrückung verwenden. Sie können das`ListIndentation.Character` -Eigenschaft auf ein beliebiges Zeichen, beispielsweise ein Leerzeichen (`' '`), zum Einrücken von Listen.

#### F: Bietet Aspose.Words für .NET weitere Funktionen zum Verwalten von Listen?
Ja, Aspose.Words für .NET bietet viele Funktionen zum Verwalten von Listen in Word-Dokumenten. Sie können nummerierte oder Aufzählungslisten erstellen, Einrückungsebenen festlegen, den Stil von Listen anpassen, Listenelemente hinzufügen und vieles mehr.