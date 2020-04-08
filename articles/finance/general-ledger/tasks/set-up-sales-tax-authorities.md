---
title: Configurar autoridades de imposto sobre vendas
description: As autoridades de impostos sobre vendas são as entidades que coletaram necessidades de impostos sobre vendas a serem informados e pagos.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dc6aeb39591c68cae78537faa077010d68628b02
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144757"
---
# <a name="set-up-sales-tax-authorities"></a><span data-ttu-id="df877-103">Configurar autoridades de imposto sobre vendas</span><span class="sxs-lookup"><span data-stu-id="df877-103">Set up sales tax authorities</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="df877-104">As autoridades de impostos sobre vendas são as entidades que coletaram necessidades de impostos sobre vendas a serem informados e pagos.</span><span class="sxs-lookup"><span data-stu-id="df877-104">Sales tax authorities are entities to which collected sales tax needs to be reported and paid.</span></span> <span data-ttu-id="df877-105">Você pode pagar impostos sobre vendas diretamente para a autoridade ou por meio de uma conta de fornecedor que você cria para a autoridade do imposto sobre vendas.</span><span class="sxs-lookup"><span data-stu-id="df877-105">You can pay sales taxes to the authority directly or through a vendor account that you create for the sales tax authority.</span></span> <span data-ttu-id="df877-106">Se você ficar isso, a empresa poderá usar suas rotinas de pagamento usuais para pagar a autoridade do imposto sobre vendas a tempo.</span><span class="sxs-lookup"><span data-stu-id="df877-106">If you do this, the company can use its usual payment routines to pay the sales tax authority on time.</span></span> <span data-ttu-id="df877-107">Se você não configurar a autoridade fiscal como um fornecedor, alguém deve preparar um pagamento manual para a autoridade fiscal na data de vencimento apropriada.</span><span class="sxs-lookup"><span data-stu-id="df877-107">If you do not set up the tax authority as a vendor, someone must prepare a manual payment to the tax authority on the appropriate due date.</span></span> <span data-ttu-id="df877-108">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="df877-108">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="df877-109">Vá para Imposto > Impostos indiretos > Imposto sobre vendas > Autoridades de impostos sobre vendas.</span><span class="sxs-lookup"><span data-stu-id="df877-109">Go to Tax > Indirect taxes > Sales tax > Sales tax authorities.</span></span>
2. <span data-ttu-id="df877-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="df877-110">Click New.</span></span>
3. <span data-ttu-id="df877-111">No campo Autoridade, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="df877-111">In the Authority field, type a value.</span></span>
4. <span data-ttu-id="df877-112">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="df877-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="df877-113">No campo Conta de fornecedor, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="df877-113">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="df877-114">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="df877-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="df877-115">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="df877-115">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="df877-116">Selecione o layout de relatório de seu país/região, se disponível.</span><span class="sxs-lookup"><span data-stu-id="df877-116">Select the report layout for your country/region, if one is available.</span></span> <span data-ttu-id="df877-117">Se os layouts de relatório não corresponderem aos requisitos da autoridade de imposto sobre vendas, use o layout padrão.</span><span class="sxs-lookup"><span data-stu-id="df877-117">If the report layouts do not correspond to the requirements of the sales tax authority, use default layout.</span></span>
9. <span data-ttu-id="df877-118">Insira valores no formulário de arredondamento e nos campos redondos para especificar como o valor total do imposto a ser pago deve ser arredondado.</span><span class="sxs-lookup"><span data-stu-id="df877-118">Enter values in the Rounding form and the Round-off fields to specify how the tax total amount to be paid should be rounded.</span></span> <span data-ttu-id="df877-119">Todas as diferenças de arredondamento serão lançadas para as transações automáticas configuradas na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="df877-119">Any rounding differences will be posted to Accounts for automatic transactions set up in General ledger.</span></span>
10. <span data-ttu-id="df877-120">No campo Arredondar, insira um número.</span><span class="sxs-lookup"><span data-stu-id="df877-120">In the Round-off field, enter a number.</span></span>
11. <span data-ttu-id="df877-121">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="df877-121">Click Save.</span></span>

