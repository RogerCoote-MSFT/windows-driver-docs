---
title: DEVPKEY_Device_DriverPropPageProvider
description: DEVPKEY_Device_DriverPropPageProvider
keywords: ["DEVPKEY_Device_DriverPropPageProvider Device and Driver Installation"]
topic_type:
- apiref
api_name:
- DEVPKEY_Device_DriverPropPageProvider
api_location:
- Devpkey.h
api_type:
- HeaderDef
ms.date: 10/17/2018
---

# DEVPKEY_Device_DriverPropPageProvider


The DEVPKEY_Device_DriverPropPageProvider device property represents the name of a DLL, and an entry point in the DLL, that is registered as a property page provider for a device instance.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr>
<th>Attribute</th>
<th>Value</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Property key</strong></p></td>
<td align="left"><p>DEVPKEY_Device_DriverPropPageProvider</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Property-data-type identifier</strong></p></td>
<td align="left"><p><a href="devprop-type-string.md" data-raw-source="[&lt;strong&gt;DEVPROP_TYPE_STRING&lt;/strong&gt;](devprop-type-string.md)"><strong>DEVPROP_TYPE_STRING</strong></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Property access</strong></p></td>
<td align="left"><p>Read-only access by installation applications and installers</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Corresponding registry value identifier and registry value name</strong></p></td>
<td align="left"><p>REGSTR_VAL_ENUMPROPPAGES_32</p>
<p><strong>EnumPropPages32</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Localized?</strong></p></td>
<td align="left"><p>No</p></td>
</tr>
</tbody>
</table>

 

## Remarks

You can set the value of DEVPKEY_Device_DriverPropPageProvider by using an [**INF AddReg directive**](./inf-addreg-directive.md) that is included the [**INF *DDInstall* section**](./inf-ddinstall-section.md) of the INF file that installs a device.

You can retrieve the value of DEVPKEY_Device_DriverPropPageProvider by calling [**SetupDiGetDeviceProperty**](/windows/win32/api/setupapi/nf-setupapi-setupdigetdevicepropertyw).

Windows Server 2003, Windows XP, and Windows 2000 support this property, but do not support the DEVPKEY_Device_DriverPropPageProvider property key. On these earlier versions of Windows, you can access the value of this property by accessing the corresponding **EnumPropPages32** registry value under the software key for the device instance. For information about how to access this property value on these earlier versions of Windows, see [Accessing Device Driver Properties](./accessing-device-driver-properties.md).

## Requirements

**Version**: Windows Vista and later versions of Windows
**Header**: Devpkey.h (include Devpkey.h)


## See also


[**INF AddReg Directive**](./inf-addreg-directive.md)

[**INF *DDInstall* Section**](./inf-ddinstall-section.md)

[**SetupDiGetDeviceProperty**](/windows/win32/api/setupapi/nf-setupapi-setupdigetdevicepropertyw)

 

