---
title: Word 문서의 무제한 섹션
linktitle: Word 문서의 무제한 섹션
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 제한되지 않은 섹션을 정의하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/document-protection/unrestricted-section/
---
이 튜토리얼에서는 Aspose.Words for .NET의 무제한 섹션 기능을 사용하는 단계를 안내합니다. 이 기능을 사용하면 문서의 나머지 부분이 보호되더라도 Word 문서에서 보호되지 않는 특정 섹션을 정의할 수 있습니다. 아래 단계를 따르십시오.

## 1단계: 문서 및 섹션 만들기

Document 클래스와 DocumentBuilder 개체의 인스턴스를 만드는 것부터 시작합니다.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계: 문서에 콘텐츠 추가
DocumentBuilder 객체를 사용하여 문서에 내용을 추가하고 섹션 나누기를 삽입합니다.

```csharp
builder.Writeln("Section 1. Unprotected.");
builder. InsertBreak(BreakType. SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");
```

## 3단계: 문서 및 섹션 보호

섹션 보호는 문서 보호가 활성화되어 있고 양식 필드에서의 편집만 허용되는 경우에만 작동합니다. Document 개체의 Protect() 메서드를 사용하여 문서를 보호할 수 있습니다.

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

올바른 보호 유형을 지정하고 원하는 비밀번호를 설정하십시오.

## 4단계: 특정 섹션에 대한 보호 비활성화

기본적으로 모든 섹션은 보호되지만 섹션 개체의 ProtectedForForms 속성을 사용하여 특정 섹션에 대한 보호를 선택적으로 비활성화할 수 있습니다.

```csharp
doc.Sections[0].ProtectedForForms = false;
```

이 예에서는 첫 번째 섹션에 대해 보호가 비활성화되어 있습니다.

## 5단계: 문서 저장

마지막으로 수정된 문서를 저장합니다.

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

섹션 제한이 없는 문서를 저장하려면 올바른 경로와 파일 이름을 지정해야 합니다.

### .NET용 Aspose.Words를 사용하는 제한되지 않은 섹션의 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하는 제한되지 않은 섹션의 전체 소스 코드입니다.


```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 일부 텍스트가 포함된 두 섹션을 삽입합니다.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1. Unprotected.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");

// 섹션 보호는 문서 보호가 켜져 있는 경우에만 작동하며 양식 필드에서의 편집만 허용됩니다.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

//기본적으로 모든 섹션은 보호되지만 선택적으로 보호를 해제할 수 있습니다.
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

다음 단계를 따르면 Aspose.Words for .NET을 사용하여 Word 문서에서 제한되지 않은 섹션을 쉽게 정의할 수 있습니다.

## 결론

이 튜토리얼에서는 문서의 나머지 부분을 보호하는 동안 Word 문서의 특정 섹션을 보호되지 않은 상태로 유지할 수 있는 Aspose.Words for .NET의 무제한 섹션 기능을 살펴보았습니다. 제공된 단계를 따르면 사용자가 다른 섹션에 대한 보호를 유지하면서 콘텐츠를 자유롭게 편집할 수 있는 문서 내의 섹션을 쉽게 정의할 수 있습니다. Aspose.Words for .NET은 문서 보호 및 사용자 정의를 위한 강력한 기능을 제공하여 Word 문서 내의 편집 권한을 제어할 수 있습니다.

### Word 문서의 제한되지 않은 섹션에 대한 FAQ

#### Q: .NET용 Aspose.Words의 제한되지 않은 섹션은 무엇입니까?

A: Aspose.Words for .NET의 제한되지 않은 섹션은 문서의 나머지 부분이 보호되더라도 보호되지 않는 Word 문서 내의 특정 섹션입니다. 이 섹션을 통해 사용자는 문서의 나머지 부분에 대한 보호를 유지하면서 해당 섹션의 내용을 수정할 수 있습니다.

#### Q: .NET용 Aspose.Words를 사용하여 제한되지 않은 섹션을 어떻게 만들 수 있나요?

A: .NET용 Aspose.Words를 사용하여 Word 문서에서 제한되지 않은 섹션을 만들려면 다음 단계를 따르세요.
1.  인스턴스를 생성합니다.`Document` 수업과`DocumentBuilder` 물체.
2.  사용`DocumentBuilder` 문서에 내용을 추가하고 섹션 나누기를 삽입합니다.
3.  다음을 사용하여 문서를 보호하세요.`Protect` 의 방법`Document` 원하는 보호 유형과 비밀번호를 지정합니다.
4.  다음을 설정하여 특정 섹션에 대한 보호를 비활성화합니다.`ProtectedForForms` 해당 속성`Section` 반대하다`false`.
5. 수정된 문서를 저장합니다.

#### 질문: Word 문서 내에 제한되지 않은 섹션을 여러 개 포함할 수 있나요?

 A: 예, Word 문서 내에는 여러 개의 무제한 섹션이 있을 수 있습니다. 다음을 사용하여 특정 섹션에 대한 보호를 선택적으로 비활성화합니다.`ProtectedForForms` 의 재산`Section`개체를 사용하면 사용자가 다른 섹션을 보호하면서 콘텐츠를 자유롭게 수정할 수 있는 여러 섹션을 정의할 수 있습니다.

#### Q4. 처음에 보호된 섹션에서 보호를 제거할 수 있나요?
 예, 다음을 설정하여 처음에 보호되었던 섹션에서 보호를 제거할 수 있습니다.`ProtectedForForms` 해당 속성`Section` 반대하다`false`. 이를 통해 사용자는 아무런 제한 없이 해당 특정 섹션의 콘텐츠를 편집할 수 있습니다.

#### Q: Word 문서에는 어떤 보호 유형을 적용할 수 있나요?

A: Aspose.Words for .NET은 다음을 포함하여 Word 문서에 적용할 수 있는 다양한 보호 유형을 제공합니다.
- NoProtection: 보호가 적용되지 않습니다.
- AllowOnlyRevisions: 사용자는 문서를 개정할 수만 있습니다.
- AllowOnlyComments: 사용자는 문서에 설명만 추가할 수 있습니다.
- AllowOnlyFormFields: 사용자는 문서의 양식 필드만 편집할 수 있습니다.
- ReadOnly: 문서는 읽기 전용이며 편집이 허용되지 않습니다.


