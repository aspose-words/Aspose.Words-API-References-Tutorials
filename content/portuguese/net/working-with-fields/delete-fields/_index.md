---
title: Excluir campos
linktitle: Excluir campos
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para excluir campos de mesclagem em seus documentos do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fields/delete-fields/
---

Para explicar como usar o recurso "Excluir campos" no Aspose. Palavras para .NET criamos um guia passo a passo abaixo. 

É importante seguir cada passo de perto para alcançar os resultados desejados. 

## Etapa 1: Criando um Novo Documento

Neste trecho de código começamos criando um novo documento vazio usando a seguinte linha: 

```csharp
Document doc = new Document();
```

## Etapa 2: remover campos de mesclagem

 Para remover todos os campos de mesclagem presentes no documento, usamos o`DeleteFields()` função. 

Isto é particularmente útil se você deseja manter apenas o conteúdo estático e remover qualquer informação de mesclagem. 

### Exemplo de código-fonte para excluir campos com Aspose.Words para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carregue o documento existente.
Document doc = new Document(dataDir + "YourDocument.docx");

// Remova os campos de mesclagem.
doc.MailMerge.DeleteFields();

// Salve o documento modificado.
doc.Save(dataDir + "YourDocument_WithoutFields.docx");
```

 No nosso exemplo, primeiro carregamos um documento existente antes de chamar`DeleteFields()`. Finalmente salvamos o documento modificado com um novo nome de arquivo. 

Para remover efetivamente campos de mesclagem de um documento usando o recurso "Remover campos" do Aspose.Words for .NET, siga a sugestão deste exemplo. 

Lembre-se sempre de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho do diretório específico. 

Nosso guia sobre como implementar a funcionalidade "Excluir Campos" através do Aspose.Words for .NET foi assim concluído.

### Perguntas frequentes

#### P: O que é um campo no Aspose.Words?

R: Um campo em Aspose.Words é uma estrutura de documento que representa um texto gerado automaticamente ou um valor calculado. Os campos são usados para exibir informações dinâmicas em um documento, como números de páginas, datas, campos de mala direta, etc.

#### P: Como excluir um campo em um documento do Word com Aspose.Words?

R: Para excluir um campo em um documento do Word com Aspose.Words, você pode seguir estas etapas:

1. Importe a classe Document do namespace Aspose.Words.
2. Crie uma instância de Document carregando seu documento existente.
3. Use o método RemoveFields para remover todos os campos do documento.

#### P: Posso excluir campos específicos em vez de excluir todos os campos de um documento?

R: Sim, você pode excluir campos específicos em vez de excluir todos os campos de um documento. Para fazer isso, você precisa acessar cada campo individualmente e usar o método Remove para removê-lo.

#### P: Como posso verificar se existe um campo em um documento do Word antes de excluí-lo?

R: Para verificar se existe um campo em um documento do Word antes de excluí-lo, você pode usar o método Contém da coleção Fields para localizar o campo especificado. Este método retorna um valor booleano que indica se o campo existe ou não.

#### P: Quais são os efeitos da exclusão de um campo no restante do documento?

R: Quando você exclui um campo em um documento do Word, o campo é removido do documento e o texto gerado ou valor calculado associado ao campo é excluído. Isso poderá afetar o layout do documento, pois o conteúdo gerado pelo campo será excluído.