---
title: Cliente mestre integrado
description: Este tópico descreve a integração de dados de cliente entre o Finance and Operations e o Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 977b74b10b4549d09a8816264f9ff603fa86e91c
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172822"
---
# <a name="integrated-customer-master"></a><span data-ttu-id="ca4f1-103">Cliente mestre integrado</span><span class="sxs-lookup"><span data-stu-id="ca4f1-103">Integrated customer master</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="ca4f1-104">Os dados do cliente podem ser dominados em mais de um aplicativo do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-104">Customer data can be mastered in more than one Dynamics 365 application.</span></span> <span data-ttu-id="ca4f1-105">Por exemplo, um registro de cliente pode se originar durante a atividade de vendas no Dynamics 365 Sales (um aplicativo baseado em modelo no Dynamics 365) ou um registro pode se originar por meio da atividade de varejo no Dynamics 365 Commerce (um aplicativo Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="ca4f1-105">For example, a customer record can originate though sales activity in Dynamics 365 Sales (a model-driven app in Dynamics 365), or a record can originate through retail activity in Dynamics 365 Commerce (a Finance and Operations app).</span></span> <span data-ttu-id="ca4f1-106">Não importa onde os dados do cliente se originam, eles são integrados em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-106">No matter where where the customer data originates, it is integrated behind the scenes.</span></span> <span data-ttu-id="ca4f1-107">O cliente mestre integrado oferece a flexibilidade para os dados principais do cliente em qualquer aplicativo Dynamics 365 e fornece uma visão abrangente do cliente no pacote de aplicativos do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-107">Integrated customer master gives you the flexibility to master customer data in any Dynamics 365 application and provides a comprehensive view of the customer across the Dynamics 365 application suite.</span></span>

## <a name="customer-data-flow"></a><span data-ttu-id="ca4f1-108">Fluxo de dados do cliente</span><span class="sxs-lookup"><span data-stu-id="ca4f1-108">Customer data flow</span></span>

<span data-ttu-id="ca4f1-109">*Cliente* é um conceito bem definido nos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-109">*Customer* is a well-defined concept in applications.</span></span> <span data-ttu-id="ca4f1-110">Portanto, a integração de dados de clientes envolve apenas a harmonização do conceito de cliente entre os dois aplicativos.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-110">Therefore, the integration of customer data just involves harmonizing the customer concept between the two applications.</span></span> <span data-ttu-id="ca4f1-111">A ilustração a seguir mostra o fluxo de dados do cliente.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-111">The following illustration shows the customer data flow.</span></span>

![Fluxo de dados do cliente](media/dual-write-customer-data-flow.png)

<span data-ttu-id="ca4f1-113">Os clientes podem ser classificados amplamente em dois tipos: clientes comerciais/organizacionais e clientes/usuários finais.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-113">Customers can be broadly classified into two types: commercial/organizational customers and consumers/end users.</span></span> <span data-ttu-id="ca4f1-114">Esses dois tipos de cliente são armazenados e processados de maneiras diferentes no Finance and Operations e no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-114">These two types of customers are stored and handled differently in Finance and Operations and Common Data Service.</span></span>

<span data-ttu-id="ca4f1-115">No Finance and Operations, os clientes comerciais/organizacionais e os consumidores/usuários finais são dominados em uma única tabela chamada **CustTable** (CustomerCustomerV3Entity) e classificados com base no atributo **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-115">In Finance and Operations, both commercial/organizational customers and consumers/end users are mastered in a single table that is named **CustTable** (CustomerCustomerV3Entity), and they are classified based on the **Type** attribute.</span></span> <span data-ttu-id="ca4f1-116">(Se **Tipo** estiver definido como **Organização**, o cliente será um cliente comercial/organizacional. Se **Tipo** estiver definido como **Pessoa**, o cliente terá um cliente/usuário final.) As informações da pessoa de contato principal é manipulada através da entidade SMMContactPersonEntity.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-116">(If **Type** is set to **Organization**, the customer is a commercial/organizational customer, and if **Type** is set to **Person**, the customer is a consumer/end user.) The primary contact person information is handled through the SMMContactPersonEntity entity.</span></span>

<span data-ttu-id="ca4f1-117">No Common Data Service, clientes comerciais/organizacionais são dominados na entidade Conta e identificados como clientes quando o atributo **RelationshipType** é definido como **Cliente**.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-117">In Common Data Service, commercial/organizational customers are mastered in the Account entity and are identified as customers when the **RelationshipType** attribute is set to **Customer**.</span></span> <span data-ttu-id="ca4f1-118">Os clientes/usuários finais e a pessoa de contato são representados pela entidade Contato.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-118">Both consumers/end users and the contact person are represented by the Contact entity.</span></span> <span data-ttu-id="ca4f1-119">Para fornecer uma separação clara entre um consumidor/usuário final e uma pessoa de contato, a entidade **Contato** tem um sinalizador booliano denominado **Comercializável**.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-119">To provide a clear separation between a consumer/end user and a contact person, the **Contact** entity has a Boolean flag that is named **Sellable**.</span></span> <span data-ttu-id="ca4f1-120">Quando **Comercializável** for **Verdadeiro**, o contato será um cliente/usuário final; as cotações e ordens podem ser criadas para esse contato.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-120">When **Sellable** is **True**, the contact is a consumer/end user, and quotations and orders can be created for that contact.</span></span> <span data-ttu-id="ca4f1-121">Quando **Comercializável** for **Falso**, o contato será apenas uma pessoa de contato principal de um cliente.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-121">When **Sellable** is **False**, the contact is just a primary contact person of a customer.</span></span>

