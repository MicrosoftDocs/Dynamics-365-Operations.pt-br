---
title: Confirmar Agendamentos de pagamento de arrendamento de ativo em um lote
description: Este tópico explica como confirmar vários agendamentos de pagamento em um lote.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: b5a90b96ac598d145e2b0697627de04731b55f59
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "4440553"
---
# <a name="confirm-asset-leasing-payment-schedules-in-a-batch"></a><span data-ttu-id="95ec4-103">Confirmar Agendamentos de pagamento de arrendamento de ativo em um lote</span><span class="sxs-lookup"><span data-stu-id="95ec4-103">Confirm Asset leasing payment schedules in a batch</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="95ec4-104">Este tópico explica como confirmar vários agendamentos de pagamento em um lote.</span><span class="sxs-lookup"><span data-stu-id="95ec4-104">This topic explains how to confirm multiple payment schedules in a batch.</span></span> <span data-ttu-id="95ec4-105">Os planos de pagamento são confirmados em uma base de arrendamento ou por meio do processo de lote de confirmação.</span><span class="sxs-lookup"><span data-stu-id="95ec4-105">Payment schedules are confirmed either on a lease-to-lease basis or through the confirmation batch process.</span></span> <span data-ttu-id="95ec4-106">Uma entrada de diário pode ser lançada somente em um arrendamento com um plano de pagamento confirmado.</span><span class="sxs-lookup"><span data-stu-id="95ec4-106">A journal entry can be posted only against a lease that has a confirmed payment schedule.</span></span> <span data-ttu-id="95ec4-107">A confirmação do plano de pagamento serve como uma aprovação final das informações financeiras para o arrendamento.</span><span class="sxs-lookup"><span data-stu-id="95ec4-107">Confirmation of the payment schedule serves as a final approval of the financial information for the lease.</span></span> <span data-ttu-id="95ec4-108">Todas as alterações futuras feitas nas informações financeiras para o arrendamento, tais como pagamentos e o prazo do arrendamento, constituem um ajuste de arrendamento e devem ser processadas dessa forma.</span><span class="sxs-lookup"><span data-stu-id="95ec4-108">All future changes to the financial information for the lease, such as payments and the lease term, constitute a lease adjustment and should be processed in that way.</span></span>

<span data-ttu-id="95ec4-109">Para confirmar vários planos de pagamento, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="95ec4-109">To confirm multiple payment schedules, follow these steps.</span></span>

1. <span data-ttu-id="95ec4-110">Vá para **Arrendamento de ativos \> Periódico \> Lote de confirmação**.</span><span class="sxs-lookup"><span data-stu-id="95ec4-110">Go to **Asset leasing \> Periodic \> Confirmation batch**.</span></span>
2. <span data-ttu-id="95ec4-111">Na página **Lote de confirmação**, selecione **Lote de confirmação**.</span><span class="sxs-lookup"><span data-stu-id="95ec4-111">On the **Confirmation batch** page, select **Confirmation batch**.</span></span>
3. <span data-ttu-id="95ec4-112">Na caixa de diálogo exibida, filtre os livros que deseja confirmar.</span><span class="sxs-lookup"><span data-stu-id="95ec4-112">In the dialog box that appears, filter for the books that you want to confirm.</span></span>

    - <span data-ttu-id="95ec4-113">Para confirmar todos os registros de um grupo de arrendamento específico, selecione o grupo no campo **Grupo de arrendamento**.</span><span class="sxs-lookup"><span data-stu-id="95ec4-113">To confirm all the books in a specific lease group, select the group in the **Lease group** field.</span></span>
    - <span data-ttu-id="95ec4-114">Para confirmar registros específicos, selecione os registros no campo **ID do registro**.</span><span class="sxs-lookup"><span data-stu-id="95ec4-114">To confirm specific books, select the books in the **Book ID** field.</span></span>
    - <span data-ttu-id="95ec4-115">Para confirmar todos os registros, ative o parâmetro **Para todos os registros**.</span><span class="sxs-lookup"><span data-stu-id="95ec4-115">To confirm all books, turn on the **For all books** parameter.</span></span>

<span data-ttu-id="95ec4-116">As informações dos registros recém confirmados são mostradas na página **Registros confirmados**.</span><span class="sxs-lookup"><span data-stu-id="95ec4-116">Information for the newly confirmed books is shown on the **Confirmed books** page.</span></span> <span data-ttu-id="95ec4-117">Depois que os planos de pagamento são confirmados, as entradas iniciais do diário de reconhecimento podem ser lançadas com base nos arrendamentos.</span><span class="sxs-lookup"><span data-stu-id="95ec4-117">After the payment schedules are confirmed, the initial recognition journal entries can be posted against the leases.</span></span>
