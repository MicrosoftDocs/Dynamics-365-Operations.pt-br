---
title: Não é possível confirmar uma remessa devido a um problema com o calendário
description: Não é possível confirmar uma remessa devido a um problema com o calendário
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f1fccd10d8867252f32b37c77f9a3bad54157bdd
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938422"
---
# <a name="you-cant-confirm-a-shipment-because-of-an-issue-with-the-calendar"></a><span data-ttu-id="e96fa-103">Não é possível confirmar uma remessa devido a um problema com o calendário</span><span class="sxs-lookup"><span data-stu-id="e96fa-103">You can't confirm a shipment because of an issue with the calendar</span></span>

<span data-ttu-id="e96fa-104">Código de erro: TRX2716</span><span class="sxs-lookup"><span data-stu-id="e96fa-104">Error code: TRX2716</span></span>

## <a name="symptoms"></a><span data-ttu-id="e96fa-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="e96fa-105">Symptoms</span></span>

<span data-ttu-id="e96fa-106">Ao tentar confirmar uma remessa, o sistema mostra a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="e96fa-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="e96fa-107">O tipo de calendário %1 requer que sejam feitos o check-in e o check-out do compromisso %2.</span><span class="sxs-lookup"><span data-stu-id="e96fa-107">The calendar type %1 requires the appointment %2 to be checked in and out.</span></span>

<span data-ttu-id="e96fa-108">Portanto, não é possível confirmar a remessa da carga.</span><span class="sxs-lookup"><span data-stu-id="e96fa-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="e96fa-109">Causa</span><span class="sxs-lookup"><span data-stu-id="e96fa-109">Cause</span></span>

<span data-ttu-id="e96fa-110">Há compromissos ativos para a carga.</span><span class="sxs-lookup"><span data-stu-id="e96fa-110">Active appointments for the load exist.</span></span> <span data-ttu-id="e96fa-111">Por exemplo, há uma regra que exige o check-in de driver.</span><span class="sxs-lookup"><span data-stu-id="e96fa-111">For example, there is a rule that requires driver check-in.</span></span> <span data-ttu-id="e96fa-112">Então, a carga está em um estado no qual a confirmação de remessa falha.</span><span class="sxs-lookup"><span data-stu-id="e96fa-112">Therefore, the load is currently in a state where shipment confirmation fails.</span></span>

## <a name="resolution"></a><span data-ttu-id="e96fa-113">Resolução</span><span class="sxs-lookup"><span data-stu-id="e96fa-113">Resolution</span></span>

<span data-ttu-id="e96fa-114">Você deve investigar e corrigir problemas com os compromissos ativos vinculados à carga.</span><span class="sxs-lookup"><span data-stu-id="e96fa-114">You must investigate and fix any issues with the active appointments that are linked to the load.</span></span>

1. <span data-ttu-id="e96fa-115">Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.</span><span class="sxs-lookup"><span data-stu-id="e96fa-115">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="e96fa-116">Selecione a carga para a qual a remessa não pode ser confirmada.</span><span class="sxs-lookup"><span data-stu-id="e96fa-116">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="e96fa-117">No Painel de Ações, na guia **Transporte**, no grupo **Compromissos**, selecione **Agendamento de compromissos**.</span><span class="sxs-lookup"><span data-stu-id="e96fa-117">On the Action Pane, on the **Transportation** tab, in the **Appointments** group, select **Appointment scheduling**.</span></span>
1. <span data-ttu-id="e96fa-118">Siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="e96fa-118">Follow one of these steps:</span></span>

    - <span data-ttu-id="e96fa-119">Verifique se o check-in/check-out do driver foi concluído para o compromisso.</span><span class="sxs-lookup"><span data-stu-id="e96fa-119">Make sure that driver check-in/check-out is completed for the appointment.</span></span>
    - <span data-ttu-id="e96fa-120">Conclua ou cancele o compromisso.</span><span class="sxs-lookup"><span data-stu-id="e96fa-120">Complete or cancel the appointment.</span></span>
    - <span data-ttu-id="e96fa-121">Desative a opção **Check-in de driver necessário** para a regra de compromisso relacionada.</span><span class="sxs-lookup"><span data-stu-id="e96fa-121">Disable the **Driver check-in required** option for the related appointment rule.</span></span>
