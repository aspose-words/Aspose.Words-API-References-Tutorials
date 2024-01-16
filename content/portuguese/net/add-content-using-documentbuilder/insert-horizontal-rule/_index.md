---
title: Inserir regra horizontal em documento do Word
linktitle: Inserir regra horizontal em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir regras horizontais em documentos do Word usando Aspose.Words for .NET. Guia passo a passo.
type: docs
weight: 10
url: /pt/net/add-content-using-documentbuilder/insert-horizontal-rule/
---
Neste exemplo abrangente, você aprenderá como inserir uma regra horizontal em um documento do Word usando Aspose.Words for .NET. Orientaremos você durante o processo e forneceremos os trechos de código C# necessários. Ao final deste guia, você poderá adicionar regras horizontais aos seus documentos para separação e organização visual.

## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
- Biblioteca Aspose.Words for .NET instalada em seu sistema.

## Etapa 1: Crie um novo documento e DocumentBuilder
Para começar, crie um novo documento usando a classe Document e inicialize um objeto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 2: inserir uma regra horizontal
A seguir, use o método Writeln da classe DocumentBuilder para adicionar um texto descritivo e depois inserir uma regra horizontal:

```csharp
builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();
```

## Etapa 3: salve o documento
Após inserir a régua horizontal, salve o documento em um arquivo utilizando o método Save da classe Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

### Exemplo de código-fonte para inserir regra horizontal usando Aspose.Words para .NET
Aqui está o código-fonte completo para inserir uma regra horizontal usando Aspose.Words for .NET:
As regras horizontais são úteis para vários cenários, como dividir seções, criar quebras visuais ou destacar informações importantes.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

Lembre-se de ajustar o código de acordo com seus requisitos específicos e aprimorá-lo com funcionalidades adicionais conforme necessário.

## Conclusão
Parabéns! Você aprendeu com sucesso como inserir uma regra horizontal em um documento do Word usando Aspose.Words for .NET. Seguindo o guia passo a passo e utilizando o código-fonte fornecido, agora você pode separar e organizar visualmente seus documentos usando regras horizontais.

### Perguntas frequentes para inserir regra horizontal em documento do Word

#### P: Posso personalizar a aparência da régua horizontal?

R: Sim, absolutamente! Aspose.Words for .NET fornece várias propriedades para personalizar a aparência da regra horizontal. Você pode ajustar largura, altura, alinhamento, cor e sombreamento para combinar com a estética do seu documento.

#### P: Posso adicionar várias regras horizontais em um único documento?

R: Certamente! Você pode inserir quantas regras horizontais forem necessárias em um documento do Word usando Aspose.Words for .NET. Basta repetir o processo de inserção para adicionar múltiplas quebras visuais ou divisores de seção.

#### P: As regras horizontais são compatíveis com outros formatos de arquivo, como PDF?

R: Sim, as regras horizontais inseridas usando Aspose.Words for .NET são compatíveis com vários formatos de arquivo, incluindo DOCX e PDF. Isso significa que você pode exportar seus documentos em diferentes formatos, mantendo as regras horizontais.

#### P: Posso inserir programaticamente uma régua horizontal em posições específicas do documento?

R: Absolutamente! Aspose.Words for .NET permite posicionar a regra horizontal em locais específicos do documento de forma programática. Você pode controlar seu posicionamento com base no conteúdo e na estrutura do seu documento.

#### P: O Aspose.Words for .NET é adequado para aplicativos desktop e web?

R: Sim, o Aspose.Words for .NET é versátil e pode ser usado em aplicativos desktop e web. Esteja você construindo um aplicativo Windows ou um sistema baseado na Web, você pode integrar a biblioteca sem esforço.