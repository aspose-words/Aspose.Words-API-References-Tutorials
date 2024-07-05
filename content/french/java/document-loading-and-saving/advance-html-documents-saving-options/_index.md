---
title: Options avancées d’enregistrement des documents HTML avec Aspose.Words Java
linktitle: Enregistrer des documents HTML avec
second_title: API de traitement de documents Java Aspose.Words
description: Dans ce didacticiel, nous avons couvert diverses options avancées d'enregistrement de documents HTML avec Aspose.Words pour Java. Ces options vous permettent de créer du HTML de haute qualité
type: docs
weight: 16
url: /fr/java/document-loading-and-saving/advance-html-documents-saving-options/
---

Dans ce didacticiel, nous explorerons les options avancées d'enregistrement de documents HTML fournies par Aspose.Words pour Java. Aspose.Words est une API Java puissante pour travailler avec des documents Word et offre un large éventail de fonctionnalités pour la manipulation et la conversion de documents.

## 1. Introduction
Aspose.Words for Java vous permet de travailler avec des documents Word par programmation. Dans ce didacticiel, nous nous concentrerons sur les options avancées d'enregistrement de documents HTML, qui vous permettent de contrôler la façon dont les documents Word sont convertis en HTML.

## 2. Exporter les informations aller-retour
 Le`exportRoundtripInformation` La méthode vous permet d'exporter des documents Word au format HTML tout en préservant les informations aller-retour. Ces informations peuvent être utiles lorsque vous souhaitez reconvertir le HTML au format Word sans perdre les détails spécifiques au document.

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. Exporter les polices en Base64
 Avec le`exportFontsAsBase64` méthode, vous pouvez exporter les polices utilisées dans le document sous forme de données codées en Base64 dans le HTML. Cela garantit que la représentation HTML conserve les mêmes styles de police que le document Word d'origine.

```java
@Test
public void exportFontsAsBase64() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportFontsAsBase64(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
}
```

## 4. Exporter des ressources
 Le`exportResources` La méthode vous permet de spécifier le type de feuille de style CSS et d’exporter les ressources de police. Vous pouvez également définir un dossier de ressources et un alias pour les ressources dans le HTML.

```java
@Test
public void exportResources() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setExportFontResources(true);
    saveOptions.setResourceFolder("Your Directory Path" + "Resources");
    saveOptions.setResourceFolderAlias("http://exemple.com/resources");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
}
```

## 5. Convertir les métafichiers en EMF ou WMF
 Le`convertMetafilesToEmfOrWmf`La méthode vous permet de convertir les métafichiers du document au format EMF ou WMF, garantissant ainsi la compatibilité et un rendu fluide en HTML.

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    // Extrait de code non affiché par souci de concision.
}
```

## 6. Convertir les métafichiers en SVG
 Utilisez le`convertMetafilesToSvg` méthode pour convertir les métafichiers au format SVG. Ce format est idéal pour afficher des graphiques vectoriels dans des documents HTML.

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    // Extrait de code non affiché par souci de concision.
}
```

## 7. Ajouter un préfixe de nom de classe CSS
 Avec le`addCssClassNamePrefix` , vous pouvez ajouter un préfixe aux noms de classes CSS dans le code HTML exporté. Cela permet d'éviter les conflits avec les styles existants.

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

## 8. Exporter les URL CID pour les ressources MHTML
 Le`exportCidUrlsForMhtmlResources` La méthode est utilisée lors de l’enregistrement de documents au format MHTML. Il permet d'exporter des URL Content-ID pour les ressources.

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    // Extrait de code non affiché par souci de concision.
}
```

## 9. Résoudre les noms de polices
 Le`resolveFontNames` La méthode aide à résoudre les noms de polices lors de l’enregistrement de documents au format HTML, garantissant ainsi un rendu cohérent sur différentes plates-formes.

```java
@Test
public void resolveFontNames() throws Exception {
    // Extrait de code non affiché par souci de concision.
}
```

## 10. Exporter le champ du formulaire de saisie de texte sous forme de texte
 Le`exportTextInputFormFieldAsText` La méthode exporte les champs du formulaire sous forme de texte brut au format HTML, les rendant facilement lisibles et modifiables.

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    // Extrait de code non affiché par souci de concision.
}
```

## 11. Conclusion
Dans ce didacticiel, nous avons exploré les options avancées d'enregistrement de documents HTML fournies par Aspose.Words pour Java. Ces options vous donnent un contrôle précis sur le processus de conversion, vous permettant de créer des documents HTML qui ressemblent étroitement aux documents Word originaux.

## 12. FAQ
Voici quelques questions fréquemment posées sur l’utilisation des options d’enregistrement de documents Aspose.Words pour Java et HTML :

### Q1 : Comment puis-je reconvertir le HTML au format Word à l'aide d'Aspose.Words pour Java ?
 Pour reconvertir le HTML au format Word, vous pouvez utiliser l'API Aspose.Words`load` méthode pour charger le document HTML puis l'enregistrer au format Word.

### Q2 : Puis-je personnaliser les styles CSS lors de l'exportation au format HTML ?
 Oui, vous pouvez personnaliser les styles CSS en modifiant les feuilles de style utilisées dans le HTML ou en utilisant l'outil`addCssClassNamePrefix` méthode pour ajouter un préfixe aux noms de classes CSS.

### Q3 : Existe-t-il un moyen d'optimiser la sortie HTML pour l'affichage Web ?
Oui, vous pouvez optimiser la sortie HTML pour l'affichage Web en configurant des options telles que l'exportation des polices au format Base64 et la conversion des métafichiers en SVG.

### Q4 : Existe-t-il des limitations lors de la conversion de documents Word complexes en HTML ?
Bien qu'Aspose.Words pour Java offre de puissantes capacités de conversion, les documents Word complexes avec des mises en page complexes peuvent nécessiter un post-traitement supplémentaire pour obtenir la sortie HTML souhaitée.