<span data-ttu-id="ca4f1-122">Quando um contato não comercializável participar de uma cotação ou processo de ordem, **Comercializável** será definido como **Verdadeiro** para sinalizar o contato como contato comercializável.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-122">When a non-sellable contact participates in a quotation or order process, **Sellable** is set to **True** to flag the contact as a sellable contact.</span></span> <span data-ttu-id="ca4f1-123">Um contato que tornou-se um contato comercializável permanece um contato comercializável.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-123">A contact that has become a sellable contact remains a sellable contact.</span></span>

## <a name="templates"></a><span data-ttu-id="ca4f1-124">Modelos</span><span class="sxs-lookup"><span data-stu-id="ca4f1-124">Templates</span></span>

<span data-ttu-id="ca4f1-125">Os dados do cliente incluem todas as informações sobre ele, como o grupo de clientes, os endereços, as informações de contato, o perfil do pagamento, o perfil da fatura e o status de fidelidade.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-125">Customer data includes all information about the customer, such as the customer group, addresses, contact information, payment profile, invoice profile, and loyalty status.</span></span> <span data-ttu-id="ca4f1-126">Um conjunto de mapas de entidades funcionam juntos durante a interação de dados do cliente, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-126">A collection of entity maps works together during customer data interaction, as shown in the following table.</span></span>

