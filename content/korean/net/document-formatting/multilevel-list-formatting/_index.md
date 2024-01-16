---
title: Word 문서의 다단계 목록 서식
linktitle: Word 문서의 다단계 목록 서식
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 다단계 목록을 만들고 Word 문서에 사용자 정의 서식을 적용하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/document-formatting/multilevel-list-formatting/
---
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서 기능에서 다단계 목록 서식을 사용하는 방법을 보여 드리겠습니다. 소스 코드를 이해하고 변경 사항을 적용하려면 아래 단계를 따르세요.

## 1단계: 문서 만들기 및 구성

시작하려면 새 문서와 관련 DocumentBuilder 개체를 만듭니다. 방법은 다음과 같습니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계: 다단계 목록 형식 지정

이제 DocumentBuilder 개체에서 사용할 수 있는 메서드를 사용하여 다단계 목록 형식을 적용하겠습니다. 방법은 다음과 같습니다.

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder. Writen("Element 2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.1");
builder.Writeln("Element 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.2.1");
builder.Writeln("Element 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 3");

builder.ListFormat.RemoveNumbers();
```

## 3단계: 문서 저장

 텍스트 입력 양식 필드를 삽입한 후,`Save` 방법. 적절한 파일 경로를 제공해야 합니다.

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

### .NET용 Aspose.Words를 사용한 다단계 목록 형식화의 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하는 다단계 목록 형식 지정 기능의 전체 소스 코드입니다.


```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.1");
builder.Writeln("Item 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.2.1");
builder.Writeln("Item 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 3");

builder.ListFormat.RemoveNumbers();

doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");

```

이 코드를 사용하면 다중 레벨 목록을 생성하고 .NET용 Aspose.Words를 사용하여 각 레벨에 적절한 서식을 적용할 수 있습니다.


## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 다단계 목록 서식 기능을 활용하는 프로세스를 살펴보았습니다. 설명된 단계를 수행하면 여러 수준으로 잘 구성된 목록을 만들어 문서의 구조와 가독성을 향상시킬 수 있습니다.

### FAQ

#### Q: Word 문서의 다단계 목록이란 무엇입니까?

A: Word 문서의 다단계 목록은 항목을 다양한 수준의 하위 항목으로 구성할 수 있는 계층적 목록입니다. 정보를 구조화된 방식으로 제시하여 독자가 내용을 더 쉽게 이해할 수 있도록 도와줍니다.

#### Q: 다단계 목록의 모양을 사용자 정의할 수 있습니까?

A: 예, Word 문서에서 다단계 목록의 모양을 사용자 지정할 수 있습니다. 글머리 기호, 숫자, 문자 등 다양한 스타일을 적용하고 들여쓰기와 간격을 조정하여 시각적으로 매력적이고 정리된 목록을 만들 수 있습니다.

#### Q: .NET용 Aspose.Words는 다른 목록 형식 지정 옵션을 지원합니까?

A: 예, Aspose.Words for .NET은 목록 형식화를 위한 포괄적인 기능 세트를 제공합니다. 글머리 기호 목록, 번호 매기기 목록, 다단계 목록 등 다양한 목록 유형을 지원합니다. 목록의 서식을 조작하고, 항목을 추가 또는 제거하고, 모양을 사용자 정의할 수 있습니다.

#### Q: Aspose.Words for .NET을 사용하여 다른 문서 요소와 작업할 수 있나요?

A: 예, Aspose.Words for .NET은 단락, 표, 이미지 등과 같은 다양한 문서 요소 작업을 위한 광범위한 기능을 제공합니다. 이를 통해 프로그래밍 방식으로 Word 문서를 생성, 수정 및 변환하여 문서 처리 작업을 간소화할 수 있습니다.