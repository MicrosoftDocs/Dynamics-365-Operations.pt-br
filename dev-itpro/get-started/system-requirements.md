---
title: "Requisitos de sistema para implantações na nuvem"
description: "Este tópico lista os requisitos do sistema para a versão atual do Microsoft Dynamics 365 for Finance and Operations, edição Enterprise, para as implantações na nuvem."
author: sericks007
manager: AnnBe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: 5230911e1febc66b294f1331846373a472789adf
ms.openlocfilehash: 46eacb2a01c3bfcc7144c7d8c39ee0189fd72e16
ms.contentlocale: pt-br
ms.lasthandoff: 08/04/2017

---

# <a name="system-requirements-for-cloud-deployments"></a><span data-ttu-id="35099-103">Requisitos de sistema para implantações na nuvem</span><span class="sxs-lookup"><span data-stu-id="35099-103">System requirements for cloud deployments</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="35099-104">Este tópico lista os requisitos do sistema para a versão atual do Microsoft Dynamics 365 for Finance and Operations, edição Enterprise, para as implantações na nuvem.</span><span class="sxs-lookup"><span data-stu-id="35099-104">This topic lists the system requirements for the current version of Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, for cloud deployments.</span></span> <span data-ttu-id="35099-105">Antes de instalar o Finance and Operations, quando esta etapa for adequada, verifique se o sistema com o qual você está trabalhando atende ou excede os requisitos mínimos de rede, hardware e de software.</span><span class="sxs-lookup"><span data-stu-id="35099-105">Before you install Finance and Operations, when this step is appropriate, verify that the system that you're working with meets or exceeds the minimum network, hardware, and software requirements.</span></span>

## <a name="supported-web-browsers"></a><span data-ttu-id="35099-106">Navegadores da web suportados</span><span class="sxs-lookup"><span data-stu-id="35099-106">Supported web browsers</span></span>
<span data-ttu-id="35099-107">O aplicativo de web pode ser executado em qualquer um dos navegadores de web que são executados nos sistemas operacionais especificados:</span><span class="sxs-lookup"><span data-stu-id="35099-107">The web application can run in any of the following web browsers that run on the specified operating systems:</span></span>

-   <span data-ttu-id="35099-108">Microsoft Edge (última versão liberada publicamente) no Windows 10</span><span class="sxs-lookup"><span data-stu-id="35099-108">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
-   <span data-ttu-id="35099-109">Internet Explorer 11 no Windows 10, Windows 8.1, ou Windows 7</span><span class="sxs-lookup"><span data-stu-id="35099-109">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
-   <span data-ttu-id="35099-110">Google Chrome (última versão liberada publicamente) no Windows 10, Windows 8.1, Windows 8, Windows 7, ou tablet Google Nexus 10</span><span class="sxs-lookup"><span data-stu-id="35099-110">Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet</span></span>
-   <span data-ttu-id="35099-111">Apple Safari (última versão liberada publicamente) no Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) ou 10.12 (Sierra), ou Apple iPad</span><span class="sxs-lookup"><span data-stu-id="35099-111">Apple Safari (latest publicly available version) on Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) or 10.12 (Sierra), or Apple iPad</span></span>

<span data-ttu-id="35099-112">Para localizar a versão mais recente de cada navegador, vá para o site do fabricante do software.</span><span class="sxs-lookup"><span data-stu-id="35099-112">To find the latest release for each web browser, go to the software manufacturer’s website.</span></span> 

