---
title: SM\_SendRPL function
description: The SM\_SendRPL WMI method sends a read port list (RPL) command through the indicated port to indicated destination port.
ms.assetid: 9297d5eb-f8c4-48f3-8536-a94c66917e66
keywords: ["SM_SendRPL function Storage Devices"]
topic_type:
- apiref
api_name:
- SM_SendRPL
api_location:
- Hbapiwmi.h
api_type:
- HeaderDef
---

# SM\_SendRPL function


The SM\_SendRPL WMI method sends a read port list (RPL) command through the indicated port to indicated destination port.

Syntax
------

```ManagedCPlusPlus
void SM_SendRPL(
   [in, HBAType("HBA_WWN")] uint8              PortWWN[8],
   [in, HBAType("HBA_WWN")] uint8              AgentWWN[8],
   [in] uint32                                 AgentDomain,
   [in] uint32                                 PortIndex,
   [in] uint32                                 InRespBufferMaxSize,
   [out, HBA_STATUS_QUALIFIERS] HBA_STATUS     HBAStatus,
   [out] uint32                                TotalRespBufferSize,
   [out] uint32                                OutRespBufferSize,
   [out, WmiSizeIs("OutRespBufferSize")] uint8 RespBuffer[]
);
```

Parameters
----------

*PortWWN*   
A worldwide name (WWN) for the local port through which the read port list (RPL) command is sent. This information is delivered to the miniport driver in the PortWWN member of a SM\_SendRPL\_IN structure.

*AgentWWN*   
A worldwide name (WWN) for the port that is to be queried for a list of ports of type FC\_Port. For a definition of FC\_Port, see the T11 committee's *Fibre Channel HBA API* specification. This information is delivered to the miniport driver in the AgentWWN member of a SM\_SendRPL\_IN structure.

*AgentDomain*   
The domain number for the domain controller that is to be queried for a list of ports of type FC\_Port. For a definition of FC\_Port, see the T11 committee's *Fibre Channel HBA API* specification. This information is delivered to the miniport driver in the agent\_domain member of a SM\_SendRPL\_IN structure.

*PortIndex*   
The port index of the first port in the list of ports of type FC\_Port to be returned. This information is delivered to the miniport driver in the portIndex member of a SM\_SendRPL\_IN structure.

*InRespBufferMaxSize*   
The maximum size of the response buffer.

*HBAStatus*   
The status of the operation. For a list of allowed values and their descriptions, see [HBA\_STATUS](hba-status.md). The miniport driver returns this information in the HBAStatus member of a SendRPL\_OUT structure.

*TotalRespBufferSize*   
The size, in bytes, of the results of the read port list (RPL) command. The miniport driver returns this information in the TotalRespBufferSize member of a SM\_SendRPL\_OUT structure.

*OutRespBufferSize*   
The size, in bytes, of the data that was actually retrieved. The miniport driver returns this information in the OutRespBufferSize member of a SM\_SendRPL\_OUT structure.

*RespBuffer*   
The results of the read port list (RPL) command. The miniport driver returns this information in the RespBuffer member of a SendRPL\_OUT structure.

Return value
------------

Not applicable to WMI methods.

Remarks
-------

This WMI method belongs to the MS\_SM\_FabricAndDomainManagementMethods WMI Class.

Requirements
------------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>Target platform</p></td>
<td align="left">Desktop</td>
</tr>
<tr class="even">
<td align="left"><p>Header</p></td>
<td align="left">Hbapiwmi.h</td>
</tr>
</tbody>
</table>

## <span id="see_also"></span>See also


[HBA\_STATUS](hba-status.md)

[**SM\_SendRPL\_IN**](https://msdn.microsoft.com/library/windows/hardware/ff566314)

[**SM\_SendRPL\_OUT**](https://msdn.microsoft.com/library/windows/hardware/ff566315)

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20[storage\storage]:%20SM_SendRPL%20function%20%20RELEASE:%20%281/11/2018%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")





