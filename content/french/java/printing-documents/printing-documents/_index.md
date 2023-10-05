---
title: Impression de documents dans Aspose.Words pour Java
linktitle: Impression de documents
second_title: API de traitement de documents Java Aspose.Words
description: Découvrez comment imprimer des documents à l'aide d'Aspose.Words pour Java. Guide étape par étape pour une impression transparente dans vos applications Java.
type: docs
weight: 10
url: /fr/java/printing-documents/printing-documents/
---

Si vous souhaitez imprimer des documents à l'aide d'Aspose.Words pour Java, vous êtes au bon endroit. Dans ce guide étape par étape, nous vous guiderons tout au long du processus d'impression de documents avec Aspose.Words for Java à l'aide du code source fourni.

## Introduction

L'impression de documents est une tâche courante dans de nombreuses applications. Aspose.Words for Java fournit une API puissante pour travailler avec des documents Word, y compris la possibilité de les imprimer. Dans ce didacticiel, nous vous guiderons étape par étape tout au long du processus d'impression d'un document Word.

## Configuration de votre environnement

Avant de plonger dans le code, assurez-vous que les conditions préalables suivantes sont en place :

- Kit de développement Java (JDK) installé
- Bibliothèque Aspose.Words pour Java téléchargée et ajoutée à votre projet

## Chargement du document

 Pour commencer, vous devrez charger le document Word que vous souhaitez imprimer. Remplacer`"Your Document Directory"` avec le chemin d'accès à votre document et`"Your Output Directory"` avec le répertoire de sortie souhaité.

```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Rendering.docx");
```

## Création d'un travail d'impression

Ensuite, nous allons créer un travail d'impression pour imprimer notre document chargé. L'extrait de code ci-dessous initialise un travail d'impression et définit les paramètres d'imprimante souhaités.

```java
// Créez un travail d'impression avec lequel imprimer notre document.
PrinterJob pj = PrinterJob.getPrinterJob();
//Initialisez un jeu d'attributs avec le nombre de pages du document.
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
// Transmettez les paramètres de l'imprimante ainsi que les autres paramètres au document à imprimer.
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
```

## Impression du document

Maintenant que nous avons configuré notre travail d'impression, il est temps d'imprimer le document. L'extrait de code suivant associe le document au travail d'impression et lance le processus d'impression.

