---
title: Estender a funcionalidade do Microsoft Dynamics 365 for Talent
description: "Se você criou um Microsoft PowerApps, poderá iniciar esses aplicativos a partir de links do Microsoft Dynamics 365 for Talent."
author: rschloma
manager: AnnBe
ms.date: 11/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-28
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: e1d0bbd71737001579218068e2ab0e02bc973f38
ms.contentlocale: pt-br
ms.lasthandoff: 01/19/2018

---
# <a name="extend-the-functionality-of-microsoft-dynamics-365-for-talent"></a><span data-ttu-id="82b31-103">Estender a funcionalidade do Microsoft Dynamics 365 for Talent</span><span class="sxs-lookup"><span data-stu-id="82b31-103">Extend the functionality of Microsoft Dynamics 365 for Talent</span></span>
<span data-ttu-id="82b31-104">Se você criou um Microsoft PowerApps, poderá iniciar esses aplicativos a partir de links do Microsoft Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="82b31-104">If you’ve created any Microsoft PowerApps, you can start those applications from links within Microsoft Dynamics 365 for Talent.</span></span> <span data-ttu-id="82b31-105">Para configurar o acesso aos seus aplicativos, será necessário configurar as informações no Talent em uma página de configuração que você pode abrir no espaço de trabalho **Administração do sistema**.</span><span class="sxs-lookup"><span data-stu-id="82b31-105">To set up access to your applications, you’ll need to set up some information in Talent on a configuration page that you can open from the **System administration** workspace.</span></span>

## <a name="configuring-embedded-powerapps-within-talent"></a><span data-ttu-id="82b31-106">Configurando o PowerApps inserido no Talent</span><span class="sxs-lookup"><span data-stu-id="82b31-106">Configuring embedded PowerApps within Talent</span></span>
<span data-ttu-id="82b31-107">Use a página **Configurar Microsoft PowerApps inserido** para configurar as páginas do Talent para iniciar os aplicativos do PowerApps.</span><span class="sxs-lookup"><span data-stu-id="82b31-107">Use the **Set embedded Microsoft PowerApps** page to configure Talent pages to start PowerApps applications.</span></span> <span data-ttu-id="82b31-108">Para abrir a página **Configurar Microsoft PowerApps inserido**, abra o espaço de trabalho **Administração do sistema** e abra a guia **Links**. Selecione **Microsoft PowerApps** no grupo **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="82b31-108">To open the **Set embedded Microsoft PowerApps** page, open the **System administration** workspace and then open the **Links** tab. Select **Microsoft PowerApps** from the **Setup** group.</span></span> 

<span data-ttu-id="82b31-109">As seguintes informações são inseridas ou configuradas nessa página:</span><span class="sxs-lookup"><span data-stu-id="82b31-109">The following information is entered or set on this page:</span></span> 

