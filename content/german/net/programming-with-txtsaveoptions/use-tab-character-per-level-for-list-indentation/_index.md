---
title: Verwenden Sie Tabulatorzeichen pro Ebene für die Listeneinrückung
linktitle: Verwenden Sie Tabulatorzeichen pro Ebene für die Listeneinrückung
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie die Funktion „Einrückungslisten mit Tabulatorzeichen“ in Aspose.Words für .NET verwenden. Sparen Sie Zeit und verbessern Sie Ihren Arbeitsablauf mit dieser leistungsstarken Funktion.
type: docs
weight: 10
url: /de/net/programming-with-txtsaveoptions/use-tab-character-per-level-for-list-indentation/
---

In diesem Tutorial untersuchen wir den C#-Quellcode, der für die Funktion „Ein Tabulatorzeichen pro Ebene für die Listeneinrückung verwenden“ mit Aspose.Words für .NET bereitgestellt wird. Mit dieser Funktion können Sie Tabulatorzeichen zum Einrücken von Listen auf jeder Ebene anwenden und so mehr Flexibilität und Kontrolle über das Erscheinungsbild Ihrer Dokumente erhalten.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung mit Aspose.Words für .NET eingerichtet haben. Stellen Sie sicher, dass Sie die erforderlichen Verweise hinzugefügt und die entsprechenden Namespaces importiert haben.

## Schritt 2: Erstellen des Dokuments und des Generators

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 In diesem Schritt erstellen wir ein neues`Document` Objekt und ein zugehöriges Objekt`DocumentBuilder` Objekt. Mit diesen Objekten können wir unser Dokument bearbeiten und generieren.

## Schritt 3: Erstellen einer Liste mit drei Einrückungsebenen

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

In diesem Schritt wenden wir das Standardformat für Listennummern an`ApplyNumberDefault()` Methode des Listenformatierers. Als Nächstes fügen wir mit dem Document Builder drei Elemente zu unserer Liste hinzu`Writeln()` Und`Write()` Methoden. Wir benutzen das`ListIndent()` Methode zum Erhöhen der Einrückung auf jeder Ebene.

## Schritt 4: Aufnahmeoptionen konfigurieren

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 1;
saveOptions.ListIndentation.Character = '\t';
```

 In diesem Schritt konfigurieren wir die Optionen zum Speichern des Dokuments. Wir schaffen ein Neues`TxtSaveOptions` Objekt und legen Sie das fest`ListIndentation.Count` -Eigenschaft auf 1, um die Anzahl der Tabulatorzeichen pro Einrückungsebene anzugeben. Wir stellen auch die ein`ListIndentation.Character` Eigenschaft auf „\t“, um anzugeben, dass wir Tabulatorzeichen verwenden möchten.

## Schritt 5: Speichern Sie das Dokument

```csharp
doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
```

 In diesem letzten Schritt speichern wir das Dokument mit den angegebenen Speicheroptionen. Wir benutzen das`Save()` Methode des Dokuments, die den vollständigen Pfad der Ausgabedatei und die Speicheroptionen übergibt.


Jetzt können Sie den Quellcode ausführen, um ein Dokument mit Listeneinrückung mithilfe von Tabulatorzeichen zu generieren. Die Ausgabedatei wird im angegebenen Verzeichnis mit dem Namen „WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt“ gespeichert.

### Beispielcodequelle für die Funktion „Ein Tabulatorzeichen pro Ebene für Listeneinrückung verwenden“ mit Aspose.Words für .NET:

```csharp

// Pfad zu Ihrem Dokumentenverzeichnis
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

Nachdem Sie nun die Generierung Ihres Dokuments mit Listeneinrückung mithilfe von Tabulatorzeichen abgeschlossen haben, können Sie Markdown verwenden, um den Inhalt Ihres Artikels zu formatieren. Achten Sie darauf, geeignete Formatierungs-Tags zu verwenden, um Titel, Untertitel und den enthaltenen Quellcode hervorzuheben.

### Häufig gestellte Fragen

#### F: Was ist die Funktion „Ein Tabulatorzeichen pro Ebene für die Listeneinrückung verwenden“ bei Aspose.Words für .NET?
Die Funktion „Ein Tabulatorzeichen pro Ebene für die Listeneinrückung verwenden“ mit Aspose.Words für .NET ermöglicht die Anwendung von Tabulatorzeichen für die Listeneinrückung auf jeder Ebene. Dies bietet mehr Flexibilität und Kontrolle über das Erscheinungsbild Ihrer Dokumente.

#### F: Wie kann ich diese Funktion mit Aspose.Words für .NET verwenden?
Um diese Funktion mit Aspose.Words für .NET zu verwenden, können Sie die folgenden Schritte ausführen:

Richten Sie Ihre Entwicklungsumgebung ein, indem Sie die erforderlichen Referenzen hinzufügen und die entsprechenden Namespaces importieren.

 Erstelle eine neue`Document` Objekt und ein zugehöriges Objekt`DocumentBuilder` Objekt.

 Benutzen Sie die`DocumentBuilder` um mithilfe der Methoden eine Liste mit mehreren Einrückungsebenen zu erstellen`ApplyNumberDefault()` um das Standardlistennummernformat anzuwenden,`Writeln()` Und`Write()` um Elemente zur Liste hinzuzufügen und`ListIndent()`um die Einrückung auf jeder Ebene zu erhöhen.

 Konfigurieren Sie Speicheroptionen, indem Sie eine erstellen`TxtSaveOptions` Objekt und Festlegen der Eigenschaften`ListIndentation.Count` auf die Anzahl der Tabulatorzeichen pro Ebene und`ListIndentation.Character` Zu`'\t'` um die Tabulatorzeichen zu verwenden.

 Speichern Sie das Dokument mit`Save()` Methode des Dokuments, die den vollständigen Pfad der Ausgabedatei und die Speicheroptionen angibt.

#### F: Ist es möglich, die Anzahl der Tabulatorzeichen pro Ebene für die Listeneinrückung anzupassen?
 Ja, Sie können die Anzahl der Tabulatorzeichen pro Ebene für die Listeneinrückung anpassen, indem Sie den Wert von ändern`ListIndentation.Count` Eigentum in der`TxtSaveOptions` Klasse. Sie können die Anzahl der gewünschten Tabulatorzeichen für jede Einrückungsebene angeben.

#### F: Welche anderen Zeichen kann ich für die Listeneinrückung mit Aspose.Words für .NET verwenden?
 Neben Tabulatorzeichen können Sie mit Aspose.Words für .NET auch andere Zeichen zum Einrücken von Listen verwenden. Sie können das einstellen`ListIndentation.Character` -Eigenschaft auf ein beliebiges Zeichen, z. B. ein Leerzeichen (`' '`), zum Einrücken von Listen.

#### F: Bietet Aspose.Words für .NET weitere Funktionen zum Verwalten von Listen?
Ja, Aspose.Words für .NET bietet viele Funktionen zum Verwalten von Listen in Word-Dokumenten. Sie können nummerierte Listen oder Listen mit Aufzählungszeichen erstellen, Einrückungsstufen festlegen, den Stil von Listen anpassen, Listenelemente hinzufügen und vieles mehr.