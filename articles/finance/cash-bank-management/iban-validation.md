---
title: Gerenciar a validação da conta do IBAN (número de conta bancária internacional)
description: Este tópico explica como gerenciar a validação da conta do IBAN (número de conta bancária internacional).
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 2aaccd7c09d6daf8a237a433cc22ac1bfc3c1541
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551238"
---
# <a name="manage-international-bank-account-number-iban-account-validation"></a><span data-ttu-id="e0d83-103">Gerenciar a validação da conta do IBAN (número de conta bancária internacional)</span><span class="sxs-lookup"><span data-stu-id="e0d83-103">Manage International Bank Account Number (IBAN) account validation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e0d83-104">A validação do IBAN aumenta o valor de validação realizada quando você adiciona um IBAN a uma conta bancária.</span><span class="sxs-lookup"><span data-stu-id="e0d83-104">International Bank Account Number (IBAN) validation increases the amount of validation that is done when you add an IBAN to a bank account.</span></span>

<span data-ttu-id="e0d83-105">As informações sobre a estrutura do IBAN são armazenadas no Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="e0d83-105">Information about the structure of the IBAN is stored in Microsoft Dynamics 365 Finance.</span></span> <span data-ttu-id="e0d83-106">Essas informações são carregadas automaticamente quando você usa o IBAN pela primeira vez em contas bancárias.</span><span class="sxs-lookup"><span data-stu-id="e0d83-106">That information is automatically loaded when you first use the IBAN on bank accounts.</span></span> <span data-ttu-id="e0d83-107">Elas contêm o tamanho do IBAN, as posições iniciais do número de conta bancária e o número de roteamento, além do tamanho do número de conta bancária e do número de roteamento.</span><span class="sxs-lookup"><span data-stu-id="e0d83-107">It contains the length of the IBAN, the starting positions of the bank account number and the routing number, and the length of the bank account number and routing number.</span></span>

## <a name="set-up-iban-structures"></a><span data-ttu-id="e0d83-108">Configurar estruturas IBAN</span><span class="sxs-lookup"><span data-stu-id="e0d83-108">Set up IBAN structures</span></span>

1. <span data-ttu-id="e0d83-109">Vá para **Gerenciamento de dinheiro e banco \> Configuração \> Estruturas IBAN**.</span><span class="sxs-lookup"><span data-stu-id="e0d83-109">Go to **Cash and bank management \> Setup \> IBAN structures**.</span></span>
2. <span data-ttu-id="e0d83-110">Observe que as estruturas IBAN de cada país ou região foram configuradas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e0d83-110">Notice that the IBAN structures for each country or region have been set up automatically.</span></span>
3. <span data-ttu-id="e0d83-111">Se desejar personalizar as estruturas de um país ou região específica, você poderá editá-las.</span><span class="sxs-lookup"><span data-stu-id="e0d83-111">If you want to customize the structures for a specific country or region, you can edit them.</span></span>
4. <span data-ttu-id="e0d83-112">As definições das estruturas farão parte de cada lançamento.</span><span class="sxs-lookup"><span data-stu-id="e0d83-112">The structure definitions will be a part of each new release.</span></span> <span data-ttu-id="e0d83-113">Você pode usar o menu **Redefinir estruturas** para carregar as definições mais recentes após cada atualização.</span><span class="sxs-lookup"><span data-stu-id="e0d83-113">You can use the **Reset structures** menu to load the latest definitions after each update.</span></span>

## <a name="validate-the-iban-structure-in-a-bank-account"></a><span data-ttu-id="e0d83-114">Validar a estrutura IBAN em uma conta bancária</span><span class="sxs-lookup"><span data-stu-id="e0d83-114">Validate the IBAN structure in a bank account</span></span>

1. <span data-ttu-id="e0d83-115">Vá para **Gerenciamento de caixa e bancos \> Contas bancárias \> Contas bancárias**.</span><span class="sxs-lookup"><span data-stu-id="e0d83-115">Go to **Cash and bank management \> Bank accounts \> Bank accounts**.</span></span>
2. <span data-ttu-id="e0d83-116">Crie uma conta bancária.</span><span class="sxs-lookup"><span data-stu-id="e0d83-116">Create a bank account.</span></span>
3. <span data-ttu-id="e0d83-117">Na Guia Rápida **Informações adicionais**, insira um IBAN.</span><span class="sxs-lookup"><span data-stu-id="e0d83-117">On the **Additional information** FastTab, enter an IBAN.</span></span>

    <span data-ttu-id="e0d83-118">Se o tamanho do IBAN não corresponder ao tamanho definido para cada país ou região, você receberá uma mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="e0d83-118">If the length of the IBAN doesn't match the length that is defined for each country or region, you will receive a warning message.</span></span> <span data-ttu-id="e0d83-119">Você não poderá continuar se o tamanho do IBAN não corresponder ao tamanho especificado na estrutura do IBAN.</span><span class="sxs-lookup"><span data-stu-id="e0d83-119">You can't continue if the length of the IBAN doesn't match the length specified in the IBAN structure.</span></span>

    <span data-ttu-id="e0d83-120">A validação também verifica se o número da conta bancária corresponde à parte do IBAN que representa o número da conta bancária.</span><span class="sxs-lookup"><span data-stu-id="e0d83-120">The validation also verifies that the bank account number matches the part of the IBAN that represents the bank account number.</span></span> <span data-ttu-id="e0d83-121">Se o número da conta bancária não coincidir, você receberá uma mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="e0d83-121">If the bank account number doesn't match, you will receive a warning message.</span></span> <span data-ttu-id="e0d83-122">Essa mensagem é apenas um aviso.</span><span class="sxs-lookup"><span data-stu-id="e0d83-122">This message is only a warning.</span></span> <span data-ttu-id="e0d83-123">Você poderá continuar mesmo se o número da conta bancária não corresponder.</span><span class="sxs-lookup"><span data-stu-id="e0d83-123">You can continue even if the bank account number doesn't match.</span></span>

    <span data-ttu-id="e0d83-124">A validação também verifica se o número de roteamento do banco corresponde à parte do IBAN que representa o número de roteamento do banco.</span><span class="sxs-lookup"><span data-stu-id="e0d83-124">The validation also verifies that the bank routing number matches the part of the IBAN that represents the bank routing number.</span></span> <span data-ttu-id="e0d83-125">O número de roteamento inclui um número de banco e, em geral, uma agência bancária adicional.</span><span class="sxs-lookup"><span data-stu-id="e0d83-125">The routing number includes a bank number and often an additional bank branch.</span></span> <span data-ttu-id="e0d83-126">Se o número de roteamento do banco não coincidir, você receberá uma mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="e0d83-126">If the bank routing number doesn't match, you will receive a warning message.</span></span> <span data-ttu-id="e0d83-127">Essa mensagem é apenas um aviso.</span><span class="sxs-lookup"><span data-stu-id="e0d83-127">This message is only a warning.</span></span> <span data-ttu-id="e0d83-128">Você poderá continuar mesmo se o número da roteamento do banco não coincidir.</span><span class="sxs-lookup"><span data-stu-id="e0d83-128">You can continue even if the bank routing number doesn't match.</span></span>