> [!NOTE]
> -   <span data-ttu-id="35099-113">Você deve instalar uma extensão do Chrome de pré-lançamento para habilitar o Gravador de tarefas a fazer capturas de tela e incluí-las em documentos do Microsoft Word que são gerados.</span><span class="sxs-lookup"><span data-stu-id="35099-113">You must install a pre-release Chrome extension to enable Task Recorder to capture screenshots and include them in Microsoft Word documents that are generated.</span></span> <!---For instructions about how to install the extension, see [Screenshot Extension setup](/dynamics365/unified-operations/dev-itpro/user-interface/task-recorder).-->
> -   <span data-ttu-id="35099-114">O editor de fluxo de trabalho é iniciado como um aplicativo ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="35099-114">The Workflow Editor is started as a ClickOnce application.</span></span> <span data-ttu-id="35099-115">Somente o Microsoft Edge e o Internet Explorer (em uma versão com suporte do Microsoft Windows) suportam aplicativos ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="35099-115">Only Microsoft Edge and Internet Explorer (on a supported version of Microsoft Windows) support ClickOnce applications.</span></span> <span data-ttu-id="35099-116">O aplicativo Editor de fluxo de trabalho ClickOnce requer um sistema operacional compatível com 64 bits.</span><span class="sxs-lookup"><span data-stu-id="35099-116">The Workflow Editor ClickOnce application requires a 64-bit-compatible operating system.</span></span>
> -   <span data-ttu-id="35099-117">O Report Designer for Financial Reporting é iniciado como um aplicativo ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="35099-117">The Report Designer for Financial reporting is started as a ClickOnce application.</span></span> <span data-ttu-id="35099-118">Ele requer um sistema operacional compatível com 64 bits.</span><span class="sxs-lookup"><span data-stu-id="35099-118">It requires a 64-bit-compatible operating system.</span></span> <span data-ttu-id="35099-119">Se estiver usando o Chrome, instale uma extensão ClickOnce para baixar o cliente de Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="35099-119">If you’re using Chrome, you must install a ClickOnce extension to download the Report Designer client.</span></span> <span data-ttu-id="35099-120">Se usar o Chrome no modo de navegação anônima, verifique se a extensão ClickOnce também está ativada para o modo de navegação anônima.</span><span class="sxs-lookup"><span data-stu-id="35099-120">If you use Chrome in Incognito mode, make sure that the ClickOnce extension is also enabled for Incognito mode.</span></span>
> -   <span data-ttu-id="35099-121">Para visualizar os arquivos PDF, recomendamos que você use navegadores como o Microsoft Edge (última versão liberada publicamente) no Windows 10 ou o Google Chrome (última versão liberada publicamente) no Windows 10, Windows 8.1, Windows 8, Windows 7 ou no tablet Google Nexus 10.</span><span class="sxs-lookup"><span data-stu-id="35099-121">To preview PDF files, we recommend that you use browsers such as Microsoft Edge (latest publicly available version) on Windows 10, or Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet.</span></span>

### <a name="supported-web-browsers-for-retail-cloud-pos"></a><span data-ttu-id="35099-122">Navegadores da web suportados para o Retail Cloud POS</span><span class="sxs-lookup"><span data-stu-id="35099-122">Supported web browsers for Retail Cloud POS</span></span>

<span data-ttu-id="35099-123">O PDV de nuvem de varejo pode ser executado em qualquer um dos navegadores de web que são executados nos sistemas operacionais especificados:</span><span class="sxs-lookup"><span data-stu-id="35099-123">Retail Cloud POS can run in any of the following web browsers that run on the specified operating systems:</span></span>

-   <span data-ttu-id="35099-124">Microsoft Edge (última versão liberada publicamente) no Windows 10</span><span class="sxs-lookup"><span data-stu-id="35099-124">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
-   <span data-ttu-id="35099-125">Internet Explorer 11 no Windows 10, Windows 8.1, ou Windows 7</span><span class="sxs-lookup"><span data-stu-id="35099-125">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
-   <span data-ttu-id="35099-126">Chrome (última versão liberada publicamente) no Windows 10, Windows 8.1, ou Windows 7</span><span class="sxs-lookup"><span data-stu-id="35099-126">Chrome (latest publicly available version) on Windows 10, Windows 8.1, or Windows 7</span></span>

