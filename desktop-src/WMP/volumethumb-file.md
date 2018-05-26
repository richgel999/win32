---
title: VolumeThumb File
description: VolumeThumb File
ms.assetid: 1e096a38-5688-4f62-b58f-954e910c5259
keywords:
- Windows Media Player Mobile skins,art files
- skins,art files
- files for skins,art
- art files for skins,VolumeThumb files
- Windows Media Player Mobile skins,VolumeThumb files
- skins,VolumeThumb files
- VolumeThumb files in skins
- thumb,VolumeThumb files
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# VolumeThumb File

The VolumeThumb file defines the image that indicates the playback volume level for a Volume trackbar. You can use one file and define it for use by both SeekThumb and VolumeThumb. Unlike the other art files, the thumb files are defined in the Trackbars section of the skin definition file.

The following image is a typical VolumeThumb file.

![volumethumb file](images/cesdkvol.png)

These two button files look the same but are slightly different sizes. The left image is the normal view that the user sees, and the right image is the Pushed image the user sees when they tap on the button.

You may want to make certain areas of the thumb images transparent. This will allow you to create thumb images in shapes other than rectangular. Any region of a thumb image that you fill with the color specified by the RGB value 255, 0, 255 will appear transparent in your skin.

## Related topics

<dl> <dt>

[**Art Files**](art-files-mobile.md)
</dt> </dl>

 

 



