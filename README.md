# .NET 10 애플리케이션 템플릿

* devcontainer를 사용하여 의존성 격리
* dockerfile를 사용하여 콘솔 앱의 이미지 빌드

콘솔 앱의 이미지를 빌드합니다.

```bash
# /DotnetTemplate
cd /src/DotnetTemplate.Console/
docker build -t dotnet_template_console:1.0 Dockerfile
```