## <a name="network-requirements"></a><span data-ttu-id="35099-127">Requisitos de rede</span><span class="sxs-lookup"><span data-stu-id="35099-127">Network requirements</span></span>
-   <span data-ttu-id="35099-128">O Finance and Operations foi projetado para redes que têm uma latência de 250–300 milissegundos (ms) ou menos.</span><span class="sxs-lookup"><span data-stu-id="35099-128">Finance and Operations is designed for networks that have a latency of 250–300 milliseconds (ms) or less.</span></span> <span data-ttu-id="35099-129">Esta latência é a latência de um cliente de navegador para o datacenter do Microsoft Azure que hospeda o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="35099-129">This latency is the latency from a browser client to the Microsoft Azure datacenter that hosts Finance and Operations.</span></span> <span data-ttu-id="35099-130">Recomendamos que teste a latência da rede em <http://www.azurespeed.com>.</span><span class="sxs-lookup"><span data-stu-id="35099-130">We recommend that you test network latency at <http://www.azurespeed.com>.</span></span>
-   <span data-ttu-id="35099-131">Os requisitos de largura do Finance and Operations dependem de seu cenário.</span><span class="sxs-lookup"><span data-stu-id="35099-131">Bandwidth requirements for Finance and Operations depend on your scenario.</span></span> <span data-ttu-id="35099-132">A maioria dos cenários típicos requerem uma largura de banda de mais de 50 kilobytes por segundo (KBps).</span><span class="sxs-lookup"><span data-stu-id="35099-132">Most typical scenarios require a bandwidth of more than 50 kilobytes per second (KBps).</span></span> <span data-ttu-id="35099-133">No entanto, recomendamos mais largura de banda para cenários com requisitos de carga elevados, como cenários que envolvam espaços de trabalho ou personalização extensiva.</span><span class="sxs-lookup"><span data-stu-id="35099-133">However, we recommend more bandwidth for scenarios that have high payload requirements, such as scenarios that involve workspaces or extensive customization.</span></span>

<span data-ttu-id="35099-134">Em geral, o Finance and Operations é otimizado para a Internet.</span><span class="sxs-lookup"><span data-stu-id="35099-134">In general, Finance and Operations is optimized for the internet.</span></span> <span data-ttu-id="35099-135">O número de viagens de ida e volta de um cliente de navegador para o datacenter do Azure é muito pequeno e toda a carga útil é compactada.</span><span class="sxs-lookup"><span data-stu-id="35099-135">The number of round trips from a browser client to the Azure datacenter is very small, and the whole payload is compressed.</span></span> 

> [!WARNING]
> <span data-ttu-id="35099-136">Não calcule os requisitos de largura de banda de um local de cliente multiplicando o número de usuários pelos requisitos mínimos de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="35099-136">Don't calculate bandwidth requirements from a client location by multiplying the number of users by the minimum bandwidth requirements.</span></span> <span data-ttu-id="35099-137">O uso simultâneo de um determinado local é muito difícil de calcular.</span><span class="sxs-lookup"><span data-stu-id="35099-137">The concurrent usage of a given location is very difficult to calculate.</span></span> <span data-ttu-id="35099-138">Os clientes que estão preocupados com os requisitos de largura de banda devem usar uma versão de visualização do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="35099-138">Customers who are concerned about bandwidth requirements should use a preview version of Finance and Operations.</span></span>

