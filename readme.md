## REPO: bug when literal route constraint appears twice in the url

https://github.com/dotnet/aspnetcore/issues/47587

#### Tested with target framework
- net7.0
- net8.0

---

✅ **FOO works**
- https://localhost:7267/weatherforecast/aa
- https://localhost:7267/weatherforecast/a0
- https://localhost:7267/weatherforecast/a0a
- https://localhost:7267/weatherforecast/ab
- https://localhost:7267/weatherforecast/a0b
- https://localhost:7267/weatherforecast/a0b0

❌ **FOO doesn't work**
- https://localhost:7267/weatherforecast/a0a0

---

✅ **BAR works**
- https://localhost:7267/weatherforecast/bb
- https://localhost:7267/weatherforecast/b0
- https://localhost:7267/weatherforecast/b0b
- https://localhost:7267/weatherforecast/b0a0

❌ **BAR doesn't work**
- https://localhost:7267/weatherforecast/b0b0

---

```
.NET SDK:
 Version:   8.0.100-preview.2.23157.25
 Commit:    54801b2435

Runtime Environment:
 OS Name:     Windows
 OS Version:  10.0.22621
 OS Platform: Windows
 RID:         win10-x64
 Base Path:   C:\Program Files\dotnet\sdk\8.0.100-preview.2.23157.25\

Host:
  Version:      8.0.0-preview.2.23128.3
  Architecture: x64
  Commit:       30b879924a

.NET SDKs installed:
  7.0.104 [C:\Program Files\dotnet\sdk]
  7.0.202 [C:\Program Files\dotnet\sdk]
  7.0.300-preview.23122.5 [C:\Program Files\dotnet\sdk]
  8.0.100-preview.2.23157.25 [C:\Program Files\dotnet\sdk]

.NET runtimes installed:
  Microsoft.AspNetCore.App 7.0.4 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
  Microsoft.AspNetCore.App 8.0.0-preview.2.23153.2 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
  Microsoft.NETCore.App 7.0.4 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
  Microsoft.NETCore.App 8.0.0-preview.2.23128.3 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
  Microsoft.WindowsDesktop.App 7.0.4 [C:\Program Files\dotnet\shared\Microsoft.WindowsDesktop.App]
  Microsoft.WindowsDesktop.App 8.0.0-preview.2.23128.5 [C:\Program Files\dotnet\shared\Microsoft.WindowsDesktop.App]
```
