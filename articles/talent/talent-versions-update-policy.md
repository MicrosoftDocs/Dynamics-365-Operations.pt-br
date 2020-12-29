---
title: Requisitos do sistema do Talent
description: Este tópico lista os requisitos do Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 10/21/2019
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
ms.openlocfilehash: 509827d5736887f56e7754a0760af7dea76277f7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4460313"
---
# <a name="talent-system-requirements"></a><span data-ttu-id="34808-103">Requisitos do sistema do Talent</span><span class="sxs-lookup"><span data-stu-id="34808-103">Talent system requirements</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="34808-104">Este tópico descreve os requisitos para o Microsoft Dynamics 365 Talent, incluindo o Attract e o Onboard.</span><span class="sxs-lookup"><span data-stu-id="34808-104">This topic describes requirements for Microsoft Dynamics 365 Talent, including Attract and Onboard.</span></span> <span data-ttu-id="34808-105">Ele também destaca os países e regiões onde Talent está disponível, além de informações sobre idiomas e localização dos dados do Talent.</span><span class="sxs-lookup"><span data-stu-id="34808-105">It also outlines the countries and regions where Talent is available, plus information about languages and localization for Talent data.</span></span> <span data-ttu-id="34808-106">Além disso, este tópico fornece a política atualizada para o Talent.</span><span class="sxs-lookup"><span data-stu-id="34808-106">In additions, this topic provides the update policy for Talent.</span></span>

## <a name="supported-web-browsers"></a><span data-ttu-id="34808-107">Navegadores da web suportados</span><span class="sxs-lookup"><span data-stu-id="34808-107">Supported web browsers</span></span>

<span data-ttu-id="34808-108">O Microsoft Dynamics 365 Talent pode ser executado em qualquer um dos navegadores da web que são executados nos sistemas operacionais especificados:</span><span class="sxs-lookup"><span data-stu-id="34808-108">Microsoft Dynamics 365 Talent can run in any of the following web browsers that run on the specified operating systems:</span></span> 

*   <span data-ttu-id="34808-109">Microsoft Edge (última versão disponível publicamente) no Windows 10</span><span class="sxs-lookup"><span data-stu-id="34808-109">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
*   <span data-ttu-id="34808-110">Internet Explorer 11 no Windows 10, Windows 8.1 ou Windows 7</span><span class="sxs-lookup"><span data-stu-id="34808-110">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
*   <span data-ttu-id="34808-111">Google Chrome (última versão disponível publicamente)</span><span class="sxs-lookup"><span data-stu-id="34808-111">Google Chrome (latest publicly available version)</span></span>
*   <span data-ttu-id="34808-112">Apple Safari (última versão disponível publicamente)</span><span class="sxs-lookup"><span data-stu-id="34808-112">Apple Safari (latest publicly available version)</span></span>

<span data-ttu-id="34808-113">Para localizar a versão mais recente de cada navegador, vá para o site do fabricante do software.</span><span class="sxs-lookup"><span data-stu-id="34808-113">To find the latest release for each web browser, go to the software manufacturer’s website.</span></span> 

