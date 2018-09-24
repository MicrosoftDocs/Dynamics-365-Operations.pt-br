---
title: "Gerenciar a validação da conta do IBAN (número de conta bancária internacional)"
description: "Este tópico explica como gerenciar a validação da conta do IBAN (número de conta bancária internacional)."
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: e091aab70a98e0f4b96c41c1ee48926947539105
ms.contentlocale: pt-br
ms.lasthandoff: 08/31/2018

---

# <a name="manage-international-bank-account-number-iban-account-validation"></a><span data-ttu-id="9d89e-103">Gerenciar a validação da conta do IBAN (número de conta bancária internacional)</span><span class="sxs-lookup"><span data-stu-id="9d89e-103">Manage International Bank Account Number (IBAN) account validation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9d89e-104">A validação da conta do IBAN aumenta a quantidade de validação realizada quando você adiciona um IBAN a uma conta bancária.</span><span class="sxs-lookup"><span data-stu-id="9d89e-104">International Bank Account Number (IBAN) account validation increases the amount of validation that is done when you add an IBAN to a bank account.</span></span>

<span data-ttu-id="9d89e-105">A estrutura do IBAN é armazenada no Microsoft Dynamics 365 for Finance and Operation e é automaticamente carregada quando você usa o IBAN pela primeira vez em contas bancárias.</span><span class="sxs-lookup"><span data-stu-id="9d89e-105">The structure of the IBAN is stored in Microsoft Dynamics 365 for Finance and Operation, and is automatically loaded when you first use the IBAN on bank accounts.</span></span> <span data-ttu-id="9d89e-106">O número de conta bancária faz parte da estrutura definida para um IBAN.</span><span class="sxs-lookup"><span data-stu-id="9d89e-106">The bank account number is part of the structure defined for an IBAN number.</span></span> <span data-ttu-id="9d89e-107">Com base nessa estrutura, se a posição e o comprimento do número da conta no IBAN não corresponderem à posição definida na estrutura para cada país ou região, você receberá mensagens de aviso.</span><span class="sxs-lookup"><span data-stu-id="9d89e-107">Based on that structure, if the position and length of the account number in the IBAN don't match the position that is defined in the structure for each country or region, you will receive warning messages.</span></span>

## <a name="set-up-iban-structures"></a><span data-ttu-id="9d89e-108">Configurar estruturas IBAN</span><span class="sxs-lookup"><span data-stu-id="9d89e-108">Set up IBAN structures</span></span>

1. <span data-ttu-id="9d89e-109">Vá para **Gerenciamento de dinheiro e banco \> Configuração \> Estruturas IBAN**.</span><span class="sxs-lookup"><span data-stu-id="9d89e-109">Go to **Cash and bank management \> Setup \> IBAN structures**.</span></span>
2. <span data-ttu-id="9d89e-110">Observe que as estruturas IBAN de cada país ou região foram configuradas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9d89e-110">Notice that the IBAN structures for each country or region have been set up automatically.</span></span>
3. <span data-ttu-id="9d89e-111">Se você precisar personalizar as estruturas de um país ou região específico, poderá editá-las.</span><span class="sxs-lookup"><span data-stu-id="9d89e-111">If you must customize the structures for a specific country or region, you can edit them.</span></span>
4. <span data-ttu-id="9d89e-112">As definições das estruturas farão parte de cada lançamento.</span><span class="sxs-lookup"><span data-stu-id="9d89e-112">The structure definitions will be a part of each new release.</span></span> <span data-ttu-id="9d89e-113">Você pode usar o menu **Redefinir estruturas** para carregar as definições mais recentes após cada atualização.</span><span class="sxs-lookup"><span data-stu-id="9d89e-113">You can use the **Reset structures** menu to load the latest definitions after each update.</span></span>

## <a name="validate-the-iban-structure-in-a-bank-account"></a><span data-ttu-id="9d89e-114">Validar a estrutura IBAN em uma conta bancária</span><span class="sxs-lookup"><span data-stu-id="9d89e-114">Validate the IBAN structure in a bank account</span></span>

1. <span data-ttu-id="9d89e-115">Vá para **Gerenciamento de caixa e bancos \> Contas bancárias \> Contas bancárias**.</span><span class="sxs-lookup"><span data-stu-id="9d89e-115">Go to **Cash and bank management \> Bank accounts \> Bank accounts**.</span></span>
2. <span data-ttu-id="9d89e-116">Crie uma conta bancária.</span><span class="sxs-lookup"><span data-stu-id="9d89e-116">Create a bank account.</span></span>
3. <span data-ttu-id="9d89e-117">Na Guia Rápida **Informações adicionais**, insira um IBAN.</span><span class="sxs-lookup"><span data-stu-id="9d89e-117">On the **Additional information** FastTab, enter an IBAN.</span></span>

    <span data-ttu-id="9d89e-118">Se a posição e o comprimento do número da conta no IBAN não corresponderem à posição definida na estrutura para cada país ou região, você receberá uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="9d89e-118">If the position and length of the account number in the IBAN don't match the position that is defined in the structure for each country or region, you receive a message.</span></span> <span data-ttu-id="9d89e-119">Você não poderá continuar se o comprimento do IBAN não corresponder ao comprimento na estrutura IBAN.</span><span class="sxs-lookup"><span data-stu-id="9d89e-119">You can't continue if the length of the IBAN doesn't match the length in the IBAN structure.</span></span>

    <span data-ttu-id="9d89e-120">A validação também verifica se o número da conta bancária corresponde à parte do IBAN que representa o número da conta bancária.</span><span class="sxs-lookup"><span data-stu-id="9d89e-120">The validation also verifies that the bank account number matches the part of the IBAN that represents the bank account number.</span></span> <span data-ttu-id="9d89e-121">Se o número da conta bancária não corresponder, você receberá uma mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="9d89e-121">If the bank account number doesn't match, you receive a warning message.</span></span> <span data-ttu-id="9d89e-122">Essa mensagem é apenas um aviso.</span><span class="sxs-lookup"><span data-stu-id="9d89e-122">This message is only a warning.</span></span> <span data-ttu-id="9d89e-123">Você poderá continuar mesmo se o número da conta bancária não corresponder.</span><span class="sxs-lookup"><span data-stu-id="9d89e-123">You can continue even if the bank account number doesn't match.</span></span>

