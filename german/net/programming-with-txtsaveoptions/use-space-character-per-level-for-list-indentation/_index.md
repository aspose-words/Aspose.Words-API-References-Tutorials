---
title: Verwenden Sie Leerzeichen pro Ebene für die Listeneinrückung
linktitle: Verwenden Sie Leerzeichen pro Ebene für die Listeneinrückung
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zur Verwendung eines Leerzeichens pro Ebene für die Listeneinrückung in Aspose.Words für .NET. Erstellen Sie mühelos gut strukturierte Word-Dokumente.
type: docs
weight: 10
url: /de/net/programming-with-txtsaveoptions/use-space-character-per-level-for-list-indentation/
---
Aspose.Words für .NET ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten und Bearbeiten von Word-Dokumenten in einer C#-Anwendung. Zu den Funktionen von Aspose.Words gehört die Möglichkeit, ein Leerzeichen pro Ebene für die Einrückung von Listen zu verwenden. In dieser Anleitung zeigen wir Ihnen, wie Sie den C#-Quellcode von Aspose.Words für .NET verwenden, um diese Funktionalität zu implementieren.

## Grundlegendes zur Aspose.Words-Bibliothek

Bevor Sie in den Code eintauchen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine beliebte Bibliothek, die die Arbeit mit Word-Dokumenten einfach und effizient macht. Es bietet zahlreiche Funktionen zum Erstellen, Ändern und Bearbeiten von Word-Dokumenten, einschließlich der Verwaltung von Listen und Einrückungen.

## Erstellen des Dokuments und Hinzufügen von Inhalten

Der erste Schritt besteht darin, ein neues Dokument zu erstellen und ihm Inhalte hinzuzufügen. Verwenden Sie die Document-Klasse, um eine neue Dokumentinstanz zu erstellen. Verwenden Sie dann die DocumentBuilder-Klasse, um Text hinzuzufügen und eine Liste mit mehreren Einrückungsebenen zu erstellen. Hier ist ein Beispiel :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Erstellen Sie eine Liste mit drei Einrückungsebenen
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

In diesem Beispiel erstellen wir ein neues Dokument und verwenden den DocumentBuilder, um Text hinzuzufügen und eine Liste mit drei Einrückungsebenen zu erstellen. Wir haben der Liste drei Elemente hinzugefügt, wobei jedes Element um eine weitere Ebene eingerückt ist.

## Verwendung eines Leerzeichens pro Ebene zum Einrücken der Liste

Sobald der Inhalt hinzugefügt wurde, können wir nun die Einrückung der Listen mit einem Leerzeichen pro Ebene konfigurieren. Dazu verwenden wir die Klasse TxtSaveOptions und setzen die Eigenschaft ListIndentation.Count auf die Anzahl der Einrückungsebenen und die Eigenschaft ListIndentation.Character auf das zu verwendende Leerzeichen. Hier ist wie:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 3;
saveOptions.ListIndentation.Character = ' ';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
```

In diesem Beispiel erstellen wir eine Instanz von TxtSaveOptions und setzen die ListIndentation.Count-Eigenschaft auf 3, um anzugeben, dass die Liste drei Einrückungsebenen enthält. Außerdem legen wir die ListIndentation.Character-Eigenschaft auf das Leerzeichen (' ') fest, das wir für die Einrückung verwenden möchten.

### Beispielquellcode für die Funktion „Ein Leerzeichen pro Ebene für Listeneinrückung verwenden“ mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode für die Funktion „Ein Leerzeichen pro Ebene für die Listeneinrückung verwenden“ mit Aspose.Words für .NET:

```csharp

using Aspose.Words;
using Aspose.Words.Saving;

