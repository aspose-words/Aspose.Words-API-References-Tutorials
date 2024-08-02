---
title: 문서 작성기 없이 TOA 필드 삽입
linktitle: 문서 작성기 없이 TOA 필드 삽입
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words에서 문서 작성기를 사용하지 않고 TOA 필드를 삽입하는 방법을 알아보세요. 법적 인용을 효율적으로 관리하려면 단계별 가이드를 따르세요.
type: docs
weight: 10
url: /ko/net/working-with-fields/insert-toafield-without-document-builder/
---
## 소개

Word 문서에서 TOA(권한 목록) 필드를 만드는 것은 복잡한 퍼즐을 맞추는 것처럼 느껴질 수 있습니다. 그러나 .NET용 Aspose.Words를 사용하면 프로세스가 원활하고 간단해집니다. 이 문서에서는 문서 작성기를 사용하지 않고 TOA 필드를 삽입하여 Word 문서 내에서 인용 및 법적 참조를 쉽게 관리하는 단계를 안내합니다.

## 전제 조건

튜토리얼을 시작하기 전에 필요한 필수 사항을 살펴보겠습니다.

-  .NET용 Aspose.Words: 최신 버전이 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[Aspose 웹사이트](https://releases.aspose.com/words/net/).
- 개발 환경: Visual Studio와 같은 .NET 호환 IDE입니다.
- 기본 C# 지식: 기본 C# 구문과 개념을 이해하면 도움이 됩니다.
- 샘플 Word 문서: TOA 필드를 삽입할 위치에 샘플 문서를 만들거나 준비합니다.

## 네임스페이스 가져오기

시작하려면 Aspose.Words 라이브러리에서 필요한 네임스페이스를 가져와야 합니다. 이 설정을 통해 문서 조작에 필요한 모든 클래스와 메서드에 액세스할 수 있습니다.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

프로세스를 간단하고 따르기 쉬운 단계로 나누어 보겠습니다. 각 단계를 안내하여 각 코드 조각이 수행하는 작업과 해당 코드가 TOA 필드 생성에 어떻게 기여하는지 설명합니다.

## 1단계: 문서 초기화

 먼저, 인스턴스를 생성해야 합니다.`Document` 수업. 이 개체는 작업 중인 Word 문서를 나타냅니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

이 코드는 새 Word 문서를 초기화합니다. 콘텐츠를 추가할 빈 캔버스를 만드는 것으로 생각할 수 있습니다.

## 2단계: TA 필드 생성 및 구성

다음으로 TA(권한 목록) 필드를 추가하겠습니다. 이 필드는 TOA에 나타날 항목을 표시합니다.

```csharp
Paragraph para = new Paragraph(doc);

// 다음과 같이 TA 및 TOA 필드를 삽입하려고 합니다.
// { TA \c 1 \l "값 0" }
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);
```

분석은 다음과 같습니다.
- Paragraph para = new Paragraph(doc);: 문서 내에 새 단락을 만듭니다.
-  FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);: 단락에 TA 필드를 추가합니다. 그만큼`FieldType.FieldTOAEntry` TOA 입력 필드임을 지정합니다.
- fieldTA.EntryCategory = "1";: 항목 카테고리를 설정합니다. 이는 다양한 유형의 항목을 분류하는 데 유용합니다.
- fieldTA.LongCitation = "Value 0";: 긴 인용 텍스트를 지정합니다. 이것은 TOA에 나타날 텍스트입니다.
- doc.FirstSection.Body.AppendChild(para);: TA 필드가 있는 단락을 문서 본문에 추가합니다.

## 3단계: TOA 필드 추가

이제 모든 TA 항목을 테이블에 컴파일하는 실제 TOA 필드를 삽입하겠습니다.

```csharp
para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);
```

이 단계에서는 다음을 수행합니다.
- FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);: 단락에 TOA 필드를 추가합니다.
- fieldToa.EntryCategory = "1";: 범주 "1"로 표시된 항목만 포함하도록 항목을 필터링합니다.

## 4단계: TOA 필드 업데이트

TOA 필드를 삽입한 후 최신 항목이 반영되도록 업데이트해야 합니다.

```csharp
fieldToa.Update();
```

이 명령은 TOA 필드를 새로 고쳐 표시된 모든 항목이 테이블에 올바르게 표시되도록 합니다.

## 5단계: 문서 저장

마지막으로 새로 추가된 TOA 필드를 사용하여 문서를 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

 이 코드 줄은 문서를 지정된 디렉터리에 저장합니다. 꼭 교체하세요`"YOUR DOCUMENT DIRECTORY"` 파일을 저장하려는 실제 경로를 사용하십시오.

## 결론

그리고 거기에 있습니다! 문서 작성기를 사용하지 않고 Word 문서에 TOA 필드를 성공적으로 추가했습니다. 이러한 단계를 따르면 인용을 효율적으로 관리하고 법률 문서에서 포괄적인 근거 목록을 만들 수 있습니다. Aspose.Words for .NET은 이 프로세스를 원활하고 효율적으로 만들어 복잡한 문서 작업을 쉽게 처리할 수 있는 도구를 제공합니다.

## FAQ

### 카테고리가 다른 여러 TA 필드를 추가할 수 있나요?
 예, 다음을 설정하여 카테고리가 다른 여러 TA 필드를 추가할 수 있습니다.`EntryCategory`그에 따라 재산.

### TOA의 모양을 어떻게 사용자 정의할 수 있나요?
항목 형식 및 범주 레이블과 같은 TOA 필드의 속성을 수정하여 TOA의 모양을 사용자 정의할 수 있습니다.

### TOA 필드를 자동으로 업데이트할 수 있나요?
 다음을 사용하여 TOA 필드를 수동으로 업데이트할 수 있습니다.`Update` 메서드를 사용하면 Aspose.Words는 현재 문서 변경 사항에 대한 자동 업데이트를 지원하지 않습니다.

### 문서의 특정 부분에 프로그래밍 방식으로 TA 필드를 추가할 수 있나요?
예, 원하는 단락이나 섹션에 TA 필드를 삽입하여 특정 위치에 추가할 수 있습니다.

### 단일 문서에서 여러 TOA 필드를 어떻게 처리합니까?
 서로 다른 TOA 필드를 할당하여 여러 TOA 필드를 관리할 수 있습니다.`EntryCategory` 값을 지정하고 각 TOA 필드가 해당 범주에 따라 항목을 필터링하는지 확인합니다.