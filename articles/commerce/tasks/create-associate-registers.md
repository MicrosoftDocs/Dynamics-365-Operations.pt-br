---
title: Criar e associar registros
description: Este procedimento demonstra como criar um registro do ponto de venda (POS).
author: rubencdelgado
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailTerminalTable
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba978a3d895394760687386197dbb3512c62ef98
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798552"
---
# <a name="create-and-associate-registers"></a><span data-ttu-id="7b2d8-103">Criar e associar registros</span><span class="sxs-lookup"><span data-stu-id="7b2d8-103">Create and associate registers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7b2d8-104">Este procedimento demonstra como criar um registro do ponto de venda (POS).</span><span class="sxs-lookup"><span data-stu-id="7b2d8-104">This procedure demonstrates how to create a point of sale (POS) register.</span></span> <span data-ttu-id="7b2d8-105">Este procedimento usa a empresa de dados de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="7b2d8-105">This procedure uses the demo data company USRT.</span></span>

1. <span data-ttu-id="7b2d8-106">Vá para Varejo e Comércio > Configuração de canal > Configuração do PDV > Terminais.</span><span class="sxs-lookup"><span data-stu-id="7b2d8-106">Go to Retail and Commerce > Channel setup > POS setup > Registers.</span></span>
2. <span data-ttu-id="7b2d8-107">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7b2d8-107">Click New.</span></span>
3. <span data-ttu-id="7b2d8-108">No campo Registrar número, digite uma ID para o novo registro.</span><span class="sxs-lookup"><span data-stu-id="7b2d8-108">In the Register number field, type an ID for the new register.</span></span>
    * <span data-ttu-id="7b2d8-109">A identificação do registro inclui tipicamente os códigos que ajudam a traçar o registro à loja que pertence e ao lugar dentro da loja.</span><span class="sxs-lookup"><span data-stu-id="7b2d8-109">The register ID typically includes codes that help map the register to the store to which it belongs, and the location within the store.</span></span>  
4. <span data-ttu-id="7b2d8-110">No campo Nome, digite um nome descritivo para o registro.</span><span class="sxs-lookup"><span data-stu-id="7b2d8-110">In the Name field, type a descriptive name for the register..</span></span>
5. <span data-ttu-id="7b2d8-111">No campo Número da loja, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7b2d8-111">In the Store number field, enter or select a value.</span></span>
6. <span data-ttu-id="7b2d8-112">No campo Perfil de hardware, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7b2d8-112">In the Hardware profile field, enter or select a value.</span></span>
    * <span data-ttu-id="7b2d8-113">Os perfis de hardware são usados para especificar os periféricos que serão conectados ao registro, tal como o caixa do dinheiro e a impressora do recibo.</span><span class="sxs-lookup"><span data-stu-id="7b2d8-113">Hardware profiles are used to specify the peripherals that will be connected to the register, such as cash drawer and receipt printer.</span></span>  
7. <span data-ttu-id="7b2d8-114">No campo Perfil visual, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7b2d8-114">In the Visual profile field, enter or select a value.</span></span>
    * <span data-ttu-id="7b2d8-115">Os perfis visuais são usados para especificar as imagens usadas no fundo da posição e na página do início de uma sessão assim como temas para a posição.</span><span class="sxs-lookup"><span data-stu-id="7b2d8-115">Visual profiles are used to specify the images used in the POS background and login page as well as themes for the POS.</span></span>  
8. <span data-ttu-id="7b2d8-116">No campo Número do registro de PDV de TEF, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7b2d8-116">In the EFT POS register number field, type a value.</span></span>
    * <span data-ttu-id="7b2d8-117">O número do registro da posição de EFT é usado para informar o processador do pagamento ao qual o terminal do pagamento está enviando pedidos da autorização.</span><span class="sxs-lookup"><span data-stu-id="7b2d8-117">The EFT POS register number is used to inform the payment processor which payment terminal is sending authorization requests.</span></span> <span data-ttu-id="7b2d8-118">Este valor é chamado frequentemente de "ID de terminal ou "TID".</span><span class="sxs-lookup"><span data-stu-id="7b2d8-118">This value is often called the "Terminal ID" or "TID".</span></span> <span data-ttu-id="7b2d8-119">O TID pode geralmente ser encontrado em uma etiqueta no dispositivo do pagamento.</span><span class="sxs-lookup"><span data-stu-id="7b2d8-119">The TID can generally be found on a sticker on the payment device.</span></span>  
9. <span data-ttu-id="7b2d8-120">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7b2d8-120">Click Save.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]