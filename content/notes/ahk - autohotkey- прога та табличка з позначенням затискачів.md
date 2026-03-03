---
title: "ahk - autohotkey- прога и табличка с обозначением зажималок"
Alias: 
tags:
- green/seed
date: 2023-08-04 10:59
---
Links:  
04.02.2022 / 0233  
табличка с обозначением зажималок (Ctrl, Shift)

```copy
; верхний регистр 1-0, хъжэ\<>/
!vk31::SendInput {!}
!vk32::SendInput {@} 
!vk33::SendInput {#}
!vk34::SendInput {;}
!vk36::SendInput {:}
!vk37::SendInput {?}
!vk38::SendInput {*}
!vk39::SendInput {(}
!vk30::SendInput {)}
!vkBA::SendInput {;}
!vkDB::SendInput {[}
!vkDD::SendInput {]}
!vkBC::SendInput {<}
!vkBE::SendInput {>}
!vkC0::SendInput {~}
!vkBF::SendInput {/}
!vkDC::SendInput {|}
!vkDE::SendInput {"}
;укр клавиши
!^vkDE::SendRaw є
!^+vkDE::SendRaw Є
!^vk53::SendRaw і
!^+vk53::SendRaw І
!^vkDD::SendRaw ї
!^+vkDD::SendRaw Ї
!^vkBF::SendRaw ’
; вместо дефиса тире 
!vkBD::SendInput {—}


; Win+F1- справка по прграмме
#F1::
MsgBox,
, HotKeys:
, win+F3-VPN`nwin+F8 - воспроизведение`nwin+F12 - поверх окон`n`n
, ctrl+L - выделить строку `n, win+o - obsidian`n, alt+(любая клавиша2-7)`n
, win+c - поиск в гугл выделенного текста`n, win+y- поиск в youtube `n
, ctrl+alt-укр, ctrl+alt+shift-большие укр
return 

; шаблон для даты
:*:datew:: 
FormatTime, CurrentDateTime,, dd.MM.yyyy
SendInput %CurrentDateTime%
return

; Win+F3 - Запустить оперу и открыть ссылку через впн
#F3::
Send, ^c
Run, D:\Programms\OperaGX\launcher.exe
sleep, 2000
WinWait, ahk_exe opera.exe
WinMaximize ; Использует окно, найденное выше.
IfWinExist ahk_exe opera.exe
{
WinActivate
sleep, 2500
Click 175,53
sleep, 100
Click 50,69
sleep, 100
Click 200,0
sleep, 100
Send, ^v {ENTER}
return
}

; Win+F8 Пауза/Плей
#F8::
DetectHiddenWindows, on
IfWinExist ahk_exe browser.exe
	SendInput, {Media_Play_Pause}
Return

; Win+F12 - выбранное окно поверх других
#F12:: Winset, Alwaysontop, , A

; ctrl+L - выделить строку
^vk4C::
send {HOME}{SHIFTDOWN}{END}{SHIFTUP}  
return

; Win+с - поиск выделеного в google
#c::
{ 
 Send, ^c
 Sleep 50 
 Run, https://www.google.com/search?q=%clipboard%
 Return
}

; Win+y - поиск выделеного в youtybe
#y::
{ 
 Send, ^c
 Sleep 50 
 Run, https://www.youtube.com/results?search_query=%clipboard%
 Return
}

; Win+o - открыть Obsidian и добавить запись
#vk4F::
IfWinExist ahk_exe Obsidian.exe
{
WinActivate
Sleep 50
Send, ^o
return
}
else
{
Run C:\Users\q2pj\AppData\Local\Obsidian\Obsidian.exe
WinWait, ahk_exe Obsidian.exe
WinMaximize ;Использует окно, найденное выше.
WinActivate ahk_exe Obsidian.exe
Sleep 500
Send, ^o
return
}


```

CTRL+J отправит ку-ку  
^j::  
Send, ку-ку

ftw отправит Free the whales  
::ftw::Free the whales

Выдает окошко с надписью Escape  
Esc::  
MsgBox, Escape!!!!

Открытия сайта в браузере по умолчанию

```copy
#z::Run www.autohotkey.com
```

Открывает блокнот. Если открыт - открывает новый  
Нижеприведенный сценарий начинается с сочетания клавиш Ctrl + Alt + n, следующие четыре строки — это команда if else, которая на английском языке переводится как «если существует окно без имени в блокноте, сделайте это окно активным, иначе запустите новый блокнот».

```copy
^!n::
{
IfWinExist Untitled - Notepad  
WinActivate  
else  
Run Notepad  
return
}
```

В приведенном ниже примере в строках три и четыре показано, как можно нажимать клавиши в скрипте для выполнения других сочетаний клавиш. Третья строка нажимает Ctrl + Shift + Home, чтобы выделить весь текст перед курсором, а следующая строка нажимает Ctrl + C, чтобы скопировать выделенный текст. Каждый раз, когда нажимается клавиша (например, {CTRLDOWN}), убедитесь, что она отпущена вверх (например, {CTRLUP}), в противном случае она останется нажатой и вызовет проблемы.

Пятая строка представляет переменную и команду% clipboard%, которая содержит что-либо в вашем буфере обмена. С этой строкой все содержимое в буфере обмена присваивается переменной example.

```copy
#F2::
{
send Hello World{!}  
send {CTRLDOWN}{SHIFTDOWN}{HOME}{CTRLUP}{SHIFTUP}  
send {CTRLDOWN}c{CTRLUP}{END}  
example = %clipboard%  
return
}
```

В первом примере откроется Obsidian  , окно в развернутом виде

```copy
#F2::Run, C:\Users\q2pj\AppData\Local\Obsidian\Obsidian.exe, max
```

С помощью этой команды, как только Win + F2 нажата, мышь щелкнет один раз в точку 980 381.

```copy

#F2::  
Click 980,381  
return

```

Проверяет, открыто ли  приложение. Если открыто - закрыть. Если закрыто - открыть

```copy
^#F2::
Process, Exist, Obsidian.exe
if (ErrorLevel) 
{
	Process, Close, Obsidian.exe 
}
else
Run, C:\Users\q2pj\AppData\Local\Obsidian\Obsidian.exe
return

```

Поиск выделенного слова в гугл, при нажатии **Ctrl + Shift + C**.

```copy

^#c::
{ 
 Send, ^c 
 Sleep 50 
 Run, https://www.google.com/search?q=%clipboard%
 Return
}

```

—  
Zero-Links  
[00 win](../0%20Z-core/00%20win.md)  
—  
Links

### Примеры выше с сайта(+ там есть подробный гайд: клики мыши, разные комбинации, запуск программы):
https://komputer03.ru/avtomatizirujte-svoju-rabotu-s-autohotkey

### для переключения виртуальных столов:
https://komputer03.ru/ispolzovanie-autohotkey-dlja-perekljuchenija


