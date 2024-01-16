---
title: Formato de regra horizontal em documento do Word
linktitle: Formato de regra horizontal em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como formatar regras horizontais em documentos do Word usando Aspose.Words for .NET. Guia passo a passo.
type: docs
weight: 10
url: /pt/net/add-content-using-documentbuilder/horizontal-rule-format/
---
Neste exemplo abrangente, você aprenderá como formatar uma regra horizontal em um documento do Word usando Aspose.Words for .NET. Orientaremos você durante o processo e forneceremos os trechos de código C# necessários. Ao final deste guia, você poderá personalizar o alinhamento, largura, altura, cor e outras propriedades de uma régua horizontal.

## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
- Biblioteca Aspose.Words for .NET instalada em seu sistema.

## Etapa 1: crie um DocumentBuilder e insira uma regra horizontal
Para começar, crie um objeto DocumentBuilder e use o método InsertHorizontalRule para inserir uma regra horizontal:

```csharp
DocumentBuilder builder = new DocumentBuilder();
Shape shape = builder.InsertHorizontalRule();
```

## Etapa 2: acesse o formato de regra horizontal
A seguir, acesse a propriedade HorizontalRuleFormat do objeto Shape para recuperar as opções de formatação:

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
```

## Etapa 3: personalize as opções de formatação
Agora você pode personalizar várias opções de formatação para a régua horizontal. Por exemplo, você pode ajustar o alinhamento, largura, altura, cor e sombreamento:

```csharp
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

## Etapa 4: salve o documento
Após formatar a régua horizontal, salve o documento em um arquivo usando o método Save do objeto Document:

```csharp
builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

### Exemplo de código-fonte para formato de regra horizontal usando Aspose.Words para .NET
Aqui está o código-fonte completo para formatar uma regra horizontal usando Aspose.Words for .NET:

```csharp
DocumentBuilder builder = new DocumentBuilder();

Shape shape = builder.InsertHorizontalRule();

HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;

builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

Lembre-se de ajustar o código de acordo com seus requisitos específicos e aprimorá-lo com funcionalidades adicionais conforme necessário.

## Conclusão
Parabéns! Você aprendeu com sucesso como formatar uma regra horizontal em um documento do Word usando Aspose.Words for .NET. Seguindo o guia passo a passo e utilizando o código-fonte fornecido, agora você pode personalizar a aparência das regras horizontais para aprimorar o layout visual do seu documento.

Experimente diferentes opções de formatação para obter o estilo e o efeito desejados para suas réguas horizontais.

### Perguntas frequentes sobre formato de regra horizontal em documentos do Word

#### P: Posso aplicar cores diferentes à régua horizontal?

R: Absolutamente! Com Aspose.Words for .NET, você pode personalizar facilmente a cor da régua horizontal definindo a propriedade Color com o valor de cor desejado. Isso permite que você combine a régua horizontal com o design geral do seu documento.

#### P: É possível ajustar a largura e a altura da régua horizontal?

R: Sim, você tem controle total sobre a largura e a altura da régua horizontal. Modificando as propriedades WidthPercent e Height, você pode obter as dimensões desejadas para a régua horizontal.

#### P: Posso alterar o alinhamento da régua horizontal no documento?

R: Certamente! Aspose.Words for .NET permite especificar o alinhamento da regra horizontal usando a propriedade Alignment. Você pode escolher entre várias opções como Centro, Esquerda, Direita e Justificado.

#### P: Posso aplicar sombreamento ou cor de fundo à régua horizontal?

R: Sim, você pode adicionar sombreamento ou cor de fundo à régua horizontal. Por padrão, a propriedade NoShade é definida como verdadeira, mas você pode defini-la como falsa e definir o sombreamento usando os métodos apropriados.

#### P: Posso inserir múltiplas réguas horizontais em um único documento?

R: Absolutamente! Você pode inserir várias regras horizontais em um documento do Word usando Aspose.Words for .NET. Simplesmente repita as etapas do tutorial conforme necessário para adicionar quantas réguas horizontais desejar.