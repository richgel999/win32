---
Description: The photo metadata policy for the System.Photo.Sharpness property.
ms.assetid: 0fda4832-940b-4b5a-bd20-7e48c7800925
title: System.Photo.Sharpness Photo Metadata Policy
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# System.Photo.Sharpness Photo Metadata Policy

The photo metadata policy for the [System.Photo.Sharpness](http://msdn.microsoft.com/en-us/library/bb787263(VS.85).aspx) property.

### PKEY

PKEY\_Photo\_Sharpness

### Containers

JPEG, TIFF

### Read-Only

No

### Output PROPVARIANT Type

VT\_UI4

### Input Type

UShort

### Conflict Resolution Policy

Values from different schemas are reconciled.

### JPEG Policy

### Read Paths



| Order | Path                          | Disk Format |
|-------|-------------------------------|-------------|
| 1     | /app1/ifd/exif/{ushort=41994} | ushort      |
| 2     | /xmp/exif:Sharpness           | unicode     |



 

### Write Paths



| Order | Path                          | Disk Format |
|-------|-------------------------------|-------------|
| 1     | /app1/ifd/exif/{ushort=41994} | ushort      |
| 2     | /xmp/exif:Sharpness           | unicode     |



 

### Remove Paths



| Order | Path                          |
|-------|-------------------------------|
| 1     | /app1/ifd/exif/{ushort=41994} |
| 2     | /xmp/exif:sharpness           |



 

### TIFF Policies

### Read Paths



| Order | Path                     | Disk Format |
|-------|--------------------------|-------------|
| 1     | /ifd/exif/{ushort=41994} | ushort      |
| 2     | /ifd/xmp/exif:Sharpness  | unicode     |



 

### Write Paths



| Order | Path                     | Disk Format |
|-------|--------------------------|-------------|
| 1     | /ifd/exif/{ushort=41994} | ushort      |
| 2     | /ifd/xmp/exif:Sharpness  | unicode     |



 

### Remove Paths



| Order | Path                     |
|-------|--------------------------|
| 1     | /ifd/exif/{ushort=41994} |
| 2     | /ifd/xmp/exif:sharpness  |



 

## Remarks

## Related topics

<dl> <dt>

[System.Photo.Sharpness](http://msdn.microsoft.com/en-us/library/bb787263(VS.85).aspx)
</dt> </dl>

 

 


