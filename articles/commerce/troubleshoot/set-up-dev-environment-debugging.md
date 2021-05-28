---
title: Configurar um ambiente de desenvolvimento de comércio eletrônico para depurar em uma máquina virtual do servidor de varejo de nível 1
description: Este tópico explica como configurar um ambiente de desenvolvimento de comércio eletrônico para depurar em uma máquina virtual (VM) do servidor de varejo de nível 1.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 38a616c418c3b32490c9adaf69a69af0d47d3478
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019437"
---
# <a name="set-up-an-e-commerce-development-environment-to-debug-against-a-tier-1-retail-server-virtual-machine"></a><span data-ttu-id="f7388-103">Configurar um ambiente de desenvolvimento de comércio eletrônico para depurar em uma máquina virtual do servidor de varejo de nível 1</span><span class="sxs-lookup"><span data-stu-id="f7388-103">Set up an e-commerce development environment to debug against a Tier 1 Retail Server virtual machine</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f7388-104">Este tópico explica como configurar um ambiente de desenvolvimento de comércio eletrônico para depurar em uma máquina virtual (VM) do servidor de varejo de nível 1.</span><span class="sxs-lookup"><span data-stu-id="f7388-104">This topic explains how to set up an e-commerce development environment to debug against a Tier 1 Retail Server virtual machine (VM).</span></span>

## <a name="description"></a><span data-ttu-id="f7388-105">descrição</span><span class="sxs-lookup"><span data-stu-id="f7388-105">Description</span></span>

<span data-ttu-id="f7388-106">Os ambientes da camada 1 do Microsoft Dynamics 365 Commerce geralmente são implantados para desenvolvimento de extensões de Commerce Runtime (CRT) e ponto de venda (PDV).</span><span class="sxs-lookup"><span data-stu-id="f7388-106">Microsoft Dynamics 365 Commerce Tier 1 environments are typically deployed for Commerce runtime (CRT) and point of sale (POS) extension development.</span></span> <span data-ttu-id="f7388-107">São ambientes autônomos.</span><span class="sxs-lookup"><span data-stu-id="f7388-107">They are standalone environments.</span></span> <span data-ttu-id="f7388-108">Devido à natureza do software como um serviço (SaaS) da arquitetura, eles não incluem componentes de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="f7388-108">Because of the software as a service (SaaS) nature of the architecture, they don't include e-commerce components.</span></span>

<span data-ttu-id="f7388-109">Em algumas situações, talvez você queira testar chamadas para extensões em um ambiente de nível 1, de forma que possa depurar extensões de componentes de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="f7388-109">In some scenarios, you might want to test calls to extensions in a Tier 1 environment, so that you can debug extensions from e-commerce components.</span></span> <span data-ttu-id="f7388-110">Para obter instruções gerais, consulte [Depuração em relação a um ambiente de desenvolvimento do Commerce de Camada 1](../e-commerce-extensibility/debug-tier-1.md).</span><span class="sxs-lookup"><span data-stu-id="f7388-110">For general instructions, see [Debug against a Tier 1 Commerce development environment](../e-commerce-extensibility/debug-tier-1.md).</span></span>

<span data-ttu-id="f7388-111">Quando você depura um ambiente de nível 1, porque o site agora está chamando um servidor de varejo diferente, as chamadas entre servidores podem causar vários erros relacionados à política de segurança de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="f7388-111">When you debug against a Tier 1 environment, because the site is now calling a different Retail Server, cross-server calls might cause various errors that are related to the content security policy.</span></span>

<span data-ttu-id="f7388-112">A ilustração a seguir mostra um exemplo de um erro que pode ocorrer quando uma variante está selecionada em uma página de detalhes do produto.</span><span class="sxs-lookup"><span data-stu-id="f7388-112">The following illustration shows an example of an error that might occur when a variant is selected on a product details page.</span></span>

![Erro quando uma grade é selecionada em uma página de detalhes do produto](media/unhandled-rejection-error.jpg)

<span data-ttu-id="f7388-114">A ilustração a seguir mostra um exemplo de erro semelhante em ferramentas de depuração de um navegador (Ferramentas para Desenvolvedores F12).</span><span class="sxs-lookup"><span data-stu-id="f7388-114">The following illustration shows an example of a similar error in a browser's debugger tools (F12 Developer Tools).</span></span> <span data-ttu-id="f7388-115">A mensagem de erro menciona violação da diretiva da política de segurança de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="f7388-115">The error message mentions violation of the content security policy directive.</span></span>

![Erro nas ferramentas do depurador](media/debugger-tools-error.JPG)

## <a name="resolution"></a><span data-ttu-id="f7388-117">Resolução</span><span class="sxs-lookup"><span data-stu-id="f7388-117">Resolution</span></span>

### <a name="disable-the-content-security-policy-for-the-site-in-commerce-site-builder"></a><span data-ttu-id="f7388-118">Desabilitar a diretiva de segurança de conteúdo do site no criador de sites do Commerce</span><span class="sxs-lookup"><span data-stu-id="f7388-118">Disable the content security policy for the site in Commerce site builder</span></span>

1. <span data-ttu-id="f7388-119">Selecione o site no qual você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="f7388-119">Select the site that you're working on.</span></span>
1. <span data-ttu-id="f7388-120">Selecione **Configurações** e, em seguida, selecione **Extensões**.</span><span class="sxs-lookup"><span data-stu-id="f7388-120">Select **Settings**, and then select **Extensions**.</span></span>
1. <span data-ttu-id="f7388-121">Na guia **Política de segurança de conteúdo**, selecione **Desabilitar política de segurança de conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="f7388-121">On the **Content security policy** tab, select **Disable content security policy**.</span></span>
1. <span data-ttu-id="f7388-122">Selecione **Salvar e publicar**.</span><span class="sxs-lookup"><span data-stu-id="f7388-122">Select **Save and publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="f7388-123">A entrada de empresa a consumidor (B2C) não funcionará em um ambiente de desenvolvimento local.</span><span class="sxs-lookup"><span data-stu-id="f7388-123">Business-to-consumer (B2C) sign-in won't work in a local development environment.</span></span> <span data-ttu-id="f7388-124">No entanto, você pode usar finalizações de compra do convidado ou compilar simulações de página para simular uma entrada do usuário, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="f7388-124">However, you can use guest checkouts or build page mocks to simulate a user sign-in as required.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f7388-125">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f7388-125">Additional resources</span></span>

[<span data-ttu-id="f7388-126">Comece com o desenvolvimento de extensibilidade online de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="f7388-126">Get started with e-commerce online extensibility development</span></span>](../e-commerce-extensibility/sdk-getting-started.md)

[<span data-ttu-id="f7388-127">Gerenciar a CSP (política de segurança de conteúdo) no site de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="f7388-127">Manage content security policy (CSP) on e-commerce site</span></span>](../manage-csp.md)
