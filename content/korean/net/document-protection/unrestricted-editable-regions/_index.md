---
title: Word 문서의 무제한 편집 가능 영역
linktitle: Word 문서의 무제한 편집 가능 영역
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 제한 없이 편집 가능한 영역을 만드는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/document-protection/unrestricted-editable-regions/
---
이 튜토리얼에서는 Aspose.Words for .NET의 무제한 편집 가능 영역 기능을 사용하는 단계를 안내합니다. 이 기능을 사용하면 문서의 나머지 부분이 읽기 전용인 경우에도 내용을 제한 없이 편집할 수 있는 Word 문서의 영역을 정의할 수 있습니다. 아래 단계를 따르십시오.

## 1단계: 문서 로드 및 보호 설정

기존 문서를 로드하여 시작합니다.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
doc.Protect(ProtectionType.ReadOnly, "MyPassword");
```

읽기 전용 보호 유형 및 비밀번호를 설정하여 문서를 보호하세요.

## 2단계: 편집 가능 영역 만들기

EditableRangeStart 및 EditableRangeEnd 개체를 사용하여 편집 가능한 영역을 만드는 것부터 시작합니다.

```csharp
EditableRangeStart edRangeStart = builder.StartEditableRange();
// 방금 만든 EditableRangeStart에 대해 EditableRange 개체가 생성됩니다.
EditableRange editableRange = edRangeStart.EditableRange;

// 편집 가능한 범위 안에 뭔가를 넣으세요.
builder.Writeln("Paragraph inside first editable range");

// 편집 가능한 범위에 시작과 끝이 있으면 제대로 구성된 것입니다.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

```

## 3단계: 편집 가능 영역 외부의 콘텐츠 추가

읽기 전용으로 유지되는 편집 가능한 영역 외부에 콘텐츠를 추가할 수 있습니다.

```csharp
builder.Writeln("This paragraph is outside of all editable areas and cannot be edited.");
```

## 4단계: 문서 저장

마지막으로 수정된 문서를 저장합니다.

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
```

편집 가능한 영역과 함께 문서를 저장하려면 올바른 경로와 파일 이름을 지정해야 합니다.

### .NET용 Aspose.Words를 사용하는 무제한 편집 가능 영역의 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 제한 없이 편집 가능한 영역에 대한 전체 소스 코드입니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서를 업로드하고 읽기 전용으로 설정하세요.
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

doc.Protect(ProtectionType.ReadOnly, "MyPassword");

builder.Writeln("Hello world! Since we have set the document's protection level to read-only, " + "we cannot edit this paragraph without the password.");

// 편집 가능한 범위를 시작합니다.
EditableRangeStart edRangeStart = builder.StartEditableRange();
// 방금 만든 EditableRangeStart에 대해 EditableRange 개체가 생성됩니다.
EditableRange editableRange = edRangeStart.EditableRange;

// 편집 가능한 범위 안에 뭔가를 넣으세요.
builder.Writeln("Paragraph inside first editable range");

// 편집 가능한 범위에 시작과 끝이 있으면 제대로 구성된 것입니다.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");

```
다음 단계를 따르면 Aspose.Words for .NET을 사용하여 Word 문서에 제한 없이 편집 가능한 영역을 쉽게 만들 수 있습니다.

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 무제한 편집 가능 영역을 만드는 방법을 배웠습니다. 제공된 단계에 따라 사용자가 문서의 나머지 부분을 읽기 전용으로 유지하면서 콘텐츠를 자유롭게 편집할 수 있는 문서 내의 특정 영역을 정의할 수 있습니다. Aspose.Words for .NET은 문서 보호 및 사용자 정의를 위한 강력한 기능을 제공하여 Word 문서의 편집 기능을 제어할 수 있습니다.

### Word 문서의 무제한 편집 가능 영역에 대한 FAQ

#### Q: .NET용 Aspose.Words에서 무제한 편집 가능 영역이란 무엇입니까?

A: Aspose.Words for .NET의 무제한 편집 가능 영역은 문서의 나머지 부분이 읽기 전용으로 설정되어 있어도 제한 없이 내용을 편집할 수 있는 Word 문서 내의 영역입니다. 이러한 영역은 전체 문서 보호를 유지하면서 사용자가 수정할 수 있는 문서의 특정 부분을 정의하는 방법을 제공합니다.

#### Q: .NET용 Aspose.Words를 사용하여 무제한 편집 가능 영역을 어떻게 만들 수 있습니까?

A: .NET용 Aspose.Words를 사용하여 Word 문서에서 무제한 편집 가능 영역을 만들려면 다음 단계를 따르세요.
1.  다음을 사용하여 기존 문서를 로드합니다.`Document` 수업.
2.  다음을 사용하여 문서 보호를 읽기 전용으로 설정하세요.`Protect` 의 방법`Document` 물체.
3.  사용`DocumentBuilder` 클래스를 추가하여 편집 가능한 범위를 생성하는 클래스`EditableRangeStart` 객체와`EditableRangeEnd` 물체.
4.  다음을 사용하여 편집 가능한 범위 내에서 콘텐츠를 추가합니다.`DocumentBuilder`.
5.  다음을 사용하여 수정된 문서를 저장합니다.`Save` 의 방법`Document` 물체.

#### 질문: Word 문서에 여러 개의 무제한 편집 가능 영역을 가질 수 있습니까?

A: 예, Word 문서에는 여러 개의 무제한 편집 가능 영역이 있을 수 있습니다. 이를 달성하려면 여러 세트를 생성할 수 있습니다.`EditableRangeStart` 그리고`EditableRangeEnd` 를 사용하는 객체`DocumentBuilder` 수업. 각 개체 세트는 사용자가 제한 없이 콘텐츠를 수정할 수 있는 별도의 편집 가능 영역을 정의합니다.

#### Q: 편집 가능 영역을 서로 중첩할 수 있습니까?

 A: 아니요. .NET용 Aspose.Words를 사용하면 편집 가능 영역을 서로 중첩할 수 없습니다. 다음에 의해 정의된 각 편집 가능 영역`EditableRangeStart` 그리고`EditableRangeEnd` 쌍은 독립적이어야 하며 다른 편집 가능한 영역 내에 중첩되거나 중첩되어서는 안 됩니다. 중첩된 편집 가능 영역은 지원되지 않습니다.

#### Q: 편집 가능 영역 내의 문서에서 읽기 전용 보호를 제거할 수 있나요?

A: 아니요. 편집 가능 영역 내의 문서에서는 읽기 전용 보호를 제거할 수 없습니다. 읽기 전용 보호는 문서 전체에 적용되며 특정 편집 가능 영역 내에서는 선택적으로 제거할 수 없습니다. 편집 가능 영역의 목적은 전체 문서를 읽기 전용으로 유지하면서 내용 수정을 허용하는 것입니다.