---
title: Salvando documentos como arquivos de texto em Aspose.Words para Java
linktitle: Salvando documentos como arquivos de texto
second_title: API de processamento de documentos Java Aspose.Words
description: Aprenda como salvar documentos como arquivos de texto em Aspose.Words for Java. Siga nosso guia passo a passo com exemplos de código Java.
type: docs
weight: 24
url: /pt/java/document-loading-and-saving/saving-documents-as-text-files/
---

## Introdução ao salvamento de documentos como arquivos de texto em Aspose.Words for Java

Neste tutorial, exploraremos como salvar documentos como arquivos de texto usando a biblioteca Aspose.Words para Java. Aspose.Words é uma API Java poderosa para trabalhar com documentos do Word e oferece várias opções para salvar documentos em diferentes formatos, incluindo texto simples. Abordaremos as etapas para conseguir isso e forneceremos exemplos de código Java ao longo do caminho.

## Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos em vigor:

- Java Development Kit (JDK) instalado em seu sistema.
-  Biblioteca Aspose.Words for Java integrada ao seu projeto. Você pode baixá-lo em[aqui](https://releases.aspose.com/words/java/).
- Conhecimento básico de programação Java.

## Etapa 1: crie um documento

Para salvar um documento como um arquivo de texto, primeiro precisamos criar um documento usando Aspose.Words. Aqui está um trecho de código Java simples para criar um documento com algum conteúdo:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.writeln("Hello world!");
builder.getParagraphFormat().setBidi(true);
builder.writeln("שלום עולם!");
builder.writeln("مرحبا بالعالم!");
```

Neste código, criamos um novo documento e adicionamos algum texto a ele, incluindo texto em diferentes idiomas.

## Etapa 2: definir opções para salvar texto

A seguir, precisamos definir as opções de salvamento de texto que especificam como o documento deve ser salvo como um arquivo de texto. Podemos definir várias configurações, como adicionar marcas bidi, recuo de lista e muito mais. Vejamos dois exemplos:

### Exemplo 1: Adicionando Marcas Bidi

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
doc.save("output.txt", saveOptions);
```

 Neste exemplo, criamos um`TxtSaveOptions` objeto e definir o`AddBidiMarks`propriedade para`true` para incluir marcas bidi na saída de texto.

### Exemplo 2: Usando caractere de tabulação para recuo de lista

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
doc.save("output.txt", saveOptions);
```

Aqui, configuramos as opções de salvamento para usar um caractere de tabulação para recuo da lista com contagem de 1.

## Etapa 3: salve o documento como texto

Agora que definimos as opções para salvar texto, podemos salvar o documento como um arquivo de texto. O código a seguir demonstra como fazer isso:

```java
doc.save("output.txt", saveOptions);
```

 Substituir`"output.txt"` com o caminho do arquivo desejado onde deseja salvar o arquivo de texto.

## Código-fonte completo para salvar documentos como arquivos de texto em Aspose.Words for Java

```java
    public void addBidiMarks() throws Exception
    {        
		Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("Hello world!");
        builder.getParagraphFormat().setBidi(true);
        builder.writeln("שלום עולם!");
        builder.writeln("مرحبا بالعالم!");
        TxtSaveOptions saveOptions = new TxtSaveOptions(); { saveOptions.setAddBidiMarks(true); }
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
    }
    @Test
    public void useTabCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Crie uma lista com três níveis de recuo.
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(1);
        saveOptions.getListIndentation().setCharacter('\t');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
    }
    @Test
    public void useSpaceCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Crie uma lista com três níveis de recuo.
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(3);
        saveOptions.getListIndentation().setCharacter(' ');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
	}
```

## Conclusão

Neste tutorial, aprendemos como salvar documentos como arquivos de texto em Aspose.Words for Java. Abordamos as etapas para criar um documento, definir opções para salvar texto e salvar o documento em formato de texto. Aspose.Words oferece ampla flexibilidade quando se trata de salvar documentos, permitindo adaptar a saída às suas necessidades específicas.

## Perguntas frequentes

### Como adiciono marcas bidi à saída de texto?

 Para adicionar marcas bidi à saída de texto, defina o`AddBidiMarks` propriedade de`TxtSaveOptions` para`true`. Por exemplo:

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
```

### Posso personalizar o caractere de recuo da lista?

 Sim, você pode personalizar o caractere de recuo da lista configurando o`ListIndentation` propriedade de`TxtSaveOptions`. Por exemplo, para usar um caractere de tabulação para recuo de lista, você pode fazer o seguinte:

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
```

### O Aspose.Words for Java é adequado para lidar com texto multilíngue?

Sim, Aspose.Words for Java é adequado para lidar com texto multilíngue. Suporta vários idiomas e codificações de caracteres, tornando-o uma escolha versátil para trabalhar com documentos em diferentes idiomas.

### Como posso acessar mais documentação e recursos para Aspose.Words for Java?

 Você pode encontrar documentação e recursos abrangentes para Aspose.Words for Java no site de documentação do Aspose:[Documentação Aspose.Words para Java](https://reference.aspose.com/words/java/).

### Onde posso baixar Aspose.Words para Java?

 Você pode baixar a biblioteca Aspose.Words para Java no site da Aspose:[Baixe Aspose.Words para Java](https://releases.aspose.com/words/java/).