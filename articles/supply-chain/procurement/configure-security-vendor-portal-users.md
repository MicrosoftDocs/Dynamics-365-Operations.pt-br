---
title: "Segurança de usuário do portal do fornecedor"
description: "Este artigo explica como configurar a segurança para fornecedores externos que usam o Portal do fornecedor. Estas informações só se aplicam a versões de fevereiro de 2016 &amp; maio de 2016 do Dynamics AX."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysUserManagement
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 30231
ms.assetid: 3574db17-81c7-4c5a-999b-0098aa0b9cda
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: f79f686720d615da6996f854a9e4cc18f840337f
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="vendor-portal-user-security"></a><span data-ttu-id="7f66d-104">Segurança de usuário do portal do fornecedor</span><span class="sxs-lookup"><span data-stu-id="7f66d-104">Vendor portal user security</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="7f66d-105">Este artigo explica como configurar a segurança para fornecedores externos que usam o Portal do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="7f66d-105">This article explains how to set up security for external vendors who use the Vendor portal.</span></span> <span data-ttu-id="7f66d-106">Estas informações só se aplicam a versões de fevereiro de 2016 &amp; maio de 2016 do Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="7f66d-106">This information applies only to the February 2016 &amp; May 2016 versions of Dynamics AX.</span></span>

<span data-ttu-id="7f66d-107">A funcionalidade de portal do fornecedor foi substituída por uma funcionalidade estendida de colaboração do fornecedor na versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="7f66d-107">The Vendor portal functionality has been replaced by extended vendor collaboration functionality in Dynamics 365 for Operations version 1611.</span></span> <span data-ttu-id="7f66d-108">Para obter mais informações sobre como configurar a segurança para a colaboração de fornecedor, consulte [Instalação e manutenção da colaboração de fornecedor](set-up-maintain-vendor-collaboration.md).</span><span class="sxs-lookup"><span data-stu-id="7f66d-108">For more information about setting up security for vendor collaboration, see [Set up and maintain vendor collaboration](set-up-maintain-vendor-collaboration.md).</span></span> <span data-ttu-id="7f66d-109">O portal do fornecedor expõe um conjunto limitado de informações sobre ordens de compra (POs) para fornecedores externos.</span><span class="sxs-lookup"><span data-stu-id="7f66d-109">The Vendor portal exposes a limited set of information about purchase orders (POs) to external vendors.</span></span> <span data-ttu-id="7f66d-110">É importante que você configure corretamente as permissões do usuário para o portal do fornecedor no Microsoft Dynamics AX, de modo que os fornecedores não tenham acesso não intencional a informações adicionais sobre a instalação do Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="7f66d-110">It's important that you correctly set up user permissions for the Vendor portal in Microsoft Dynamics AX, so that vendors don't have unintended access to additional information in your Dynamics AX installation.</span></span> <span data-ttu-id="7f66d-111">**Importante:** Diferente dos outros usuários, os fornecedores externos não devem ter a função **SystemUser**.</span><span class="sxs-lookup"><span data-stu-id="7f66d-111">**Important:** Unlike other users, external vendors should not have the **SystemUser** role.</span></span> <span data-ttu-id="7f66d-112">A função **SystemUser** concede acesso a um conjunto de privilégios que não são adequados para usuários externos.</span><span class="sxs-lookup"><span data-stu-id="7f66d-112">The **SystemUser** role grants access to a set of privileges that aren't suitable for external users.</span></span>

## <a name="setting-up-a-vendor-portal-user"></a><span data-ttu-id="7f66d-113">Configurando um usuário do portal do fornecedor</span><span class="sxs-lookup"><span data-stu-id="7f66d-113">Setting up a Vendor portal user</span></span>
<span data-ttu-id="7f66d-114">Antes de criar uma conta de usuário para alguém que usará o portal do fornecedor, configure o fornecedor para permitir a colaboração do portal do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="7f66d-114">Before you create a user account for someone who will use the Vendor portal, you must set up the vendor to allow for Vendor portal collaboration.</span></span> <span data-ttu-id="7f66d-115">Use o campo **Colaboração da ordem de compra** na guia **Geral** da página **Fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="7f66d-115">Use the **Purchase order collaboration** field on the **General** tab on the **Vendors** page.</span></span> <span data-ttu-id="7f66d-116">Os fornecedores externos que usam o portal do fornecedor devem ter a seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="7f66d-116">External vendors that use the Vendor portal must have the following setup:</span></span>

