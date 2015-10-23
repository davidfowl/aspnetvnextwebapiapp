### .NET Generations

### Terms and examples
- **Platform** - e.g. .NET Framework 4.5, Windows Phone 8.1
- **Generation** - A representation of the common surface area across *all* Platforms.

Platforms expose .NET surface area from a particular generation.

Below is the mapping table from platform to generation. Targeting a generation means you can run on the platform specified on the right. 

e.g. If a library targets Generation 5.4, it can run *only* run on .NET 4.6, Universal Windows Platform 10 (UWP) and DNX Core 5.0

| Generation | Supported Platforms |
| :---------- | :--------- |
| 5.1 |.NET Framework >= 4.5 |
||Windows >= 8 |
||Windows Phone >= 8.1|
||Universal Windows Platform 10 (UWP) |
||DNX Core >= 5.0|
||Windows Phone Silverlight 8 |
||Windows Phone Silverlight 8.1 |
| 5.2 |.NET Framework >= 4.5 | 
||Windows >= 8| 
||Windows Phone >= 8.1| 
||Universal Windows Platform 10 (UWP)|
||DNX Core >= 5.0 |
|5.3|.NET Framework >= 4.5.1| 
||Windows >= 8.1| 
||Windows Phone >= 8.1| 
||Universal Windows Platform 10 (UWP)| 
||DNX Core >= 5.0 |
|5.4|.NET Framework >= 4.6| 
||Universal Windows Platform 10 (UWP)| 
||DNX Core >= 5.0|
|5.5|.NET Framework >= 4.6.x| 
||DNX Core >= 5.0|

Each generation enables more features, which means it's available on fewer platforms. As the platforms rev, their newer versions jump up into newer generation buckets.
Platforms which have stopped revving -- like Silverlight on the phone -- will only ever be available in the earliest generations.

**TODO: Xamarin Platforms**

### NuGet mapping
When building a NuGet package, specifing folder with the mapping is enough to indicate what platforms your package targets.

MyPackage
```
MyPackage/lib/net45/MyPackage.dll
```

The above package targets .NET Framework 4.5.

**TODO: List other rules around dependency groups in nuget packages with examples.**

#### Generation mapping

| Generation | NuGet identifier |
| ---------| --------------- |
| 5.1-5.5 | dotnet5.1, dotnet5.5 |

#### Specific platform mapping

| Platform | NuGet identifier |
| ---------| --------------- |
| .NET Framework 2.0-4.6 | net20 - net46 |
| Windows 8 | win8, netcore45 |
| Windows 8.1 | win8, netcore451 |
| Windows Phone Silverlight (8, 8.1) | wp8, wp81 |
| Windows Phone 8.1 | wpa8.1 |
| Universal Windows Platform 10 | uap10, netcore50 |
| DNX Core 5.0 | dnxcore50  |

### List of BCL APIs and their associated generations

#### Legend 
- `X` - API appeared in specific generation
- `⇠` - API version determined by nearest `X` e.g. In the table below, if you target generation 5.5 and reference Microsoft.CSharp, you'd get the 5.1 API version.