## <a name="net-framework-requirements"></a><span data-ttu-id="35099-139">Requisitos do .NET Framework</span><span class="sxs-lookup"><span data-stu-id="35099-139">.NET Framework requirements</span></span>
<span data-ttu-id="35099-140">O Finance and Operations requer a versão 4.6.2 do Microsoft .NET Framework para todos os aplicativos ClickOnce, como o agente de roteamento de documentos.</span><span class="sxs-lookup"><span data-stu-id="35099-140">Finance and Operations requires the Microsoft .NET Framework version 4.6.2 for all ClickOnce applications, such as the document routing agent.</span></span> <span data-ttu-id="35099-141">Para obter instruções de instalação, consulte [Instalando o .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="35099-141">For installation instructions, see [Installing the .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).</span></span>

## <a name="supported-microsoft-office-applications"></a><span data-ttu-id="35099-142">Aplicativos Microsoft Office suportados</span><span class="sxs-lookup"><span data-stu-id="35099-142">Supported Microsoft Office applications</span></span>
<span data-ttu-id="35099-143">Os seguintes aplicativos do Microsoft Office têm suporte nas implantações de nuvem e locais do Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="35099-143">The following Microsoft Office applications are supported in cloud and on-premises deployments of Finance and Operations:</span></span>

-   <span data-ttu-id="35099-144">Para executar os suplementos do Microsoft Excel e Word, você deve ter o Microsoft Office 2016 para Windows ou Mac instalado.</span><span class="sxs-lookup"><span data-stu-id="35099-144">To run the Microsoft Excel and Word add-ins, you must have Microsoft Office 2016 for Windows or Mac installed.</span></span> <span data-ttu-id="35099-145">Para saber mais sobre os requisitos de versão, consulte [Solução de problemas de integração do Office](/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="35099-145">For more information about version requirements, see [Office integration troubleshooting](/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-troubleshooting).</span></span>
-   <span data-ttu-id="35099-146">Para exibir documentos que são gerados pela exportação para Excel ou exportar para funcionalidade do Word, você deve ter o Microsoft Office 2007 ou posterior instalado.</span><span class="sxs-lookup"><span data-stu-id="35099-146">To view documents that are generated by the Export to Excel or Export to Word functionality, you must have Microsoft Office 2007 or later installed.</span></span>

## <a name="retail-modern-pos-requirements"></a><span data-ttu-id="35099-147">Requisitos modernos de POS de varejo</span><span class="sxs-lookup"><span data-stu-id="35099-147">Retail Modern POS requirements</span></span>

> [!NOTE]
> <span data-ttu-id="35099-148">Se o Retail Modern POS usar um banco de dados offline, o computador deverá atender a todos os requisitos do sistema para o Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="35099-148">If Retail Modern POS will use an offline database, the computer must meet all system requirements for Microsoft SQL Server.</span></span> <span data-ttu-id="35099-149">Um banco de dados offline do Retail Modern POS funcionará no Microsoft SQL Server 2012 com o Service Pack 3 ou posterior, o Microsoft SQL Server 2014 com Service Pack 2 ou posterior, e o Microsoft SQL Server 2016.</span><span class="sxs-lookup"><span data-stu-id="35099-149">A Retail Modern POS offline database will work on Microsoft SQL Server 2012 with Service Pack 3 or later, Microsoft SQL Server 2014 with Service Pack 2 or later, and Microsoft SQL Server 2016.</span></span> <span data-ttu-id="35099-150">Recomendamos usar sempre a versão mais recente disponível e a instalação todos os service packs mais recentes.</span><span class="sxs-lookup"><span data-stu-id="35099-150">We recommend that you always use the latest version that is available, and that you install all the latest service packs.</span></span>

### <a name="supported-operating-systems"></a><span data-ttu-id="35099-151">Sistemas operacionais suportados</span><span class="sxs-lookup"><span data-stu-id="35099-151">Supported operating systems</span></span>

-   <span data-ttu-id="35099-152">O Retail POS moderno é um aplicativo de 32 bits, mas será executado em ambas as arquiteturas x86 e x64.</span><span class="sxs-lookup"><span data-stu-id="35099-152">Retail Modern POS is a 32-bit application, but it will run on both x86 and x64 architectures.</span></span>
-   <span data-ttu-id="35099-153">O varejo POS moderno é suportado somente em edições de ramal de serviço de longo prazo Enterprise (LTSB), do Windows 10 Pro, e Enterprise.</span><span class="sxs-lookup"><span data-stu-id="35099-153">Retail Modern POS is supported only on Windows 10 Pro, Enterprise, and Enterprise Long Term Servicing Branch (LTSB) editions.</span></span>

### <a name="minimum-system-requirements"></a><span data-ttu-id="35099-154">Requisitos mínimos do sistema</span><span class="sxs-lookup"><span data-stu-id="35099-154">Minimum system requirements</span></span>

-   <span data-ttu-id="35099-155">A resolução mínima suportada é 1280 × 1024.</span><span class="sxs-lookup"><span data-stu-id="35099-155">The minimum supported resolution is 1,280 × 1,024.</span></span>
-   <span data-ttu-id="35099-156">O computador em que o Retail Modern POS funciona deve atender a esses requisitos:</span><span class="sxs-lookup"><span data-stu-id="35099-156">The computer that Retail Modern POS runs on must meet these requirements:</span></span>

    -   <span data-ttu-id="35099-157">Ele deve ter, no mínimo, um processador dual-core que funciona a não menos de 2 gigahertz (GHz).</span><span class="sxs-lookup"><span data-stu-id="35099-157">It must have, at a minimum, a dual-core processor that runs at no less than 2 gigahertz (GHz).</span></span>
    -   <span data-ttu-id="35099-158">Ele deve ter, no mínimo, 3 gigabytes (GB) de RAM.</span><span class="sxs-lookup"><span data-stu-id="35099-158">It must have, at a minimum, 3 gigabytes (GB) of random-access memory (RAM).</span></span>
    -   <span data-ttu-id="35099-159">Ele deve ter acesso à Internet.</span><span class="sxs-lookup"><span data-stu-id="35099-159">It must have internet access.</span></span>

## <a name="retail-hardware-station-requirements"></a><span data-ttu-id="35099-160">Requisitos de estações de hardware de varejo</span><span class="sxs-lookup"><span data-stu-id="35099-160">Retail hardware station requirements</span></span>
### <a name="supported-operating-systems"></a><span data-ttu-id="35099-161">Sistemas operacionais suportados</span><span class="sxs-lookup"><span data-stu-id="35099-161">Supported operating systems</span></span>

-   <span data-ttu-id="35099-162">A estação de hardware de varejo é um aplicativo de 32 bits, mas será executado em ambas as arquiteturas x86 e x64.</span><span class="sxs-lookup"><span data-stu-id="35099-162">Retail hardware station is a 32-bit application, but it will run on both x86 and x64 architectures.</span></span>
-   <span data-ttu-id="35099-163">A estação de hardware de varejo é suportada nos seguintes sistemas operacionais:</span><span class="sxs-lookup"><span data-stu-id="35099-163">Retail hardware station is supported on the following operating systems:</span></span>

    -   <span data-ttu-id="35099-164">Edições do Windows 7 Professional, Enterprise, e Ultimate</span><span class="sxs-lookup"><span data-stu-id="35099-164">Windows 7 Professional, Enterprise, and Ultimate editions</span></span> 
    
        > [!NOTE]
        > <span data-ttu-id="35099-165">O Windows 7 tem suporte apenas se o Internet Explorer 11 for instalado manualmente no sistema.</span><span class="sxs-lookup"><span data-stu-id="35099-165">Windows 7 is supported only if Internet Explorer 11 is manually installed on the system.</span></span>

    -   <span data-ttu-id="35099-166">Windows 8.1 Update 1 Professional, Enterprise e edições incorporadas</span><span class="sxs-lookup"><span data-stu-id="35099-166">Windows 8.1 Update 1 Professional, Enterprise, and Embedded editions</span></span>
    -   <span data-ttu-id="35099-167">Edições LTSB Enterprise, Windows 10 Pro, e Enterprise</span><span class="sxs-lookup"><span data-stu-id="35099-167">Windows 10 Pro, Enterprise, and Enterprise LTSB editions</span></span>

### <a name="minimum-system-requirements"></a><span data-ttu-id="35099-168">Requisitos mínimos do sistema</span><span class="sxs-lookup"><span data-stu-id="35099-168">Minimum system requirements</span></span>

<span data-ttu-id="35099-169">O computador deve atender a todos os requisitos do sistema para instalar e usar os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="35099-169">The computer must meet all system requirements for installing and using the following items:</span></span>

-   <span data-ttu-id="35099-170">Serviços de Informações da Internet (IIS)</span><span class="sxs-lookup"><span data-stu-id="35099-170">Internet Information Services (IIS)</span></span>
-   <span data-ttu-id="35099-171">Hardware de terceiros</span><span class="sxs-lookup"><span data-stu-id="35099-171">Third-party hardware</span></span>

## <a name="retail-store-scale-unit-requirements"></a><span data-ttu-id="35099-172">Requisitos da unidade de escala de loja de varejo</span><span class="sxs-lookup"><span data-stu-id="35099-172">Retail Store Scale Unit requirements</span></span>
### <a name="supported-operating-systems"></a><span data-ttu-id="35099-173">Sistemas operacionais suportados</span><span class="sxs-lookup"><span data-stu-id="35099-173">Supported operating systems</span></span>

-   <span data-ttu-id="35099-174">A unidade de escala de loja de varejo é um aplicativo de 32 bits, mas será executado em ambas as arquiteturas x86 e x64.</span><span class="sxs-lookup"><span data-stu-id="35099-174">Retail Store Scale Unit is a 32-bit application, but it will run on both x86 and x64 architectures.</span></span>
-   <span data-ttu-id="35099-175">A unidade de escala de loja de varejo é suportada nos seguintes sistemas operacionais:</span><span class="sxs-lookup"><span data-stu-id="35099-175">Retail Store Scale Unit is supported on the following operating systems:</span></span>

    -   <span data-ttu-id="35099-176">Edições do Windows 7 Professional, Enterprise, e Ultimate</span><span class="sxs-lookup"><span data-stu-id="35099-176">Windows 7 Professional, Enterprise, and Ultimate editions</span></span>
    -   <span data-ttu-id="35099-177">Windows 8.1 Update 1 Professional, Enterprise e edições incorporadas</span><span class="sxs-lookup"><span data-stu-id="35099-177">Windows 8.1 Update 1 Professional, Enterprise, and Embedded editions</span></span>
    -   <span data-ttu-id="35099-178">Edições LTSB Enterprise, Windows 10 Pro, e Enterprise</span><span class="sxs-lookup"><span data-stu-id="35099-178">Windows 10 Pro, Enterprise, and Enterprise LTSB editions</span></span>

### <a name="minimum-system-requirements"></a><span data-ttu-id="35099-179">Requisitos mínimos do sistema</span><span class="sxs-lookup"><span data-stu-id="35099-179">Minimum system requirements</span></span>

-   <span data-ttu-id="35099-180">4 GB de RAM</span><span class="sxs-lookup"><span data-stu-id="35099-180">4 GB of RAM</span></span>
-   <span data-ttu-id="35099-181">Velocidade máxima de CPU de 1,6 GHz por núcleo (dois núcleos no mínimo.)</span><span class="sxs-lookup"><span data-stu-id="35099-181">1.6 GHz peak CPU speed per core (Two cores are the minimum.)</span></span>
-   <span data-ttu-id="35099-182">Pelo menos 10 GB de espaço livre (o banco de dados de canal pode exigir uma grande quantidade de espaço.)</span><span class="sxs-lookup"><span data-stu-id="35099-182">At least 10 GB of free space (The channel database can require a large amount of space.)</span></span>

### <a name="recommended-system-requirements"></a><span data-ttu-id="35099-183">Requisitos de sistema recomendados</span><span class="sxs-lookup"><span data-stu-id="35099-183">Recommended system requirements</span></span>

-   <span data-ttu-id="35099-184">6 GB de RAM</span><span class="sxs-lookup"><span data-stu-id="35099-184">6 GB of RAM</span></span>
-   <span data-ttu-id="35099-185">i7 com 2,4 GHz (ou equivalente) de velocidade máxima de CPU por núcleo (são recomendados quatro núcleos.)</span><span class="sxs-lookup"><span data-stu-id="35099-185">2.4 GHz i7 (or equivalent) peak CPU speed per core (Four cores are recommended.)</span></span>
-   <span data-ttu-id="35099-186">Pelo menos 10 GB de espaço livre (o banco de dados de canal pode exigir uma grande quantidade de espaço.)</span><span class="sxs-lookup"><span data-stu-id="35099-186">At least 10 GB of free space (The channel database can require a large amount of space.)</span></span>

## <a name="connector-requirements"></a><span data-ttu-id="35099-187">Requisitos do conector</span><span class="sxs-lookup"><span data-stu-id="35099-187">Connector requirements</span></span>
### <a name="supported-operating-systems"></a><span data-ttu-id="35099-188">Sistemas operacionais suportados</span><span class="sxs-lookup"><span data-stu-id="35099-188">Supported operating systems</span></span>

-   <span data-ttu-id="35099-189">O conector do Microsoft Dynamics AX tem dois instaladores separados, um para o Serviço de Conector do Async Server e um para o Serviço em tempo Real do Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="35099-189">The Connector for Microsoft Dynamics AX has two separate installers, one for Async Server Connector service and one for Real-time service for Dynamics AX 2012 R3.</span></span>
-   <span data-ttu-id="35099-190">Ambos os componentes são aplicativos de 32 bits, mas serão executados em arquiteturas x86 e x64.</span><span class="sxs-lookup"><span data-stu-id="35099-190">Both components are 32-bit applications, but they will run on both x86 and x64 architectures.</span></span>
-   <span data-ttu-id="35099-191">Os componentes são suportados nos seguintes sistemas operacionais:</span><span class="sxs-lookup"><span data-stu-id="35099-191">Both components are supported on the following operating systems:</span></span>

    -   <span data-ttu-id="35099-192">Edições do Windows 7 Professional, Enterprise, e Ultimate</span><span class="sxs-lookup"><span data-stu-id="35099-192">Windows 7 Professional, Enterprise, and Ultimate editions</span></span>
    -   <span data-ttu-id="35099-193">Windows 8.1 Update 1 Professional, Enterprise e edições incorporadas</span><span class="sxs-lookup"><span data-stu-id="35099-193">Windows 8.1 Update 1 Professional, Enterprise, and Embedded editions</span></span>
    -   <span data-ttu-id="35099-194">Edições LTSB Enterprise, Windows 10 Pro, e Enterprise</span><span class="sxs-lookup"><span data-stu-id="35099-194">Windows 10 Pro, Enterprise, and Enterprise LTSB editions</span></span>
    -   <span data-ttu-id="35099-195">Microsoft Windows Server 2012 R2 e Microsoft Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="35099-195">Microsoft Windows Server 2012 R2 and Microsoft Windows Server 2016</span></span>

### <a name="minimum-system-requirements"></a><span data-ttu-id="35099-196">Requisitos mínimos do sistema</span><span class="sxs-lookup"><span data-stu-id="35099-196">Minimum system requirements</span></span>
-   <span data-ttu-id="35099-197">2 GB de RAM, (4 GB de RAM são recomendados.)</span><span class="sxs-lookup"><span data-stu-id="35099-197">2 GB of RAM (4 GB of RAM are recommended.)</span></span>
-   <span data-ttu-id="35099-198">Velocidade máxima de CPU de 1,6 GHz por núcleo (dois núcleos no mínimo.)</span><span class="sxs-lookup"><span data-stu-id="35099-198">1.6 GHz peak CPU speed per core (Two cores are the minimum.)</span></span>
-   <span data-ttu-id="35099-199">Pelo menos 10 GB de espaço livre (o banco de dados de canal pode exigir uma grande quantidade de espaço.)</span><span class="sxs-lookup"><span data-stu-id="35099-199">At least 10 GB of free space (The channel database can require a large amount of space.)</span></span>

## <a name="requirements-for-development-on-local-vms"></a><span data-ttu-id="35099-200">Requisitos do desenvolvimento em VMs locais</span><span class="sxs-lookup"><span data-stu-id="35099-200">Requirements for development on local VMs</span></span>
<span data-ttu-id="35099-201">Para obter informações sobre os requisitos de desenvolvimento em máquinas virtuais locais (VMs), consulte [VM em execução no local](../dev-tools/access-instances.md).</span><span class="sxs-lookup"><span data-stu-id="35099-201">For information about the requirements for development on local virtual machines (VMs), see [VM running on-premises](../dev-tools/access-instances.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="35099-202">Consulte também</span><span class="sxs-lookup"><span data-stu-id="35099-202">See also</span></span>

[<span data-ttu-id="35099-203">Obtenha uma cópia de avaliação do Dynamics 365 for Finance and Operations, edição Enterprise</span><span class="sxs-lookup"><span data-stu-id="35099-203">Get an evaluation copy of Dynamics 365 for Finance and Operations, Enterprise edition</span></span>](/dynamics365/unified-operations/dev-itpro/dev-tools/get-evaluation-copy)

