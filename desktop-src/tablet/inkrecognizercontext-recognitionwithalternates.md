---
Description: Occurs when the InkRecognizerContext Class has generated results after calling the BackgroundRecognizeWithAlternates Method method.
ms.assetid: 5e86a4d5-c0a7-4283-81cc-ec3a26f74880
title: InkRecognizerContext.RecognitionWithAlternates event
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# InkRecognizerContext.RecognitionWithAlternates event

Occurs when the [**InkRecognizerContext Class**](/windows/win32/msinkaut/?branch=master) has generated results after calling the [**BackgroundRecognizeWithAlternates Method**](inkrecognizercontext-backgroundrecognizewithalternates.md) method.

## Syntax


```C++
void RecognitionWithAlternates(
  [in] IInkRecognitionResult *RecognitionResult,
  [in] VARIANT               CustomData,
  [in] InkRecognitionStatus  RecognitionStatus
);
```



## Parameters

<dl> <dt>

*RecognitionResult* \[in\]
</dt> <dd>

The recognition result from the event.

</dd> <dt>

*CustomData* \[in\]
</dt> <dd>

The custom data for the recognition result.

For more information about the VARIANT structure, see [Using the COM Library](using-the-com-library.md).

</dd> <dt>

*RecognitionStatus* \[in\]
</dt> <dd>

The recognition status as of the most recent recognition result.

</dd> </dl>

## Return value

This event does not return a value.

## Remarks

The behavior of the application programming interface (API) is unpredictable if you try to gain access to the original [**InkRecognizerContext**](/windows/win32/msinkaut/?branch=master) object from the recognition event handler. Do not attempt to do this. Instead, if you need to do this, create a flag and set it in the [**Recognition**](inkrecognizercontext-recognition.md) event handler. Then you can poll that flag to determine when to change the **InkRecognizerContext** properties outside of the event handler.

This event method is defined in the \_IInkEvents interface. The \_IInkEvents interface implements the [**IDispatch**](ebbff4bc-36b2-4861-9efa-ffa45e013eb5) interface with an identifier of DISPID\_IRERecognitionWithAlternates.

## Requirements



|                                     |                                                                                                                     |
|-------------------------------------|---------------------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP Tablet PC Edition \[desktop apps only\]<br/>                                                       |
| Minimum supported server<br/> | None supported<br/>                                                                                           |
| Header<br/>                   | <dl> <dt>Msinkaut.h (also requires Msinkaut\_i.c)</dt> </dl> |
| Library<br/>                  | <dl> <dt>InkObj.dll</dt> </dl>                               |



## See also

<dl> <dt>

[**InkRecognizerContext Class**](/windows/win32/msinkaut/?branch=master)
</dt> <dt>

[**BackgroundRecognizeWithAlternates Method**](inkrecognizercontext-backgroundrecognizewithalternates.md)
</dt> <dt>

[**Recognize Method**](/windows/win32/msinkaut/?branch=master)
</dt> <dt>

[**IInkRecognitionResult Interface**](/windows/win32/msinkaut/nn-msinkaut-iinkrecognitionresult?branch=master)
</dt> </dl>

 

 



