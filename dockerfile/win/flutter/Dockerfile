FROM mcr.microsoft.com/windows/servercore:1809

#SHELL ["cmd", "/S", "/C"]
SHELL ["powershell"]

ADD https://github.com/git-for-windows/git/releases/download/v2.35.1.windows.2/MinGit-2.35.1.2-64-bit.zip C:/TEMP/MinGit.zip
RUN expand-Archive C:/TEMP/MinGit.zip -DestinationPath c:\Git; \
    cd c:\ ;\
  c:\Git\cmd\git clone https://github.com/flutter/flutter.git -b stable --depth 1
#RUN  set PATH=%PATH%;c:\flutter\bin ;\
RUN $Env:PATH += \";c:\flutter\bin;c:\git\cmd\" ;\
  flutter config --no-analytics; \
  flutter precache --web; \
  flutter doctor 
RUN 

RUN setx path \"%PATH%;c:\flutter\bin;c:\git\cmd\"

