---
title: Verwenden von Listen in Aspose.Words für Java
linktitle: Verwenden von Listen
second_title: Aspose.Words Java-Dokumentverarbeitungs-API
description: Erfahren Sie in diesem Schritt-für-Schritt-Tutorial, wie Sie Listen in Aspose.Words für Java verwenden. Organisieren und formatieren Sie Ihre Dokumente effektiv.
type: docs
weight: 18
url: /de/java/using-document-elements/using-lists/
---

In diesem umfassenden Tutorial erfahren Sie, wie Sie Listen in Aspose.Words für Java, einer leistungsstarken API für die programmgesteuerte Arbeit mit Microsoft Word-Dokumenten, effektiv nutzen. Listen sind für die Strukturierung und Organisation von Inhalten in Ihren Dokumenten unerlässlich. Wir werden zwei wichtige Aspekte der Arbeit mit Listen behandeln: das Neustarten von Listen in jedem Abschnitt und das Festlegen von Listenebenen. Lass uns eintauchen!

## Einführung in Aspose.Words für Java

Bevor wir mit der Arbeit mit Listen beginnen, machen wir uns mit Aspose.Words für Java vertraut. Diese API bietet Entwicklern die Tools zum Erstellen, Ändern und Bearbeiten von Word-Dokumenten in einer Java-Umgebung. Es handelt sich um eine vielseitige Lösung für Aufgaben, die von der einfachen Dokumentenerstellung bis hin zur komplexen Formatierung und Inhaltsverwaltung reichen.

