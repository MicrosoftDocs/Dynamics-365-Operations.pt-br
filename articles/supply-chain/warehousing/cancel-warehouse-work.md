---
title: Cancelar trabalho de depósito para tratamento de exceções
description: Este tópico descreve a funcionalidade Cancelar trabalho, que permite que supervisores de depósito tratem o trabalho bloqueado.
author: omulvad
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSTroubIeshootingSeIfService, WHSTroubleshootingSelfService
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2019-10-1
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 21cfa03ed52ffce32267ec0497ae3443937c1018
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233094"
---
# <a name="cancel-warehouse-work-for-exception-handling"></a><span data-ttu-id="72caa-103">Cancelar trabalho de depósito para tratamento de exceções</span><span class="sxs-lookup"><span data-stu-id="72caa-103">Cancel warehouse work for exception handling</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="72caa-104">A funcionalidade Cancelar trabalho no Microsoft Dynamics 365 Supply Chain Management permite que o usuário administrador cancele um trabalho de depósito específico que esteja em andamento, mas que tenha sido bloqueado pelo sistema ou que não possa ser concluído devido a circunstâncias excepcionais.</span><span class="sxs-lookup"><span data-stu-id="72caa-104">The Cancel work functionality in Microsoft Dynamics 365 Supply Chain Management lets the admin user cancel specific warehouse work that is currently in progress, but that is blocked by the system or can't be completed because of exceptional circumstances.</span></span> <span data-ttu-id="72caa-105">Essa funcionalidade é uma alternativa atraente e segura aos scripts corretivos em SQL que corrigem dados inconsistentes.</span><span class="sxs-lookup"><span data-stu-id="72caa-105">This functionality is an attractive and secure alternative to SQL corrective scripts that fix inconsistent data.</span></span> <span data-ttu-id="72caa-106">Entretanto, enquanto os scripts são normalmente solicitados de profissionais de TI, a funcionalidade Cancelar trabalho pode ser usada pelos usuários na empresa com direitos de administrador.</span><span class="sxs-lookup"><span data-stu-id="72caa-106">However, whereas these scripts are typically requested from IT professionals, the Cancel work functionality can be used by users in the company who have admin rights.</span></span>

<span data-ttu-id="72caa-107">Você pode acessar a funcionalidade Cancelar trabalho em **Gerenciamento de depósito** \> **Tarefas periódicas** \> **Limpar \> Cancelar trabalho**.</span><span class="sxs-lookup"><span data-stu-id="72caa-107">You can access the Cancel work functionality at **Warehouse management** \> **Periodic tasks** \> **Clean up \> Cancel work**.</span></span> <span data-ttu-id="72caa-108">Na caixa de diálogo **Cancelar trabalho**, especifique a ID do trabalho a ser cancelado e então selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="72caa-108">In the **Cancel work** dialog box, specify the work ID of the work to cancel, and then select **OK**.</span></span>

## <a name="warehouse-work-that-can-be-canceled"></a><span data-ttu-id="72caa-109">O trabalho de depósito que pode ser cancelado</span><span class="sxs-lookup"><span data-stu-id="72caa-109">Warehouse work that can be canceled</span></span>

<span data-ttu-id="72caa-110">Durante as operações de separação de depósito, um trabalhador poderá encontrar situações onde foram registradas quantidades como selecionadas de um local de armazenamento para seu local de usuário, mas não poderá registrar a operação de colocação.</span><span class="sxs-lookup"><span data-stu-id="72caa-110">During warehouse picking operations, a worker might encounter situations where they have registered quantities as picked from a storage location to their user location, but then they can't register the put operation.</span></span> <span data-ttu-id="72caa-111">Os dados de depósito inconsistentes são geralmente, mas nem sempre, o motivo pelo qual o trabalho é bloqueado.</span><span class="sxs-lookup"><span data-stu-id="72caa-111">Inconsistent warehouse data is often, but not always, the reason why work is blocked.</span></span>

<span data-ttu-id="72caa-112">Ao contrário da funcionalidade Cancelar normal, que pode ser acessada usando o botão **Cancelar** no cabeçalho do trabalho, a funcionalidade não exige que a última linha de trabalho concluído seja uma linha de trabalho do tipo **colocar**.</span><span class="sxs-lookup"><span data-stu-id="72caa-112">Unlike the regular Cancel functionality that can be accessed by using the **Cancel** button on the work header, the Cancel work functionality doesn't require that the last completed work line be a work line of the **put** type.</span></span> <span data-ttu-id="72caa-113">Em outras palavras, para a funcionalidade Cancelar trabalho, a lógica de cancelamento poderá ser executada mesma se a quantidade do item em uma linha de trabalho estiver em um local do usuário.</span><span class="sxs-lookup"><span data-stu-id="72caa-113">In other words, for the Cancel work functionality, cancellation logic can be run even if the item quantity on a work line is in a user location.</span></span>

> [!NOTE]
> <span data-ttu-id="72caa-114">Para os trabalhos que devem ser cancelados por motivos operacionais, os usuários do depósito deverão continuar a usar a funcionalidade Cancelar normal na página do trabalho.</span><span class="sxs-lookup"><span data-stu-id="72caa-114">For work that must be canceled for operational reasons, warehouse users must continue to use the regular Cancel functionality on the work page.</span></span>

<span data-ttu-id="72caa-115">Somente o trabalho do tipo **Vendas**, **Emissão de transferência**, **Separação da matéria-prima** ou **Reabastecimento** pode ser cancelado usando a funcionalidade Cancelar trabalho.</span><span class="sxs-lookup"><span data-stu-id="72caa-115">Only work of the **Sales**, **Transfer issue**, **Raw material picking**, or **Replenishment** type can be canceled by using the Cancel work functionality.</span></span> <span data-ttu-id="72caa-116">A lógica de cancelamento não será executada para o trabalho de separação de matéria-prima congelado ou o trabalho que pode ser cancelado usando a funcionalidade Cancelar normal (consulte a observação anterior).</span><span class="sxs-lookup"><span data-stu-id="72caa-116">Cancellation logic won't be run for frozen raw material picking work or work that can be canceled by using the regular Cancel functionality (see the preceding note).</span></span>

<span data-ttu-id="72caa-117">Para desbloquear o trabalho, o sistema cancela todas as linhas de trabalho restantes e corrige os dados de depósito associados à ID do trabalho que o usuário especificou.</span><span class="sxs-lookup"><span data-stu-id="72caa-117">To unblock the work, the system cancels any remaining work lines and fixes the warehouse data that is associated with the work ID that the user specified.</span></span> <span data-ttu-id="72caa-118">Todas as operações de manuseio de depósito comuns que envolvem a quantidade de itens afetados podem então ser retomadas.</span><span class="sxs-lookup"><span data-stu-id="72caa-118">Any regular warehouse-handling operations that involve the affected item quantity can then resume.</span></span>

<span data-ttu-id="72caa-119">Para colocar o item afetado em um determinado local depois que o trabalho tiver sido cancelado, o usuário deverá usar uma operação de movimentos de estoque ou de ajuste de quantidade em um dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="72caa-119">To put the affected item in a specific location after the work is canceled, the user must use an inventory movement or quantity adjustment operation on a mobile device.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]