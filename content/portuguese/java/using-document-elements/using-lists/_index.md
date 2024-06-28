---
title: Usando listas em Aspose.Words para Java
linktitle: Usando listas
second_title: API de processamento de documentos Java Aspose.Words
description: Aprenda a usar listas em Aspose.Words for Java com este tutorial passo a passo. Organize e formate seus documentos de forma eficaz.
type: docs
weight: 18
url: /pt/java/using-document-elements/using-lists/
---

Neste tutorial abrangente, exploraremos como usar listas de maneira eficaz no Aspose.Words for Java, uma API poderosa para trabalhar programaticamente com documentos do Microsoft Word. As listas são essenciais para estruturar e organizar o conteúdo dos seus documentos. Abordaremos dois aspectos principais do trabalho com listas: reiniciar listas em cada seção e especificar níveis de lista. Vamos mergulhar!

## Introdução ao Aspose.Words para Java

Antes de começarmos a trabalhar com listas, vamos nos familiarizar com Aspose.Words for Java. Esta API fornece aos desenvolvedores ferramentas para criar, modificar e manipular documentos do Word em um ambiente Java. É uma solução versátil para tarefas que vão desde a simples geração de documentos até formatação complexa e gerenciamento de conteúdo.

### Configurando seu ambiente

 Para começar, certifique-se de ter o Aspose.Words for Java instalado e configurado em seu ambiente de desenvolvimento. Você pode baixá-lo[aqui](https://releases.aspose.com/words/java/). 

## Reiniciando listas em cada seção

Em muitos cenários, pode ser necessário reiniciar as listas em cada seção do documento. Isso pode ser útil para criar documentos estruturados com múltiplas seções, como relatórios, manuais ou trabalhos acadêmicos.

Aqui está um guia passo a passo sobre como conseguir isso usando Aspose.Words for Java:

### Inicialize seu documento: 
Comece criando um novo objeto de documento.

```java
Document doc = new Document();
```

### Adicione uma lista numerada: 
Adicione uma lista numerada ao seu documento. Usaremos o estilo de numeração padrão.

```java
doc.getLists().add(ListTemplate.NUMBER_DEFAULT);
```

### Definir configurações de lista: 
\Ative a lista para reiniciar em cada seção.

```java
List list = doc.getLists().get(0);
list.isRestartAtEachSection(true);
```

### Configuração do DocumentBuilder: 
Crie um DocumentBuilder para adicionar conteúdo ao seu documento.

```java
DocumentBuilder builder = new DocumentBuilder(doc);
builder.getListFormat().setList(list);
```

### Adicionar itens da lista: 
Use um loop para adicionar itens de lista ao seu documento. Inseriremos uma quebra de seção após o 15º item.

```java
for (int i = 1; i < 45; i++) {
    builder.writeln(MessageFormat.format("List Item {0}", i));
    if (i == 15)
        builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
}
```

### Salve seu documento: 
Salve o documento com as opções desejadas.

```java
OoxmlSaveOptions options = new OoxmlSaveOptions();
options.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL);
doc.save(outPath + "RestartListAtEachSection.docx", options);
```

Seguindo estes passos, você pode criar documentos com listas que se reiniciam a cada seção, mantendo uma estrutura de conteúdo clara e organizada.

## Especificando níveis de lista

Aspose.Words for Java permite especificar níveis de lista, o que é particularmente útil quando você precisa de diferentes formatos de lista em seu documento. Vamos explorar como fazer isso:

### Inicialize seu documento: 
Crie um novo objeto de documento.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### Crie uma lista numerada: 
Aplique um modelo de lista numerada do Microsoft Word.

```java
builder.getListFormat().setList(doc.getLists().add(ListTemplate.NUMBER_ARABIC_DOT));
```

### Especifique os níveis da lista: 
Itere através de diferentes níveis de lista e adicione conteúdo.

```java
for (int i = 0; i < 9; i++) {
    builder.getListFormat().setListLevelNumber(i);
    builder.writeln("Level " + i);
}
```

### Crie uma lista com marcadores: 
Agora, vamos criar uma lista com marcadores.

```java
builder.getListFormat().setList(doc.getLists().add(ListTemplate.BULLET_DIAMONDS));
```

### Especifique os níveis da lista com marcadores: 
Semelhante à lista numerada, especifique níveis e adicione conteúdo.

```java
for (int i = 0; i < 9; i++) {
    builder.getListFormat().setListLevelNumber(i);
    builder.writeln("Level " + i);
}
```

### Parar a formatação da lista: 
Para interromper a formatação da lista, defina a lista como nula.

```java
builder.getListFormat().setList(null);
```

### Salve seu documento: 
Salve o documento.

```java
builder.getDocument().save(outPath + "SpecifyListLevel.docx");
```

Seguindo essas etapas, você pode criar documentos com níveis de lista personalizados, permitindo controlar a formatação das listas em seus documentos.

## Código fonte completo
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
        // IsRestartAtEachSection será gravado somente se a conformidade for superior a OoxmlComplianceCore.Ecma376.
        OoxmlSaveOptions options = new OoxmlSaveOptions(); { options.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL); }
        doc.save(outPath + "WorkingWithList.RestartListAtEachSection.docx", options);
    }
    @Test
    public void specifyListLevel() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Crie uma lista numerada com base em um dos modelos de lista do Microsoft Word.
        // aplique-o ao parágrafo atual do construtor de documentos.
        builder.getListFormat().setList(doc.getLists().add(ListTemplate.NUMBER_ARABIC_DOT));
        // Existem nove níveis nesta lista, vamos experimentar todos eles.
        for (int i = 0; i < 9; i++)
        {
            builder.getListFormat().setListLevelNumber(i);
            builder.writeln("Level " + i);
        }
        // Crie uma lista com marcadores com base em um dos modelos de lista do Microsoft Word.
        // aplique-o ao parágrafo atual do construtor de documentos.
        builder.getListFormat().setList(doc.getLists().add(ListTemplate.BULLET_DIAMONDS));
        for (int i = 0; i < 9; i++)
        {
            builder.getListFormat().setListLevelNumber(i);
            builder.writeln("Level " + i);
        }
        // Esta é uma forma de interromper a formatação da lista.
        builder.getListFormat().setList(null);
        builder.getDocument().save(outPath + "WorkingWithList.SpecifyListLevel.docx");
    }
    @Test
    public void restartListNumber() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Crie uma lista com base em um modelo.
        List list1 = doc.getLists().add(ListTemplate.NUMBER_ARABIC_PARENTHESIS);
        list1.getListLevels().get(0).getFont().setColor(Color.RED);
        list1.getListLevels().get(0).setAlignment(ListLevelAlignment.RIGHT);
        builder.writeln("List 1 starts below:");
        builder.getListFormat().setList(list1);
        builder.writeln("Item 1");
        builder.writeln("Item 2");
        builder.getListFormat().removeNumbers();
        // Para reutilizar a primeira lista, precisamos reiniciar a numeração criando uma cópia da formatação original da lista.
        List list2 = doc.getLists().addCopy(list1);
        // Podemos modificar a nova lista de qualquer forma, inclusive definindo um novo número inicial.
        list2.getListLevels().get(0).setStartAt(10);
        builder.writeln("List 2 starts below:");
        builder.getListFormat().setList(list2);
        builder.writeln("Item 1");
        builder.writeln("Item 2");
        builder.getListFormat().removeNumbers();
        builder.getDocument().save(outPath + "WorkingWithList.RestartListNumber.docx");
	}