### Einrichten Ihrer Umgebung

 Stellen Sie zunächst sicher, dass Aspose.Words für Java in Ihrer Entwicklungsumgebung installiert und eingerichtet ist. Sie können es herunterladen[Hier](https://releases.aspose.com/words/java/). 

## Listen in jedem Abschnitt neu starten

In vielen Fällen müssen Sie die Listen möglicherweise in jedem Abschnitt Ihres Dokuments neu starten. Dies kann nützlich sein, um strukturierte Dokumente mit mehreren Abschnitten zu erstellen, beispielsweise Berichte, Handbücher oder wissenschaftliche Arbeiten.

Hier ist eine Schritt-für-Schritt-Anleitung, wie Sie dies mit Aspose.Words für Java erreichen:

### Initialisieren Sie Ihr Dokument: 
Beginnen Sie mit der Erstellung eines neuen Dokumentobjekts.

```java
Document doc = new Document();
```

### Fügen Sie eine nummerierte Liste hinzu: 
Fügen Sie Ihrem Dokument eine nummerierte Liste hinzu. Wir verwenden den Standard-Nummerierungsstil.

```java
doc.getLists().add(ListTemplate.NUMBER_DEFAULT);
```

### Listeneinstellungen konfigurieren: 
\Aktivieren Sie, dass die Liste in jedem Abschnitt neu gestartet wird.

```java
List list = doc.getLists().get(0);
list.isRestartAtEachSection(true);
```

### DocumentBuilder-Setup: 
Erstellen Sie einen DocumentBuilder, um Ihrem Dokument Inhalte hinzuzufügen.

```java
DocumentBuilder builder = new DocumentBuilder(doc);
builder.getListFormat().setList(list);
```

### Listenelemente hinzufügen: 
Verwenden Sie eine Schleife, um Listenelemente zu Ihrem Dokument hinzuzufügen. Nach dem 15. Element fügen wir einen Abschnittswechsel ein.

```java
for (int i = 1; i < 45; i++) {
    builder.writeln(MessageFormat.format("List Item {0}", i));
    if (i == 15)
        builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
}
```

### Speichern Sie Ihr Dokument: 
Speichern Sie das Dokument mit den gewünschten Optionen.

```java
OoxmlSaveOptions options = new OoxmlSaveOptions();
options.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL);
doc.save(outPath + "RestartListAtEachSection.docx", options);
```

Wenn Sie diese Schritte befolgen, können Sie Dokumente mit Listen erstellen, die in jedem Abschnitt neu beginnen und dabei eine klare und organisierte Inhaltsstruktur beibehalten.

## Angeben von Listenebenen

Mit Aspose.Words für Java können Sie Listenebenen angeben, was besonders nützlich ist, wenn Sie in Ihrem Dokument unterschiedliche Listenformate benötigen. Sehen wir uns an, wie das geht:

### Initialisieren Sie Ihr Dokument: 
Erstellen Sie ein neues Dokumentobjekt.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### Erstellen Sie eine nummerierte Liste: 
Wenden Sie eine nummerierte Listenvorlage aus Microsoft Word an.

```java
builder.getListFormat().setList(doc.getLists().add(ListTemplate.NUMBER_ARABIC_DOT));
```

### Listenebenen angeben: 
Durchlaufen Sie verschiedene Listenebenen und fügen Sie Inhalte hinzu.

```java
for (int i = 0; i < 9; i++) {
    builder.getListFormat().setListLevelNumber(i);
    builder.writeln("Level " + i);
}
```

### Erstellen Sie eine Aufzählungsliste: 
Lassen Sie uns nun eine Liste mit Aufzählungszeichen erstellen.

```java
builder.getListFormat().setList(doc.getLists().add(ListTemplate.BULLET_DIAMONDS));
```

### Geben Sie die Ebenen der Aufzählungsliste an: 
Geben Sie ähnlich wie bei der nummerierten Liste Ebenen an und fügen Sie Inhalte hinzu.

```java
for (int i = 0; i < 9; i++) {
    builder.getListFormat().setListLevelNumber(i);
    builder.writeln("Level " + i);
}
```

### Formatierung der Stoppliste: 
Um die Listenformatierung zu stoppen, setzen Sie die Liste auf Null.

```java
builder.getListFormat().setList(null);
```

### Speichern Sie Ihr Dokument: 
Speichern Sie das Dokument.

```java
builder.getDocument().save(outPath + "SpecifyListLevel.docx");
```

Wenn Sie diese Schritte befolgen, können Sie Dokumente mit benutzerdefinierten Listenebenen erstellen und so die Formatierung von Listen in Ihren Dokumenten steuern.

## Vollständiger Quellcode
```java
	string outPath = "Your Output Directory";
 public void restartListAtEachSection() throws Exception
    {
        Document doc = new Document();
        doc.getLists().add(ListTemplate.NUMBER_DEFAULT);
        List list = doc.getLists().get(0);
        list.isRestartAtEachSection(true);
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.getListFormat().setList(list);
        for (int i = 1; i < 45; i++)
        {
            builder.writeln(MessageFormat.format("List Item {0}", i));
            if (i == 15)
                builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
        }
        // IsRestartAtEachSection wird nur geschrieben, wenn die Compliance höher als OoxmlComplianceCore.Ecma376 ist.
        OoxmlSaveOptions options = new OoxmlSaveOptions(); { options.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL); }
        doc.save(outPath + "WorkingWithList.RestartListAtEachSection.docx", options);
    }
    @Test
    public void specifyListLevel() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Erstellen Sie eine nummerierte Liste basierend auf einer der Microsoft Word-Listenvorlagen.
        //und wenden Sie es auf den aktuellen Absatz des Document Builders an.
        builder.getListFormat().setList(doc.getLists().add(ListTemplate.NUMBER_ARABIC_DOT));
        // Es gibt neun Level in dieser Liste, probieren wir sie alle aus.
        for (int i = 0; i < 9; i++)
        {
            builder.getListFormat().setListLevelNumber(i);
            builder.writeln("Level " + i);
        }
        // Erstellen Sie eine Liste mit Aufzählungszeichen basierend auf einer der Microsoft Word-Listenvorlagen.
        //und wenden Sie es auf den aktuellen Absatz des Document Builders an.
        builder.getListFormat().setList(doc.getLists().add(ListTemplate.BULLET_DIAMONDS));
        for (int i = 0; i < 9; i++)
        {
            builder.getListFormat().setListLevelNumber(i);
            builder.writeln("Level " + i);
        }
        // Dies ist eine Möglichkeit, die Listenformatierung zu stoppen.
        builder.getListFormat().setList(null);
        builder.getDocument().save(outPath + "WorkingWithList.SpecifyListLevel.docx");
    }
    @Test
    public void restartListNumber() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Erstellen Sie eine Liste basierend auf einer Vorlage.
        List list1 = doc.getLists().add(ListTemplate.NUMBER_ARABIC_PARENTHESIS);
        list1.getListLevels().get(0).getFont().setColor(Color.RED);
        list1.getListLevels().get(0).setAlignment(ListLevelAlignment.RIGHT);
        builder.writeln("List 1 starts below:");
        builder.getListFormat().setList(list1);
        builder.writeln("Item 1");
        builder.writeln("Item 2");
        builder.getListFormat().removeNumbers();
        // Um die erste Liste wiederzuverwenden, müssen wir die Nummerierung neu starten, indem wir eine Kopie der ursprünglichen Listenformatierung erstellen.
        List list2 = doc.getLists().addCopy(list1);
        // Wir können die neue Liste beliebig ändern, einschließlich der Festlegung einer neuen Startnummer.
        list2.getListLevels().get(0).setStartAt(10);
        builder.writeln("List 2 starts below:");
        builder.getListFormat().setList(list2);
        builder.writeln("Item 1");
        builder.writeln("Item 2");
        builder.getListFormat().removeNumbers();
        builder.getDocument().save(outPath + "WorkingWithList.RestartListNumber.docx");
	}
```

## Abschluss

Glückwunsch! Sie haben gelernt, wie Sie effektiv mit Listen in Aspose.Words für Java arbeiten. Listen sind für die Organisation und Präsentation von Inhalten in Ihren Dokumenten von entscheidender Bedeutung. Unabhängig davon, ob Sie Listen in jedem Abschnitt neu starten oder Listenebenen angeben müssen, bietet Aspose.Words für Java die Tools, die Sie zum Erstellen professionell aussehender Dokumente benötigen.

Jetzt können Sie diese Funktionen getrost nutzen, um Ihre Dokumenterstellungs- und Formatierungsaufgaben zu verbessern. Wenn Sie Fragen haben oder weitere Hilfe benötigen, zögern Sie nicht, sich an die zu wenden[Aspose-Community-Forum](https://forum.aspose.com/) zur Unterstützung.

## FAQs

### Wie installiere ich Aspose.Words für Java?
 Sie können Aspose.Words für Java herunterladen von[Hier](https://releases.aspose.com/words/java/) und befolgen Sie die Installationsanweisungen in der Dokumentation.

### Kann ich das Nummerierungsformat von Listen anpassen?
Ja, Aspose.Words für Java bietet umfangreiche Optionen zum Anpassen von Listennummerierungsformaten. Einzelheiten finden Sie in der API-Dokumentation.

### Ist Aspose.Words für Java mit den neuesten Word-Dokumentstandards kompatibel?
Ja, Sie können Aspose.Words für Java so konfigurieren, dass es verschiedenen Word-Dokumentstandards entspricht, einschließlich ISO 29500.

### Kann ich mit Aspose.Words für Java komplexe Dokumente mit Tabellen und Bildern generieren?
Absolut! Aspose.Words für Java unterstützt erweiterte Dokumentformatierung, einschließlich Tabellen, Bilder und mehr. Beispiele finden Sie in der Dokumentation.

### Wo kann ich eine temporäre Lizenz für Aspose.Words für Java erhalten?
 Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).
