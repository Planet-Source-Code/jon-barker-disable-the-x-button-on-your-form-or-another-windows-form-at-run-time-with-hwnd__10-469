<div align="center">

## \_ Disable the X button on your form, or another Windows form at run\-time \(with HWND\)  \_


</div>

### Description

This code will disable the X button on any form you know the HWND (unique number) for.

To test this code on your own application, provide the function with ActiveForm.Handle().ToInt32()
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Jon Barker](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/jon-barker.md)
**Level**          |Beginner
**User Rating**    |4.3 (26 globes from 6 users)
**Compatibility**  |VB\.NET
**Category**       |[System Services/ Functions](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/system-services-functions__10-23.md)
**World**          |[\.Net \(C\#, VB\.net\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/net-c-vb-net.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/jon-barker-disable-the-x-button-on-your-form-or-another-windows-form-at-run-time-with-hwnd__10-469/archive/master.zip)





### Source Code

```
Public Declare Function GetSystemMenu Lib "user32" (ByVal hwnd As Integer, ByVal bRevert As Integer) As Integer
 Public Declare Function RemoveMenu Lib "user32" (ByVal hMenu As Integer, ByVal nPosition As Integer, ByVal wFlags As Integer) As Integer
Public Const SC_CLOSE = &HF060&
Public Const MF_BYCOMMAND = &H0&
Function RemoveXButton(ByVal iHWND As Integer) As Integer
  Dim iSysMenu As Integer
  iSysMenu = GetSystemMenu(iHWND, False)
  Return RemoveMenu(iSysMenu, SC_CLOSE, MF_BYCOMMAND)
 End Function
'Disable the button on the current form:
RemoveXButton(ActiveForm.Handle().ToInt32())
'Thats it! tHe_cLeanER ownz you...
```

