---
title: "How to: Install an assembly into the global assembly cache"
ms.date: 02/04/2019
helpviewer_keywords:
  - "assemblies [.NET Framework], global assembly cache"
  - "Gacutil.exe"
  - "strong-named assemblies, global assembly cache"
  - "global assembly cache, installing assemblies"
  - "Global Assembly Cache tool"
  - "windows installer, global assembly cache"
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
author: "rpetrusha"
ms.author: "ronpet"
---
# How to: Install an assembly into the global assembly cache

The global assembly cache (GAC) stores assemblies that are shared by several applications. Install an assembly into the [global assembly cache](https://docs.microsoft.com/en-us/dotnet/framework/app-domains/gac) with one of the following components: 
- [Windows Installer](#windows-installer)
- [Global assembly cache tool](#global-assembly-cache-tool).

> [!IMPORTANT]
> You can install only strong-named assemblies into the GAC. For information about how to create a strong-named assembly, see [How to: Sign an assembly with a strong name](how-to-sign-an-assembly-with-a-strong-name.md).

## Windows Installer

[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), the Windows installation engine, is the recommended way to add assemblies to the global assembly cache. Windows Installer provides reference counting of assemblies in the global assembly cache and other benefits. To create an installer package for Windows Installer, use the [WiX toolset extension for Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension).

## Global assembly cache tool

You can use the [global assembly cache tool (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to add assemblies to the global assembly cache and to view the contents of the global assembly cache.

   > [!NOTE]
   > *Gacutil.exe* is for development purposes only. Don't use it to install production assemblies into the global assembly cache.

The syntax for gacutil is as follows:

```shell
gacutil -i <assembly name>
```

In this command, *\<assembly name>* is the name of the assembly to install in the global assembly cache.

If *gacutil.exe* isn't in your system path, use the <Developer Command Prompt for Visual Studio>(https://docs.microsoft.com/en-us/dotnet/framework/tools/developer-command-prompt-for-vs). 

The following example installs an assembly with the file name `hello.dll` into the global assembly cache.

```shell
gacutil -i hello.dll
```

> [!NOTE]
> In earlier versions of the .NET Framework, the *Shfusion.dll* Windows shell extension enabled you to install assemblies by dragging them in **File Explorer**. Beginning with .NET Framework Version 4, *Shfusion.dll* is obsolete.

## See also

- [Working with assemblies and the global assembly cache](working-with-assemblies-and-the-gac.md)
- [How to: Remove an assembly from the global assembly cache](how-to-remove-an-assembly-from-the-gac.md)
- [Gacutil.exe (Global assembly cache tool)](../tools/gacutil-exe-gac-tool.md)
- [How to: Sign an assembly with a strong name](how-to-sign-an-assembly-with-a-strong-name.md)