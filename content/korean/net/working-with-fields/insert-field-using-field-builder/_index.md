---
title: 필드 빌더를 사용하여 필드 삽입
linktitle: 필드 빌더를 사용하여 필드 삽입
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에 사용자 정의 필드를 삽입하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-fields/insert-field-using-field-builder/
---

다음은 .NET용 Aspose.Words의 "FieldBuilder를 사용하여 필드 삽입" 기능을 사용하는 아래 C# 소스 코드를 설명하는 단계별 가이드입니다. 원하는 결과를 얻으려면 각 단계를 주의 깊게 따르십시오.

## 1단계: 문서 디렉터리 설정

제공된 코드에서 문서의 디렉터리를 지정해야 합니다. "YOUR DOCUMENT DIRECTORY" 값을 문서 디렉토리에 대한 적절한 경로로 바꾸십시오.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 만들기

새 문서를 만드는 것부터 시작합니다.

```csharp
Document doc = new Document();
```

## 3단계: FieldBuilder를 사용하여 IF 필드 구축

FieldBuilder 클래스를 사용하여 두 개의 중첩된 MERGEFIELD 필드가 있는 IF 필드를 구성합니다. 이 예에서 IF 필드는 조건에 따라 이름과 성을 표시합니다.

```csharp
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));
```

## 4단계: 문서에 IF 필드 삽입

 우리는`BuildAndInsert()` 문서의 특정 위치에 IF 필드를 작성하고 삽입하는 방법입니다.

```csharp
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();
```

### .NET용 Aspose.Words와 함께 FieldBuilder를 사용하여 필드를 삽입하는 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서 생성.
Document doc = new Document();

// FieldBuilder를 사용하여 IF 필드 구성.
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));

// IF 필드를 문서에 삽입합니다.
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();

doc.Save(dataDir + "InsertFieldWithFieldBuilder.docx");
```

이 예에서는 새 문서를 만들고 중첩된 MERGEFIELD 필드로 IF 필드를 구성한 다음 해당 필드를 문서의 지정된 위치에 삽입했습니다. 그러면 문서가 특정 파일 이름으로 저장됩니다.

### FAQ

#### Q: Aspose.Words의 필드 생성자는 무엇입니까?

A: Aspose.Words의 필드 빌더는 Word 문서에서 필드를 생성하고 조작하기 위한 강력한 도구입니다. 필드 코드 삽입, 서식 옵션 관리 등 필드 작성 및 사용자 정의를 위한 고급 기능을 제공합니다.

#### Q: 필드 빌더를 사용하여 어떤 유형의 필드를 삽입할 수 있습니까?

A: Aspose.Words의 필드 빌더를 사용하면 Word 문서에 다양한 유형의 필드를 삽입할 수 있습니다. 다음은 일반적으로 사용되는 필드 유형의 몇 가지 예입니다.

- MERGEFIELD: 외부 소스의 데이터를 병합하는 데 사용됩니다.
- DATE: 현재 날짜를 표시합니다.
- PAGE: 현재 페이지 번호를 표시합니다.
- IF: 조건에 따라 콘텐츠 표시를 조절할 수 있습니다.
- TOC: 문서 제목 스타일을 기반으로 목차를 자동으로 생성합니다.

#### Q: 필드 작성기로 삽입된 필드를 사용자 정의하는 방법은 무엇입니까?

A: 필드 빌더는 삽입된 필드에 대한 사용자 정의 옵션을 제공합니다. 필드 생성자 메서드 및 속성을 사용하여 필드 서식, 인수, 스위치 및 기본값과 같은 옵션을 설정할 수 있습니다. 예를 들어 날짜 형식, 숫자 형식, 천 단위 구분 기호 등을 설정할 수 있습니다.
  