-   <span data-ttu-id="7f66d-117">Uma conta de usuário do AAD (Active Directory do Microsoft Azure) deve ser registrada para o fornecedor na página **Usuários** do Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="7f66d-117">A Microsoft Azure Active Directory (AAD) user account must be registered for the vendor on the **Users** page in Dynamics AX.</span></span>
-   <span data-ttu-id="7f66d-118">O fornecedor deve ter a função de segurança **Fornecedor (externo)**, e não a função **SystemUser**.</span><span class="sxs-lookup"><span data-stu-id="7f66d-118">The vendor must have the **Vendor (external)** security role, not the **SystemUser** role.</span></span> <span data-ttu-id="7f66d-119">**Observação:** a função **SystemUser** é concedida automaticamente quando você cria uma nova conta de usuário no Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="7f66d-119">**Note:** The **SystemUser** role is automatically granted when you create a new user account in Dynamics AX.</span></span> <span data-ttu-id="7f66d-120">Portanto, remova essa função e confirme a mensagem de aviso recebida.</span><span class="sxs-lookup"><span data-stu-id="7f66d-120">Therefore, you must remove that role and acknowledge the warning message that you receive.</span></span>
-   <span data-ttu-id="7f66d-121">O usuário fornecedor não deve receber permissão para adicionar campos extras das tabelas de OC à exibição da OC.</span><span class="sxs-lookup"><span data-stu-id="7f66d-121">The vendor user should not be granted permission to add additional fields from the PO tables to their view of the PO.</span></span> <span data-ttu-id="7f66d-122">Na guia **Personalização**, na guia **Usuários**, defina a opção **Personalização explícita permitida** do usuário para **Não**.</span><span class="sxs-lookup"><span data-stu-id="7f66d-122">On the **Personalization** tab, on the **Users** tab, set the **Explicit personalization allowed** option for the user to **No**.</span></span>
-   <span data-ttu-id="7f66d-123">A conta de usuário deve ser associada à pessoa de contato registrada.</span><span class="sxs-lookup"><span data-stu-id="7f66d-123">The user account must be associated with a registered contact person.</span></span> <span data-ttu-id="7f66d-124">Na página **Usuários**, selecione uma pessoa de contato no campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="7f66d-124">On the **Users** page, select a contact person in the **Name** field.</span></span> <span data-ttu-id="7f66d-125">A pessoa selecionada deve ter a função **Contato** do fornecedor relevante.</span><span class="sxs-lookup"><span data-stu-id="7f66d-125">The person that you select should have the **Contact** role for the relevant vendor.</span></span>

<span data-ttu-id="7f66d-126">Se a mesma pessoa precisar de acesso ao portal do fornecedor em várias contas de fornecedor (para entidades legais diferentes, talvez), cada uma das contas de usuário dessa pessoa deverá ser associada com à mesma pessoa de contato registrada.</span><span class="sxs-lookup"><span data-stu-id="7f66d-126">If the same person requires access to the Vendor portal for multiple vendor accounts (for different legal entities, perhaps), each of that person's user accounts must be associated with the same registered contact person.</span></span> <span data-ttu-id="7f66d-127">A função **Fornecedor (externo)** inclui todos os recursos básicos necessários para usar a funcionalidade disponibilizada no portal do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="7f66d-127">The **Vendor (external)** role includes all the basic capabilities that are required in order to use the functionality that is available in the Vendor portal.</span></span> <span data-ttu-id="7f66d-128">Essa configuração garante que a interface do usuário exibida para o usuário externo terá como foco apenas o cenário desejado.</span><span class="sxs-lookup"><span data-stu-id="7f66d-128">This setup helps guarantee that the user interface that the external user sees is focused on the intended scenario only.</span></span>

<a name="see-also"></a><span data-ttu-id="7f66d-129">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7f66d-129">See also</span></span>
--------

[<span data-ttu-id="7f66d-130">Colaboração do fornecedor</span><span class="sxs-lookup"><span data-stu-id="7f66d-130">Vendor collaboration</span></span>](collaborate-vendors-vendor-portal.md)




