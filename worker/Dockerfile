FROM microsoft/dotnet:1.0.0-preview2-sdk

WORKDIR /worker/code

ADD /worker/src/Worker /worker/code/src/Worker

RUN dotnet restore -v minimal src/ \
    && dotnet publish -c Release -o ./ src/Worker/ \
    && rm -rf src/ $HOME/.nuget/

CMD dotnet Worker.dll
