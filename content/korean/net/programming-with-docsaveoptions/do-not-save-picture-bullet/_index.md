---
title: 그림 글머리 기호를 저장하지 마세요
linktitle: 그림 글머리 기호를 저장하지 마세요
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 이미지 글머리 기호 저장을 비활성화하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-docsaveoptions/do-not-save-picture-bullet/
---

그림 글머리 기호는 Word 문서에서 사용자 지정 글머리 기호를 추가하기 위해 일반적으로 사용되는 기능입니다. 그러나 경우에 따라 .NET용 Aspose.Words Library를 사용하여 문서를 조작할 때 이미지 글머리 기호 등록을 비활성화해야 할 수도 있습니다. 이 단계별 가이드에서는 .NET용 Aspose.Words C# 소스 코드를 사용하여 DocSaveOptions 저장 옵션을 사용하여 이미지 글머리 기호 저장을 비활성화하는 방법을 설명합니다.

## Aspose.Words 라이브러리 이해

코드를 살펴보기 전에 .NET용 Aspose.Words 라이브러리를 이해하는 것이 중요합니다. Aspose.Words는 .NET을 포함한 다양한 플랫폼에서 Word 문서를 생성, 편집, 변환 및 보호하는 강력한 라이브러리입니다. 텍스트 삽입, 서식 변경, 섹션 추가 등과 같은 문서 조작을 위한 다양한 기능을 제공합니다.

## 1단계: 문서 디렉토리 설정

첫 번째 단계는 문서가 있는 디렉터리를 정의하는 것입니다. 전체 디렉터리 경로를 지정해야 합니다. 예를 들어 :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

"YOUR DOCUMENTS DIRECTORY"를 문서 디렉토리의 실제 경로로 바꾸십시오.

## 2단계: 이미지 글머리 기호가 포함된 문서 로드

다음으로 이미지 글머리 기호가 있는 문서를 로드해야 합니다. Document 클래스를 사용하여 파일에서 문서를 로드합니다. 예를 들어 :

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

이 예에서는 "Image bullet points.docx" 파일에서 문서를 로드합니다.

  문서 디렉토리에 있습니다.

## 3단계: 녹음 옵션 구성

이제 문서의 저장 옵션을 구성해 보겠습니다. DocSaveOptions 클래스를 사용하여 저장 설정을 지정합니다. 예를 들어 :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };
```

이 예에서는 새 DocSaveOptions 개체를 만들고 SavePictureBullet 속성을 false로 설정하여 그림 글머리 기호 저장을 비활성화합니다.

## 4단계: "그림 글머리 기호 저장 안 함" 기능 활성화

"그림 글머리 기호 저장 안 함" 기능을 활성화하기 위해 이미 SavePictureBullet을 false로 설정하여 저장 옵션을 구성했습니다. 이렇게 하면 이미지 글머리 기호가 최종 문서에 저장되지 않습니다.

## 5단계: 문서 저장

마지막으로 Document 클래스의 Save 메서드를 사용하여 문서를 저장할 수 있습니다. 파일의 전체 경로와 원하는 파일 이름을 지정합니다. 예를 들어 :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

"dataDir"을 문서의 디렉터리 경로로 바꿔야 합니다.

## .NET용 Aspose.Words를 사용하는 "그림 글머리 기호 저장 안 함" 기능이 포함된 DocSaveOptions 저장 옵션의 예제 소스 코드

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 이미지 글머리 기호가 포함된 문서 로드
Document doc = new Document(dataDir + "Image bullet points.docx");

// "그림 글머리 기호 저장 안 함" 기능으로 저장 옵션 구성
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };

// 지정된 옵션으로 문서를 저장합니다.
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

## 결론

이 가이드에서는 .NET용 Aspose.Words 라이브러리를 사용하여 문서에서 이미지 글머리 기호 저장을 비활성화하는 방법을 다루었습니다. 제공된 단계를 따르고 제공된 C# 소스 코드를 사용하면 C# 애플리케이션에 이 기능을 쉽게 적용할 수 있습니다. 그림 글머리 기호 저장을 비활성화하면 그림 글머리 기호를 저장하지 않고 문서 구조와 서식을 유지하려는 상황에 따라 유용할 수 있습니다.