```java
// Transmettez le document à imprimer à l'aide du travail d'impression.
pj.setPrintable(awPrintDoc);
pj.print();
```
## Code source complet
```java
string dataDir = "Your Document Directory";
Document doc = new Document(dataDir + "Rendering.docx");
// Créez un travail d'impression avec lequel imprimer notre document.
PrinterJob pj = PrinterJob.getPrinterJob();
//Initialisez un jeu d'attributs avec le nombre de pages du document.
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
// Transmettez les paramètres de l'imprimante ainsi que les autres paramètres au document à imprimer.
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
// Transmettez le document à imprimer à l'aide du travail d'impression.
pj.setPrintable(awPrintDoc);
pj.print();
```
Code source de MultipagePrintDocument
```java
class MultipagePrintDocument implements Printable
{
    private final Document mDocument;
    private final int mPagesPerSheet;
    private final boolean mPrintPageBorders;
    private final AttributeSet mAttributeSet;
    /// <résumé>
    /// Le constructeur de la classe PrintDocument personnalisée.
    // / </résumé>
    public MultipagePrintDocument(Document document, int pagesPerSheet, boolean printPageBorders,
                                  AttributeSet attributes) {
        if (document == null)
            throw new IllegalArgumentException("document");
        mDocument = document;
        mPagesPerSheet = pagesPerSheet;
        mPrintPageBorders = printPageBorders;
        mAttributeSet = attributes;
    }
    public int print(Graphics g, PageFormat pf, int page) {
        // Les indices de début et de fin de page tels que définis dans l'ensemble d'attributs.
        int[][] pageRanges = ((PageRanges) mAttributeSet.get(PageRanges.class)).getMembers();
        int fromPage = pageRanges[0][0] - 1;
        int toPage = pageRanges[0][1] - 1;
        Dimension thumbCount = getThumbCount(mPagesPerSheet, pf);
        // Calculez l'index de la page qui doit être rendu ensuite.
        int pagesOnCurrentSheet = (int) (page * (thumbCount.getWidth() * thumbCount.getHeight()));
        // Si l'index de la page est supérieur à la plage totale de pages, il n'y a rien
        // plus à rendre.
        if (pagesOnCurrentSheet > (toPage - fromPage))
            return Printable.NO_SUCH_PAGE;
        // Calculez la taille de chaque espace réservé de vignette en points.
        Point2D.Float thumbSize = new Point2D.Float((float) (pf.getImageableWidth() / thumbCount.getWidth()),
                (float) (pf.getImageableHeight() / thumbCount.getHeight()));
        // Calculez le numéro de la première page à imprimer sur cette feuille de papier.
        int startPage = pagesOnCurrentSheet + fromPage;
        // Sélectionnez le numéro de la dernière page à imprimer sur cette feuille de papier.
        int pageTo = Math.max(startPage + mPagesPerSheet - 1, toPage);
        //Parcourez les pages sélectionnées depuis la page actuelle stockée jusqu'à la page calculée.
        // dernière page.
        for (int pageIndex = startPage; pageIndex <= pageTo; pageIndex++) {
            // Calculez les indices de colonne et de ligne.
            int rowIdx = (int) Math.floor((pageIndex - startPage) / thumbCount.getWidth());
            int columnIdx = (int) Math.floor((pageIndex - startPage) % thumbCount.getWidth());
            // Définissez l'emplacement de la vignette en coordonnées mondiales (des points dans ce cas).
            float thumbLeft = columnIdx * thumbSize.x;
            float thumbTop = rowIdx * thumbSize.y;
            try {
                // Calculez les positions de départ gauche et supérieure.
                int leftPos = (int) (thumbLeft + pf.getImageableX());
                int topPos = (int) (thumbTop + pf.getImageableY());
                // Restituer la page du document à l'objet Graphics en utilisant les coordonnées calculées
                // et la taille de l'espace réservé à la vignette.
                // La valeur de retour utile est l'échelle à laquelle la page a été rendue.
                float scale = mDocument.renderToSize(pageIndex, (Graphics2D) g, leftPos, topPos, (int) thumbSize.x,
                        (int) thumbSize.y);
                // Dessinez les bordures de la page (la vignette de la page peut être plus petite que la vignette
                // taille de l'espace réservé).
                if (mPrintPageBorders) {
                    // Obtenez la taille réelle à 100 % de la page en points.
                    Point2D.Float pageSize = mDocument.getPageInfo(pageIndex).getSizeInPoints();
                    // Dessinez la bordure autour de la page mise à l'échelle en utilisant le facteur d'échelle connu.
                    g.setColor(Color.black);
                    g.drawRect(leftPos, topPos, (int) (pageSize.x * scale), (int) (pageSize.y * scale));
                    // Tracez la bordure autour de l’espace réservé à la vignette.
                    g.setColor(Color.red);
                    g.drawRect(leftPos, topPos, (int) thumbSize.x, (int) thumbSize.y);
                }
            } catch (Exception e) {
                // Si des erreurs se produisent lors du rendu, ne faites rien.
                // Cela dessinera une page blanche s'il y a des erreurs lors du rendu.
            }
        }
        return Printable.PAGE_EXISTS;
    }
    private Dimension getThumbCount(int pagesPerSheet, PageFormat pf) {
        Dimension size;
        // Définissez le nombre de colonnes et de lignes sur la feuille pour le
        //Papier orienté paysage.
        switch (pagesPerSheet) {
            case 16:
                size = new Dimension(4, 4);
                break;
            case 9:
                size = new Dimension(3, 3);
                break;
            case 8:
                size = new Dimension(4, 2);
                break;
            case 6:
                size = new Dimension(3, 2);
                break;
            case 4:
                size = new Dimension(2, 2);
                break;
            case 2:
                size = new Dimension(2, 1);
                break;
            default:
                size = new Dimension(1, 1);
                break;
        }
        // Inversez la largeur et la hauteur si le papier est en orientation Portrait.
        if ((pf.getWidth() - pf.getImageableX()) < (pf.getHeight() - pf.getImageableY()))
            return new Dimension((int) size.getHeight(), (int) size.getWidth());
        return size;
	}
}
```

## Conclusion

Toutes nos félicitations! Vous avez imprimé avec succès un document Word à l'aide d'Aspose.Words pour Java. Ce guide étape par étape devrait vous aider à intégrer de manière transparente l'impression de documents dans vos applications Java.

## FAQ

### Q1 : Puis-je imprimer des pages spécifiques d'un document à l'aide d'Aspose.Words pour Java ?

 Oui, vous pouvez spécifier la plage de pages lors de l'impression d'un document. Dans l'exemple de code, nous avons utilisé`attributes.add(new PageRanges(1, doc.getPageCount()))` pour imprimer toutes les pages. Vous pouvez ajuster la plage de pages selon vos besoins.

### Q2 : Aspose.Words pour Java est-il adapté à l’impression par lots ?

Absolument! Aspose.Words for Java est bien adapté aux tâches d'impression par lots. Vous pouvez parcourir une liste de documents et les imprimer un par un en utilisant un code similaire.

### Q3 : Comment puis-je gérer les erreurs d’impression ou les exceptions ?

Vous devez gérer toutes les exceptions potentielles pouvant survenir pendant le processus d’impression. Consultez la documentation Aspose.Words pour Java pour plus d'informations sur la gestion des exceptions.

### Q4 : Puis-je personnaliser davantage les paramètres d'impression ?

Oui, vous pouvez personnaliser les paramètres d'impression pour répondre à vos besoins spécifiques. Explorez la documentation Aspose.Words pour Java pour en savoir plus sur les options d'impression disponibles.

### Q5 : Où puis-je obtenir davantage d'aide et de support pour Aspose.Words pour Java ?

 Pour un soutien et une assistance supplémentaires, vous pouvez visiter le[Forum Aspose.Words pour Java](https://forum.aspose.com/).

---

Maintenant que vous avez appris avec succès comment imprimer des documents à l'aide d'Aspose.Words pour Java, vous pouvez commencer à implémenter cette fonctionnalité dans vos applications Java. Bon codage !