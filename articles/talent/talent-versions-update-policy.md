---
title: "Requisitos do sistema e política de atualização do Talent"
description: "Este tópico lista os requisitos para o Dynamics 365 for Talent. A política de atualização também está descrita."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 965826f5fddc2f53f33157434929eb265979376e
ms.openlocfilehash: 0fa2b7c2dc5b88349cb4012b6b0ba9009a361fa0
ms.contentlocale: pt-br
ms.lasthandoff: 09/17/2018

---

# <a name="talent-system-requirements-and-update-policy"></a><span data-ttu-id="0d08b-104">Requisitos do sistema e política de atualização do Talent</span><span class="sxs-lookup"><span data-stu-id="0d08b-104">Talent system requirements and update policy</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0d08b-105">Este tópico lista os requisitos para o Microsoft Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="0d08b-105">This topic lists requirements for Microsoft Dynamics 365 for Talent.</span></span> <span data-ttu-id="0d08b-106">A política de atualização também está descrita.</span><span class="sxs-lookup"><span data-stu-id="0d08b-106">The update policy is outlined, as well.</span></span>

## <a name="supported-web-browsers"></a><span data-ttu-id="0d08b-107">Navegadores da web suportados</span><span class="sxs-lookup"><span data-stu-id="0d08b-107">Supported web browsers</span></span>

<span data-ttu-id="0d08b-108">O aplicativo da Web do Microsoft Dynamics 365 for Talent pode ser executado em qualquer um dos navegadores da Web que são executados nos sistemas operacionais especificados:</span><span class="sxs-lookup"><span data-stu-id="0d08b-108">The Microsoft Dynamics 365 for Talent web application can run in any of the following web browsers that run on the specified operating systems:</span></span> 

*   <span data-ttu-id="0d08b-109">Microsoft Edge (última versão liberada publicamente) no Windows 10</span><span class="sxs-lookup"><span data-stu-id="0d08b-109">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
*   <span data-ttu-id="0d08b-110">Internet Explorer 11 no Windows 10, Windows 8.1, ou Windows 7</span><span class="sxs-lookup"><span data-stu-id="0d08b-110">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
*   <span data-ttu-id="0d08b-111">Google Chrome (última versão liberada publicamente) no Windows 10, Windows 8.1, Windows 8, Windows 7, ou tablet Google Nexus 10</span><span class="sxs-lookup"><span data-stu-id="0d08b-111">Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet</span></span>
*   <span data-ttu-id="0d08b-112">Apple Safari (última versão liberada publicamente) no Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) ou 10.12 (Sierra), ou Apple iPad</span><span class="sxs-lookup"><span data-stu-id="0d08b-112">Apple Safari (latest publicly available version) on Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) or 10.12 (Sierra), or Apple iPad</span></span>

<span data-ttu-id="0d08b-113">Para localizar a versão mais recente de cada navegador, vá para o site do fabricante do software.</span><span class="sxs-lookup"><span data-stu-id="0d08b-113">To find the latest release for each web browser, go to the software manufacturer’s website.</span></span> 

