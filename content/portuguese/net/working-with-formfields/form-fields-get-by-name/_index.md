---
title: Campos de formulário obtidos por nome
linktitle: Campos de formulário obtidos por nome
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como recuperar e modificar campos de formulário por nome em documentos do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-formfields/form-fields-get-by-name/
---

Neste tutorial passo a passo, iremos orientá-lo sobre como usar Aspose.Words for .NET para recuperar campos de formulário por nome de um documento do Word. Explicaremos o código-fonte C# fornecido e mostraremos como implementá-lo em seus próprios projetos.

 Para começar, certifique-se de ter o Aspose.Words for .NET instalado e configurado em seu ambiente de desenvolvimento. Caso ainda não tenha feito isso, baixe e instale a biblioteca em[Aspose.Releases]https://releases.aspose.com/words/net/.

## Etapa 1: inicializando o objeto Documento

 Primeiro, inicialize o`Document` objeto fornecendo o caminho para o documento de origem contendo campos de formulário:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");
```

## Etapa 2: recuperando campos do formulário

 A seguir, acesse o`FormFields` propriedade do`Range` objeto no documento para recuperar todos os campos do formulário:

```csharp
FormFieldCollection documentFormFields = doc.Range.FormFields;
```

Você pode recuperar campos de formulário por índice ou por nome. Neste exemplo, recuperamos um campo de formulário usando ambos os métodos:

```csharp
FormField formField1 = documentFormFields[3]; // Recuperando por índice
FormField formField2 = documentFormFields["Text2"]; // Recuperando por nome
```

## Etapa 3: Modificando as propriedades do campo do formulário

Depois de recuperar os campos do formulário, você poderá modificar suas propriedades conforme necessário. Neste exemplo, alteramos o tamanho da fonte de`formField1` para 20 e a cor da fonte de`formField2` para vermelho:

```csharp
formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;
```

## Etapa 4: salvando o documento

Por fim, salve o documento modificado:

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

É isso! Você recuperou com êxito os campos do formulário por nome e modificou suas propriedades em um documento do Word usando Aspose.Words for .NET.

### Exemplo de código-fonte para campos de formulário obtidos por nome usando Aspose.Words for .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection documentFormFields = doc.Range.FormFields;

FormField formField1 = documentFormFields[3];
FormField formField2 = documentFormFields["Text2"];

formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;

doc.Save(dataDir + "ModifiedFormFields.docx");
```

Sinta-se à vontade para usar este código em seus próprios projetos e modificá-lo de acordo com suas necessidades específicas.

### Perguntas frequentes

#### P: Como posso obter um campo de formulário por nome no Aspose.Words?

 R: Para obter um campo de formulário por nome no Aspose.Words, você pode usar o`Document.Range.FormFields[name]` método. Este método retorna o campo do formulário correspondente ao nome especificado.

#### P: E se o campo do formulário com o nome especificado não existir no documento?

 R: Se o campo do formulário com o nome especificado não existir no documento, o`Document.Range.FormFields[name]` método retornará`null`. Você pode verificar este resultado para lidar com casos em que o campo do formulário não foi encontrado.

#### P: Como posso modificar as propriedades de um campo de formulário encontrado?

R: Depois de obter um campo de formulário por nome, você poderá acessar suas propriedades individuais para editá-los. Por exemplo, você pode alterar o valor do campo, ativar ou desativar sua visibilidade ou modificar outras propriedades conforme necessário.

#### P: Posso obter vários campos de formulário com o mesmo nome em um documento?

 R: Sim, é possível ter vários campos de formulário com o mesmo nome em um documento. Neste caso, o`Document.Range.FormFields[name]` método retornará o primeiro campo de formulário encontrado com o nome especificado. Se você tiver vários campos de formulário com o mesmo nome, precisará levar isso em consideração ao manipular os campos.

#### P: Como posso iterar todos os campos do formulário em um documento?

 R: Para iterar todos os campos do formulário em um documento, você pode usar um`foreach` loop no`Document.Range.FormFields` coleção. Isso permitirá que você acesse cada campo do formulário individualmente e execute operações em cada um deles.