> [!NOTE]
> * <span data-ttu-id="34808-114">Para capturar imagens geradas a partir do Gravador de Tarefas e incluí-las em documentos do Microsoft Word, você deve ter uma extensão do Chrome instalada.</span><span class="sxs-lookup"><span data-stu-id="34808-114">To capture images that are generated from Task Recorder and include them in Microsoft Word documents, you must have a Chrome extension installed.</span></span> 
> * <span data-ttu-id="34808-115">O editor de fluxo de trabalho é iniciado como um aplicativo ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="34808-115">The Workflow Editor is started as a ClickOnce application.</span></span> <span data-ttu-id="34808-116">Apenas o Microsoft Edge e o Internet Explorer (em uma versão compatível do Microsoft Windows) são compatíveis com os aplicativos ClickOnces.</span><span class="sxs-lookup"><span data-stu-id="34808-116">Only Microsoft Edge and Internet Explorer (on a supported version of Microsoft Windows) support ClickOnce applications.</span></span> <span data-ttu-id="34808-117">O aplicativo Editor de fluxo de trabalho ClickOnce requer um sistema operacional compatível com 64 bits.</span><span class="sxs-lookup"><span data-stu-id="34808-117">The Workflow Editor ClickOnce application requires a 64-bit compatible operating system.</span></span>
> * <span data-ttu-id="34808-118">Para visualizar os arquivos PDF, recomendamos que você use navegadores modernos como o Microsoft Edge (última versão disponível publicamente) no Windows 10 ou o Google Chrome (última versão disponível publicamente) no Windows 10, Windows 8.1, Windows 8, Windows 7 ou no tablet Google Nexus 10.</span><span class="sxs-lookup"><span data-stu-id="34808-118">To preview PDF files, we recommend that you use modern browsers like Microsoft Edge (latest publicly available version) on Windows 10, or Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet.</span></span>
>   <span data-ttu-id="34808-119">Requisitos de rede</span><span class="sxs-lookup"><span data-stu-id="34808-119">Network requirements</span></span>
> * <span data-ttu-id="34808-120">O Dynamics 365 Talent é projetado para redes com latência de 250 a 300 milissegundos (ms) ou menos.</span><span class="sxs-lookup"><span data-stu-id="34808-120">Dynamics 365 Talent is designed for networks with latency of 250-300 milliseconds (ms) or less.</span></span> <span data-ttu-id="34808-121">Esta é a latência de um cliente de navegador para o data center do Microsoft Azure que hospeda o Talent.</span><span class="sxs-lookup"><span data-stu-id="34808-121">This is the latency from a browser client to the Microsoft Azure data center that hosts Talent.</span></span> <span data-ttu-id="34808-122">Recomendamos que você teste a latência de rede em [www.azurespeed.com](https://www.azurespeed.com "Teste de Latência do Azure").</span><span class="sxs-lookup"><span data-stu-id="34808-122">We recommend that you test network latency at [www.azurespeed.com](https://www.azurespeed.com "Azure Latency Test").</span></span>
> * <span data-ttu-id="34808-123">Os requisitos de largura de banda do Talent dependem do seu cenário.</span><span class="sxs-lookup"><span data-stu-id="34808-123">Bandwidth requirements for Talent depend on your scenario.</span></span> <span data-ttu-id="34808-124">A maioria dos cenários típicos requerem uma largura de banda de mais de 50 kilobytes por segundo (KBps).</span><span class="sxs-lookup"><span data-stu-id="34808-124">Most typical scenarios require a bandwidth of more than 50 kilobytes per second (KBps).</span></span>
> 
> [!WARNING]
> <span data-ttu-id="34808-125">Não calcule os requisitos de largura de banda de um local de cliente multiplicando o número de usuários pelos requisitos mínimos de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="34808-125">Don't compute bandwidth requirements from a client location by multiplying the number of users by the minimum bandwidth requirements.</span></span> <span data-ttu-id="34808-126">O uso simultâneo de um determinado local é muito difícil de calcular.</span><span class="sxs-lookup"><span data-stu-id="34808-126">The concurrent usage of a given location is very difficult to calculate.</span></span> <span data-ttu-id="34808-127">Para clientes que estão preocupados com os requisitos de largura de banda, use uma versão de avaliação do Talent.</span><span class="sxs-lookup"><span data-stu-id="34808-127">For customers who are concerned about bandwidth requirements, use a trial version of Talent.</span></span>

## <a name="supported-microsoft-office-applications"></a><span data-ttu-id="34808-128">Aplicativos Microsoft Office com suporte</span><span class="sxs-lookup"><span data-stu-id="34808-128">Supported Microsoft Office applications</span></span>

* <span data-ttu-id="34808-129">Para executar os suplementos do Microsoft Excel e Word, você deve ter o Microsoft Office 2016 para Windows ou Mac instalado.</span><span class="sxs-lookup"><span data-stu-id="34808-129">To run the Microsoft Excel and Word add-ins, you must have Microsoft Office 2016 for Windows or Mac installed.</span></span> <span data-ttu-id="34808-130">Para obter mais detalhes sobre os requisitos de versão, consulte [Solução de problemas de integração do Office](../dev-itpro/office-integration/office-integration-troubleshooting.md "Solução de problemas de integração do Office").</span><span class="sxs-lookup"><span data-stu-id="34808-130">For more details about version requirements, see [Office integration troubleshooting](../dev-itpro/office-integration/office-integration-troubleshooting.md "Office integration troubleshooting").</span></span>
* <span data-ttu-id="34808-131">Para exibir documentos que são gerados pela funcionalidade Exportar para o Excel ou Exportar para o Word, você deve ter o Microsoft Office 2007 ou posterior instalado.</span><span class="sxs-lookup"><span data-stu-id="34808-131">To view documents that are generated by the Export to Excel or Export to Word functionality, you must have Microsoft Office 2007 or later installed.</span></span>

## <a name="regional-availability-languages-and-localization"></a><span data-ttu-id="34808-132">Disponibilidade regional, idiomas e localização</span><span class="sxs-lookup"><span data-stu-id="34808-132">Regional availability, languages, and localization</span></span>

<span data-ttu-id="34808-133">Você pode baixar um arquivo PDF dos países, regiões e idiomas para os quais Talent oferece suporte em [Disponibilidade internacional do Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).</span><span class="sxs-lookup"><span data-stu-id="34808-133">You can download a PDF file of the countries, regions, and languages Talent supports at [International availability of Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).</span></span> 

> [!NOTE]
> <span data-ttu-id="34808-134">Por mais que a interface de usuário esteja localizada em outros idiomas, todos os dados do usuário são armazenados no idioma no qual foi inserido.</span><span class="sxs-lookup"><span data-stu-id="34808-134">While the user interface is localized into other languages, all user data is stored in the language in which it was entered.</span></span> <span data-ttu-id="34808-135">Você pode criar e-mails e modelos em outros idiomas, mas os dados como informações de agendamento só estão disponíveis em Inglês no momento.</span><span class="sxs-lookup"><span data-stu-id="34808-135">You can create emails and templates in other languages, but data such as scheduling information is only available in English at this time.</span></span>

<span data-ttu-id="34808-136">Se você é um desenvolvedor interessado na criação de personalizações específicas do país ou região, ou em criar uma solução para um país ou região não suportado atualmente pela Microsoft, consulte [Globalização](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).</span><span class="sxs-lookup"><span data-stu-id="34808-136">If you're a developer interested in creating country- or region-specific customizations, or in creating a solution for a country or region not currently supported by Microsoft, see [Globalization](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).</span></span>

