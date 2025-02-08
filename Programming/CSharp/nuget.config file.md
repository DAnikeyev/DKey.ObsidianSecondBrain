---
date_added: 2025-02-08
tags:
  - csharp
---
Up: [Nuget package](Nuget%20package.md)
___
  Is used, for example by [command dotnet restore](command%20dotnet%20restore.md) to specify sources and package restore configuration
  
  ```cs
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
