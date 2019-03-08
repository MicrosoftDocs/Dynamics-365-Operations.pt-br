---
title: Novidades ou alterações no Dynamics 365 for Talent Core HR (23 de janeiro de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 01/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-01-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 135be837a82af8cee22d83c015a78da3b89b7978
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "303200"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-january-23-2019"></a><span data-ttu-id="66e3e-103">Novidades ou alterações no Dynamics 365 for Talent Core HR (23 de janeiro de 2019)</span><span class="sxs-lookup"><span data-stu-id="66e3e-103">What's new or changed in Dynamics 365 for Talent Core HR (January 23, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="66e3e-104">**Compilação 8.1.2121**</span><span class="sxs-lookup"><span data-stu-id="66e3e-104">**Build 8.1.2121**</span></span>

<span data-ttu-id="66e3e-105">Este tópico descreve os recursos novos ou alterados no Core HR.</span><span class="sxs-lookup"><span data-stu-id="66e3e-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="changes"></a><span data-ttu-id="66e3e-106">Alterações</span><span class="sxs-lookup"><span data-stu-id="66e3e-106">Changes</span></span>

### <a name="import-of-employee-fixed-compensation-not-working-when-creating-new-fixed-compensation-records"></a><span data-ttu-id="66e3e-107">A importação de remuneração fixa do funcionário não está funcionando na criação de novos registros de remuneração fixa</span><span class="sxs-lookup"><span data-stu-id="66e3e-107">Import of employee fixed compensation not working when creating new fixed compensation records</span></span>
<span data-ttu-id="66e3e-108">Uma alteração foi feita na entidade de remuneração fixa do funcionário para recuperar o nível da remuneração na importação.</span><span class="sxs-lookup"><span data-stu-id="66e3e-108">A change has been made to the employee fixed compensation entity to retrieve the compensation level upon import.</span></span> <span data-ttu-id="66e3e-109">Antes desta versão, uma mensagem era exibida indicando que o nível era necessário.</span><span class="sxs-lookup"><span data-stu-id="66e3e-109">Prior to this release, a message was displayed indicating that the level was required.</span></span>

### <a name="remove-the-minimum-balance-field-from-the-time-off-request-dialog-box"></a><span data-ttu-id="66e3e-110">Remover o campo saldo mínimo usando a caixa de diálogo de solicitação de folga</span><span class="sxs-lookup"><span data-stu-id="66e3e-110">Remove the minimum balance field from the time off request dialog box</span></span>
<span data-ttu-id="66e3e-111">O campo **Saldo mínimo** foi removido da caixa de diálogo **Solicitação de folga**.</span><span class="sxs-lookup"><span data-stu-id="66e3e-111">The **Minimum balance** field has been removed from the **Time off request** dialog box.</span></span> <span data-ttu-id="66e3e-112">Esta alteração afeta todas as áreas em que a folga pode ser solicitada.</span><span class="sxs-lookup"><span data-stu-id="66e3e-112">This change affects all areas where time off can be requested.</span></span>

### <a name="data-upgrade-for-compensation-levels-not-updating-in-all-scenarios"></a><span data-ttu-id="66e3e-113">A atualização de dados dos níveis de remuneração não estão sendo atualizados em todos os cenários</span><span class="sxs-lookup"><span data-stu-id="66e3e-113">Data upgrade for compensation levels not updating in all scenarios</span></span>
<span data-ttu-id="66e3e-114">Uma alteração foi feita para atualizar o nível de remuneração nos planos de remuneração fixa.</span><span class="sxs-lookup"><span data-stu-id="66e3e-114">A change has been made to update the compensation level on fixed compensation plans.</span></span> <span data-ttu-id="66e3e-115">Esta alteração preencherá o nível de remuneração nos planos fixos para os trabalhos atribuídos ao funcionário.</span><span class="sxs-lookup"><span data-stu-id="66e3e-115">This change will populate the compensation level on fixed plans for the job assigned to the employee.</span></span>

### <a name="payroll-information-in-the-manage-changes-page-is-only-available-when-logged-in-as-system-administrator"></a><span data-ttu-id="66e3e-116">As informações de folha de pagamento na página Gerenciar alterações só estão disponíveis quando se faz logon como administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="66e3e-116">Payroll information in the Manage changes page is only available when logged in as System Administrator</span></span>
<span data-ttu-id="66e3e-117">Esta alteração permite aos funcionários com a função Administrador de folha de pagamento acessar informações de folha de pagamento na página **Linha do tempo das alterações > Gerenciar alterações** para a posição.</span><span class="sxs-lookup"><span data-stu-id="66e3e-117">This change allows employees with the Payroll Administrator role access to the payroll information on the **Changes timeline > Manage changes** page for the position.</span></span>

### <a name="job-fields-default-to-positions"></a><span data-ttu-id="66e3e-118">Os campos de trabalho são padronizados com posições</span><span class="sxs-lookup"><span data-stu-id="66e3e-118">Job fields default to positions</span></span>
<span data-ttu-id="66e3e-119">Ao alterar os trabalhos em uma posição, os campos de trabalho assumirão como padrão a posição.</span><span class="sxs-lookup"><span data-stu-id="66e3e-119">When changing the job on a position, job fields will default to the position.</span></span> <span data-ttu-id="66e3e-120">Uma mensagem de alerta aparecerá dando a opção de aceitar os valores padrão ou manter os valores existentes para esses campos.</span><span class="sxs-lookup"><span data-stu-id="66e3e-120">An alert message will appear giving an option to accept the default values or keep the existing values for those fields.</span></span>

### <a name="probation-period-and-calendar-are-not-displayed-for-future-hired-employees"></a><span data-ttu-id="66e3e-121">O período e o calendário de experiência não são exibidos para futuros funcionários contratados.</span><span class="sxs-lookup"><span data-stu-id="66e3e-121">Probation period and calendar are not displayed for future hired employees.</span></span>
<span data-ttu-id="66e3e-122">Com esta alteração, os campos **Período de experiência** e **Calendário** foram adicionados à página **Gerenciar alterações** para permitir a entrada de dados de funcionários futuros e passados.</span><span class="sxs-lookup"><span data-stu-id="66e3e-122">With this change, **Probation period** and **Calendar** fields have been added to the **Manage changes** page to allow for data entry for future and past employees.</span></span>

### <a name="platform-update-23"></a><span data-ttu-id="66e3e-123">Update 23 para plataforma</span><span class="sxs-lookup"><span data-stu-id="66e3e-123">Platform update 23</span></span>
<span data-ttu-id="66e3e-124">Pequenas correções de bugs foram incluídas como parte da atualização 23 da Plataforma.</span><span class="sxs-lookup"><span data-stu-id="66e3e-124">Minor bug fixes have been included as part of Platform update 23.</span></span> <span data-ttu-id="66e3e-125">Para obter mais informações, consulte [Novidades ou alterações na atualização 23 da plataforma do Dynamics 365 for Finance and Operations (janeiro de 2019)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-23).</span><span class="sxs-lookup"><span data-stu-id="66e3e-125">For more information, see [What's new or changed in Dynamics 365 for Finance and Operations platform update 23 (January 2019)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-23).</span></span> 
