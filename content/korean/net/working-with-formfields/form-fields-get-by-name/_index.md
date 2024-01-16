---
title: 양식 필드 이름으로 가져오기
linktitle: 양식 필드 이름으로 가져오기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 이름으로 양식 필드를 검색하고 수정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-formfields/form-fields-get-by-name/
---

이 단계별 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 이름으로 양식 필드를 검색하는 방법을 안내합니다. 제공된 C# 소스 코드를 설명하고 이를 자신의 프로젝트에 구현하는 방법을 보여 드리겠습니다.

 시작하려면 개발 환경에 Aspose.Words for .NET이 설치 및 설정되어 있는지 확인하세요. 아직 수행하지 않은 경우 다음에서 라이브러리를 다운로드하여 설치하십시오.[Aspose.Releases]https://releases.aspose.com/words/net/.

## 1단계: 문서 개체 초기화

 먼저, 초기화`Document` 양식 필드가 포함된 소스 문서에 대한 경로를 제공하여 개체를 만듭니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");
```

## 2단계: 양식 필드 검색

 다음으로`FormFields` 의 재산`Range` 모든 양식 필드를 검색하려면 문서의 개체를 사용하세요.

```csharp
FormFieldCollection documentFormFields = doc.Range.FormFields;
```

색인이나 이름으로 양식 필드를 검색할 수 있습니다. 이 예에서는 두 가지 방법을 모두 사용하여 양식 필드를 검색합니다.

```csharp
FormField formField1 = documentFormFields[3]; // 인덱스로 검색
FormField formField2 = documentFormFields["Text2"]; // 이름으로 검색 중
```

## 3단계: 양식 필드 속성 수정

양식 필드를 검색한 후에는 필요에 따라 해당 속성을 수정할 수 있습니다. 이 예에서는 글꼴 크기를 변경합니다.`formField1` 20까지와 글꼴 색상`formField2` 빨간색으로:

```csharp
formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;
```

## 4단계: 문서 저장

마지막으로 수정된 문서를 저장합니다.

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

그게 다야! .NET용 Aspose.Words를 사용하여 Word 문서에서 이름으로 양식 필드를 성공적으로 검색하고 해당 속성을 수정했습니다.

### .NET용 Aspose.Words를 사용하여 이름으로 가져오기 양식 필드에 대한 예제 소스 코드

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection documentFormFields = doc.Range.FormFields;

FormField formField1 = documentFormFields[3];
FormField formField2 = documentFormFields["Text2"];

formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;

doc.Save(dataDir + "ModifiedFormFields.docx");
```

자신의 프로젝트에서 이 코드를 자유롭게 사용하고 특정 요구 사항에 따라 수정하십시오.

### FAQ

#### Q: Aspose.Words에서 이름으로 양식 필드를 어떻게 얻을 수 있나요?

 A: Aspose.Words에서 이름으로 양식 필드를 얻으려면 다음을 사용할 수 있습니다.`Document.Range.FormFields[name]` 방법. 이 메소드는 지정된 이름에 해당하는 양식 필드를 반환합니다.

#### Q: 지정된 이름의 양식 필드가 문서에 존재하지 않으면 어떻게 되나요?

 A: 지정된 이름의 양식 필드가 문서에 존재하지 않는 경우`Document.Range.FormFields[name]` 메서드가 반환됩니다.`null`. 이 결과를 확인하여 양식 필드를 찾을 수 없는 경우를 처리할 수 있습니다.

#### Q: 찾은 양식 필드의 속성을 어떻게 수정합니까?

A: 이름으로 양식 필드를 얻은 후에는 해당 개별 속성에 액세스하여 편집할 수 있습니다. 예를 들어 필드 값을 변경하거나, 가시성을 활성화 또는 비활성화하거나, 필요에 따라 다른 속성을 수정할 수 있습니다.

#### Q: 문서에서 동일한 이름을 가진 여러 양식 필드를 얻을 수 있습니까?

 A: 예, 한 문서에 동일한 이름을 가진 여러 양식 필드가 있을 수 있습니다. 이 경우,`Document.Range.FormFields[name]` 메소드는 지정된 이름으로 발견된 첫 번째 양식 필드를 반환합니다. 이름이 같은 양식 필드가 여러 개 있는 경우 필드를 조작할 때 이를 고려해야 합니다.

#### Q: 문서의 모든 양식 필드를 반복하려면 어떻게 해야 합니까?

 A: 문서의 모든 양식 필드를 반복하려면`foreach` 루프에`Document.Range.FormFields` 수집. 이렇게 하면 각 양식 필드에 개별적으로 액세스하고 각 필드에 대한 작업을 수행할 수 있습니다.