---
title: "Configurações de solicitação de fornecedor"
description: "Este tópico descreve os campos que precisam ser preenchidos em uma nova solicitação do fornecedor."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendProspectiveVendorRegistrationConfig
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 9089b9ad773890424a6f73107a26a35a32e988ae
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="vendor-request-configurations"></a><span data-ttu-id="a3902-103">Configurações de solicitação de fornecedor</span><span class="sxs-lookup"><span data-stu-id="a3902-103">Vendor request configurations</span></span>
[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="a3902-104">Para concluir uma solicitação do fornecedor, uma pessoa de contato do fornecedor deve concluir o assistente de registro de fornecedor em potencial.</span><span class="sxs-lookup"><span data-stu-id="a3902-104">To complete a vendor request, a vendor contact person must complete the prospective vendor registration wizard.</span></span>

<span data-ttu-id="a3902-105">No formulário **Configurações da solicitação do fornecedor**, você pode criar os perfis que especificam campos obrigatórios e campos visíveis em assistente de registro de fornecedor potencial.</span><span class="sxs-lookup"><span data-stu-id="a3902-105">In the **Vendor request configurations** form, you can create profiles that specify required fields and visible fields in the prospective vendor registration wizard.</span></span>

<span data-ttu-id="a3902-106">O assistente de registro de fornecedor começará a perguntar para o usuário do fornecedor potencial em qual país/região o fornecedor está fazendo negócios.</span><span class="sxs-lookup"><span data-stu-id="a3902-106">The vendor registration wizard will start out by asking the prospective vendor user which country/region the vendor is doing business in.</span></span> <span data-ttu-id="a3902-107">Essas informações determinam a configuração aplicável.</span><span class="sxs-lookup"><span data-stu-id="a3902-107">This information determines the applicable configuration.</span></span> <span data-ttu-id="a3902-108">Se nenhuma configuração específica for definida para um país/região, a configuração padrão será usada.</span><span class="sxs-lookup"><span data-stu-id="a3902-108">If no specific configuration is defined for a country/region, a default configuration will be used.</span></span>

### <a name="set-up-a-vendor-request-configuration"></a><span data-ttu-id="a3902-109">Definição de uma configuração de solicitação de fornecedor</span><span class="sxs-lookup"><span data-stu-id="a3902-109">Set up a vendor request configuration</span></span>

<span data-ttu-id="a3902-110">Por padrão, há uma configuração de fornecedor disponível no formulário de configurações de solicitação do Fornecedor.</span><span class="sxs-lookup"><span data-stu-id="a3902-110">By default, there is a vendor configuration available in the Vendor request configurations form.</span></span>

<span data-ttu-id="a3902-111">Não é possível selecionar país/regiões para a configuração padrão, assim a seção **Países/regiões** não pode ser alterada.</span><span class="sxs-lookup"><span data-stu-id="a3902-111">It is not possible to select country/regions for the default configuration, so the **Countries/regions** section cannot be changed.</span></span>

1. <span data-ttu-id="a3902-112">Clique em **Compras** > **Configuração** > **Fornecedores** e depois em **Configurações de solicitação de fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="a3902-112">Click **Procurement and sourcing** > **Setup** > **Vendors**, and then click **Vendor request configurations**.</span></span>
2. <span data-ttu-id="a3902-113">Clique na guia **Campos** para definir o status dos campos listados.</span><span class="sxs-lookup"><span data-stu-id="a3902-113">Click the **Fields** tab to set the status of the listed fields.</span></span>
3. <span data-ttu-id="a3902-114">Oculto (Não visível)</span><span class="sxs-lookup"><span data-stu-id="a3902-114">Hidden (Not visible)</span></span>
4. <span data-ttu-id="a3902-115">Exibido (Visível, mas não obrigatório)</span><span class="sxs-lookup"><span data-stu-id="a3902-115">Displayed (Visible but not mandatory)</span></span>
5. <span data-ttu-id="a3902-116">Obrigatório (Visível e obrigatório)</span><span class="sxs-lookup"><span data-stu-id="a3902-116">Required (Visible and mandatory)</span></span>
6. <span data-ttu-id="a3902-117">Clique na guia **Conteúdo** para especificar se o texto está prestes a ser mostrado no assistente e se há uma confirmação de que o usuário do fornecedor potencial deve aceitar isso, antes de se mover para a próxima etapa no assistente.</span><span class="sxs-lookup"><span data-stu-id="a3902-117">Click the **Content** tab to specify if text is going to be shown on the wizard and if there should be an acknowledgement that the prospective vendor user must accept this before moving to the next step in the wizard.</span></span> <span data-ttu-id="a3902-118">A confirmação será solicitada para os termos e as condições que o usuário deve aceitar para continuar.</span><span class="sxs-lookup"><span data-stu-id="a3902-118">The acknowledgement will be requested for any terms and conditions that the user must accept to continue.</span></span>

<span data-ttu-id="a3902-119">Você também pode inserir uma mensagem de confirmação que será exibida quando o assistente for finalizado, e poderá adicionar um ou mais questionários.</span><span class="sxs-lookup"><span data-stu-id="a3902-119">You can also enter a confirmation message that will be displayed when the wizard is finalized, and you can add one or more questionnaires.</span></span>

### <a name="create-a-vendor-configuration-for-a-specific-countryregion"></a><span data-ttu-id="a3902-120">Crie uma configuração de fornecedor para um país/região específicos</span><span class="sxs-lookup"><span data-stu-id="a3902-120">Create a vendor configuration for a specific country/region</span></span>
1.  <span data-ttu-id="a3902-121">Clique em **Compras** > **Configuração** > **Fornecedores** e depois em **Configurações de solicitação de fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="a3902-121">Click **Procurement and sourcing** > **Setup** > **Vendors**, and then click **Vendor request configurations**.</span></span>
2.  <span data-ttu-id="a3902-122">Clique em **Novo** para criar uma nova configuração, e fornecer um nome para a configuração.</span><span class="sxs-lookup"><span data-stu-id="a3902-122">Click **New** to create a new configuration, and provide a name for the configuration.</span></span>
3.  <span data-ttu-id="a3902-123">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a3902-123">Click **Save**.</span></span>
4.  <span data-ttu-id="a3902-124">Abra a guia **País/regiões** para selecionar o país/região em que a configuração será usada.</span><span class="sxs-lookup"><span data-stu-id="a3902-124">Open the **Country/regions** tab to select the country/region that the configuration should be used for.</span></span>
5.  <span data-ttu-id="a3902-125">Conclua a configuração seguindo as diretrizes para a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="a3902-125">Complete the configuration by following the guidelines for the default configuration.</span></span>


