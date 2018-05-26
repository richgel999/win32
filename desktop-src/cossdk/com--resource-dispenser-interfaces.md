---
Description: COM+ Resource Dispenser Interfaces
ms.assetid: 66ee4dd6-15d2-49e8-89a3-6fbb5770cabf
title: COM+ Resource Dispenser Interfaces
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# COM+ Resource Dispenser Interfaces

Application components use resource dispensers to access shared information. The interfaces described in the following table provide detailed reference information for developers of resource dispensers.



| Interfaces                                                | Description                                                                                                               |
|-----------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|
| [**IDispenserDriver**](/windows/win32/ComSvcs/nn-comsvcs-idispenserdriver?branch=master)<br/>   | This interface is called by the resource dispenser holder to create, enlist, evaluate, and destroy a resource.<br/> |
| [**IDispenserManager**](/windows/win32/ComSvcs/nn-comsvcs-idispensermanager?branch=master)<br/> | Resource dispensers use this interface to connect to the dispenser manager.<br/>                                    |
| [**IHolder**](/windows/win32/ComSvcs/nn-comsvcs-iholder?branch=master)<br/>                     | This interface is used to prepare and handle resources.<br/>                                                        |



 

## Related topics

<dl> <dt>

[COM+ Resource Dispenser Concepts](com--resource-dispenser-concepts.md)
</dt> <dt>

[Types Used in COM+ Resource Dispenser Interfaces](types-used-in-com--resource-dispenser-interfaces.md)
</dt> </dl>

 

 