```

## Conclusão

Parabéns! Você aprendeu como trabalhar com listas no Aspose.Words for Java de maneira eficaz. As listas são cruciais para organizar e apresentar o conteúdo dos seus documentos. Se você precisa reiniciar listas em cada seção ou especificar níveis de lista, Aspose.Words for Java fornece as ferramentas necessárias para criar documentos com aparência profissional.

Agora você pode usar esses recursos com segurança para aprimorar suas tarefas de geração e formatação de documentos. Se você tiver alguma dúvida ou precisar de mais assistência, não hesite em entrar em contato com o[Fórum da comunidade Aspose](https://forum.aspose.com/) para suporte.

## Perguntas frequentes

### Como faço para instalar o Aspose.Words para Java?
 Você pode baixar Aspose.Words para Java em[aqui](https://releases.aspose.com/words/java/) e siga as instruções de instalação na documentação.

### Posso personalizar o formato de numeração das listas?
Sim, Aspose.Words for Java oferece amplas opções para personalizar formatos de numeração de lista. Você pode consultar a documentação da API para obter detalhes.

### O Aspose.Words for Java é compatível com os padrões de documentos do Word mais recentes?
Sim, você pode configurar o Aspose.Words for Java para estar em conformidade com vários padrões de documentos do Word, incluindo ISO 29500.

### Posso gerar documentos complexos com tabelas e imagens usando Aspose.Words for Java?
Absolutamente! Aspose.Words for Java oferece suporte à formatação avançada de documentos, incluindo tabelas, imagens e muito mais. Verifique a documentação para exemplos.

### Onde posso obter uma licença temporária para Aspose.Words for Java?
 Você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
