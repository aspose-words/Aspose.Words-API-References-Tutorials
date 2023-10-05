---
title: Erweiterte Optionen zum Speichern von HTML-Dokumenten mit Aspose.Words Java
linktitle: Speichern von HTML-Dokumenten mit
second_title: Aspose.Words Java-Dokumentverarbeitungs-API
description: In diesem Tutorial haben wir verschiedene erweiterte Optionen zum Speichern von HTML-Dokumenten mit Aspose.Words für Java behandelt. Mit diesen Optionen können Sie hochwertiges HTML erstellen
type: docs
weight: 16
url: /de/java/document-loading-and-saving/advance-html-documents-saving-options/
---

In diesem Tutorial werden wir die erweiterten Optionen zum Speichern von HTML-Dokumenten erkunden, die Aspose.Words für Java bietet. Aspose.Words ist eine leistungsstarke Java-API für die Arbeit mit Word-Dokumenten und bietet eine breite Palette von Funktionen zur Dokumentbearbeitung und -konvertierung.

## 1. Einleitung
Mit Aspose.Words für Java können Sie programmgesteuert mit Word-Dokumenten arbeiten. In diesem Tutorial konzentrieren wir uns auf erweiterte Optionen zum Speichern von HTML-Dokumenten, mit denen Sie steuern können, wie Word-Dokumente in HTML konvertiert werden.

## 2. Roundtrip-Informationen exportieren
 Der`exportRoundtripInformation` Mit dieser Methode können Sie Word-Dokumente in HTML exportieren und dabei die Roundtrip-Informationen beibehalten. Diese Informationen können nützlich sein, wenn Sie HTML zurück in das Word-Format konvertieren möchten, ohne dokumentspezifische Details zu verlieren.

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. Schriftarten als Base64 exportieren
 Mit dem`exportFontsAsBase64` Mit dieser Methode können Sie im Dokument verwendete Schriftarten als Base64-codierte Daten in den HTML-Code exportieren. Dadurch wird sichergestellt, dass die HTML-Darstellung dieselben Schriftarten wie das ursprüngliche Word-Dokument beibehält.

```java
@Test
public void exportFontsAsBase64() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportFontsAsBase64(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
}
```

## 4. Ressourcen exportieren
 Der`exportResources` Mit der Methode können Sie den Typ des CSS-Stylesheets angeben und Schriftartressourcen exportieren. Sie können im HTML auch einen Ressourcenordner und einen Alias für Ressourcen festlegen.

```java
@Test
public void exportResources() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setExportFontResources(true);
    saveOptions.setResourceFolder("Your Directory Path" + "Resources");
    saveOptions.setResourceFolderAlias("http://example.com/resources");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
}
```

## 5. Konvertieren Sie Metadateien in EMF oder WMF
 Der`convertMetafilesToEmfOrWmf`Mit der Methode können Sie Metadateien im Dokument entweder in das EMF- oder WMF-Format konvertieren und so Kompatibilität und reibungslose Darstellung in HTML gewährleisten.

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    // Der Kürze halber wird der Codeausschnitt nicht angezeigt.
}
```

## 6. Konvertieren Sie Metadateien in SVG
 Benutzen Sie die`convertMetafilesToSvg` Methode zum Konvertieren von Metadateien in das SVG-Format. Dieses Format eignet sich ideal für die Darstellung von Vektorgrafiken in HTML-Dokumenten.

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    // Der Kürze halber wird der Codeausschnitt nicht angezeigt.
}
```

## 7. Fügen Sie das Präfix für den CSS-Klassennamen hinzu
 Mit dem`addCssClassNamePrefix` Mit der Methode können Sie CSS-Klassennamen im exportierten HTML ein Präfix hinzufügen. Dies trägt dazu bei, Konflikte mit vorhandenen Stilen zu vermeiden.

```java
@Test
public void addCssClassNamePrefix() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setCssClassNamePrefix("pfx_");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
}
```

## 8. Exportieren Sie CID-URLs für MHTML-Ressourcen
 Der`exportCidUrlsForMhtmlResources` Die Methode wird beim Speichern von Dokumenten im MHTML-Format verwendet. Es ermöglicht den Export von Content-ID-URLs für Ressourcen.

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    // Der Kürze halber wird der Codeausschnitt nicht angezeigt.
}
```

## 9. Schriftartnamen auflösen
 Der`resolveFontNames` Die Methode hilft bei der Auflösung von Schriftartnamen beim Speichern von Dokumenten im HTML-Format und sorgt so für eine konsistente Darstellung auf verschiedenen Plattformen.

```java
@Test
public void resolveFontNames() throws Exception {
    // Der Kürze halber wird der Codeausschnitt nicht angezeigt.
}
```

## 10. Texteingabeformularfeld als Text exportieren
 Der`exportTextInputFormFieldAsText` Die Methode exportiert Formularfelder als einfachen Text in den HTML-Code, sodass sie leicht lesbar und bearbeitbar sind.

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    // Der Kürze halber wird der Codeausschnitt nicht angezeigt.
}
```

## 11. Fazit
In diesem Tutorial haben wir die erweiterten Optionen zum Speichern von HTML-Dokumenten untersucht, die Aspose.Words für Java bietet. Mit diesen Optionen haben Sie eine detaillierte Kontrolle über den Konvertierungsprozess und können so HTML-Dokumente erstellen, die den Original-Word-Dokumenten sehr ähnlich sind.

## 12. FAQs
Hier sind einige häufig gestellte Fragen zur Arbeit mit Aspose.Words für Java und den Optionen zum Speichern von HTML-Dokumenten:

### F1: Wie kann ich HTML mit Aspose.Words für Java zurück in das Word-Format konvertieren?
 Um HTML zurück in das Word-Format zu konvertieren, können Sie die Aspose.Words-APIs verwenden`load` Methode zum Laden des HTML-Dokuments und zum anschließenden Speichern im Word-Format.

### F2: Kann ich die CSS-Stile beim Exportieren nach HTML anpassen?
 Ja, Sie können CSS-Stile anpassen, indem Sie die im HTML verwendeten Stylesheets ändern oder indem Sie die verwenden`addCssClassNamePrefix` Methode zum Hinzufügen eines Präfixes zu CSS-Klassennamen.

### F3: Gibt es eine Möglichkeit, die HTML-Ausgabe für die Webanzeige zu optimieren?
Ja, Sie können die HTML-Ausgabe für die Webanzeige optimieren, indem Sie Optionen wie den Export von Schriftarten als Base64 und die Konvertierung von Metadateien in SVG konfigurieren.

### F4: Gibt es Einschränkungen beim Konvertieren komplexer Word-Dokumente in HTML?
Während Aspose.Words für Java leistungsstarke Konvertierungsfunktionen bietet, erfordern komplexe Word-Dokumente mit komplizierten Layouts möglicherweise eine zusätzliche Nachbearbeitung, um die gewünschte HTML-Ausgabe zu erzielen.
