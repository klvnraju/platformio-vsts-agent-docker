FROM microsoft/windowsservercore:10.0.14393.1358
ENV WINDOWS_IMAGE_VERSION=10.0.14393
MAINTAINER Nagaraju KLV <klvnraju@gmail.com>

ENV chocolateyUseWindowsCompression=false
RUN @powershell -NoProfile -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"

RUN choco config set cachelocation C:\chococache

RUN choco install \
    python2 \
    --confirm \
    --limit-output \
    --timeout 216000 \
    && rmdir /S /Q C:\chococache

RUN @powershell -NoProfile -ExecutionPolicy Bypass -Command "[Environment]::SetEnvironmentVariable(\"Path\", \"$env:Path;C:\\tools\\python\\Scripts\\\", \"User\")"

RUN pip install --upgrade pip

RUN pip install -U platformio \
    && platformio platforms install espressif8266

RUN mkdir C:\BuildAgent
WORKDIR C:/BuildAgent
COPY ./Start.* ./

CMD ["Start.cmd"]