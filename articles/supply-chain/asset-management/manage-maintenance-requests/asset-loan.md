---
title: Empréstimos de ativos
description: Este tópico descreve como registrar ativos de empréstimo em Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectLoanSend, EntAssetObjectLoanListPage, EntAssetObjectLoanReturn, EntAssetObjectLoanInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cba680d0ad626e0275539d7478a83639a9d22635
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889640"
---
# <a name="asset-loans"></a><span data-ttu-id="ed364-103">Empréstimos de ativos</span><span class="sxs-lookup"><span data-stu-id="ed364-103">Asset loans</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="ed364-104">Se a sua empresa recebe ativos para trabalhos de reparo ou manutenção de locais internos ou clientes e se você empresta temporariamente ativos para esses locais ou clientes, o Gerenciamentos de Ativos pode rastrear os empréstimos de ativos.</span><span class="sxs-lookup"><span data-stu-id="ed364-104">If your company receives assets for repair or maintenance jobs from either internal locations or customers, and if you temporarily loan assets to those locations or customers, Asset Management can track the asset loans.</span></span>

## <a name="register-asset-loans-on-a-maintenance-request"></a><span data-ttu-id="ed364-105">Registre empréstimos de ativos em uma solicitação de manutenção</span><span class="sxs-lookup"><span data-stu-id="ed364-105">Register asset loans on a maintenance request</span></span>

1. <span data-ttu-id="ed364-106">Selecione **Gerenciamento de ativos** \> **Comum** \> **Solicitações de manutenção** \> **Todas as solicitações de manutenção** ou **Solicitações manutenção de ativos**.</span><span class="sxs-lookup"><span data-stu-id="ed364-106">Select **Asset management** \> **Common** \> **Maintenance requests** \> **All maintenance requests** or **Active maintenance requests**.</span></span>
2. <span data-ttu-id="ed364-107">Selecione a solicitação de manutenção para registrar um empréstimo de ativo e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ed364-107">Select the maintenance request to register an asset loan on, and then select **Edit**.</span></span>
3. <span data-ttu-id="ed364-108">Na página **Solicitação**, selecione **Enviar ativo de empréstimo**.</span><span class="sxs-lookup"><span data-stu-id="ed364-108">On the **Request** page, select **Send loan asset**.</span></span>
4. <span data-ttu-id="ed364-109">Selecione o ativo e insira a data de devolução prevista.</span><span class="sxs-lookup"><span data-stu-id="ed364-109">Select the asset, and enter the expected return date.</span></span>
5. <span data-ttu-id="ed364-110">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="ed364-110">Select **OK**.</span></span>

> [!NOTE]
> - <span data-ttu-id="ed364-111">Você só poderá enviar um ativo de empréstimo se um ativo do mesmo tipo de ativo fixo estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="ed364-111">You can send a loan asset only if an asset of the same asset type is available.</span></span>
> - <span data-ttu-id="ed364-112">O ativo que você empresta deve ter um estado do ciclo de vida do ativo que permita ser usado como um ativo de empréstimo, como **InStorage**.</span><span class="sxs-lookup"><span data-stu-id="ed364-112">The asset that you loan must have an asset lifecycle state that allows it to be used as a loan asset, such as **InStorage**.</span></span> <span data-ttu-id="ed364-113">Quando o empréstimo de ativo é registrado, o estado do ciclo de vida do ativo é atualizado automaticamente, por exemplo, para **OnLoan**.</span><span class="sxs-lookup"><span data-stu-id="ed364-113">When the asset loan is registered, the asset lifecycle state of the asset is automatically updated to, for example, **OnLoan**.</span></span>

<span data-ttu-id="ed364-114">Para exibir uma lista de todos os ativos que você emprestou a outros locais ou clientes, selecione **Gerenciamento de ativos** \> **Comum** \> **Empréstimo de ativo** \> **Todos os empréstimos de ativos**.</span><span class="sxs-lookup"><span data-stu-id="ed364-114">To view a list of all the assets that you've loaned to other locations or customers, select **Asset management** \> **Common** \> **Asset loan** \> **All asset loans**.</span></span> <span data-ttu-id="ed364-115">Se a caixa de seleção **Concluído** estiver marcada para um ativo, significa que o ativo foi registrado como devolvido para sua empresa.</span><span class="sxs-lookup"><span data-stu-id="ed364-115">If the **Ended** check box is selected for an asset, the asset has been registered as returned to your company.</span></span>

![Gerenciar Solicitações de Manutenção](media/06-manage-maintenance-requests.png)

<span data-ttu-id="ed364-117">Na página **Empréstimos de ativos em ação**, exiba uma lista de todos os ativos de empréstimo que ainda não foram devolvidos à sua empresa.</span><span class="sxs-lookup"><span data-stu-id="ed364-117">On the **Active asset loans** page, you can view a list of all the loan assets that haven't yet been returned to your company.</span></span>

## <a name="register-loan-assets-as-returned"></a><span data-ttu-id="ed364-118">Registre ativos de empréstimo conforme devolvidos</span><span class="sxs-lookup"><span data-stu-id="ed364-118">Register loan assets as returned</span></span>

1. <span data-ttu-id="ed364-119">Selecione **Gerenciamento de ativos** \> **Comum** \> **Empréstimo de ativo** \> **Empréstimos de ativos em ação**.</span><span class="sxs-lookup"><span data-stu-id="ed364-119">Select **Asset management** \> **Common** \> **Asset loan** \> **Active asset loans**.</span></span>
2. <span data-ttu-id="ed364-120">Selecione o empréstimo de ativo para registrar como devolvido e selecione **Devolver empréstimo de ativo**.</span><span class="sxs-lookup"><span data-stu-id="ed364-120">Select the asset loan to register as returned, and then select **Return asset loan**.</span></span>
3. <span data-ttu-id="ed364-121">No campo **Devolvido**, insira a data e a hora.</span><span class="sxs-lookup"><span data-stu-id="ed364-121">In the **Returned** field, enter the date and time.</span></span>
4. <span data-ttu-id="ed364-122">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="ed364-122">Select **OK**.</span></span>
5. <span data-ttu-id="ed364-123">Atualize a página **Empréstimos de ativos em ação** e observe que o empréstimo de ativos não aparece mais na lista.</span><span class="sxs-lookup"><span data-stu-id="ed364-123">Refresh the **Active asset loans** list page, and notice that the asset loan no longer appears in the list.</span></span>
