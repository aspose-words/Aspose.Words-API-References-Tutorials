---
title: 필드 삽입
linktitle: 필드 삽입
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에 필드를 삽입하는 방법을 알아보세요. 동적 필드로 문서를 개인화하세요.
type: docs
weight: 10
url: /ko/net/working-with-fields/insert-field/
---

다음은 Aspose.Words for .NET의 "필드 삽입" 기능을 사용하는 아래 C# 소스 코드를 설명하는 단계별 가이드입니다. 원하는 결과를 얻으려면 각 단계를 주의 깊게 따르십시오.

## 1단계: 문서 디렉터리 설정

제공된 코드에서 문서의 디렉터리를 지정해야 합니다. "YOUR DOCUMENT DIRECTORY" 값을 문서 디렉토리에 대한 적절한 경로로 바꾸십시오.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 및 DocumentBuilder 만들기

새 문서를 만들고 DocumentBuilder를 초기화하는 것부터 시작합니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3단계: 필드 삽입

 우리는`InsertField()` DocumentBuilder의 메소드를 사용하여 문서에 필드를 삽입합니다. 이 예에서는 필드 이름이 "MyFieldName"이고 병합 형식이 있는 병합 필드(MERGEFIELD)를 삽입합니다.

```csharp
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");
```

### .NET용 Aspose.Words를 사용하여 필드를 삽입하기 위한 소스 코드 예

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서와 DocumentBuilder를 만듭니다.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 필드를 삽입합니다.
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");

doc.Save(dataDir + "InsertionField.docx");
```

이 예에서는 새 문서를 만들고 DocumentBuilder를 초기화한 다음 필드 이름이 "MyFieldName"이고 병합 형식인 병합 필드를 삽입했습니다. 그러면 문서가 지정된 파일 이름으로 저장됩니다.

이것으로 .NET용 Aspose.Words에서 "필드 삽입" 기능을 사용하는 방법에 대한 가이드를 마칩니다.

### FAQ

#### Q: Word의 필드란 무엇입니까?

A: Word의 필드는 문서에 동적 데이터를 삽입하고 조작할 수 있는 요소입니다. 날짜, 페이지 번호, 표, 수학 공식 등과 같은 변수 정보를 표시하는 데 사용할 수 있습니다.

#### Q: Word 문서에 필드를 삽입하는 방법은 무엇입니까?

A: Word 문서에 필드를 삽입하려면 다음 단계를 따르세요.

1. 필드를 삽입하려는 위치에 커서를 놓습니다.
2. 리본의 "삽입" 탭으로 이동합니다.
3. "텍스트" 그룹에서 "필드" 버튼을 클릭하여 필드 대화 상자를 엽니다.
4. 드롭다운 목록에서 삽입하려는 필드 유형을 선택합니다.
5. 필요에 따라 필드 옵션을 구성합니다.
6. 문서에 필드를 삽입하려면 "확인" 버튼을 클릭하세요.

#### Q: Word에서 일반적으로 사용되는 필드 유형은 무엇입니까?

A: Word에서는 문서에 사용할 수 있는 다양한 필드 유형을 제공합니다. 다음은 일반적으로 사용되는 필드 유형 중 일부입니다.

- 날짜 및 시간: 현재 날짜 및 시간을 표시합니다.
- 페이지 번호: 현재 페이지 번호를 표시합니다.
- 목차: 제목 스타일에 따라 목차를 자동으로 생성합니다.
- 계산: 수식을 사용하여 수학적 계산을 수행합니다.
- 채우기 텍스트: 문서를 채울 임의의 텍스트를 생성합니다.

#### Q: Word에서 필드 모양을 사용자 지정할 수 있나요?

A: 예, 사용 가능한 서식 옵션을 사용하여 Word의 필드 모양을 사용자 지정할 수 있습니다. 예를 들어 필드에 있는 텍스트의 글꼴, 크기, 색상 및 스타일을 변경할 수 있습니다. 굵게, 기울임꼴, 밑줄 등의 서식 효과를 적용할 수도 있습니다.
  