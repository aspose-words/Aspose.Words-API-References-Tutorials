---
title: Salvando documentos como formato ODT no Aspose.Words para Java
linktitle: Salvando documentos como formato ODT
second_title: API de processamento de documentos Java Aspose.Words
description: Aprenda a salvar documentos em formato ODT usando Aspose.Words para Java. Garanta compatibilidade com suítes de escritório de código aberto.
type: docs
weight: 19
url: /pt/java/document-loading-and-saving/saving-documents-as-odt-format/
---

## Introdução ao salvamento de documentos como formato ODT no Aspose.Words para Java

Neste artigo, exploraremos como salvar documentos como formato ODT (Open Document Text) usando Aspose.Words para Java. ODT é um formato de documento padrão aberto popular usado por vários pacotes de escritório, incluindo OpenOffice e LibreOffice. Ao salvar documentos no formato ODT, você pode garantir a compatibilidade com esses pacotes de software.

## Pré-requisitos

Antes de começar, certifique-se de que você tenha os seguintes pré-requisitos:

1. Ambiente de desenvolvimento Java: certifique-se de ter o Java Development Kit (JDK) instalado no seu sistema.

2.  Aspose.Words para Java: Baixe e instale a biblioteca Aspose.Words para Java. Você pode encontrar o link para download[aqui](https://releases.aspose.com/words/java/).

3. Documento de exemplo: tenha um documento de exemplo do Word (por exemplo, "Documento.docx") que você deseja converter para o formato ODT.

## Etapa 1: Carregue o documento

Primeiro, vamos carregar o documento do Word usando o Aspose.Words para Java:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
```

 Aqui,`"Your Directory Path"` deve apontar para o diretório onde seu documento está localizado.

## Etapa 2: especifique as opções de salvamento do ODT

Para salvar o documento como ODT, precisamos especificar as opções de salvamento do ODT. Além disso, podemos definir a unidade de medida para o documento. O Open Office usa centímetros, enquanto o MS Office usa polegadas. Vamos defini-lo como polegadas:

```java
OdtSaveOptions saveOptions = new OdtSaveOptions();
saveOptions.setMeasureUnit(OdtSaveMeasureUnit.INCHES);
```

## Etapa 3: Salve o documento

Agora, é hora de salvar o documento no formato ODT:

```java
doc.save("Your Directory Path" + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

 Aqui,`"Your Directory Path"` deve apontar para o diretório onde você deseja salvar o arquivo ODT convertido.

## Código fonte completo para salvar documentos como formato ODT em Aspose.Words para Java

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
// O Open Office usa centímetros ao especificar comprimentos, larguras e outras formatações mensuráveis
// e propriedades de conteúdo em documentos, enquanto o MS Office usa polegadas.
OdtSaveOptions saveOptions = new OdtSaveOptions(); { saveOptions.setMeasureUnit(OdtSaveMeasureUnit.INCHES); }
doc.save("Your Directory Path" + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## Conclusão

Neste artigo, aprendemos como salvar documentos como formato ODT usando Aspose.Words para Java. Isso pode ser especialmente útil quando você precisa garantir compatibilidade com suítes de escritório de código aberto, como OpenOffice e LibreOffice.

## Perguntas frequentes

### Como posso baixar o Aspose.Words para Java?

 Você pode baixar Aspose.Words para Java do site Aspose. Visite[este link](https://releases.aspose.com/words/java/) para acessar a página de download.

### Qual é o benefício de salvar documentos no formato ODT?

Salvar documentos no formato ODT garante a compatibilidade com pacotes de escritório de código aberto, como OpenOffice e LibreOffice, facilitando o acesso e a edição de seus documentos pelos usuários desses pacotes de software.

### Preciso especificar a unidade de medida ao salvar no formato ODT?

Sim, é uma boa prática especificar a unidade de medida. O Open Office usa centímetros por padrão, então defini-lo como polegadas garante uma formatação consistente.

### Posso converter vários documentos para o formato ODT em um processo em lote?

Sim, você pode automatizar a conversão de vários documentos para o formato ODT usando o Aspose.Words para Java iterando pelos seus arquivos de documentos e aplicando o processo de conversão.

### O Aspose.Words para Java é compatível com as versões mais recentes do Java?

Aspose.Words para Java é atualizado regularmente para suportar as versões mais recentes do Java, garantindo compatibilidade e melhorias de desempenho. Certifique-se de verificar os requisitos do sistema na documentação para obter as informações mais recentes.