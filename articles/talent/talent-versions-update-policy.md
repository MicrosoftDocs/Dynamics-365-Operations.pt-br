---
title: Requisitos do sistema e política de atualização do Talent
description: Este tópico lista os requisitos do Dynamics 365 for Talent. A política de atualização também está descrita.
author: andreabichsel
manager: AnnBe
ms.date: 05/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: ea8b7485b142245a359648a2a85d2a3e2a6d6629
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1517345"
---
# <a name="talent-system-requirements-and-update-policy"></a><span data-ttu-id="0509f-104">Requisitos do sistema e política de atualização do Talent</span><span class="sxs-lookup"><span data-stu-id="0509f-104">Talent system requirements and update policy</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0509f-105">Este tópico descreve os requisitos do Microsoft Dynamics 365 for Talent, incluindo Attract, Onboard e Core HR.</span><span class="sxs-lookup"><span data-stu-id="0509f-105">This topic describes requirements for Microsoft Dynamics 365 for Talent, including Attract, Onboard, and Core HR.</span></span> <span data-ttu-id="0509f-106">Ele também destaca os países e regiões onde Talent está disponível, além de informações sobre idiomas e localização dos dados do Talent.</span><span class="sxs-lookup"><span data-stu-id="0509f-106">It also outlines the countries and regions where Talent is available, plus information about languages and localization for Talent data.</span></span> <span data-ttu-id="0509f-107">Além disso, este tópico fornece a política atualizada para o Talent.</span><span class="sxs-lookup"><span data-stu-id="0509f-107">In additions, this topic provides the update policy for Talent.</span></span>

## <a name="supported-web-browsers"></a><span data-ttu-id="0509f-108">Navegadores da web suportados</span><span class="sxs-lookup"><span data-stu-id="0509f-108">Supported web browsers</span></span>

<span data-ttu-id="0509f-109">O aplicativo da web do Microsoft Dynamics 365 for Talent pode ser executado em qualquer um dos navegadores da web que são executados nos sistemas operacionais especificados:</span><span class="sxs-lookup"><span data-stu-id="0509f-109">The Microsoft Dynamics 365 for Talent web application can run in any of the following web browsers that run on the specified operating systems:</span></span> 

*   <span data-ttu-id="0509f-110">Microsoft Edge (última versão disponível publicamente) no Windows 10</span><span class="sxs-lookup"><span data-stu-id="0509f-110">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
*   <span data-ttu-id="0509f-111">Internet Explorer 11 no Windows 10, Windows 8.1 ou Windows 7</span><span class="sxs-lookup"><span data-stu-id="0509f-111">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
*   <span data-ttu-id="0509f-112">Google Chrome (última versão disponível publicamente)</span><span class="sxs-lookup"><span data-stu-id="0509f-112">Google Chrome (latest publicly available version)</span></span>
*   <span data-ttu-id="0509f-113">Apple Safari (última versão disponível publicamente)</span><span class="sxs-lookup"><span data-stu-id="0509f-113">Apple Safari (latest publicly available version)</span></span>

<span data-ttu-id="0509f-114">Para localizar a versão mais recente de cada navegador, vá para o site do fabricante do software.</span><span class="sxs-lookup"><span data-stu-id="0509f-114">To find the latest release for each web browser, go to the software manufacturer’s website.</span></span> 

