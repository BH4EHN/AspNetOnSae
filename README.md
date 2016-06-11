# AspNetOnSae
Run ASP.NET MVC/WebForm application on [SinaAppEngine](http://www.sinacloud.com/sae.html)  
* Any [ASP.NET MVC 5](http://www.asp.net/mvc/overview/getting-started/introduction/getting-started) or less and ASP.NET WebForm should support
- This is **NOT** .NET Core or ASP.NET 5
- Should run on ANY PaaS support Docker
* Based on [Ubuntu 14.04 docker image](https://github.com/dockerfile/ubuntu) and latest [Mono beta](http://www.mono-project.com/download/beta/) build

Just create `Dockerfile` in your solution folder (besides `.sln` file)
```Dockerfile
FROM cloveryang/mono-xsp4
WORKDIR /var/app/source/YourProjectName
EXPOSE 5050
CMD ["IOMAP=all", "xsp4", "--port 5050", "--nonstop"]
```
replace the port require by PaaS (5050 is for SinaAppEngine)
