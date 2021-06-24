---
title: Devolver produtos controlados por número de série no POS
description: Este tópico descreve os recursos para validar itens serializados como parte do processo de devolução no aplicativo Microsoft Dynamics 365 Commerce point of sale (POS).
author: hhainesms
ms.date: 06/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 7a067994828f3df577c0dc4146d26ac81990d4ac
ms.sourcegitcommit: 927574c77f4883d906e5c7bddf0af9b717e492bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129793"
---
# <a name="return-serial-numbercontrolled-products-in-pos"></a><span data-ttu-id="02a16-103">Devolver produtos controlados por número de série no POS</span><span class="sxs-lookup"><span data-stu-id="02a16-103">Return serial number–controlled products in POS</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="02a16-104">Este tópico descreve os recursos para validar itens serializados como parte do processo de devolução no aplicativo Microsoft Dynamics 365 Commerce point of sale (POS).</span><span class="sxs-lookup"><span data-stu-id="02a16-104">This topic describes the capabilities for validating serialized items as part of the return process in the Microsoft Dynamics 365 Commerce point of sale (POS) application.</span></span>

> [!NOTE]
> <span data-ttu-id="02a16-105">Na versão 10.0.20 e posterior do Commerce, um novo recurso chamado **Experiência de processamento de devolução unificado para POS** está disponível.</span><span class="sxs-lookup"><span data-stu-id="02a16-105">In the Commerce version 10.0.20 release and later, a new feature that is named **Unified return processing experience in POS** is available.</span></span> <span data-ttu-id="02a16-106">Para usar a validação de número de série durante o processamento de ordem de devolução no POS, você deve ativar este recurso.</span><span class="sxs-lookup"><span data-stu-id="02a16-106">To use serial number validation during return order processing in POS, you must turn on this feature.</span></span> <span data-ttu-id="02a16-107">Para mais informações sobre outras funcionalidades que este recurso oferece quando é ativado, consulte [Criar devoluções no POS)](POS-returns.md).</span><span class="sxs-lookup"><span data-stu-id="02a16-107">For information about others capabilities that this feature provides when it's turned on, see [Create returns in POS)](POS-returns.md).</span></span>
>
> <span data-ttu-id="02a16-108">Depois que o recurso é ativado, não é possível desativá-lo.</span><span class="sxs-lookup"><span data-stu-id="02a16-108">After the feature is turned on, it can't be turned off.</span></span>

## <a name="options-for-validating-serialized-returns"></a><span data-ttu-id="02a16-109">Opções para validar devoluções serializadas</span><span class="sxs-lookup"><span data-stu-id="02a16-109">Options for validating serialized returns</span></span>

<span data-ttu-id="02a16-110">Quando o recurso **Experiência de processamento de devolução unificado para POS** é ativado, as organizações podem realizar uma validação das devoluções de itens controlados por número de série no POS.</span><span class="sxs-lookup"><span data-stu-id="02a16-110">When the **Unified return processing experience in POS** feature is turned on, organizations can perform a validation on returns of serial number–controlled items through POS.</span></span> <span data-ttu-id="02a16-111">Esta funcionalidade pode avisar os usuários se o número de série está sendo devolvido difere do número de série original que foi vendido.</span><span class="sxs-lookup"><span data-stu-id="02a16-111">This capability can warn users if the serial number that is being returned differs from the original serial number that was sold.</span></span> <span data-ttu-id="02a16-112">No Commerce versão 10.0.20 e posterior, a mensagem que os usuários recebem é somente uma mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="02a16-112">In the Commerce version 10.0.20 release and later, the message that users receive is only a warning message.</span></span> <span data-ttu-id="02a16-113">Os usuários podem continuar processando uma devolução com base em um número de série que seja diferente do número de série original que foi vendido.</span><span class="sxs-lookup"><span data-stu-id="02a16-113">Users can continue to process a return against a serial number that differs from the serial number that was originally sold.</span></span>

<span data-ttu-id="02a16-114">Para configurar a validação do número de série para uma organização após o recurso **Experiência de processamento de devolução unificado para POS** for ativado, vá para **Retail e Commerce \> Configurações da sede \> Parâmetros \> Parâmetros do CommerceParâmetros** na sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="02a16-114">To configure serial number validation for an organization after the **Unified return processing experience in POS** feature is turned on, go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters** in Commerce headquarters.</span></span> <span data-ttu-id="02a16-115">Na guia **Inventário**, na FastTab **Armazenar operações de inventário**, defina a opção **Habilitar validar de números de série nas devoluções do POS** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="02a16-115">On the **Inventory** tab, on the **Store inventory operations** FastTab, set the **Enable validation of serial numbers on POS returns** option to **Yes**.</span></span>

## <a name="process-returns-for-serialized-items-in-pos"></a><span data-ttu-id="02a16-116">Processar devoluções para itens serializados no POS</span><span class="sxs-lookup"><span data-stu-id="02a16-116">Process returns for serialized items in POS</span></span>

<span data-ttu-id="02a16-117">Se a opção **Habilitar validar de números de série nas devoluções do POS** tiver sido definida como **Sim**, quando um item controlado por número de série é devolvida no POS, o usuário pode digitar o número de série para a linha de devolução no painel de detalhes na página **Produtos que podem ser devolvidos**.</span><span class="sxs-lookup"><span data-stu-id="02a16-117">If the **Enable validation of serial numbers on POS returns** option has been set to **Yes**, when a serial number–controlled item is returned through POS, the user can enter the serial number for the return line in the details pane on the **Returnable products** page.</span></span> <span data-ttu-id="02a16-118">Se o número de série inserido não corresponder ao número de série original que foi vendido para a transação de vendas, o usuário receberá uma mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="02a16-118">If the serial number that is entered doesn't match the original serial number that was sold for the sales transaction, the user receives a warning message.</span></span> <span data-ttu-id="02a16-119">No entanto, o aplicativo não impede que o usuário continue publicando a devolução.</span><span class="sxs-lookup"><span data-stu-id="02a16-119">However, the application doesn't prevent the user from continuing to post the return.</span></span>

> [!NOTE]
> <span data-ttu-id="02a16-120">No momento, o POS é compatível com a validação de números de série somente nas linhas de devolução em que a quantidade comprada original não seja maior que um.</span><span class="sxs-lookup"><span data-stu-id="02a16-120">Currently, POS supports validation of serial numbers only on return lines where the original ordered quantity is no more than one.</span></span> <span data-ttu-id="02a16-121">Se a linha de ordem de venda original tiver sido criada em um canal que não é do POS, e se a quantidade comprada do item serializado em uma determinada linha de venda for maior que um, o item não poderá ser retornado corretamente no POS.</span><span class="sxs-lookup"><span data-stu-id="02a16-121">If the original sales order line was created in a non-POS channel, and if the quantity that was ordered for the serialized item on a given sales line is more than one, the item can't be correctly returned through POS.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="02a16-122">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="02a16-122">Additional resources</span></span>

[<span data-ttu-id="02a16-123">Criar devoluções no POS</span><span class="sxs-lookup"><span data-stu-id="02a16-123">Create returns in POS</span></span>](POS-returns.md)
