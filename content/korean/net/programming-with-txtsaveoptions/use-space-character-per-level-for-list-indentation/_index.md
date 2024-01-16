---
title: 목록 들여쓰기에 레벨당 공백 문자 사용
linktitle: 목록 들여쓰기에 레벨당 공백 문자 사용
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET에서 목록 들여쓰기를 위해 레벨당 공백 문자를 사용하는 방법에 대한 단계별 가이드입니다. 체계적으로 구성된 Word 문서를 쉽게 만드세요.
type: docs
weight: 10
url: /ko/net/programming-with-txtsaveoptions/use-space-character-per-level-for-list-indentation/
---
Aspose.Words for .NET은 C# 애플리케이션에서 Word 문서를 생성, 편집 및 조작하기 위한 강력한 라이브러리입니다. Aspose.Words가 제공하는 기능 중에는 목록 들여쓰기에 레벨당 하나의 공백 문자를 사용할 수 있는 가능성이 있습니다. 이 가이드에서는 .NET용 Aspose.Words의 C# 소스 코드를 사용하여 이 기능을 구현하는 방법을 보여줍니다.

## Aspose.Words 라이브러리 이해

코드를 살펴보기 전에 .NET용 Aspose.Words 라이브러리를 이해하는 것이 중요합니다. Aspose.Words는 Word 문서로 Words 처리를 쉽고 효율적으로 만들어주는 인기 있는 라이브러리입니다. 목록 및 들여쓰기 관리를 포함하여 Word 문서를 생성, 수정 및 조작하기 위한 광범위한 기능을 제공합니다.

## 문서 작성 및 내용 추가

첫 번째 단계는 새 문서를 만들고 콘텐츠를 추가하는 것입니다. Document 클래스를 사용하여 새 문서 인스턴스를 만듭니다. 그런 다음 DocumentBuilder 클래스를 사용하여 텍스트를 추가하고 여러 수준의 들여쓰기가 포함된 목록을 만듭니다. 예는 다음과 같습니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 세 가지 들여쓰기 수준으로 목록 만들기
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

이 예에서는 새 문서를 만들고 DocumentBuilder를 사용하여 텍스트를 추가하고 세 가지 들여쓰기 수준이 있는 목록을 만듭니다. 목록에 세 가지 항목을 추가했으며 각 항목은 추가 수준으로 들여쓰기되었습니다.

## 목록 들여쓰기에 레벨당 하나의 공백 문자 사용

콘텐츠가 추가되면 이제 레벨당 하나의 공백 문자를 사용하여 목록 들여쓰기를 구성할 수 있습니다. 이를 위해 TxtSaveOptions 클래스를 사용하고 ListIndentation.Count 속성을 들여쓰기 수준 수로 설정하고 ListIndentation.Character 속성을 사용할 공백 문자로 설정합니다. 방법은 다음과 같습니다.

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 3;
saveOptions.ListIndentation.Character = ' ';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
```

이 예에서는 TxtSaveOptions의 인스턴스를 만들고 ListIndentation.Count 속성을 3으로 설정하여 목록에 세 가지 들여쓰기 수준이 있음을 나타냅니다. 또한 ListIndentation.Character 속성을 들여쓰기에 사용할 공백 문자(' ')로 설정합니다.

### .NET용 Aspose.Words를 사용하는 "목록 들여쓰기를 위해 수준당 하나의 공백 문자 사용" 기능에 대한 예제 소스 코드

다음은 .NET용 Aspose.Words의 "목록 들여쓰기를 위해 수준당 하나의 공백 문자 사용" 기능에 대한 전체 샘플 소스 코드입니다.

```csharp

using Aspose.Words;
using Aspose.Words.Saving;

