---
title: Retorno de chamada de hifenização
linktitle: Retorno de chamada de hifenização
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como usar o retorno de chamada de hifenização em Aspose.Words for .NET para lidar com a hifenização de palavras.
type: docs
weight: 10
url: /pt/net/working-with-hyphenation/hyphenation-callback/
---

Neste tutorial passo a passo, mostraremos como usar o recurso de retorno de chamada de hifenização no Aspose.Words for .NET. Explicaremos o código-fonte C# fornecido e mostraremos como implementá-lo em seus próprios projetos.

 Para começar, certifique-se de ter o Aspose.Words for .NET instalado e configurado em seu ambiente de desenvolvimento. Se ainda não o fez, baixe e instale a biblioteca em[Aspose.Releases]https://releases.aspose.com/words/net/.

## Etapa 1: salvar lembrete de hifenização

 Primeiro, registraremos o retorno de chamada de hifenização usando um comando personalizado`CustomHyphenationCallback` aula. Isso nos permitirá lidar com a hifenização de palavras de acordo com nossas próprias regras:

```csharp
Hyphenation.Callback = new CustomHyphenationCallback();
```

 Certifique-se de ter implementado o`CustomHyphenationCallback` aula de acordo com suas necessidades específicas.

## Etapa 2: Carregar o documento e aplicar a hifenização

Em seguida, carregue seu documento do diretório especificado e hifenize as palavras usando Aspose.Words:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "German text.docx");
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

## Etapa 3: Tratamento de erros de dicionário ausentes

Caso falte um dicionário de hifenização, capturaremos a exceção correspondente e exibiremos uma mensagem de erro:

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
     Console.WriteLine(e.Message);
}
```

## Etapa 4: limpar e desativar o lembrete de hifenização

Por fim, para limpeza e para desligar o lembrete de hifenização, execute as seguintes etapas:

```csharp
finally
{
     Hyphenation. Callback = null;
}
```

Isso limpa e desativa o lembrete de hifenização após concluir o processamento.

Então ! Você usou com sucesso o retorno de chamada de hifenização em Aspose.Words for .NET.

### Exemplo de código-fonte para retorno de chamada de hifenização com Aspose.Words para .NET

```csharp
try
{
	 // Registrar retorno de chamada de hifenização.
	 Hyphenation.Callback = new CustomHyphenationCallback();
	 string dataDir = "YOUR DOCUMENT DIRECTORY";
	 Document document = new Document(dataDir + "German text.docx");
	 document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
}
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
	 Console.WriteLine(e.Message);
}
finally
{
	 Hyphenation. Callback = null;
}

```

Sinta-se à vontade para usar este código em seus próprios projetos e modificá-lo para atender às suas necessidades específicas.

### Perguntas frequentes

#### P: O que é um lembrete de silabização em Aspose.Words?

R: Um lembrete de silabização no Aspose.Words é um recurso que permite personalizar como as palavras são silabizadas em seus documentos. Ao usar um lembrete de silabização, você pode especificar regras personalizadas para silabização de palavras, o que pode ser útil para idiomas específicos ou cenários específicos onde a silabização padrão não produz os resultados desejados.

#### P: Como definir um lembrete de silabização em Aspose.Words?

 R: Para definir um retorno de chamada de hifenização em Aspose.Words, você precisa criar uma classe que implemente o`HyphenationCallback` interface e implementar o`HandleWord()` método. Este método será chamado para cada palavra encontrada durante a silabização. Você pode aplicar regras de silabização personalizadas a ele e retornar a palavra silabizada. Então você pode vincular seu retorno de chamada de hifenização usando o`Document.HyphenationCallback` propriedade do seu documento.

#### P: Qual é a vantagem de usar um lembrete de silabização no Aspose.Words?

R: A vantagem de usar um lembrete de silabização no Aspose.Words é a capacidade de personalizar como as palavras são silabizadas em seus documentos. Isso lhe dá mais controle sobre a silabização, especialmente para idiomas ou cenários específicos onde a silabização padrão não fornece os resultados desejados. Você pode aplicar regras específicas a cada palavra para obter uma silabização precisa de acordo com suas necessidades.

#### P: Quais são alguns cenários comuns em que o uso de um lembrete de silabização pode ser útil?

R: Usar um reforço de silabização pode ser útil em vários cenários, como:
- Silabização de palavras em idiomas específicos que possuem regras específicas de silabização.
- A aplicação de regras de silabização personalizadas para siglas ou palavras técnicas.
- Adaptação da silabização de acordo com preferências estilísticas ou padrões tipográficos.

#### P: Como posso testar a silabização personalizada com um lembrete de silabização no Aspose.Words?

 R: Para testar a silabização personalizada com um lembrete de silabização no Aspose.Words, você pode criar um documento de teste contendo palavras às quais deseja aplicar regras de silabização personalizadas. Então você pode definir seu retorno de chamada de silabização personalizado, chamar o`Document.Range.Replace()` método para substituir as palavras no documento e usar o`Hyphenate()` método do`Hyphenation` class para obter a silabização das palavras. Você pode então formatar as palavras silabizadas conforme necessário, por exemplo, adicionando hífens entre as sílabas.