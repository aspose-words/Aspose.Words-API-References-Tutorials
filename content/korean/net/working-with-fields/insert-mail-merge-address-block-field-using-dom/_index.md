---
title: DOM을 사용하여 메일 병합 주소 블록 필드 삽입
linktitle: DOM을 사용하여 메일 병합 주소 블록 필드 삽입
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에 메일 병합 주소 블록 필드를 삽입하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-fields/insert-mail-merge-address-block-field-using-dom/
---

다음은 Aspose.Words for .NET의 "메일 병합 주소 블록 필드 삽입" 기능을 사용하는 아래 C# 소스 코드를 설명하는 단계별 가이드입니다. 원하는 결과를 얻으려면 각 단계를 주의 깊게 따르십시오.

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

## 3단계: 커서를 단락으로 이동

 우리는 DocumentBuilder를 사용합니다.`MoveTo()` 편지 병합 주소 블록 필드를 삽입하려는 단락으로 커서를 이동하는 방법입니다.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## 4단계: 편지 병합 주소 블록 필드 삽입

 우리는 DocumentBuilder를 사용합니다.`InsertField()` 편지 병합 주소 블록 필드를 단락에 삽입하는 방법입니다.

```csharp
FieldAddressBlock field = (FieldAddressBlock)builder.InsertField(FieldType.FieldAddressBlock, false);
```

그런 다음 국가/지역 이름 포함, 국가/지역에 따른 주소 형식 지정, 제외된 국가/지역 이름, 이름 및 주소 형식, 언어 식별자 등 적절한 옵션을 지정하여 주소 블록 필드의 속성을 구성합니다.

```csharp
field.IncludeCountryOrRegionName = "1";
field.FormatAddressOnCountryOrRegion = true;
field.ExcludedCountryOrRegionName = "Test2";
field.NameAndAddressFormat = "Test3";
field.LanguageId = "Test 4";
```

 마지막으로 우리는`Update()` 필드를 업데이트하는 방법입니다.

```csharp
field. Update();
```

### .NET용 Aspose.Words를 사용하여 메일 병합 주소 블록 필드를 삽입하기 위한 샘플 소스 코드

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Paragraph para = (Paragraph) doc.GetChildNodes(NodeType.Paragraph, true)[0];

builder. MoveTo(para);

// 다음과 같이 메일 병합 주소 블록을 삽입하려고 합니다.
// { 주소 블록 \\c 1 \\d \\e 테스트2 \\f 테스트3 \\l \"테스트 4\" }

FieldAddressBlock field = (FieldAddressBlock) builder.InsertField(FieldType.FieldAddressBlock, false);

// { 주소 블록 \\c 1" }
field.IncludeCountryOrRegionName = "1";

// { 주소 블록 \\c 1 \\d" }
field.FormatAddressOnCountryOrRegion = true;

// { 주소 블록 \\c 1 \\d \\e 테스트2 }
field.ExcludedCountryOrRegionName = "Test2";

// { 주소 블록 \\c 1 \\d \\e 테스트2 \\f 테스트3 }
field.NameAndAddressFormat = "Test3";

// { 주소 블록 \\c 1 \\d \\e 테스트2 \\f 테스트3 \\l \"테스트 4\" }
field.LanguageId = "Test 4";

field. Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertMailMergeAddressBlockFieldUsingDOM.docx");
```
### FAQ

#### Q: Aspose.Words for .NET을 사용하여 Word 문서의 우편 주소 형식을 어떻게 사용자 정의할 수 있나요?

 A: Aspose.Words for .NET의 속성을 사용하여 Word 문서의 우편 주소 형식을 사용자 정의할 수 있습니다.`FieldAddressBlock`물체. 주소 스타일, 구분 기호, 옵션 항목 등과 같은 형식 옵션을 설정하여 원하는 형식을 얻을 수 있습니다.

#### Q: Aspose.Words for .NET의 우편 주소 필드에 대한 소스 데이터를 어떻게 지정할 수 있습니까?

 A: Aspose.Words for .NET의 우편 주소 필드에 대한 소스 데이터를 지정하려면 다음을 사용할 수 있습니다.`FieldAddressBlock.StartAddress`그리고`FieldAddressBlock.EndAddress` 속성. 이러한 속성은 CSV 파일, 데이터베이스 등과 같은 외부 데이터 소스의 주소 범위를 정의하는 데 사용됩니다.

#### Q: Aspose.Words for .NET을 사용하여 우편 주소 필드에 선택적 요소를 포함할 수 있습니까?

 A: 예, Aspose.Words for .NET을 사용하면 우편 주소 필드에 선택적 요소를 포함할 수 있습니다. 다음을 사용하여 선택적 요소를 정의할 수 있습니다.`FieldAddressBlock.OmitOptional` 수신자 이름, 회사명 등의 선택적 요소를 포함할지 제외할지를 지정하는 방법입니다.

#### Q: DOM을 사용하여 우편 주소 필드를 삽입하면 Aspose.Words for .NET을 사용하는 Word 문서 구조에 영향을 줍니까?

대답: DOM을 사용하여 우편 주소 필드를 삽입해도 Word 문서의 구조에 직접적인 영향을 미치지 않습니다. 그러나 문서 콘텐츠에 새 필드 요소를 추가합니다. 필요에 따라 기존 요소를 추가, 삭제, 수정하여 문서 구조를 조작할 수 있습니다.