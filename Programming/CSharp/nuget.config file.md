---
date_added: 2025-02-08
tags:
  - csharp
---
Up: [Nuget package](Nuget%20package.md)
___

When a config file is not specified explicitly on the command line, NuGet loads settings from the different config files in the following order:

1. (_Uncommon_) The [`NuGetDefaults.Config` file](https://learn.microsoft.com/en-us/nuget/consume-packages/configuring-nuget-behavior#nuget-defaults-file), which contains settings related only to package sources.
2. The computer-level file.
3. The user-level file.
4. Files found in every folder in the path from the drive root to the current folder (where `nuget.exe` is invoked or the folder containing the Visual Studio solution). For example, if a command is invoked in `c:\A\B\C`, NuGet looks for and loads config files in `c:\`, then `c:\A`, then `c:\A\B`, and finally `c:\A\B\C`.

When a config file is explicitly specified on the command line, for example `nuget -configFile my.config` or `dotnet restore --configfile my.config`, only the settings from the specified file will be used.

As NuGet finds settings in these files, they are applied as follows:

1. For single-item elements, NuGet replaced any previously-found value for the same key. This means that settings that are "closest" to the current folder or solution override any others found earlier. For example, the `defaultPushSource` setting in `NuGetDefaults.Config` is overridden if it exists in any other config file.
2. For collection elements (such as `<packageSources>`), NuGet combines the values from all configuration files into a single collection.
3. When `<clear />` is present for a given node, NuGet ignores previously defined configuration values for that node.

Has many sections, but most important is `<packageSources>` which specifies the sources where NuGet should look for packages.

```xml
<packageSources>
    <clear />
    <add key="nuget.org" value="https://api.nuget.org/v3/index.json" protocolVersion="3" />
    <add key="Contoso" value="https://contoso.com/packages/" />
    <add key="http-source" value="http://httpsourcetrusted/" allowInsecureConnections="true" />
    <add key="Invalid-certificate-https-source" value="https://httpsSourceTrusted/" disableTLSCertificateValidation="true" />
    <add key="Test Source" value="c:\packages" />
</packageSources>
```
# Usage
Is used, for example by [command dotnet restore](command%20dotnet%20restore.md) to specify sources and package restore configuration.
  
  ```xml
  <?xml version="1.0" encoding="utf-8"?>
<configuration>
  <!-- Package Sources -->
  <packageSources>
    <add key="nuget.org" value="https://api.nuget.org/v3/index.json" protocolVersion="3" />
    <!-- Add other package sources here -->
    <!-- <add key="MyPrivateRepo" value="https://myprivaterepo.com/nuget" /> -->
  </packageSources>

  <!-- Package Source Credentials -->
  <!--
  <packageSourceCredentials>
    <MyPrivateRepo>
      <add key="Username" value="myusername" />
      <add key="ClearTextPassword" value="mypassword" />
    </MyPrivateRepo>
  </packageSourceCredentials>
  -->

  <!-- Configuring Package Restore -->
  <packageRestore>
    <add key="enabled" value="True" />
    <add key="automatic" value="True" />
  </packageRestore>

  <!-- Disabling Source Control Integration -->
  <solution>
    <add key="disableSourceControlIntegration" value="true" />
  </solution>

  <!-- Configuring Package Management Format -->
  <packageManagement>
    <add key="format" value="1" /> <!-- 1 for packages.config, 2 for PackageReference -->
    <add key="disabled" value="false" />
  </packageManagement>

  <!-- Configuring Global Packages Folder -->
  <!--
  <config>
    <add key="globalPackagesFolder" value="C:\MyCustomPackagesFolder" />
  </config>
  -->

  <!-- HTTP Cache Configuration -->
  <!--
  <config>
    <add key="httpCacheFolder" value="C:\MyCustomCacheFolder" />
  </config>
  -->
</configuration>
```

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
