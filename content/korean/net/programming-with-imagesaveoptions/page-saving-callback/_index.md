---
title: 페이지 저장 콜백
linktitle: 페이지 저장 콜백
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 문서 페이지를 이미지에 저장하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-imagesaveoptions/page-saving-callback/
---

이 튜토리얼에서는 .NET용 Aspose.Words 이미지 저장 옵션과 함께 페이지 저장 콜백을 사용하기 위해 제공되는 C# 소스 코드를 살펴보겠습니다. 이 기능을 사용하면 문서의 각 페이지를 이미지로 저장할 때 사용자 지정 작업을 수행할 수 있습니다.

## 1단계: 환경 설정

시작하기 전에 Aspose.Words for .NET을 사용하여 개발 환경을 설정했는지 확인하세요. 필요한 참조를 추가하고 적절한 네임스페이스를 가져왔는지 확인하세요.

## 2단계: 문서 로드

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 이 단계에서는 다음을 사용하여 문서를 로드합니다.`Document` 메서드를 사용하고 로드할 DOCX 파일의 경로를 전달합니다.

## 3단계: 이미지 백업 옵션 구성

```csharp
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
     PageSavingCallback = new HandlePageSavingCallback()
};
```

 이 단계에서는 새 이미지를 생성하여 이미지 저장 옵션을 구성합니다.`ImageSaveOptions` 물체. 원하는 백업 형식을 지정합니다. 여기서는 PNG 형식을 "Png"로 지정합니다. 우리는 사용`PageSet` 저장할 페이지 범위를 지정하려면 문서의 첫 번째 페이지부터 마지막 페이지까지(`doc.PageCount - 1`). 우리도 설정`PageSavingCallback` 다음의 인스턴스에`HandlePageSavingCallback`, 이는 페이지 저장 콜백을 처리하는 사용자 정의 클래스입니다.

## 4단계: 페이지 저장 콜백 구현

```csharp
public class HandlePageSavingCallback : IPageSavingCallback
{
     public void PageSaving(PageSavingArgs args)
     {
         // 여기에 맞춤 작업을 구현하세요.
         // "args.PageIndex" 속성을 통해 페이지 정보에 액세스할 수 있습니다.
         // 각 페이지의 저장 옵션을 개별적으로 변경할 수도 있습니다.
     }
}
```

 이 단계에서는 다음을 구현합니다.`HandlePageSavingCallback` 구현하는 클래스`IPageSavingCallback` 상호 작용. 특정 작업을`PageSaving` 방법. 다음을 통해 페이지 정보에 액세스할 수 있습니다.`args.PageIndex` 의 재산`PageSavingArgs` 인수로 전달된 개체입니다.

## 5단계: 페이지를 이미지로 저장

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

 이 마지막 단계에서는 문서의 각 페이지를 이미지로 저장합니다.`Save` 메서드를 사용하여 출력 파일의 경로를 전달합니다.`.png` 확장명과 함께 지정된 저장 옵션이 포함됩니다.

이제 문서의 각 페이지를 이미지로 저장할 때 소스 코드를 실행하여 사용자 지정 작업을 수행할 수 있습니다. 결과 파일은 "WorkingWithImageSaveOptions.PageSavingCallback.png"라는 이름으로 지정된 디렉터리에 저장됩니다.

### .NET용 Aspose.Words를 사용하는 페이지 저장 콜백의 샘플 소스 코드


```csharp 
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY"; 


Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
	PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
	PageSavingCallback = new HandlePageSavingCallback()
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
        
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.Words 이미지 저장 옵션을 사용하여 페이지 저장 콜백 기능을 살펴보았습니다. 문서의 각 페이지를 이미지로 저장할 때 사용자 지정 작업을 수행하는 방법을 배웠습니다.

이 기능은 이미지로 변환할 때 각 페이지에서 특정 작업을 수행하려는 경우에 유용합니다. 페이지 정보에 액세스하고 이를 사용하여 백업 옵션을 사용자 정의하거나 기타 페이지별 처리를 수행할 수 있습니다.

Aspose.Words for .NET은 문서 조작 및 생성을 위한 광범위한 고급 기능을 제공합니다. 페이지 저장 알림은 페이지를 이미지로 저장하는 프로세스를 사용자 정의할 수 있는 많은 강력한 도구 중 하나입니다.