---
title: Utilizzo degli elenchi in Aspose.Words per Java
linktitle: Utilizzo delle liste
second_title: API di elaborazione dei documenti Java Aspose.Words
description: Impara a utilizzare gli elenchi in Aspose.Words per Java con questo tutorial passo passo. Organizza e formatta i tuoi documenti in modo efficace.
type: docs
weight: 18
url: /it/java/using-document-elements/using-lists/
---

In questo tutorial completo, esploreremo come utilizzare in modo efficace gli elenchi in Aspose.Words per Java, una potente API per lavorare con documenti Microsoft Word a livello di codice. Gli elenchi sono essenziali per strutturare e organizzare i contenuti dei tuoi documenti. Tratteremo due aspetti chiave del lavoro con gli elenchi: riavviare gli elenchi in ogni sezione e specificare i livelli degli elenchi. Immergiamoci!

## Introduzione ad Aspose.Words per Java

Prima di iniziare a lavorare con gli elenchi, facciamo conoscenza con Aspose.Words per Java. Questa API fornisce agli sviluppatori gli strumenti per creare, modificare e manipolare documenti Word in un ambiente Java. È una soluzione versatile per attività che vanno dalla semplice generazione di documenti alla formattazione complessa e alla gestione dei contenuti.

### Configurazione dell'ambiente

 Per iniziare, assicurati di avere Aspose.Words per Java installato e configurato nel tuo ambiente di sviluppo. Puoi scaricarlo[Qui](https://releases.aspose.com/words/java/). 

## Elenchi di riavvio in ciascuna sezione

In molti scenari, potrebbe essere necessario riavviare gli elenchi in ogni sezione del documento. Ciò può essere utile per creare documenti strutturati con più sezioni, come report, manuali o documenti accademici.

Ecco una guida passo passo su come ottenere questo risultato utilizzando Aspose.Words per Java:

### Inizializza il tuo documento: 
Inizia creando un nuovo oggetto documento.

```java
Document doc = new Document();
```

### Aggiungi un elenco numerato: 
Aggiungi un elenco numerato al tuo documento. Utilizzeremo lo stile di numerazione predefinito.

```java
doc.getLists().add(ListTemplate.NUMBER_DEFAULT);
```

### Configura le impostazioni dell'elenco: 
\Abilita il riavvio dell'elenco da ogni sezione.

```java
List list = doc.getLists().get(0);
list.isRestartAtEachSection(true);
```

### Configurazione di DocumentBuilder: 
Crea un DocumentBuilder per aggiungere contenuto al tuo documento.

```java
DocumentBuilder builder = new DocumentBuilder(doc);
builder.getListFormat().setList(list);
```

### Aggiungi elementi all'elenco: 
Utilizza un ciclo per aggiungere elementi di elenco al tuo documento. Inseriremo un'interruzione di sezione dopo il quindicesimo elemento.

```java
for (int i = 1; i < 45; i++) {
    builder.writeln(MessageFormat.format("List Item {0}", i));
    if (i == 15)
        builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
}
```

### Salva il tuo documento: 
Salvare il documento con le opzioni desiderate.

```java
OoxmlSaveOptions options = new OoxmlSaveOptions();
options.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL);
doc.save(outPath + "RestartListAtEachSection.docx", options);
```

Seguendo questi passaggi, puoi creare documenti con elenchi che ricominciano da ogni sezione, mantenendo una struttura dei contenuti chiara e organizzata.

## Specifica dei livelli di elenco

Aspose.Words per Java ti consente di specificare i livelli di elenco, il che è particolarmente utile quando hai bisogno di formati di elenco diversi all'interno del tuo documento. Esploriamo come eseguire questa operazione:

### Inizializza il tuo documento: 
Crea un nuovo oggetto documento.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### Crea un elenco numerato: 
Applica un modello di elenco numerato da Microsoft Word.

```java
builder.getListFormat().setList(doc.getLists().add(ListTemplate.NUMBER_ARABIC_DOT));
```

### Specificare i livelli di elenco: 
Scorri diversi livelli di elenco e aggiungi contenuto.

```java
for (int i = 0; i < 9; i++) {
    builder.getListFormat().setListLevelNumber(i);
    builder.writeln("Level " + i);
}
```

### Crea un elenco puntato: 
Ora creiamo un elenco puntato.

```java
builder.getListFormat().setList(doc.getLists().add(ListTemplate.BULLET_DIAMONDS));
```

### Specificare i livelli dell'elenco puntato: 
Similmente all'elenco numerato, specifica i livelli e aggiungi contenuto.

```java
for (int i = 0; i < 9; i++) {
    builder.getListFormat().setListLevelNumber(i);
    builder.writeln("Level " + i);
}
```

### Formattazione dell'elenco delle fermate: 
Per interrompere la formattazione dell'elenco, impostare l'elenco su null.

```java
builder.getListFormat().setList(null);
```

### Salva il tuo documento: 
Salva il documento.

```java
builder.getDocument().save(outPath + "SpecifyListLevel.docx");
```

Seguendo questi passaggi, puoi creare documenti con livelli di elenco personalizzati, consentendoti di controllare la formattazione degli elenchi nei tuoi documenti.

## Codice sorgente completo
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
        // IsRestartAtEachSection verrà scritto solo se la conformità è superiore a OoxmlComplianceCore.Ecma376.
        OoxmlSaveOptions options = new OoxmlSaveOptions(); { options.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL); }
        doc.save(outPath + "WorkingWithList.RestartListAtEachSection.docx", options);
    }
    @Test
    public void specifyListLevel() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Crea un elenco numerato basato su uno dei modelli di elenco di Microsoft Word.
        // applicarlo al paragrafo corrente del generatore di documenti.
        builder.getListFormat().setList(doc.getLists().add(ListTemplate.NUMBER_ARABIC_DOT));
        // Ci sono nove livelli in questo elenco, proviamoli tutti.
        for (int i = 0; i < 9; i++)
        {
            builder.getListFormat().setListLevelNumber(i);
            builder.writeln("Level " + i);
        }
        // Crea un elenco puntato basato su uno dei modelli di elenco di Microsoft Word.
        // applicarlo al paragrafo corrente del generatore di documenti.
        builder.getListFormat().setList(doc.getLists().add(ListTemplate.BULLET_DIAMONDS));
        for (int i = 0; i < 9; i++)
        {
            builder.getListFormat().setListLevelNumber(i);
            builder.writeln("Level " + i);
        }
        // Questo è un modo per interrompere la formattazione dell'elenco.
        builder.getListFormat().setList(null);
        builder.getDocument().save(outPath + "WorkingWithList.SpecifyListLevel.docx");
    }
    @Test
    public void restartListNumber() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Crea un elenco basato su un modello.
        List list1 = doc.getLists().add(ListTemplate.NUMBER_ARABIC_PARENTHESIS);
        list1.getListLevels().get(0).getFont().setColor(Color.RED);
        list1.getListLevels().get(0).setAlignment(ListLevelAlignment.RIGHT);
        builder.writeln("List 1 starts below:");
        builder.getListFormat().setList(list1);
        builder.writeln("Item 1");
        builder.writeln("Item 2");
        builder.getListFormat().removeNumbers();
        // Per riutilizzare il primo elenco è necessario riavviare la numerazione creando una copia della formattazione dell'elenco originale.
        List list2 = doc.getLists().addCopy(list1);
        // Possiamo modificare il nuovo elenco in qualsiasi modo, anche impostando un nuovo numero di partenza.
        list2.getListLevels().get(0).setStartAt(10);
        builder.writeln("List 2 starts below:");
        builder.getListFormat().setList(list2);
        builder.writeln("Item 1");
        builder.writeln("Item 2");
        builder.getListFormat().removeNumbers();
        builder.getDocument().save(outPath + "WorkingWithList.RestartListNumber.docx");
	}
