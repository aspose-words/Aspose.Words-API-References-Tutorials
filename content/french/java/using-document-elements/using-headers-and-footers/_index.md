---
title: Utilisation des en-têtes et des pieds de page dans Aspose.Words pour Java
linktitle: Utiliser les en-têtes et pieds de page
second_title: API de traitement de documents Java Aspose.Words
description: Découvrez étape par étape comment utiliser les en-têtes et les pieds de page dans Aspose.Words pour Java. Créez des documents professionnels sans effort.
type: docs
weight: 16
url: /fr/java/using-document-elements/using-headers-and-footers/
---

Dans ce guide complet, nous vous guiderons tout au long du processus d'utilisation des en-têtes et des pieds de page dans Aspose.Words pour Java. Les en-têtes et pieds de page sont des éléments essentiels dans le formatage des documents, et Aspose.Words fournit des outils puissants pour les créer et les personnaliser en fonction de vos besoins.

Examinons maintenant chacune de ces étapes en détail.

## 1. Introduction à Aspose.Words

Aspose.Words est une puissante API Java qui vous permet de créer, manipuler et restituer des documents Word par programme. Il fournit des fonctionnalités étendues pour le formatage des documents, notamment les en-têtes et les pieds de page.

## 2. Configuration de votre environnement Java

 Avant de commencer à utiliser Aspose.Words, assurez-vous que votre environnement de développement Java est correctement configuré. Vous pouvez trouver les instructions de configuration nécessaires sur la page de documentation Aspose.Words :[Aspose.Words Documentation Java](https://reference.aspose.com/words/java/).

## 3. Création d'un nouveau document

Pour travailler avec les en-têtes et les pieds de page, vous devez créer un nouveau document à l'aide d'Aspose.Words. Le code suivant montre comment procéder :

```java
// Code Java pour créer un nouveau document
string dataDir = "Your Document Directory";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 4. Comprendre la mise en page

 La mise en page est cruciale pour contrôler la mise en page de votre document. Vous pouvez spécifier diverses propriétés liées aux en-têtes et pieds de page à l'aide de l'option`PageSetup` classe. Par exemple:

```java
// Configuration des propriétés de la page
Section currentSection = builder.getCurrentSection();
PageSetup pageSetup = currentSection.getPageSetup();
pageSetup.setDifferentFirstPageHeaderFooter(true);
pageSetup.setHeaderDistance(20.0);
```

## 5. En-tête/pied de page de première page différents

Aspose.Words vous permet d'avoir différents en-têtes et pieds de page pour la première page de votre document. Utiliser`pageSetup.setDifferentFirstPageHeaderFooter(true);` pour activer cette fonctionnalité.

## 6. Travailler avec les en-têtes

### 6.1. Ajout de texte aux en-têtes

 Vous pouvez ajouter du texte aux en-têtes en utilisant le`DocumentBuilder`. Voici un exemple :

```java
// Ajout de texte à l'en-tête de la première page
builder.moveToHeaderFooter(HeaderFooterType.HEADER_FIRST);
builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
builder.getFont().setName("Arial");
builder.getFont().setBold(true);
builder.getFont().setSize(14.0);
builder.write("Aspose.Words Header/Footer Creation Primer - Title Page.");
```

### 6.2. Insérer des images dans les en-têtes

 Pour insérer des images dans les en-têtes, vous pouvez utiliser le`insertImage` méthode. Voici un exemple :

```java
// Insérer une image dans l'en-tête
builder.insertImage(getImagesDir() + "Graphics Interchange Format.gif", RelativeHorizontalPosition.PAGE, 10.0,
    RelativeVerticalPosition.PAGE, 10.0, 50.0, 50.0, WrapType.THROUGH);
```

### 6.3. Personnalisation des styles d'en-tête

Vous pouvez personnaliser les styles d'en-tête en définissant diverses propriétés telles que la police, l'alignement, etc., comme indiqué dans les exemples ci-dessus.

## 7. Travailler avec des pieds de page

### 7.1. Ajout de texte aux pieds de page

 Semblable aux en-têtes, vous pouvez ajouter du texte aux pieds de page à l'aide de l'option`DocumentBuilder`. Voici un exemple :

```java
// Ajout de texte au pied de page principal
builder.moveToHeaderFooter(HeaderFooterType.FOOTER_PRIMARY);
// Insérez du texte et des champs selon vos besoins
```

### 7.2. Insérer des images dans les pieds de page

 Pour insérer des images dans les pieds de page, utilisez le`insertImage` méthode, tout comme dans les en-têtes.

### 7.3. Personnalisation des styles de pied de page

 Personnalisez les styles de pied de page à l'aide de l'outil`DocumentBuilder`similaire à la personnalisation des en-têtes.

## 8. Numérotation des pages

 Vous pouvez inclure des numéros de page dans vos en-têtes et pieds de page en utilisant des champs tels que`PAGE`et`NUMPAGES`. Ces champs sont automatiquement mis à jour lorsque vous ajoutez ou supprimez des pages.

## 9. Informations sur les droits d'auteur dans les pieds de page

Pour ajouter des informations de copyright au pied de page de votre document, vous pouvez utiliser un tableau avec deux cellules, en alignant l'une à gauche et l'autre à droite, comme indiqué dans l'extrait de code.

## 10. Travailler avec plusieurs sections

Aspose.Words vous permet de travailler avec plusieurs sections dans un document. Vous pouvez définir différentes mises en page et en-têtes/pieds de page pour chaque section.

## 11. Orientation paysage

Vous pouvez modifier l'orientation de sections spécifiques en mode paysage si nécessaire.

## 12. Copie des en-têtes/pieds de page des sections précédentes

La copie des en-têtes et des pieds de page des sections précédentes peut permettre de gagner du temps lors de la création de documents complexes.

## 13. Sauvegarde de votre document

Après avoir créé et personnalisé votre document, n'oubliez pas de l'enregistrer à l'aide du`doc.save()` méthode.

## Code source complet
```java
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        Section currentSection = builder.getCurrentSection();
        PageSetup pageSetup = currentSection.getPageSetup();
        // Spécifiez si nous voulons que les en-têtes/pieds de page de la première page soient différents des autres pages.
        // Vous pouvez également utiliser la propriété PageSetup.OddAndEvenPagesHeaderFooter pour spécifier
        // différents en-têtes/pieds de page pour les pages paires et impaires.
        pageSetup.setDifferentFirstPageHeaderFooter(true);
        pageSetup.setHeaderDistance(20.0);
        builder.moveToHeaderFooter(HeaderFooterType.HEADER_FIRST);
        builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
        builder.getFont().setName("Arial");
        builder.getFont().setBold(true);
        builder.getFont().setSize(14.0);
        builder.write("Aspose.Words Header/Footer Creation Primer - Title Page.");
        pageSetup.setHeaderDistance(20.0);
        builder.moveToHeaderFooter(HeaderFooterType.HEADER_PRIMARY);
        // Insérez une image positionnée dans le coin supérieur/gauche de l’en-tête.
        // La distance depuis les bords supérieur/gauche de la page est définie sur 10 points.
        builder.insertImage(getImagesDir() + "Graphics Interchange Format.gif", RelativeHorizontalPosition.PAGE, 10.0,
            RelativeVerticalPosition.PAGE, 10.0, 50.0, 50.0, WrapType.THROUGH);
        builder.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
        builder.write("Aspose.Words Header/Footer Creation Primer.");
        builder.moveToHeaderFooter(HeaderFooterType.FOOTER_PRIMARY);
        // Nous utilisons un tableau avec deux cellules pour constituer une partie du texte sur la ligne (avec numérotation des pages).
        // A aligner à gauche, et l'autre partie du texte (avec copyright) à droite.
        builder.startTable();
        builder.getCellFormat().clearFormatting();
        builder.insertCell();
        builder.getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 / 3));
        // Il utilise les champs PAGE et NUMPAGES pour calculer automatiquement le numéro de page actuel et le nombre de pages.
        builder.write("Page ");
        builder.insertField("PAGE", "");
        builder.write(" of ");
        builder.insertField("NUMPAGES", "");
        builder.getCurrentParagraph().getParagraphFormat().setAlignment(ParagraphAlignment.LEFT);
        builder.insertCell();
        builder.getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 * 2 / 3));
        builder.write("(C) 2001 Aspose Pty Ltd. All rights reserved.");
        builder.getCurrentParagraph().getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
        builder.endRow();
        builder.endTable();
        builder.moveToDocumentEnd();
        // Faites un saut de page pour créer une deuxième page sur laquelle les principaux en-têtes/pieds de page seront visibles.
        builder.insertBreak(BreakType.PAGE_BREAK);
        builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
        currentSection = builder.getCurrentSection();
        pageSetup = currentSection.getPageSetup();
        pageSetup.setOrientation(Orientation.LANDSCAPE);
        // Cette section n'a pas besoin d'un en-tête/pied de page de première page différent, nous n'avons besoin que d'une seule page de titre dans le document,
        //et l'en-tête/pied de page de cette page a déjà été défini dans la section précédente.
        pageSetup.setDifferentFirstPageHeaderFooter(false);
        // Cette section affiche les en-têtes/pieds de page de la section précédente
        // par défaut, appelez currentSection.HeadersFooters.LinkToPrevious(false) pour annuler cette largeur de page
        // est différent pour la nouvelle section et nous devons donc définir différentes largeurs de cellules pour un tableau de pied de page.
        currentSection.getHeadersFooters().linkToPrevious(false);
        // Si nous voulons utiliser l’ensemble d’en-tête/pied de page déjà existant pour cette section.
        // Mais avec quelques modifications mineures, il peut être judicieux de copier les en-têtes/pieds de page
        // de la section précédente et appliquez les modifications nécessaires là où nous le souhaitons.
        copyHeadersFootersFromPreviousSection(currentSection);
        HeaderFooter primaryFooter = currentSection.getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);
        Row row = primaryFooter.getTables().get(0).getFirstRow();
        row.getFirstCell().getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 / 3));
        row.getLastCell().getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 * 2 / 3));
        doc.save("Your Directory Path" + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```	
Code source de la méthode copyHeadersFootersFromPreviousSection
```java
    /// <résumé>
    /// Clone et copie les en-têtes/pieds de page de la section précédente vers la section spécifiée.
    /// </résumé>
    private void copyHeadersFootersFromPreviousSection(Section section)
    {
        Section previousSection = (Section)section.getPreviousSibling();
        if (previousSection == null)
            return;
        section.getHeadersFooters().clear();
        for (HeaderFooter headerFooter : (Iterable<HeaderFooter>) previousSection.getHeadersFooters())
            section.getHeadersFooters().add(headerFooter.deepClone(true));
	}
```

## Conclusion

Dans ce didacticiel, nous avons couvert les bases de l'utilisation des en-têtes et des pieds de page dans Aspose.Words pour Java. Vous avez appris à créer, personnaliser et styliser des en-têtes et des pieds de page, ainsi qu'à d'autres techniques essentielles de formatage de documents.

 Pour plus de détails et de fonctionnalités avancées, reportez-vous au[Aspose.Words Documentation Java](https://reference.aspose.com/words/java/).

## FAQ

### 1. Comment puis-je ajouter des numéros de page au pied de page de mon document ?
 Vous pouvez ajouter des numéros de page en insérant le`PAGE` champ dans le pied de page en utilisant Aspose.Words.

### 2. Aspose.Words est-il compatible avec les environnements de développement Java ?
Oui, Aspose.Words prend en charge le développement Java. Assurez-vous d’avoir mis en place la configuration nécessaire.

### 3. Puis-je personnaliser la police et le style des en-têtes et des pieds de page ?
Absolument, vous pouvez personnaliser les polices, l'alignement et d'autres styles pour rendre vos en-têtes et pieds de page visuellement attrayants.

### 4. Est-il possible d'avoir des en-têtes différents pour les pages paires et impaires ?
 Oui, vous pouvez utiliser`PageSetup.OddAndEvenPagesHeaderFooter` pour spécifier des en-têtes différents pour les pages paires et impaires.

### 5. Comment démarrer avec Aspose.Words pour Java ?
 Pour commencer, visitez le[Aspose.Words Documentation Java](https://reference.aspose.com/words/java/) pour obtenir des conseils complets sur l’utilisation de l’API.