> [!NOTE]
> * <span data-ttu-id="0509f-115">Para capturar imagens geradas a partir do Gravador de Tarefas e incluí-las em documentos do Microsoft Word, você deve ter uma extensão do Chrome instalada.</span><span class="sxs-lookup"><span data-stu-id="0509f-115">To capture images that are generated from Task Recorder and include them in Microsoft Word documents, you must have a Chrome extension installed.</span></span> 
> * <span data-ttu-id="0509f-116">O editor de fluxo de trabalho é iniciado como um aplicativo ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="0509f-116">The Workflow Editor is started as a ClickOnce application.</span></span> <span data-ttu-id="0509f-117">Apenas o Microsoft Edge e o Internet Explorer (em uma versão compatível do Microsoft Windows) são compatíveis com os aplicativos ClickOnces.</span><span class="sxs-lookup"><span data-stu-id="0509f-117">Only Microsoft Edge and Internet Explorer (on a supported version of Microsoft Windows) support ClickOnce applications.</span></span> <span data-ttu-id="0509f-118">O aplicativo Editor de fluxo de trabalho ClickOnce requer um sistema operacional compatível com 64 bits.</span><span class="sxs-lookup"><span data-stu-id="0509f-118">The Workflow Editor ClickOnce application requires a 64-bit compatible operating system.</span></span>
> * <span data-ttu-id="0509f-119">Para visualizar os arquivos PDF, recomendamos que você use navegadores modernos como o Microsoft Edge (última versão disponível publicamente) no Windows 10 ou o Google Chrome (última versão disponível publicamente) no Windows 10, Windows 8.1, Windows 8, Windows 7 ou no tablet Google Nexus 10.</span><span class="sxs-lookup"><span data-stu-id="0509f-119">To preview PDF files, we recommend that you use modern browsers like Microsoft Edge (latest publicly available version) on Windows 10, or Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet.</span></span>
>   <span data-ttu-id="0509f-120">Requisitos de rede</span><span class="sxs-lookup"><span data-stu-id="0509f-120">Network requirements</span></span>
> * <span data-ttu-id="0509f-121">O Dynamics 365 for Talent é projetado para redes com latência de 250 a 300 milissegundos (ms) ou menos.</span><span class="sxs-lookup"><span data-stu-id="0509f-121">Dynamics 365 for Talent is designed for networks with latency of 250-300 milliseconds (ms) or less.</span></span> <span data-ttu-id="0509f-122">Esta é a latência de um cliente de navegador para o centro de dados do Microsoft Azureque hospeda o Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="0509f-122">This is the latency from a browser client to the Microsoft Azure data center that hosts Dynamics 365 for Talent.</span></span> <span data-ttu-id="0509f-123">Recomendamos que você teste a latência de rede em [www.azurespeed.com](https://www.azurespeed.com "Teste de latência do Azure").</span><span class="sxs-lookup"><span data-stu-id="0509f-123">We recommend that you test network latency at [www.azurespeed.com](https://www.azurespeed.com "Azure Latency Test").</span></span>
> * <span data-ttu-id="0509f-124">Os requisitos de largura de banda do Dynamics 365 for Talent dependem do seu cenário.</span><span class="sxs-lookup"><span data-stu-id="0509f-124">Bandwidth requirements for Dynamics 365 for Talent depend on your scenario.</span></span> <span data-ttu-id="0509f-125">A maioria dos cenários típicos requerem uma largura de banda de mais de 50 kilobytes por segundo (KBps).</span><span class="sxs-lookup"><span data-stu-id="0509f-125">Most typical scenarios require a bandwidth of more than 50 kilobytes per second (KBps).</span></span>
> 
> [!WARNING]
> <span data-ttu-id="0509f-126">Não calcule os requisitos de largura de banda de um local de cliente multiplicando o número de usuários pelos requisitos mínimos de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="0509f-126">Don't compute bandwidth requirements from a client location by multiplying the number of users by the minimum bandwidth requirements.</span></span> <span data-ttu-id="0509f-127">O uso simultâneo de um determinado local é muito difícil de calcular.</span><span class="sxs-lookup"><span data-stu-id="0509f-127">The concurrent usage of a given location is very difficult to calculate.</span></span> <span data-ttu-id="0509f-128">Para clientes que estão preocupados com os requisitos de largura de banda, use uma versão de avaliação do Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="0509f-128">For customers who are concerned about bandwidth requirements, use a trial version of Dynamics 365 for Talent.</span></span>

## <a name="supported-microsoft-office-applications"></a><span data-ttu-id="0509f-129">Aplicativos Microsoft Office com suporte</span><span class="sxs-lookup"><span data-stu-id="0509f-129">Supported Microsoft Office applications</span></span>

* <span data-ttu-id="0509f-130">Para executar os suplementos do Microsoft Excel e Word, você deve ter o Microsoft Office 2016 para Windows ou Mac instalado.</span><span class="sxs-lookup"><span data-stu-id="0509f-130">To run the Microsoft Excel and Word add-ins, you must have Microsoft Office 2016 for Windows or Mac installed.</span></span> <span data-ttu-id="0509f-131">Para obter mais detalhes sobre requisitos de versão, consulte [Solução de problemas de integração do Office](../dev-itpro/office-integration/office-integration-troubleshooting.md "Solução de problemas de integração do Office").</span><span class="sxs-lookup"><span data-stu-id="0509f-131">For more details about version requirements, see [Office integration troubleshooting](../dev-itpro/office-integration/office-integration-troubleshooting.md "Office integration troubleshooting").</span></span>
* <span data-ttu-id="0509f-132">Para exibir documentos que são gerados pela funcionalidade Exportar para o Excel ou Exportar para o Word, você deve ter o Microsoft Office 2007 ou posterior instalado.</span><span class="sxs-lookup"><span data-stu-id="0509f-132">To view documents that are generated by the Export to Excel or Export to Word functionality, you must have Microsoft Office 2007 or later installed.</span></span>

## <a name="regional-availability-languages-and-localization"></a><span data-ttu-id="0509f-133">Disponibilidade regional, idiomas e localização</span><span class="sxs-lookup"><span data-stu-id="0509f-133">Regional availability, languages, and localization</span></span>

<span data-ttu-id="0509f-134">Você pode baixar um arquivo PDF dos países, regiões e idiomas para os quais Talent oferece suporte em [Disponibilidade internacional do Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).</span><span class="sxs-lookup"><span data-stu-id="0509f-134">You can download a PDF file of the countries, regions, and languages Talent supports at [International availability of Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).</span></span> 

> [!NOTE]
> <span data-ttu-id="0509f-135">Por mais que a interface de usuário esteja localizada em outros idiomas, todos os dados do usuário são armazenados no idioma no qual foi inserido.</span><span class="sxs-lookup"><span data-stu-id="0509f-135">While the user interface is localized into other languages, all user data is stored in the language in which it was entered.</span></span> <span data-ttu-id="0509f-136">Você pode criar e-mails e modelos em outros idiomas, mas os dados como informações de agendamento só estão disponíveis em Inglês no momento.</span><span class="sxs-lookup"><span data-stu-id="0509f-136">You can create emails and templates in other languages, but data such as scheduling information is only available in English at this time.</span></span>

<span data-ttu-id="0509f-137">Se você é um desenvolvedor interessado na criação de personalizações específicas do país ou região, ou em criar uma solução para um país ou região não suportado atualmente pela Microsoft, consulte [Globalização](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).</span><span class="sxs-lookup"><span data-stu-id="0509f-137">If you're a developer interested in creating country- or region-specific customizations, or in creating a solution for a country or region not currently supported by Microsoft, see [Globalization](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).</span></span>

## <a name="update-policy"></a><span data-ttu-id="0509f-138">Política de atualização</span><span class="sxs-lookup"><span data-stu-id="0509f-138">Update policy</span></span>

<span data-ttu-id="0509f-139">O Dynamics 365 for Talent é apresentado como uma oferta da nuvem.</span><span class="sxs-lookup"><span data-stu-id="0509f-139">Microsoft Dynamics 365 for Talent is serviced as a cloud offering.</span></span> <span data-ttu-id="0509f-140">As atualizações do Dynamics 365 for Talent são contínuas e são aplicadas automaticamente pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0509f-140">Updates to Dynamics 365 for Talent are continuous and applied automatically by Microsoft.</span></span>

<span data-ttu-id="0509f-141">As atualizações são liberadas em uma cadência normal e serão feitas em todos os ambientes.</span><span class="sxs-lookup"><span data-stu-id="0509f-141">Updates are released on a regular cadence and will be made to all environments.</span></span> <span data-ttu-id="0509f-142">O Dynamics 365 for Talent é compatível de acordo com a [política de Ciclo de Vida de Suporte da Microsoft](https://support.microsoft.com/en-us/gp/lifecycle#gp/OSSLpolicy "Ciclo de Vida de Suporte da Microsoft"), que oferece diretrizes consistentes e previsíveis para a disponibilidade do suporte a produtos.</span><span class="sxs-lookup"><span data-stu-id="0509f-142">Dynamics 365 for Talent is supported according to the [Microsoft Support Lifecycle policy](https://support.microsoft.com/en-us/gp/lifecycle#gp/OSSLpolicy "Microsoft Support Lifecycle"), which provides consistent and predictable guidelines for product support availability.</span></span>