```

## Conclusione

Congratulazioni! Hai imparato come lavorare in modo efficace con gli elenchi in Aspose.Words per Java. Gli elenchi sono fondamentali per organizzare e presentare i contenuti nei tuoi documenti. Se è necessario riavviare gli elenchi in ciascuna sezione o specificare i livelli di elenco, Aspose.Words per Java fornisce gli strumenti necessari per creare documenti dall'aspetto professionale.

Ora puoi utilizzare con sicurezza queste funzionalità per migliorare le attività di generazione e formattazione dei documenti. Se hai domande o hai bisogno di ulteriore assistenza, non esitare a contattare il[Aspose forum della comunità](https://forum.aspose.com/) per supporto.

## Domande frequenti

### Come installo Aspose.Words per Java?
 È possibile scaricare Aspose.Words per Java da[Qui](https://releases.aspose.com/words/java/) e seguire le istruzioni di installazione nella documentazione.

### Posso personalizzare il formato di numerazione degli elenchi?
Sì, Aspose.Words per Java fornisce ampie opzioni per personalizzare i formati di numerazione degli elenchi. Puoi fare riferimento alla documentazione dell'API per i dettagli.

### Aspose.Words per Java è compatibile con gli ultimi standard di documenti Word?
Sì, puoi configurare Aspose.Words per Java in modo che sia conforme a vari standard di documenti Word, incluso ISO 29500.

### Posso generare documenti complessi con tabelle e immagini utilizzando Aspose.Words per Java?
Assolutamente! Aspose.Words per Java supporta la formattazione avanzata dei documenti, incluse tabelle, immagini e altro. Controllare la documentazione per esempi.

### Dove posso ottenere una licenza temporanea per Aspose.Words per Java?
 È possibile ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
