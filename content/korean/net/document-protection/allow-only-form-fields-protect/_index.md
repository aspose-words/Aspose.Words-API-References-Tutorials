---
title: Word 문서에서 양식 필드 보호만 허용
linktitle: Word 문서에서 양식 필드 보호만 허용
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서를 보호하고 양식 필드만 편집할 수 있도록 하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/document-protection/allow-only-form-fields-protect/
---
문서 보호는 C# 애플리케이션 내에서 파일을 단어 처리할 때 필수적인 기능입니다. .NET용 Aspose.Words 라이브러리를 사용하면 문서를 쉽게 보호하고 양식 필드만 편집할 수 있습니다. 이 단계별 가이드에서는 .NET용 Aspose.Words의 양식 필드 보호만 허용 기능을 사용하여 양식 필드만 편집할 수 있도록 C# 소스 코드를 사용하는 방법을 안내합니다.

## 1단계: 문서 디렉터리 설정

첫 번째 단계는 문서의 디렉터리를 정의하는 것입니다. 보호된 문서를 저장할 경로를 지정해야 합니다. 예를 들어 :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

"YOUR DOCUMENTS DIRECTORY"를 문서 디렉토리의 실제 경로로 바꾸십시오.

## 2단계: 섹션 및 텍스트 삽입

다음으로 문서에 섹션과 텍스트를 삽입해야 합니다. Aspose.Words에서 제공하는 DocumentBuilder 클래스를 사용하여 문서 콘텐츠를 빌드하세요. 다음은 간단한 예입니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

이 예에서는 새 빈 문서를 만든 다음 DocumentBuilder를 사용하여 텍스트 줄을 추가합니다.

## 3단계: 문서 보호 활성화

 문서 보호는 문서 보호가 활성화된 경우에만 작동합니다. 다음을 사용하여 문서 보호를 활성화할 수 있습니다.`Protect` Document 클래스의 메소드 방법은 다음과 같습니다.

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

이 예에서는 보호 유형 `을 지정하여 문서 보호를 활성화합니다.

AllowOnlyFormFields` 및 비밀번호 설정.

## 4단계: 양식 필드만 허용

이제 문서 보호가 활성화되었으므로 양식 필드 편집만 허용되도록 지정해야 합니다. 이렇게 하면 사용자는 양식 필드인 문서 부분만 편집할 수 있습니다. 방법은 다음과 같습니다.

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

"password"를 이전에 설정한 비밀번호로 바꿔야 합니다.

## 5단계: 보호된 문서 저장

 마지막으로 다음을 사용하여 보호된 문서를 저장할 수 있습니다.`Save` Document 클래스의 메소드 전체 파일 경로와 원하는 파일 이름을 지정하십시오. 예를 들어 :

```csharp
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

"dataDir"을 문서 디렉토리 경로로 바꾸십시오.

### .NET용 Aspose.Words를 사용하여 양식 필드 보호만 허용 기능에 대한 예제 소스 코드

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 일부 텍스트가 포함된 두 섹션을 삽입합니다.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// 문서 보호는 문서 보호가 켜져 있고 양식 필드에서의 편집만 허용되는 경우에만 작동합니다.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// 보호된 문서를 저장하세요.
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

## 결론

이 가이드에서는 .NET용 Aspose.Words 라이브러리를 사용하여 문서를 보호하고 양식 필드만 편집할 수 있도록 허용하는 방법을 살펴보았습니다. 제공된 단계를 따르면 C# 애플리케이션에서 이 기능을 쉽게 구현할 수 있습니다. 문서 보호는 문서의 보안과 기밀성을 보장하는 데 필수적입니다.

### Word 문서에서 양식 필드만 보호하도록 허용하는 FAQ

#### Q: Aspose.Words for .NET의 문서 보호란 무엇입니까?

A: Aspose.Words for .NET의 문서 보호는 편집, 서식 지정 또는 콘텐츠 수정과 같은 특정 작업을 제한하여 문서를 보호할 수 있는 기능입니다. 무단 변경을 방지하여 문서의 무결성과 기밀성을 유지하는 데 도움이 됩니다.

#### Q: Aspose.Words for .NET을 사용하여 문서를 보호하고 양식 필드만 편집하도록 허용하려면 어떻게 해야 합니까?

A: 문서를 보호하고 .NET용 Aspose.Words를 사용하여 양식 필드만 편집할 수 있도록 하려면 다음 단계를 따르세요.
1. 문서의 디렉터리 경로를 정의합니다.
2.  다음을 사용하여 문서에 섹션과 텍스트를 삽입합니다.`DocumentBuilder` 수업.
3.  다음을 사용하여 문서 보호를 활성화합니다.`Protect` 의 방법`Document` 클래스, 보호 유형을 다음과 같이 지정`AllowOnlyFormFields` 그리고 비밀번호를 제공합니다.
4.  다음을 사용하여 보호된 문서를 저장하세요.`Save` 의 방법`Document` 수업.

#### Q: Aspose.Words for .NET을 사용하여 보호된 문서에 양식 필드를 삽입할 수 있습니까?

A: 예, Aspose.Words for .NET을 사용하여 보호된 문서에 양식 필드를 삽입할 수 있습니다. 문서 보호`AllowOnlyFormFields` type을 사용하면 사용자는 문서의 나머지 내용을 보호하면서 양식 필드만 편집할 수 있습니다. 당신은 사용할 수 있습니다`DocumentBuilder` 보호를 활성화하기 전에 문서에 양식 필드를 삽입하는 클래스입니다.

#### Q: 보호된 문서에서 문서 보호를 제거할 수 있나요?

 A: 예, Aspose.Words for .NET을 사용하여 보호된 문서에서 문서 보호를 제거할 수 있습니다. 보호를 제거하려면 다음을 사용할 수 있습니다.`Unprotect` 의 방법`Document` 수업을 듣고 올바른 비밀번호를 입력하세요. 이렇게 하면 보호 기능이 제거되고 문서를 제한 없이 편집할 수 있습니다.

#### Q: 여러 가지 보호 유형으로 문서를 보호할 수 있나요?

 A: 아니요, .NET용 Aspose.Words에서는 한 번에 하나의 보호 유형만 문서에 적용할 수 있습니다. 그러나, 그`AllowOnlyFormFields` 보호 유형은 다음과 같은 다른 보호 유형을 허용하면서 양식 필드에 대한 편집을 효과적으로 제한할 수 있습니다.`AllowOnlyComments` 또는`AllowOnlyRevisions`양식 필드 보호와 결합됩니다.

#### Q: 문서의 다양한 보호 유형에 대해 서로 다른 비밀번호를 설정할 수 있나요?

A: 아니요, Aspose.Words for .NET을 사용하면 보호 유형에 관계없이 문서 보호를 위한 단일 비밀번호를 설정할 수 있습니다. 문서 보호를 활성화 및 비활성화하는 데 동일한 비밀번호가 사용됩니다.