| Contract | 5.1 | 5.2 | 5.3 | 5.4 | 5.5 |
| -------- | --- | --- | --- | --- | --- |
| Microsoft.CSharp | X | ⇠ | ⇠ | ⇠ | ⇠ |
| Microsoft.VisualBasic |  | X | ⇠ | ⇠ | ⇠ |
| Microsoft.Win32.Primitives | X | ⇠ | ⇠ | ⇠ | ⇠ |
| Microsoft.Win32.Registry |  | X | ⇠ | ⇠ | ⇠ |
| Microsoft.Win32.Registry.AccessControl | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.AppContext | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Collections | X | ⇠ | ⇠ | X | ⇠ |
| System.Collections.Concurrent |  | X | ⇠ | X | ⇠ |
| System.Collections.NonGeneric | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Collections.Specialized | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.ComponentModel | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.ComponentModel.Annotations |  | X | ⇠ | X | ⇠ |
| System.ComponentModel.EventBasedAsync | X | ⇠ | ⇠ | X | ⇠ |
| System.ComponentModel.Primitives | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.ComponentModel.TypeConverter | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Console | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Data.Common | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Data.SqlClient | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Diagnostics.Contracts | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Diagnostics.Debug | X | ⇠ | ⇠ | X | ⇠ |
| System.Diagnostics.FileVersionInfo | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Diagnostics.Process |  |  |  | X | X |
| System.Diagnostics.StackTrace | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Diagnostics.TextWriterTraceListener | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Diagnostics.Tools | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Diagnostics.TraceSource | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Diagnostics.Tracing |  | X | X | X | ⇠ |
| System.Dynamic.Runtime | X | ⇠ | ⇠ | X | ⇠ |
| System.Globalization | X | ⇠ | ⇠ | X | ⇠ |
| System.Globalization.Calendars | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Globalization.Extensions | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.IO | X | ⇠ | ⇠ | X | ⇠ |
| System.IO.Compression |  | X | ⇠ | ⇠ | ⇠ |
| System.IO.Compression.ZipFile |  | X | ⇠ | ⇠ | ⇠ |
| System.IO.FileSystem |  |  |  | X | ⇠ |
| System.IO.FileSystem.AccessControl | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.IO.FileSystem.DriveInfo | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.IO.FileSystem.Primitives | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.IO.FileSystem.Watcher | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.IO.IsolatedStorage | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.IO.MemoryMappedFiles |  |  |  | X | ⇠ |
| System.IO.Pipes |  |  |  | X | ⇠ |
| System.IO.UnmanagedMemoryStream |  | X | ⇠ | ⇠ | ⇠ |
| System.Linq | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Linq.Expressions | X | ⇠ | ⇠ | X | ⇠ |
| System.Linq.Parallel |  | X | ⇠ | ⇠ | ⇠ |
| System.Linq.Queryable | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Net.Http |  | X | ⇠ | ⇠ | ⇠ |
| System.Net.Http.Rtc |  | X | ⇠ | ⇠ | ⇠ |
| System.Net.NameResolution |  |  |  | X | ⇠ |
| System.Net.NetworkInformation | X | ⇠ | ⇠ | ⇠ | X |
| System.Net.Primitives | X | X | ⇠ | X | ⇠ |
| System.Net.Requests | X | X | ⇠ | X | ⇠ |
| System.Net.Security |  |  |  | X | ⇠ |
| System.Net.Sockets |  |  |  | X | X |
| System.Net.Utilities |  |  |  | X | ⇠ |
| System.Net.WebHeaderCollection |  |  |  | X | ⇠ |
| System.Net.WebSockets | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Net.WebSockets.Client |  |  |  | X | ⇠ |
| System.Numerics.Vectors |  |  |  | X | ⇠ |
| System.ObjectModel | X | ⇠ | ⇠ | X | ⇠ |
| System.Reflection | X | ⇠ | ⇠ | X | X |
| System.Reflection.Context |  | X | ⇠ | ⇠ | ⇠ |
| System.Reflection.DispatchProxy | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Reflection.Emit |  | X | ⇠ | ⇠ | ⇠ |
| System.Reflection.Emit.ILGeneration | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Reflection.Emit.Lightweight | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Reflection.Extensions | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Reflection.Primitives | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Reflection.TypeExtensions | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Resources.ReaderWriter | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Resources.ResourceManager | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Runtime | X | ⇠ | X | X | ⇠ |
| System.Runtime.CompilerServices.VisualC | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Runtime.Extensions | X | ⇠ | ⇠ | X | ⇠ |
| System.Runtime.Handles |  |  |  | X | ⇠ |
| System.Runtime.InteropServices |  | X | X | X | ⇠ |
| System.Runtime.InteropServices.RuntimeInformation | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Runtime.InteropServices.WindowsRuntime | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Runtime.Loader | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Runtime.Numerics |  | X | ⇠ | ⇠ | ⇠ |
| System.Runtime.Serialization.Json | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Runtime.Serialization.Primitives | X | ⇠ | ⇠ | X | ⇠ |
| System.Runtime.Serialization.Xml | X | ⇠ | ⇠ | X | ⇠ |
| System.Runtime.WindowsRuntime | X | ⇠ | X | ⇠ | ⇠ |
| System.Runtime.WindowsRuntime.UI.Xaml |  | X | ⇠ | ⇠ | ⇠ |
| System.Security.AccessControl |  |  |  | X | ⇠ |
| System.Security.Claims | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Security.Cryptography.Algorithms | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Security.Cryptography.Cng |  | X | ⇠ | ⇠ | ⇠ |
| System.Security.Cryptography.Csp | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Security.Cryptography.Encoding | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Security.Cryptography.OpenSsl |  |  |  | X | ⇠ |
| System.Security.Cryptography.Primitives | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Security.Cryptography.X509Certificates |  |  |  | X | ⇠ |
| System.Security.Principal | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Security.Principal.Windows |  |  |  | X | ⇠ |
| System.ServiceModel.Duplex |  | X | ⇠ | ⇠ | ⇠ |
| System.ServiceModel.Http | X | X | ⇠ | X | ⇠ |
| System.ServiceModel.NetTcp |  | X | ⇠ | X | ⇠ |
| System.ServiceModel.Primitives | X | X | ⇠ | X | ⇠ |
| System.ServiceModel.Security | X | X | ⇠ | ⇠ | ⇠ |
| System.ServiceProcess.ServiceController |  |  |  | X | ⇠ |
| System.Text.Encoding | X | ⇠ | ⇠ | X | ⇠ |
| System.Text.Encoding.CodePages |  |  |  | X | ⇠ |
| System.Text.Encoding.Extensions | X | ⇠ | ⇠ | X | ⇠ |
| System.Text.RegularExpressions | X | ⇠ | ⇠ | X | ⇠ |
| System.Threading | X | ⇠ | ⇠ | X | ⇠ |
| System.Threading.AccessControl | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Threading.Overlapped |  |  |  | X | ⇠ |
| System.Threading.Tasks | X | ⇠ | ⇠ | X | ⇠ |
| System.Threading.Tasks.Parallel |  | X | ⇠ | ⇠ | ⇠ |
| System.Threading.Thread | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Threading.ThreadPool |  | X | ⇠ | ⇠ | ⇠ |
| System.Threading.Timer |  |  | X | ⇠ | ⇠ |
| System.Xml.ReaderWriter | X | ⇠ | ⇠ | X | ⇠ |
| System.Xml.XDocument | X | ⇠ | ⇠ | X | ⇠ |
| System.Xml.XmlDocument | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Xml.XmlSerializer | X | ⇠ | ⇠ | X | ⇠ |
| System.Xml.XPath | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Xml.XPath.XDocument | X | ⇠ | ⇠ | ⇠ | ⇠ |
| System.Xml.XPath.XmlDocument | X | ⇠ | ⇠ | ⇠ | ⇠ |