namespace Example
{
     class Program
     {
         static void Main(string[] args)
         {
             // 문서 디렉터리 경로
             string dataDir = "YOUR DOCUMENTS DIRECTORY";

             // 문서 만들기 및 콘텐츠 추가
             Document doc = new Document();
             DocumentBuilder builder = new DocumentBuilder(doc);

             // 세 가지 들여쓰기 수준으로 목록 만들기
             builder.ListFormat.ApplyNumberDefault();
             builder. Writen("Element 1");
             builder.ListFormat.ListIndent();
             builder. Writen("Element 2");
             builder.ListFormat.ListIndent();
             builder.Write("Element 3");

             // 목록 들여쓰기에는 레벨당 하나의 공백 문자를 사용하십시오.
             TxtSaveOptions saveOptions = new TxtSaveOptions();
             saveOptions.ListIndentation.Count = 3;
             saveOptions.ListIndentation.Character = ' ';

             // 지정된 옵션으로 문서를 저장합니다.
             doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
         }
     }
}

```

## 결론

이 가이드에서는 .NET용 Aspose.Words를 사용하여 "목록 들여쓰기에 레벨당 공백 문자 하나 사용" 기능을 적용하는 방법을 설명했습니다. 제공된 단계를 따르고 제공된 C# 소스 코드를 사용하면 수준당 하나의 공백 문자를 사용하여 Word 문서에서 목록 들여쓰기를 쉽게 구성할 수 있습니다. Aspose.Words는 텍스트 서식 지정 및 목록 관리를 통해 단어 처리에 엄청난 유연성과 성능을 제공하므로 C# 응용 프로그램에서 잘 구조화된 문서를 만들 수 있습니다.

### 자주 묻는 질문

#### Q: .NET용 Aspose.Words가 무엇인가요?
Aspose.Words for .NET은 C# 애플리케이션에서 Word 문서를 생성, 편집 및 조작하기 위한 강력한 라이브러리입니다. 목록 들여쓰기를 위해 수준당 하나의 공백을 사용하는 기능을 포함하여 Word 문서의 단어 처리를 위한 많은 기능을 제공합니다.

#### Q: Aspose.Words for .NET을 사용하여 목록 들여쓰기를 위해 레벨당 하나의 공백을 어떻게 사용할 수 있습니까?
다음 단계에 따라 목록 들여쓰기에 수준당 하나의 공백을 사용할 수 있습니다.

 다음을 사용하여 새 문서를 만듭니다.`Document` 수업.

 사용`DocumentBuilder`문서에 내용을 추가하고 여러 수준의 들여쓰기가 포함된 목록을 만드는 클래스입니다.

 콘텐츠를 추가하고 목록 들여쓰기를 구성한 후`TxtSaveOptions` 클래스를 설정하고`ListIndentation.Count` 들여쓰기 수준 수에 대한 속성과`ListIndentation.Character` 공간의 속성(`' '`) 사용.

 다음을 사용하여 지정된 옵션으로 문서를 저장합니다.`Save` 의 방법`Document` 수업.

#### Q: Aspose.Words는 목록 들여쓰기에 다른 문자를 지원합니까?
예, Aspose.Words는 목록 들여쓰기에 다른 문자를 지원합니다. 탭(`'\t'` ) 또는 기타 특수 문자를 설정하여`ListIndentation.Character` 원하는 캐릭터에 속성을 부여합니다.

#### Q: 목록 들여쓰기에 대한 수준당 공백 수를 사용자 정의할 수 있습니까?
 예, 값을 변경하여 목록 들여쓰기에 대한 수준당 공백 수를 사용자 정의할 수 있습니다.`ListIndentation.Count` 에 있는 재산`TxtSaveOptions` 수업. 각 들여쓰기 수준에 대해 원하는 공백 수를 지정할 수 있습니다.

#### Q: Aspose.Words는 목록 관리를 위해 어떤 다른 기능을 제공합니까?
Aspose.Words는 Word 문서의 목록을 관리하기 위한 다양한 기능을 제공합니다. 번호 매기기 또는 글머리 기호 목록을 생성하고, 들여쓰기 수준을 설정하고, 목록 스타일을 사용자 정의하고, 목록 항목을 추가하는 등의 작업을 수행할 수 있습니다.