namespace Example
{
     class Program
     {
         static void Main(string[] args)
         {
             // Pfad zu Ihrem Dokumentenverzeichnis
             string dataDir = "YOUR DOCUMENTS DIRECTORY";

             // Erstellen Sie das Dokument und fügen Sie Inhalte hinzu
             Document doc = new Document();
             DocumentBuilder builder = new DocumentBuilder(doc);

             // Erstellen Sie eine Liste mit drei Einrückungsebenen
             builder.ListFormat.ApplyNumberDefault();
             builder. Writen("Element 1");
             builder.ListFormat.ListIndent();
             builder. Writen("Element 2");
             builder.ListFormat.ListIndent();
             builder.Write("Element 3");

             // Verwenden Sie für die Listeneinrückung ein Leerzeichen pro Ebene
             TxtSaveOptions saveOptions = new TxtSaveOptions();
             saveOptions.ListIndentation.Count = 3;
             saveOptions.ListIndentation.Character = ' ';

             // Speichern Sie das Dokument mit den angegebenen Optionen
             doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
         }
     }
}

```

## Abschluss

In diesem Handbuch haben wir erklärt, wie Sie Aspose.Words für .NET verwenden, um die Funktionalität „Ein Leerzeichen pro Ebene für die Listeneinrückung verwenden“ anzuwenden. Indem Sie die bereitgestellten Schritte befolgen und den bereitgestellten C#-Quellcode verwenden, können Sie die Einrückung von Listen in Ihren Word-Dokumenten einfach mit einem Leerzeichen pro Ebene konfigurieren. Aspose.Words bietet enorme Flexibilität und Leistungsfähigkeit für die Arbeit mit Textformatierung und Listenverwaltung, sodass Sie gut strukturierte Dokumente in Ihrer C#-Anwendung erstellen können.

### Häufig gestellte Fragen

#### F: Was ist Aspose.Words für .NET?
Aspose.Words für .NET ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten und Bearbeiten von Word-Dokumenten in einer C#-Anwendung. Es bietet viele Funktionen für die Arbeit mit Word-Dokumenten, einschließlich der Möglichkeit, ein Leerzeichen pro Ebene zum Einrücken von Listen zu verwenden.

#### F: Wie kann ich mit Aspose.Words für .NET ein Leerzeichen pro Ebene für die Listeneinrückung verwenden?
Sie können ein Leerzeichen pro Ebene für die Listeneinrückung verwenden, indem Sie die folgenden Schritte ausführen:

 Erstellen Sie ein neues Dokument mit`Document` Klasse.

 Benutzen Sie die`DocumentBuilder`Klasse, um dem Dokument Inhalte hinzuzufügen und eine Liste mit mehreren Einrückungsebenen zu erstellen.

 Nachdem Sie den Inhalt hinzugefügt und die Listeneinrückung konfiguriert haben, verwenden Sie die`TxtSaveOptions` Klasse und legen Sie die fest`ListIndentation.Count` Eigenschaft auf die Anzahl der Einrückungsebenen und die`ListIndentation.Character` Eigentum auf dem Raum (`' '`) benutzen.

 Speichern Sie das Dokument mit den angegebenen Optionen mithilfe von`Save` Methode der`Document` Klasse.

#### F: Unterstützt Aspose.Words andere Zeichen für die Listeneinrückung?
Ja, Aspose.Words unterstützt andere Zeichen zum Einrücken von Listen. Sie können Nicht-Leerzeichen wie Tabulatoren (`'\t'` ) oder andere Sonderzeichen, indem Sie die festlegen`ListIndentation.Character` Eigenschaft auf den gewünschten Charakter.

#### F: Ist es möglich, die Anzahl der Leerzeichen pro Ebene für die Listeneinrückung anzupassen?
 Ja, Sie können die Anzahl der Leerzeichen pro Ebene für die Listeneinrückung anpassen, indem Sie den Wert von ändern`ListIndentation.Count` Eigentum in der`TxtSaveOptions` Klasse. Sie können die gewünschte Anzahl an Leerzeichen für jede Einrückungsebene angeben.

#### F: Welche weiteren Funktionen bietet Aspose.Words für die Listenverwaltung?
Aspose.Words bietet viele Funktionen zum Verwalten von Listen in Word-Dokumenten. Sie können nummerierte Listen oder Listen mit Aufzählungszeichen erstellen, Einrückungsstufen festlegen, den Stil von Listen anpassen, Listenelemente hinzufügen und vieles mehr.