> - <span data-ttu-id="82b31-110">Um nome descritivo ou um identificador para cada aplicativo do PowerApps.</span><span class="sxs-lookup"><span data-stu-id="82b31-110">A descriptive name or identifier for each PowerApps application.</span></span>
> - <span data-ttu-id="82b31-111">Um identificador exclusivo (GUID) para cada aplicativo adicionado a uma página do Talent.</span><span class="sxs-lookup"><span data-stu-id="82b31-111">A unique identifier (GUID) for each application that you add to a Talent page.</span></span> <span data-ttu-id="82b31-112">A ID do aplicativo está disponível no site de PowerApps [powerapps.com](http://powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="82b31-112">The app ID is available on the PowerApps site, [powerapps.com](http://powerapps.com/).</span></span> 
> - <span data-ttu-id="82b31-113">A página da qual os usuários podem abrir um aplicativo ou relatório.</span><span class="sxs-lookup"><span data-stu-id="82b31-113">The page from which users can open an application or report.</span></span> <span data-ttu-id="82b31-114">Nem todas as páginas do Talent oferecem suporte a relatórios do Power BI ou do PowerApps inserido.</span><span class="sxs-lookup"><span data-stu-id="82b31-114">Not all Talent pages support embedded PowerApps and Power BI reports.</span></span> 

 > [!NOTE]
 >  <span data-ttu-id="82b31-115">Insira o nome interno da página, e não o nome de exibição que é exibido na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="82b31-115">Enter the internal name of the page, rather than the display name that appears at the top of the page.</span></span> <span data-ttu-id="82b31-116">Para encontrar o nome interno, abra a página da qual você precisa do nome interno e clique com o botão direito em qualquer lugar nela.</span><span class="sxs-lookup"><span data-stu-id="82b31-116">To find the internal name, open the page that you need the internal name of, and right-click anywhere on the page.</span></span> <span data-ttu-id="82b31-117">Quando o menu abrir, passe o mouse sobre o item **Informações de formulário**.</span><span class="sxs-lookup"><span data-stu-id="82b31-117">When the menu opens, hover over the **Form information** item.</span></span> <span data-ttu-id="82b31-118">O nome do formulário interno será exibido ao lado do item **Informações do formulário** no menu.</span><span class="sxs-lookup"><span data-stu-id="82b31-118">The internal form name is displayed next to the **Form information** item in the menu.</span></span>
 
> - <span data-ttu-id="82b31-119">Especifique o controle de formulário do qual o aplicativo pode recuperar dados de contexto.</span><span class="sxs-lookup"><span data-stu-id="82b31-119">Specify the form control from which the application can retrieve context data.</span></span> <span data-ttu-id="82b31-120">Por exemplo, um aplicativo pode usar dados sobre um trabalhador.</span><span class="sxs-lookup"><span data-stu-id="82b31-120">For example, an application might use data about a worker.</span></span> <span data-ttu-id="82b31-121">Se você inserir a página **Trabalhador** no campo **Contexto**, a página **Trabalhador** abrirá quando você iniciar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="82b31-121">If you enter the **Worker** page in the **Context** field, the **Worker** page will open when you start the application.</span></span> <span data-ttu-id="82b31-122">Uma entrada no **Campo de contexto** é opcional.</span><span class="sxs-lookup"><span data-stu-id="82b31-122">An entry in the **Context field** is optional.</span></span> 
> - <span data-ttu-id="82b31-123">Defina o tamanho da caixa de diálogo na qual o aplicativo PowerApps será executado.</span><span class="sxs-lookup"><span data-stu-id="82b31-123">Set the size of the dialog box on which the PowerApps application will run.</span></span> <span data-ttu-id="82b31-124">As caixas de diálogo são designadas como "pequenas"ou “grandes” para otimizar a interface de usuário quando o aplicativo for executado em um telefone ou em um dispositivo maior, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="82b31-124">The dialog boxes are designated as “small” or “large” to optimize the user interface when your application for running on a phone or a larger device, respectively.</span></span> 

<span data-ttu-id="82b31-125">Também é possível especificar para quais entidades legais um aplicativo estará disponível, ou você pode disponibilizá-lo para todas as entidades legais.</span><span class="sxs-lookup"><span data-stu-id="82b31-125">You can also specify which legal entities an application will be available for, or you can make it available to all your legal entities.</span></span> <span data-ttu-id="82b31-126">Por padrão, os aplicativos do PowerApps estão disponíveis para todas as entidades legais.</span><span class="sxs-lookup"><span data-stu-id="82b31-126">By default, your PowerApps applications are available to all legal entities.</span></span>

## <a name="opening-an-application"></a><span data-ttu-id="82b31-127">Abrindo um aplicativo</span><span class="sxs-lookup"><span data-stu-id="82b31-127">Opening an application</span></span>
<span data-ttu-id="82b31-128">Ao configurar os aplicativos do PowerApps inseridos, links para os aplicativos especificados serão adicionados às páginas no Talent.</span><span class="sxs-lookup"><span data-stu-id="82b31-128">When you’ve configured embedded PowerApps applications, links to the applications that you specified will be added to the pages within Talent.</span></span> <span data-ttu-id="82b31-129">Clique em um link para abrir um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="82b31-129">Click a link to open an application.</span></span> 



