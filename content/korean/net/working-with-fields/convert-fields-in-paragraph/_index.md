---
title: 단락의 필드 변환
linktitle: 단락의 필드 변환
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 IF 필드를 단락의 일반 텍스트로 변환합니다.
type: docs
weight: 10
url: /ko/net/working-with-fields/convert-fields-in-paragraph/
---

다음은 .NET용 Aspose.Words와 함께 필드를 단락으로 변환 기능을 사용하는 방법을 보여주는 튜토리얼입니다. 이 코드는 문서의 마지막 단락에 있는 모든 IF 유형 필드를 일반 텍스트로 변환합니다. 이 코드를 이해하고 실행하려면 아래 단계를 따르세요.

시작하기 전에 .NET용 Aspose.Words를 설치하고 개발 환경을 설정했는지 확인하세요.

## 1단계: 참조 가져오기

프로젝트에서 Aspose.Words를 사용하려면 필요한 참조를 추가해야 합니다. 프로젝트에 Aspose.Words 라이브러리에 대한 참조를 추가했는지 확인하세요.

## 2단계: 문서 로드

필드를 변환하려면 먼저 변환할 필드가 포함된 문서를 로드해야 합니다. 문서가 포함된 디렉터리의 올바른 경로를 지정해야 합니다. 문서를 업로드하는 방법은 다음과 같습니다.

```csharp
//문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서를 로드합니다.
Document doc = new Document(dataDir + "Linked fields.docx");
```

"YOUR DOCUMENTS DIRECTORY"를 문서 디렉토리의 실제 경로로 바꾸십시오.

## 3단계: 필드를 텍스트로 변환

이제 문서가 로드되었으므로 유형 필드를 일반 텍스트로 변환하는 작업을 진행할 수 있습니다. 이 예에서는 문서의 마지막 단락에 있는 필드만 대상으로 합니다. 이 변환을 수행하는 코드는 다음과 같습니다.

```csharp
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());
```

 이 코드는 LINQ 메서드 조합을 사용하여 문서의 마지막 단락에 있는 필드를 필터링한 다음 다음을 호출하여 일반 텍스트로 변환합니다.`Unlink()` 방법.

## 4단계: 수정된 문서 저장

 필드가 변환되면 수정된 문서를 저장할 수 있습니다. 사용`Save()` 이에 대한 방법. 예는 다음과 같습니다.

```csharp
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

백업에 대한 올바른 경로와 파일 이름을 지정하십시오.

### .NET용 Aspose.Words를 사용하여 단락의 필드 변환에 대한 소스 코드 예

```csharp
//문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서를 로드합니다.
Document doc = new Document(dataDir + "Linked fields.docx");

// 문서의 마지막 단락에서 IF 필드를 일반 텍스트로 변환합니다.
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());

// 수정된 문서를 저장합니다.
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

### FAQ

#### Q: Aspose.Words의 변환 필드는 무엇입니까?

A: Aspose.Words의 변환 필드는 값이나 표현식을 다른 형식이나 데이터 유형으로 변환하는 필드 유형입니다. 예를 들어 변환 필드를 사용하여 날짜를 특정 형식으로 변환하거나 숫자를 텍스트로 변환하거나 다른 유형의 변환을 수행할 수 있습니다.

#### Q: Aspose.Words를 사용하여 단락에 변환 필드를 삽입하는 방법은 무엇입니까?

A: Aspose.Words를 사용하여 단락에 변환 필드를 삽입하려면 다음 단계를 따르세요.

1. Aspose.Words 네임스페이스에서 Document 클래스를 가져옵니다.
2. 기존 문서를 로드하여 Document 인스턴스를 만듭니다.
3. 변환 필드를 삽입하려는 단락을 가져옵니다.
4. InsertField 메서드를 사용하여 올바른 구문으로 변환 필드를 삽입하세요.

#### Q: Aspose.Words는 어떤 변환 형식을 지원합니까?

A: Aspose.Words는 날짜 형식, 숫자 형식, 텍스트 형식, 통화 형식, 백분율 형식 등을 포함하여 필드에서 광범위한 변환 형식을 지원합니다. 사용 가능한 변환 형식의 전체 목록은 Aspose.Words 문서를 확인하세요.

#### Q: Aspose.Words를 사용하여 Word 문서의 변환 필드를 업데이트하는 방법은 무엇입니까?

A: Aspose.Words를 사용하여 Word 문서의 변환 필드를 업데이트하려면 UpdateFields 메서드를 사용할 수 있습니다. 이 방법은 문서를 반복하고 변환 필드를 포함한 모든 필드를 업데이트하여 현재 데이터를 기반으로 값을 다시 계산합니다.