<span data-ttu-id="ca4f1-127">Aplicativos Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ca4f1-127">Finance and Operations apps</span></span> | <span data-ttu-id="ca4f1-128">Outros aplicativos do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="ca4f1-128">Other Dynamics 365 apps</span></span>         | <span data-ttu-id="ca4f1-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="ca4f1-129">Description</span></span>
----------------------------|---------------------------------|------------
<span data-ttu-id="ca4f1-130">Contatos do CDS V2</span><span class="sxs-lookup"><span data-stu-id="ca4f1-130">CDS Contacts V2</span></span>             | <span data-ttu-id="ca4f1-131">contatos</span><span class="sxs-lookup"><span data-stu-id="ca4f1-131">contacts</span></span>                        | <span data-ttu-id="ca4f1-132">Este modelo sincroniza todas as informações de contato principais, secundárias e terciárias de clientes e fornecedores.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-132">This template synchronizes all primary, secondary, and tertiary contact information, for both customers and vendors.</span></span>
<span data-ttu-id="ca4f1-133">Grupos de clientes</span><span class="sxs-lookup"><span data-stu-id="ca4f1-133">Customer groups</span></span>             | <span data-ttu-id="ca4f1-134">msdyn_customergroups</span><span class="sxs-lookup"><span data-stu-id="ca4f1-134">msdyn_customergroups</span></span>            | <span data-ttu-id="ca4f1-135">Este modelo sincroniza informações do grupo de clientes.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-135">This template synchronizes customer group information.</span></span>
<span data-ttu-id="ca4f1-136">Método de pagamento do cliente</span><span class="sxs-lookup"><span data-stu-id="ca4f1-136">Customer payment method</span></span>     | <span data-ttu-id="ca4f1-137">msdyn_customerpaymentmethods</span><span class="sxs-lookup"><span data-stu-id="ca4f1-137">msdyn_customerpaymentmethods</span></span>    | <span data-ttu-id="ca4f1-138">Este modelo sincroniza informações sobre o método de pagamento dos clientes.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-138">This template synchronizes customer payment method information.</span></span>
<span data-ttu-id="ca4f1-139">Clientes V3</span><span class="sxs-lookup"><span data-stu-id="ca4f1-139">Customers V3</span></span>                | <span data-ttu-id="ca4f1-140">contas</span><span class="sxs-lookup"><span data-stu-id="ca4f1-140">accounts</span></span>                        | <span data-ttu-id="ca4f1-141">Este modelo sincroniza informações mestre de clientes relacionadas a clientes comerciais e organizacionais.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-141">This template synchronizes customer master information for commercial and organizational customers.</span></span>
<span data-ttu-id="ca4f1-142">Clientes V3</span><span class="sxs-lookup"><span data-stu-id="ca4f1-142">Customers V3</span></span>                | <span data-ttu-id="ca4f1-143">contatos</span><span class="sxs-lookup"><span data-stu-id="ca4f1-143">contacts</span></span>                        | <span data-ttu-id="ca4f1-144">Este modelo sincroniza dados mestres de clientes relacionados a clientes e usuários finais.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-144">This template synchronizes customer master data for consumers and end users.</span></span>
<span data-ttu-id="ca4f1-145">Afixos de nome</span><span class="sxs-lookup"><span data-stu-id="ca4f1-145">Name affixes</span></span>                | <span data-ttu-id="ca4f1-146">msdyn_nameaffixes</span><span class="sxs-lookup"><span data-stu-id="ca4f1-146">msdyn_nameaffixes</span></span>               | <span data-ttu-id="ca4f1-147">Este modelo sincroniza dados de referência de afixos de nome de clientes e fornecedores.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-147">This template synchronizes name affixes reference data, for both customers and vendors.</span></span>
<span data-ttu-id="ca4f1-148">Linhas de dia de pagamento CDS V2</span><span class="sxs-lookup"><span data-stu-id="ca4f1-148">Payment day lines CDS V2</span></span>    | <span data-ttu-id="ca4f1-149">msdyn_paymentdaylines</span><span class="sxs-lookup"><span data-stu-id="ca4f1-149">msdyn_paymentdaylines</span></span>           | <span data-ttu-id="ca4f1-150">Este modelo sincroniza dados de referência de linhas de pagamento de clientes e fornecedores.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-150">This template synchronizes payment day lines reference data, for both customers and vendors.</span></span>
<span data-ttu-id="ca4f1-151">Dias de pagamento CDS</span><span class="sxs-lookup"><span data-stu-id="ca4f1-151">Payment days CDS</span></span>            | <span data-ttu-id="ca4f1-152">msdyn_paymentdays</span><span class="sxs-lookup"><span data-stu-id="ca4f1-152">msdyn_paymentdays</span></span>               | <span data-ttu-id="ca4f1-153">Este modelo sincroniza dados de referência de dias de pagamento de clientes e fornecedores.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-153">This template synchronizes payment days reference data, for both customers and vendors.</span></span>
<span data-ttu-id="ca4f1-154">Linhas de plano de pagamento</span><span class="sxs-lookup"><span data-stu-id="ca4f1-154">Payment schedule lines</span></span>      | <span data-ttu-id="ca4f1-155">msdyn_paymentschedulelines</span><span class="sxs-lookup"><span data-stu-id="ca4f1-155">msdyn_paymentschedulelines</span></span>      | <span data-ttu-id="ca4f1-156">Sincroniza dados de referência de linhas de plano de pagamento de clientes e fornecedores.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-156">Syncs payment schedule lines reference data, for both customers and vendors.</span></span>
<span data-ttu-id="ca4f1-157">Agenda de pagamento</span><span class="sxs-lookup"><span data-stu-id="ca4f1-157">Payment schedule</span></span>            | <span data-ttu-id="ca4f1-158">msdyn_paymentschedules</span><span class="sxs-lookup"><span data-stu-id="ca4f1-158">msdyn_paymentschedules</span></span>          | <span data-ttu-id="ca4f1-159">Este modelo sincroniza dados de referência de planos de pagamento de clientes e fornecedores.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-159">This template synchronizes payment schedule reference data, for both customers and vendors.</span></span>
<span data-ttu-id="ca4f1-160">Condições de pagamento</span><span class="sxs-lookup"><span data-stu-id="ca4f1-160">Terms of payment</span></span>            | <span data-ttu-id="ca4f1-161">msdyn_paymentterms</span><span class="sxs-lookup"><span data-stu-id="ca4f1-161">msdyn_paymentterms</span></span>              | <span data-ttu-id="ca4f1-162">Este modelo sincroniza dados de referência de condições de pagamento (condições de pagamento) de clientes e fornecedores.</span><span class="sxs-lookup"><span data-stu-id="ca4f1-162">This template synchronizes payment terms (terms of payment) reference data, for both customers and vendors.</span></span>

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping contacts contacts](includes/CDSContactsV2-contacts.md)]

[!include [mapping customer group](includes/CustCustomerGroup-msdyn-customergroups.md)]

[!include [mapping customer payment method](includes/CustomerPaymentMethod-msdyn-customerpaymentmethods.md)]

[!include [mapping customer accounts](includes/CustomersV3-accounts.md)]

[!include [mapping customer contacts](includes/CustomersV3-contacts.md)]

[!include [mapping name affixes](includes/NameAffixes-msdyn-nameaffixes.md)]

[!include [mapping payment day lines](includes/PaymentDayLinesCdsV2-msdyn-paymentdaylines.md)]

[!include [mapping payment days](includes/PaymentDaysCds-msdyn-paymentdays.md)]

[!include [mapping payment schedule lines](includes/PaymentScheduleLines-msdyn-paymentschedulelines.md)]

[!include [mapping payment schedules](includes/PaymentSchedules-msdyn-paymentschedules.md)]

[!include [mapping terms of payment](includes/TermsofPayment-msdyn-paymentterms.md)]