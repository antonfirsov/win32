---
title: CDN\_FOLDERCHANGE notification code
description: Sent by an Explorer-style Open or Save As dialog box when a new folder is opened.
ms.assetid: '864ab80d-cd99-4dd6-8aff-49beed246e53'
keywords: ["CDN_FOLDERCHANGE notification code Dialog Boxes"]
topic_type:
- apiref
api_name:
- CDN_FOLDERCHANGE
api_location:
- Commdlg.h
api_type:
- HeaderDef
---

# CDN\_FOLDERCHANGE notification code

\[Starting with Windows�Vista, the **Open** and **Save As** common dialog boxes have been superseded by the [Common Item Dialog](_shell_common_file_dialog). We recommended that you use the Common Item Dialog API instead of these dialog boxes from the Common Dialog Box Library.\]

Sent by an Explorer-style **Open** or **Save As** dialog box when a new folder is opened.

Your [*OFNHookProc*](ofnhookproc.md) hook procedure receives this message in the form of a [**WM\_NOTIFY**](_win32_WM_NOTIFY) message.


```C++
#define CDN_FIRST               (0U-601U)
#define CDN_FOLDERCHANGE        (CDN_FIRST - 0x0002)
```



## Parameters

<dl> <dt>

*wParam* 
</dt> <dd>

This parameter is not used.

</dd> <dt>

*lParam* 
</dt> <dd>

A pointer to an [**OFNOTIFY**](ofnotify-str.md) structure. The **OFNOTIFY** structure contains an [**NMHDR**](_win32_nmhdr_str) structure whose **code** member indicates the **CDN\_FOLDERCHANGE** notification message.

</dd> </dl>

## Return value

The return value is ignored.

## Remarks

The system sends this notification only if the dialog box was created using the **OFN\_EXPLORER** value.

To get the path of the newly opened folder, the hook procedure can send the [**CDM\_GETFOLDERPATH**](cdm-getfolderpath.md) message to the dialog box.

## Requirements



|                                     |                                                                                                          |
|-------------------------------------|----------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows�2000 Professional \[desktop apps only\]<br/>                                               |
| Minimum supported server<br/> | Windows�2000 Server \[desktop apps only\]<br/>                                                     |
| Header<br/>                   | <dl> <dt>Commdlg.h (include Windows.h)</dt> </dl> |



## See also

<dl> <dt>

**Reference**
</dt> <dt>

[**CDM\_GETFOLDERPATH**](cdm-getfolderpath.md)
</dt> <dt>

[**GetOpenFileName**](getopenfilename.md)
</dt> <dt>

[**GetSaveFileName**](getsavefilename.md)
</dt> <dt>

[*OFNHookProc*](ofnhookproc.md)
</dt> <dt>

[**OFNOTIFY**](ofnotify-str.md)
</dt> <dt>

**Conceptual**
</dt> <dt>

[Common Dialog Box Library](common-dialog-box-library.md)
</dt> </dl>

�

�




