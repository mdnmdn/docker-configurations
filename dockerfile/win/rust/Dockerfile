FROM mcr.microsoft.com/windows/servercore:1809

SHELL ["cmd", "/S", "/C"]

ADD https://aka.ms/vs/15/release/vs_buildtools.exe C:/TEMP/vs_buildtools.exe
ADD https://static.rust-lang.org/rustup/dist/i686-pc-windows-gnu/rustup-init.exe C:/TEMP/rustup-init.exe

RUN C:/TEMP/vs_buildtools.exe --quiet --wait --norestart --nocache --installPath C:\BuildTool  --includeRecommended   --add Microsoft.VisualStudio.Workload.ManagedDesktopBuildTools  --add Microsoft.VisualStudio.Workload.MSBuildTools --add Microsoft.VisualStudio.Workload.VCTools
RUN C:/TEMP/rustup-init.exe -y -v --default-toolchain stable-x86_64-pc-windows-msvc
RUN setx path "%path%;%USERPROFILE%/.cargo/bin"
