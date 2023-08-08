#Instalar os Apps pelo Choco

Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))

choco install --confirm googlechrome --force

choco install --confirm notepadplusplus.install --force

choco install --confirm  postman --force

#============================================================================================

#$Function de Realizar Download
function DownloadFile {
    param(
        [string]$url,
        [string]$outputPath
    )

    $webClient = New-Object System.Net.WebClient
    $webClient.DownloadFile($url, $outputPath)
}


#============================================================================================

$folderPath = "C:\Temp"

# Verificar se a pasta já existe
if (-not (Test-Path -Path $folderPath -PathType Container)) {
    # Se não existe, criar a pasta
    New-Item -Path $folderPath -ItemType Directory
    Write-Host "Pasta criada em $folderPath"
} else {
    Write-Host "A pasta já existe em $folderPath"
}

#============================================================================================

$icoUrl = "https://icon-icons.com/download/20403/PNG/72/"
#$TempFile = "$env:TEMP\notepad++.ico"
$TempFile  = "$folderPath\notepad++.png"

DownloadFile -url $icoUrl -outputPath $TempFile

#$origem = $TempFile
$destino = "C:\Program Files\Notepad++\"

# Copiar o arquivo da origem para o destino
Copy-Item -Path $TempFile -Destination $destino -Force

# Verificar se o arquivo foi copiado corretamente
if (Test-Path $destino) {
    Write-Host "Arquivo copiado com sucesso para $destino"
}
else {
    Write-Host "Falha ao copiar o arquivo."
    exit 1
}

Remove-Item -Path $TempFile -Force -Recurse

#============================================================================================




