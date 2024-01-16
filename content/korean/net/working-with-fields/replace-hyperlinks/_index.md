---
title: 하이퍼링크 바꾸기
linktitle: 하이퍼링크 바꾸기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서의 하이퍼링크를 바꿉니다. 하이퍼링크 교체에 대한 단계별 지침입니다.
type: docs
weight: 10
url: /ko/net/working-with-fields/replace-hyperlinks/
---

다음은 .NET 기능용 Aspose.Words를 사용하여 하이퍼링크를 대체하기 위한 다음 C# 소스 코드를 설명하는 단계별 가이드입니다. 이 코드를 사용하기 전에 프로젝트에 Aspose.Words 라이브러리를 포함했는지 확인하세요.

## 1단계: 문서 디렉터리 경로 설정

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

 다음을 포함하는 문서 디렉토리의 올바른 경로를 지정하십시오.`Hyperlinks.docx` 파일.

## 2단계: 하이퍼링크가 포함된 문서 로드

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

 여기서 우리는`Document` 지정된 파일의 클래스입니다.

## 3단계: 필드를 탐색하여 하이퍼링크 찾기

```csharp
foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // 일부 하이퍼링크는 로컬(문서 내부 책갈피에 대한 링크)일 수 있으므로 무시됩니다.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}
```

 이 루프는 문서의 모든 필드를 거쳐 다음 유형의 필드를 찾습니다.`FieldType.FieldHyperlink` . 이 유형의 필드가 발견되면 다음을 확인하여 로컬 링크인지 확인합니다.`SubAddress` 재산. 그렇지 않은 경우 링크 주소를 다음으로 바꿉니다.`"http://www.aspose.com"` 결과는`"Aspose - The .NET & Java Component Editor"`.

## 4단계: 수정된 문서 저장

```csharp
doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

마지막으로 지정된 파일에 대한 대체된 하이퍼링크와 함께 수정된 문서를 저장합니다.

### 하이퍼링크를 .NET용 Aspose.Words로 대체하는 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Hyperlinks.docx");

foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // 일부 하이퍼링크는 로컬(문서 내부 책갈피에 대한 링크)일 수 있으므로 무시됩니다.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}

doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Aspose.Words for .NET을 사용하여 문서의 하이퍼링크를 대체하는 샘플 소스 코드입니다.

### FAQ

#### Q: .NET용 Aspose.Words를 사용하여 Word 문서의 하이퍼링크를 어떻게 바꿀 수 있나요?

 A: .NET용 Aspose.Words를 사용하여 Word 문서의 하이퍼링크를 바꾸려면 다음을 사용할 수 있습니다.`Document.Range.Replace`검색할 텍스트와 대체 텍스트를 지정하는 메서드입니다. 검색 및 바꾸기 매개변수를 설정하려면 적절한 옵션을 사용해야 합니다.

#### Q: Word 문서의 특정 하이퍼링크만 Aspose.Words for .NET으로 바꿀 수 있나요?

A: 예, Word 문서의 특정 하이퍼링크만 Aspose.Words for .NET으로 바꾸는 것이 가능합니다. 링크 URL, 링크 텍스트 또는 기타 관련 속성과 같은 특정 기준을 사용하여 대체할 하이퍼링크를 필터링할 수 있습니다. 그런 다음 일치하는 하이퍼링크에만 대체를 적용할 수 있습니다.

#### Q: Aspose.Words for .NET으로 교체할 때 머리글, 바닥글 또는 각주의 하이퍼링크를 어떻게 무시할 수 있나요?

A: .NET용 Aspose.Words로 교체할 때 머리글, 바닥글 또는 각주의 하이퍼링크를 무시하려면 고급 검색 옵션을 사용하고 적절한 검색 제한을 지정할 수 있습니다. 예를 들어 문서의 주요 섹션으로 검색을 제한하고 머리글, 바닥글 또는 각주를 제외할 수 있습니다.

#### Q: 하이퍼링크를 문서의 다른 부분에 대한 내부 링크로 바꾸는 것이 가능합니까?

 A: 예, Aspose.Words for .NET을 사용하여 하이퍼링크를 문서의 다른 부분에 대한 내부 링크로 바꾸는 것이 가능합니다. 앵커나 텍스트 ID를 사용하여 내부 링크를 만든 다음`Document.Range.Replace` 적절한 옵션을 사용하는 방법입니다.

#### Q: 하이퍼링크를 .NET용 Aspose.Words로 바꾸면 색상이나 스타일과 같은 링크 속성이 유지됩니까?

A: 예, 하이퍼링크를 .NET용 Aspose.Words로 바꾸면 색상이나 스타일과 같은 링크 속성이 유지됩니다. 일관된 결과를 얻기 위해 대체 텍스트에 동일한 서식 속성을 지정할 수 있습니다.