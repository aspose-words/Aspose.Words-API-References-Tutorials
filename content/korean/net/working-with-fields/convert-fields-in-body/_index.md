---
title: 본문의 필드 변환
linktitle: 본문의 필드 변환
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 페이지 필드를 Word 문서 본문의 텍스트로 변환하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-fields/convert-fields-in-body/
---

이 단계별 튜토리얼에서는 제공된 C# 소스 코드를 사용하여 Aspose.Words for .NET의 ConvertFieldsInBody 기능을 사용하는 방법을 안내합니다. 이 기능을 사용하면 문서 본문의 특정 필드를 일반 텍스트로 변환하여 문서를 더 쉽게 처리할 수 있습니다. 이 기능을 효과적으로 사용하려면 아래 단계를 따르십시오.

## 1단계: 전제조건

시작하기 전에 Aspose.Words for .NET을 설치했고 처리할 문서가 준비되어 있는지 확인하세요. 또한 문서의 디렉터리 경로가 있는지 확인하세요.

## 2단계: 문서 넣기

문서 디렉터리 경로에 대한 변수를 선언하여 시작한 다음 해당 변수를 사용하여 지정된 문서에서 Document 개체를 초기화합니다. 이 예에서는 문서 이름이 "Linked fields.docx"입니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서를 로드하세요
Document doc = new Document(dataDir + "Linked fields.docx");
```

## 3단계: 페이지 필드를 일반 텍스트로 변환

 이제 문서가 로드되었으므로 변환 단계로 넘어갈 수 있습니다. 첫 번째 섹션 본문의 페이지 필드를 일반 텍스트로 변환하려면 다음을 사용할 수 있습니다.`Range.Fields` 지정된 범위의 모든 필드를 가져온 다음 해당 유형의 필드를 필터링하는 메서드`FieldType.FieldPage` . 그런 다음`ForEach` 각 필드를 반복하고 호출하는 메서드`Unlink()` 일반 텍스트로 변환하는 방법입니다.

```csharp
// 페이지 필드를 첫 번째 섹션 본문의 일반 텍스트로 변환하려면 적절한 매개변수를 전달하세요.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.Unlink());
```

## 4단계: 수정된 문서 저장

페이지 필드를 일반 텍스트로 변환한 후에는 다음을 사용하여 수정된 문서를 저장할 수 있습니다.`Save()` 방법을 사용하고 출력 파일의 경로와 이름을 지정합니다. 이 예에서는 이를 "WorkingWithFields.ConvertFieldsInBody.docx"로 저장합니다.

```csharp
// 수정된 문서를 저장하세요
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### .NET용 Aspose.Words를 사용하여 본문의 필드를 변환하는 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 필드를 본문으로 변환하는 전체 소스 코드 예입니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서를 로드하세요
Document doc = new Document(dataDir + "Linked fields.docx");

// 페이지 필드를 첫 번째 섹션 본문의 일반 텍스트로 변환하려면 적절한 매개변수를 전달하세요.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.A
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### FAQ

#### Q: Aspose.Words는 다른 버전의 Microsoft Word와 호환됩니까?

A: 예, Aspose.Words는 Word 2003, Word 2007, Word 2010, Word 2013, Word 2016 및 Word 2019를 포함한 다양한 버전의 Microsoft Word와 호환됩니다.

#### Q: Aspose.Words는 복잡한 필드 구조를 처리할 수 있나요?

답: 물론이죠! Aspose.Words는 중첩된 필드, 계산 및 조건식을 포함한 복잡한 필드 구조에 대한 광범위한 지원을 제공합니다. 강력한 API를 활용하여 모든 유형의 필드 구조로 작업할 수 있습니다.

#### Q: Aspose.Words는 필드 업데이트 작업을 지원합니까?

A: 예, Aspose.Words를 사용하면 프로그래밍 방식으로 필드를 업데이트할 수 있습니다. API를 사용하면 쉽게 필드 값을 업데이트하고, 계산을 새로 고치고, 기타 필드 관련 작업을 수행할 수 있습니다.

#### Q: Aspose.Words를 사용하여 필드를 일반 텍스트로 변환할 수 있나요?

답: 물론이죠! Aspose.Words는 필드를 일반 텍스트로 변환하는 방법을 제공합니다. 이는 필드 관련 서식이나 기능 없이 콘텐츠를 추출해야 할 때 유용할 수 있습니다.

#### Q: Aspose.Words를 사용하여 동적 필드가 있는 Word 문서를 생성할 수 있습니까?

답: 물론이죠! Aspose.Words는 동적 필드가 포함된 Word 문서를 생성하는 강력한 기능을 제공합니다. 사전 정의된 필드로 템플릿을 생성하고 여기에 데이터를 동적으로 입력하여 유연하고 효율적인 문서 생성 솔루션을 제공할 수 있습니다.