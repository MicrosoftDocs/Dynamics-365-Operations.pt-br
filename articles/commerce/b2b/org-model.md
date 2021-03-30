---
title: Criar hierarquias de modelagem de organização para organizações B2B
description: Este tópico descreve como criar hierarquias de modelagem organizacional para organizações business-to-business (B2B).
author: josaw1
manager: AnnBe
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 91cb01637faa69bd3c7fefefae69c60cb948510e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211216"
---
# <a name="create-org-modeling-hierarchies-for-b2b-organizations"></a><span data-ttu-id="5e3d7-103">Criar hierarquias de modelagem de organização para organizações B2B</span><span class="sxs-lookup"><span data-stu-id="5e3d7-103">Create org modeling hierarchies for B2B organizations</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5e3d7-104">Este tópico descreve como criar hierarquias de modelagem organizacional para organizações business-to-business (B2B) no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5e3d7-104">This topic describes how to create organizational modeling hierarchies for business-to-business (B2B) organizations in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="5e3d7-105">Na sede do Commerce, as organizações parceiras comerciais são representadas por entidades de clientes e hierarquia de clientes.</span><span class="sxs-lookup"><span data-stu-id="5e3d7-105">In Commerce headquarters, business partner organizations are represented by customer and customer hierarchy entities.</span></span> <span data-ttu-id="5e3d7-106">A organização parceira comercial e seus usuários são representados como clientes, e as hierarquias do cliente são usadas para associar esses clientes entre si.</span><span class="sxs-lookup"><span data-stu-id="5e3d7-106">The business partner organization and its users are represented as customers, and customer hierarchies are used to associate those customers with each other.</span></span>

<span data-ttu-id="5e3d7-107">Quando é aprovada uma solicitação de parceiro comercial para ingressar em um site de comércio eletrônico B2B, as seguintes ações são executadas:</span><span class="sxs-lookup"><span data-stu-id="5e3d7-107">When a business partner request to join a B2B e-commerce site is approved, the following actions are performed:</span></span>

- <span data-ttu-id="5e3d7-108">Dois novos registros de clientes são criados no sistema: um registro de cliente de **Tipo Organização** para a organização parceira comercial e um registro de cliente de **Tipo Pessoa** para o solicitante (ou seja, o usuário parceiro comercial que enviou a solicitação).</span><span class="sxs-lookup"><span data-stu-id="5e3d7-108">Two new customer records are created in the system: a **Type Organization** customer record for the business partner organization and a **Type Person** customer record for the requestor (that is, the business partner user who submitted the request).</span></span>
- <span data-ttu-id="5e3d7-109">Um novo registro de hierarquia de cliente é criado em **Cliente \> Hierarquia do cliente**.</span><span class="sxs-lookup"><span data-stu-id="5e3d7-109">A new customer hierarchy record is created under **Customer \> Customer hierarchy**.</span></span> <span data-ttu-id="5e3d7-110">Este registro tem as seguintes propriedades de cabeçalho:</span><span class="sxs-lookup"><span data-stu-id="5e3d7-110">This record has the following header properties:</span></span>

    - <span data-ttu-id="5e3d7-111">**ID da hierarquia do cliente** – uma ID exclusiva para a hierarquia do cliente.</span><span class="sxs-lookup"><span data-stu-id="5e3d7-111">**Customer hierarchy ID** – A unique ID for the customer hierarchy.</span></span> <span data-ttu-id="5e3d7-112">Essa ID usa a sequência numérica definida em parâmetros compartilhados do Commerce na sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="5e3d7-112">This ID uses the number sequence that is defined in Commerce shared parameters in Commerce headquarters.</span></span>
    - <span data-ttu-id="5e3d7-113">**Nome** – o nome da organização parceira comercial, conforme especificado na solicitação de integração.</span><span class="sxs-lookup"><span data-stu-id="5e3d7-113">**Name** – The organization name of the business partner, as specified in the onboarding request.</span></span>
    - <span data-ttu-id="5e3d7-114">**Finalidade** – esta propriedade é definida como o valor predefinido da **organização B2B**.</span><span class="sxs-lookup"><span data-stu-id="5e3d7-114">**Purpose** – This property is set to the predefined value **B2B organization**.</span></span>
    - <span data-ttu-id="5e3d7-115">**Organização** – a ID de cliente do parceiro comercial.</span><span class="sxs-lookup"><span data-stu-id="5e3d7-115">**Organization** – The customer ID of the business partner.</span></span>

<span data-ttu-id="5e3d7-116">Estes são os detalhes do registro da hierarquia do cliente:</span><span class="sxs-lookup"><span data-stu-id="5e3d7-116">Here are the details of the customer hierarchy record:</span></span>

