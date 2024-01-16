---
title: Inserir campo de formulário de caixa de seleção em documento do Word
linktitle: Inserir campo de formulário de caixa de seleção em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir campos de formulário de caixa de seleção em documentos do Word usando Aspose.Words for .NET. Guia passo a passo.
type: docs
weight: 10
url: /pt/net/add-content-using-documentbuilder/insert-check-box-form-field/
---
Neste tutorial abrangente, você aprenderá como inserir um campo de formulário de caixa de seleção em um documento do Word usando Aspose.Words for .NET. Orientaremos você durante o processo e forneceremos os trechos de código C# necessários. Ao final deste guia, você poderá adicionar campos de formulário de caixa de seleção com propriedades personalizáveis aos seus documentos.

## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
- Biblioteca Aspose.Words for .NET instalada em seu sistema.

## Etapa 1: Crie um novo documento e DocumentBuilder
Para começar, crie um novo documento usando a classe Document e inicialize um objeto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 2: inserir um campo de formulário de caixa de seleção
Em seguida, use o método InsertCheckBox da classe DocumentBuilder para inserir um campo de formulário de caixa de seleção. Forneça o nome, o estado verificado, o estado padrão e os parâmetros de tamanho como argumentos:

```csharp
builder.InsertCheckBox("CheckBox", true, true, 0);
```

## Etapa 3: salve o documento
Após inserir o campo do formulário check box, salve o documento em um arquivo utilizando o método Save da classe Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
```

### Exemplo de código-fonte para inserir campo de formulário de caixa de seleção usando Aspose.Words para .NET
Aqui está o código-fonte completo para inserir um campo de formulário de caixa de seleção usando Aspose.Words for .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertCheckBox("CheckBox", true, true, 0);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
```

Lembre-se de ajustar o código de acordo com seus requisitos específicos e aprimorá-lo com funcionalidades adicionais conforme necessário.

## Conclusão
Parabéns! Você aprendeu com sucesso como inserir um campo de formulário de caixa de seleção em um documento do Word usando Aspose.Words for .NET. Seguindo o guia passo a passo e utilizando o código-fonte fornecido, agora você pode aprimorar seus documentos com campos de formulário de caixa de seleção interativos.

### Perguntas frequentes

#### P: Posso inserir vários campos de formulário de caixa de seleção em um único documento?

R: Absolutamente! Você pode inserir quantos campos de formulário de caixa de seleção forem necessários em um documento do Word usando Aspose.Words for .NET. Basta repetir o processo de inserção para adicionar várias caixas de seleção interativas.

#### P: Posso definir o estado inicial (marcado ou desmarcado) do campo do formulário da caixa de seleção?

R: Sim, você tem controle total sobre o estado inicial do campo do formulário da caixa de seleção. Ao definir o parâmetro de estado verificado como verdadeiro ou falso, você pode definir se a caixa de seleção será inicialmente marcada ou desmarcada.

#### P: Os campos de formulário com caixa de seleção são compatíveis com outros formatos de arquivo, como PDF?

R: Sim, os campos de formulário de caixa de seleção inseridos usando Aspose.Words for .NET são compatíveis com vários formatos de arquivo, incluindo DOCX e PDF. Isso permite exportar seus documentos em diferentes formatos, mantendo as caixas de seleção interativas.

#### P: Posso ajustar o tamanho do campo do formulário da caixa de seleção?

R: Certamente! Você pode especificar o tamanho do campo do formulário da caixa de seleção usando o parâmetro size no método InsertCheckBox. Isso permite controlar as dimensões da caixa de seleção de acordo com suas preferências de design.

#### P: O Aspose.Words for .NET é adequado para aplicativos desktop e web?

R: Sim, Aspose.Words for .NET é uma biblioteca versátil adequada para aplicativos desktop e web. Esteja você construindo um aplicativo Windows ou um sistema baseado na Web, você pode integrar a biblioteca sem esforço.