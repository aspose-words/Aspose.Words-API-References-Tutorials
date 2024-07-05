---
title: Leerzeichen pro Ebene zur Listeneinrückung verwenden
linktitle: Leerzeichen pro Ebene zur Listeneinrückung verwenden
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zur Verwendung eines Leerzeichens pro Ebene für Listeneinrückungen in Aspose.Words für .NET. Erstellen Sie mühelos gut strukturierte Word-Dokumente.
type: docs
weight: 10
url: /de/net/programming-with-txtsaveoptions/use-space-character-per-level-for-list-indentation/
---
Aspose.Words für .NET ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten und Manipulieren von Word-Dokumenten in einer C#-Anwendung. Zu den von Aspose.Words angebotenen Funktionen gehört die Möglichkeit, ein Leerzeichen pro Ebene zum Einrücken von Listen zu verwenden. In dieser Anleitung zeigen wir Ihnen, wie Sie den C#-Quellcode von Aspose.Words für .NET verwenden, um diese Funktionalität zu implementieren.

## Die Aspose.Words-Bibliothek verstehen

Bevor Sie sich in den Code vertiefen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine beliebte Bibliothek, die die Textverarbeitung mit Word-Dokumenten einfach und effizient macht. Sie bietet eine breite Palette an Funktionen zum Erstellen, Ändern und Bearbeiten von Word-Dokumenten, einschließlich der Verwaltung von Listen und Einrückungen.

## Erstellen des Dokuments und Hinzufügen von Inhalten

Der erste Schritt besteht darin, ein neues Dokument zu erstellen und Inhalt hinzuzufügen. Verwenden Sie die Klasse Document, um eine neue Dokumentinstanz zu erstellen. Verwenden Sie dann die Klasse DocumentBuilder, um Text hinzuzufügen und eine Liste mit mehreren Einrückungsebenen zu erstellen. Hier ist ein Beispiel:

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

In diesem Beispiel erstellen wir ein neues Dokument und verwenden den DocumentBuilder, um Text hinzuzufügen und eine Liste mit drei Einrückungsebenen zu erstellen. Wir haben der Liste drei Elemente hinzugefügt, wobei jedes Element eine weitere Ebene eingerückt ist.

## Ein Leerzeichen pro Ebene zur Listeneinrückung verwenden

Nachdem der Inhalt hinzugefügt wurde, können wir nun die Einrückung der Listen mit einem Leerzeichen pro Ebene konfigurieren. Dazu verwenden wir die Klasse TxtSaveOptions und setzen die Eigenschaft ListIndentation.Count auf die Anzahl der Einrückungsebenen und die Eigenschaft ListIndentation.Character auf das zu verwendende Leerzeichen. So geht's:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 3;
saveOptions.ListIndentation.Character = ' ';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
```

In diesem Beispiel erstellen wir eine Instanz von TxtSaveOptions und setzen die Eigenschaft ListIndentation.Count auf 3, um anzugeben, dass die Liste drei Einrückungsebenen enthält. Außerdem setzen wir die Eigenschaft ListIndentation.Character auf das Leerzeichen (' '), das wir für die Einrückung verwenden möchten.

### Beispielquellcode für die Funktion „Ein Leerzeichen pro Ebene für Listeneinrückung verwenden“ mit Aspose.Words für .NET

Hier ist der vollständige Beispiel-Quellcode für die Funktion „Ein Leerzeichen pro Ebene für Listeneinrückung verwenden“ mit Aspose.Words für .NET:

```csharp

using Aspose.Words;
using Aspose.Words.Saving;

namespace Example
{
     class Program
     {
         static void Main(string[] args)
         {
             // Pfad zu Ihrem Dokumentverzeichnis
             string dataDir = "YOUR DOCUMENTS DIRECTORY";

             // Erstellen Sie das Dokument und fügen Sie Inhalt hinzu
             Document doc = new Document();
             DocumentBuilder builder = new DocumentBuilder(doc);

             // Erstellen Sie eine Liste mit drei Einrückungsebenen
             builder.ListFormat.ApplyNumberDefault();
             builder. Writen("Element 1");
             builder.ListFormat.ListIndent();
             builder. Writen("Element 2");
             builder.ListFormat.ListIndent();
             builder.Write("Element 3");

             // Verwenden Sie ein Leerzeichen pro Ebene für die Listeneinrückung
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

In diesem Handbuch haben wir erklärt, wie Sie mit Aspose.Words für .NET die Funktion „Ein Leerzeichen pro Ebene für Listeneinrückung verwenden“ anwenden. Indem Sie die angegebenen Schritte befolgen und den bereitgestellten C#-Quellcode verwenden, können Sie die Einrückung von Listen in Ihren Word-Dokumenten ganz einfach mit einem Leerzeichen pro Ebene konfigurieren. Aspose.Words bietet enorme Flexibilität und Leistung für die Textverarbeitung mit Textformatierung und Listenverwaltung, sodass Sie in Ihrer C#-Anwendung gut strukturierte Dokumente erstellen können.

### Häufig gestellte Fragen

#### F: Was ist Aspose.Words für .NET?
Aspose.Words für .NET ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten und Manipulieren von Word-Dokumenten in einer C#-Anwendung. Sie bietet zahlreiche Funktionen für die Textverarbeitung mit Word-Dokumenten, einschließlich der Möglichkeit, ein Leerzeichen pro Ebene zum Einrücken von Listen zu verwenden.

#### F: Wie kann ich mit Aspose.Words für .NET ein Leerzeichen pro Ebene zum Einrücken von Listen verwenden?
Sie können ein Leerzeichen pro Ebene zum Einrücken von Listen verwenden, indem Sie die folgenden Schritte ausführen:

 Erstellen Sie ein neues Dokument mit dem`Document` Klasse.

 Verwenden Sie die`DocumentBuilder`Klasse, um dem Dokument Inhalt hinzuzufügen und eine Liste mit mehreren Einrückungsebenen zu erstellen.

 Nachdem Sie den Inhalt hinzugefügt und die Listeneinrückung konfiguriert haben, verwenden Sie die`TxtSaveOptions` Klasse und legen Sie die`ListIndentation.Count` Eigenschaft auf die Anzahl der Einrückungsebenen und die`ListIndentation.Character` Eigenschaft auf dem Raum (`' '`) benutzen.

 Speichern Sie das Dokument mit den angegebenen Optionen über den`Save` Methode der`Document` Klasse.

#### F: Unterstützt Aspose.Words andere Zeichen für Listeneinrückungen?
Ja, Aspose.Words unterstützt andere Zeichen zum Einrücken von Listen. Sie können andere Zeichen als Leerzeichen verwenden, z. B. Tabulatoren (`'\t'` ) oder andere Sonderzeichen, indem Sie den`ListIndentation.Character` -Eigenschaft auf das gewünschte Zeichen.

#### F: Ist es möglich, die Anzahl der Leerzeichen pro Ebene für die Listeneinrückung anzupassen?
 Ja, Sie können die Anzahl der Leerzeichen pro Ebene für die Listeneinrückung anpassen, indem Sie den Wert des`ListIndentation.Count` Eigentum in der`TxtSaveOptions` Klasse. Sie können die Anzahl der gewünschten Leerzeichen für jede Einrückungsebene angeben.

#### F: Welche anderen Funktionen bietet Aspose.Words für die Listenverwaltung?
Aspose.Words bietet zahlreiche Funktionen zum Verwalten von Listen in Word-Dokumenten. Sie können nummerierte oder Aufzählungslisten erstellen, Einrückungsebenen festlegen, den Stil von Listen anpassen, Listenelemente hinzufügen und vieles mehr.