- <span data-ttu-id="5e3d7-117">O registro de cliente do solicitante está associado à hierarquia do cliente.</span><span class="sxs-lookup"><span data-stu-id="5e3d7-117">The customer record of the requestor is associated with the customer hierarchy.</span></span>
- <span data-ttu-id="5e3d7-118">A função de administrador está associada ao solicitante.</span><span class="sxs-lookup"><span data-stu-id="5e3d7-118">The administrator role is associated with the requestor.</span></span>

<span data-ttu-id="5e3d7-119">Quando o administrador adiciona mais usuários à organização parceira comercial em um site B2B, um novo registro de cliente para cada usuário é criado na sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="5e3d7-119">When the administrator adds more users are to the business partner organization on a B2B site, a new customer record for each user is created in Commerce headquarters.</span></span> <span data-ttu-id="5e3d7-120">Esse registro de cliente também é adicionado ao registro de hierarquia de cliente relevante para o parceiro comercial e tem a função de "usuário".</span><span class="sxs-lookup"><span data-stu-id="5e3d7-120">This customer record is also added to the relevant customer hierarchy record for the business partner and has the role of a "user."</span></span>

> [!NOTE]
> <span data-ttu-id="5e3d7-121">Na maioria dos casos, os valores de propriedade correspondentes de todos os registros de cliente em uma hierarquia devem coincidir.</span><span class="sxs-lookup"><span data-stu-id="5e3d7-121">In most cases, the corresponding property values of all customer records in a hierarchy should match.</span></span> <span data-ttu-id="5e3d7-122">Por exemplo, como todos os usuários parceiros comerciais devem obter preços semelhantes para produtos, seu grupo de preços e configurações associadas devem coincidir.</span><span class="sxs-lookup"><span data-stu-id="5e3d7-122">For example, because all business partner users should get similar prices for products, their price group and associated configurations should match.</span></span> <span data-ttu-id="5e3d7-123">No entanto, o sistema não impõe essa consistência.</span><span class="sxs-lookup"><span data-stu-id="5e3d7-123">However, the system doesn't enforce this consistency.</span></span> <span data-ttu-id="5e3d7-124">Portanto, os usuários da sede do Commerce relevantes são responsáveis por garantir que os valores de propriedade e as configurações correspondam a todos os clientes em determinada hierarquia.</span><span class="sxs-lookup"><span data-stu-id="5e3d7-124">Therefore, the relevant Commerce headquarters users are responsible for ensuring that the property values and configurations match for all customers in a given hierarchy.</span></span>

<span data-ttu-id="5e3d7-125">Os usuários da sede do Commerce podem verificar os valores de propriedade de todos os registros de clientes na hierarquia em um modo de exibição lado a lado.</span><span class="sxs-lookup"><span data-stu-id="5e3d7-125">Commerce headquarters users can look at the property values for all customer records in the hierarchy in a side-by-side view.</span></span> <span data-ttu-id="5e3d7-126">Selecione as propriedades de registro de cliente relevantes selecionando os nomes de guias no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="5e3d7-126">Select the relevant customer record properties by selecting the tab names on the drop-down menu.</span></span> <span data-ttu-id="5e3d7-127">Os usuários podem exibir e editar diretamente os valores de propriedade neste modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="5e3d7-127">Users can directly view and edit the property values from this view.</span></span> <span data-ttu-id="5e3d7-128">Como alternativa, se você desejar aplicar todos os valores do registro de cliente administrador a todos os registros de cliente do usuário, selecione **Substituir** nos detalhes da hierarquia do cliente.</span><span class="sxs-lookup"><span data-stu-id="5e3d7-128">Alternatively, if you want to apply all the values from the administrator customer record to all the user customer records, select **Override** in the customer hierarchy details.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5e3d7-129">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="5e3d7-129">Additional resources</span></span>

[<span data-ttu-id="5e3d7-130">Configurar um site de comércio eletrônico B2B</span><span class="sxs-lookup"><span data-stu-id="5e3d7-130">Set up a B2B e-commerce site</span></span>](set-up-b2b-site.md)

[<span data-ttu-id="5e3d7-131">Gerenciar usuários parceiros comerciais em sites de comércio eletrônico B2B</span><span class="sxs-lookup"><span data-stu-id="5e3d7-131">Manage business partner users on B2B e-commerce sites</span></span>](manage-b2b-users.md)

[<span data-ttu-id="5e3d7-132">Configurar o método de pagamento da conta do cliente para sites de comércio eletrônico B2B</span><span class="sxs-lookup"><span data-stu-id="5e3d7-132">Configure the customer account payment method for B2B e-commerce sites</span></span>](payment-method.md)

[<span data-ttu-id="5e3d7-133">Definir limites de quantidade de produto para sites de comércio eletrônico B2B</span><span class="sxs-lookup"><span data-stu-id="5e3d7-133">Set product quantity limits for B2B e-commerce sites</span></span>](quantity-limits.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]