> [!NOTE]
> * <span data-ttu-id="0d08b-114">Para capturar imagens geradas a partir do Gravador de Tarefas e incluí-las em documentos do Microsoft Word, você deve ter uma extensão do Chrome instalada.</span><span class="sxs-lookup"><span data-stu-id="0d08b-114">To capture images that are generated from Task Recorder and include them in Microsoft Word documents, you must have a Chrome extension installed.</span></span> 
> * <span data-ttu-id="0d08b-115">O editor de fluxo de trabalho é iniciado como um aplicativo ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="0d08b-115">The Workflow Editor is started as a ClickOnce application.</span></span> <span data-ttu-id="0d08b-116">Somente o Microsoft Edge e o Internet Explorer (em uma versão com suporte do Microsoft Windows) suportam aplicativos ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="0d08b-116">Only Microsoft Edge and Internet Explorer (on a supported version of Microsoft Windows) support ClickOnce applications.</span></span> <span data-ttu-id="0d08b-117">O aplicativo Editor de fluxo de trabalho ClickOnce requer um sistema operacional compatível com 64 bits.</span><span class="sxs-lookup"><span data-stu-id="0d08b-117">The Workflow Editor ClickOnce application requires a 64-bit compatible operating system.</span></span>
> * <span data-ttu-id="0d08b-118">Para visualizar os arquivos PDF, recomendamos que você use navegadores modernos como o Microsoft Edge (última versão liberada publicamente) no Windows 10 ou o Google Chrome (última versão liberada publicamente) no Windows 10, Windows 8.1, Windows 8, Windows 7 ou no tablet Google Nexus 10.</span><span class="sxs-lookup"><span data-stu-id="0d08b-118">To preview PDF files, we recommend that you use modern browsers like Microsoft Edge (latest publicly available version) on Windows 10, or Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet.</span></span>
>   <span data-ttu-id="0d08b-119">Requisitos de rede</span><span class="sxs-lookup"><span data-stu-id="0d08b-119">Network requirements</span></span>
> * <span data-ttu-id="0d08b-120">O Dynamics 365 for Talent foi projetado para redes com latência entre 250 e 300 milissegundos (ms) ou menos.</span><span class="sxs-lookup"><span data-stu-id="0d08b-120">Dynamics 365 for Talent is designed for networks with latency of 250-300 milliseconds (ms) or less.</span></span> <span data-ttu-id="0d08b-121">Esta é a latência de um cliente de navegador para o data center do Microsoft Azure que hospeda Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="0d08b-121">This is the latency from a browser client to the Microsoft Azure data center that hosts Dynamics 365 for Talent.</span></span> <span data-ttu-id="0d08b-122">Recomendamos que você teste a latência de rede em [www.azurespeed.com](https://www.azurespeed.com "Teste de latência do Azure").</span><span class="sxs-lookup"><span data-stu-id="0d08b-122">We recommend that you test network latency at [www.azurespeed.com](https://www.azurespeed.com "Azure Latency Test").</span></span>
> * <span data-ttu-id="0d08b-123">Os requisitos de largura de banda para o Dynamics 365 for Talent dependem do seu cenário.</span><span class="sxs-lookup"><span data-stu-id="0d08b-123">Bandwidth requirements for Dynamics 365 for Talent depend on your scenario.</span></span> <span data-ttu-id="0d08b-124">A maioria dos cenários típicos requerem uma largura de banda de mais de 50 kilobytes por segundo (KBps).</span><span class="sxs-lookup"><span data-stu-id="0d08b-124">Most typical scenarios require a bandwidth of more than 50 kilobytes per second (KBps).</span></span>
> 
> [!WARNING]
> <span data-ttu-id="0d08b-125">Não calcule os requisitos de largura de banda de um local de cliente multiplicando o número de usuários pelos requisitos mínimos de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="0d08b-125">Don't compute bandwidth requirements from a client location by multiplying the number of users by the minimum bandwidth requirements.</span></span> <span data-ttu-id="0d08b-126">O uso simultâneo de um determinado local é muito difícil de calcular.</span><span class="sxs-lookup"><span data-stu-id="0d08b-126">The concurrent usage of a given location is very difficult to calculate.</span></span> <span data-ttu-id="0d08b-127">Para clientes que estão preocupados com os requisitos de largura de banda, use uma versão de avaliação do Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="0d08b-127">For customers who are concerned about bandwidth requirements, use a trial version of Dynamics 365 for Talent.</span></span>

## <a name="supported-microsoft-office-applications"></a><span data-ttu-id="0d08b-128">Aplicativos Microsoft Office suportados</span><span class="sxs-lookup"><span data-stu-id="0d08b-128">Supported Microsoft Office applications</span></span>

* <span data-ttu-id="0d08b-129">Para executar os suplementos do Microsoft Excel e Word, você deve ter o Microsoft Office 2016 para Windows ou Mac instalado.</span><span class="sxs-lookup"><span data-stu-id="0d08b-129">To run the Microsoft Excel and Word add-ins, you must have Microsoft Office 2016 for Windows or Mac installed.</span></span> <span data-ttu-id="0d08b-130">Para obter mais detalhes sobre requisitos de versão, consulte [Solução de problemas de integração do Office](../dev-itpro/office-integration/office-integration-troubleshooting.md "Solução de problemas de integração do Office").</span><span class="sxs-lookup"><span data-stu-id="0d08b-130">For more details about version requirements, see [Office integration troubleshooting](../dev-itpro/office-integration/office-integration-troubleshooting.md "Office integration troubleshooting").</span></span>
* <span data-ttu-id="0d08b-131">Para exibir documentos que são gerados pela exportação para Excel ou exportar para funcionalidade do Word, você deve ter o Microsoft Office 2007 ou posterior instalado.</span><span class="sxs-lookup"><span data-stu-id="0d08b-131">To view documents that are generated by the Export to Excel or Export to Word functionality, you must have Microsoft Office 2007 or later installed.</span></span>

## <a name="update-policy"></a><span data-ttu-id="0d08b-132">Política de atualização</span><span class="sxs-lookup"><span data-stu-id="0d08b-132">Update policy</span></span>

<span data-ttu-id="0d08b-133">O Microsoft Dynamics 365 for Talent tem manutenção como uma oferta de nuvem.</span><span class="sxs-lookup"><span data-stu-id="0d08b-133">Microsoft Dynamics 365 for Talent is serviced as a cloud offering.</span></span> <span data-ttu-id="0d08b-134">As atualizações do Dynamics 365 for Talent são contínuas e são aplicadas automaticamente pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0d08b-134">Updates to Dynamics 365 for Talent are continuous and applied automatically by Microsoft.</span></span>

<span data-ttu-id="0d08b-135">As atualizações são liberadas em uma cadência normal e serão feitas em todos os ambientes.</span><span class="sxs-lookup"><span data-stu-id="0d08b-135">Updates are released on a regular cadence, updates will be made to all environments.</span></span>  <span data-ttu-id="0d08b-136">O Dynamics 365 for Talent tem suporte de acordo com a [política de Ciclo de Vida de Suporte da Microsoft](https://support.microsoft.com/en-us/gp/lifecycle#gp/OSSLpolicy "Ciclo de Vida de Suporte da Microsoft"), que oferece diretrizes consistentes e previsíveis para a disponibilidade do suporte a produtos.</span><span class="sxs-lookup"><span data-stu-id="0d08b-136">Dynamics 365 for Talent is supported according to the [Microsoft Support Lifecycle policy](https://support.microsoft.com/en-us/gp/lifecycle#gp/OSSLpolicy "Microsoft Support Lifecycle"), which provides consistent and predictable guidelines for product support availability.</span></span>

