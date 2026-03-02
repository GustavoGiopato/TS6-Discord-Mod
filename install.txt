@echo off
echo ======================================

set TARGET=%LOCALAPPDATA%\Programs\TeamSpeak\html\client_ui\sound\default
set SOURCE=%~dp0default

echo.
echo Searching TeamSpeak Files

if not exist "%TARGET%" (
    echo ERROR: Path not found.
    echo Expected Path:
    echo %TARGET%
    pause
    exit
)

echo.
echo Backing up the original Folder...

if not exist "%TARGET%_backup" (
    xcopy "%TARGET%" "%TARGET%_backup" /E /I /H /Y
)

echo.
echo Coping new sounds...

xcopy "%SOURCE%" "%TARGET%" /E /I /H /Y

echo.
echo Sounds installed successfully!
echo Restart the client if its open.
echo
echo ======================================
echo  TeamSpeak 6 Discord Sound Installer
echo  From: Sua Gatinha, Roki  
echo ======================================
pause