---
title: Criar um contrato de recursos bancários para uma carta de crédito
description: Essa tarefa caminha com a criação de um contrato de recursos bancários para processar uma carta de crédito.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankDocumentFacilityAgreement, BankAccountTableLookUp, BankDocumentFacilityAgreementExtension, DefaultDashboard
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cb624700e0b052de977fabecf9670b3515d32ab7
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141701"
---
# <a name="create-a-bank-facility-agreement-for-a-letter-of-credit"></a><span data-ttu-id="c3205-103">Criar um contrato de recursos bancários para uma carta de crédito</span><span class="sxs-lookup"><span data-stu-id="c3205-103">Create a bank facility agreement for a letter of credit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c3205-104">Essa tarefa caminha com a criação de um contrato de recursos bancários para processar uma carta de crédito.</span><span class="sxs-lookup"><span data-stu-id="c3205-104">This task walks through the creating a Bank facility agreement to process a Letter of credit.</span></span> <span data-ttu-id="c3205-105">Você desejará configurar parâmetros de recursos e perfis de lançamentos antes desta tarefa.</span><span class="sxs-lookup"><span data-stu-id="c3205-105">You will want to set up bank facilities and posting profiles before this task.</span></span>  <span data-ttu-id="c3205-106">Este tarefa usa a empresa demo 'USMF'.</span><span class="sxs-lookup"><span data-stu-id="c3205-106">This task uses the demo company 'USMF'.</span></span>  


## <a name="create-bank-facility-agreement"></a><span data-ttu-id="c3205-107">Criar um Contrato de recursos bancários</span><span class="sxs-lookup"><span data-stu-id="c3205-107">Create Bank facility agreement</span></span>
1. <span data-ttu-id="c3205-108">Vá para Gerenciamento de dinheiro e banco > Cartas de crédito > Contratos de facilidade do banco.</span><span class="sxs-lookup"><span data-stu-id="c3205-108">Go to Cash and bank management > Letters of credit > Bank facility agreements.</span></span>
2. <span data-ttu-id="c3205-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="c3205-109">Click New.</span></span>
3. <span data-ttu-id="c3205-110">No campo Número do contrato, insira o número do contrato de acordo com o contrato com o banco.</span><span class="sxs-lookup"><span data-stu-id="c3205-110">In the Agreement number field, enter the agreement number according to the agreement with the bank.</span></span>
4. <span data-ttu-id="c3205-111">No campo Conta de banco, insira o número da conta do banco emissor.</span><span class="sxs-lookup"><span data-stu-id="c3205-111">In the Bank account field, enter the account number at the issuing bank.</span></span>
5. <span data-ttu-id="c3205-112">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c3205-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="c3205-113">No campo de data Iniciar, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="c3205-113">In the Start date field, enter a date and time.</span></span>
7. <span data-ttu-id="c3205-114">No campo de data Finalizar, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="c3205-114">In the End date field, enter a date and time.</span></span>
8. <span data-ttu-id="c3205-115">Expandir ou recolher a seção Geral.</span><span class="sxs-lookup"><span data-stu-id="c3205-115">Expand or collapse the General section.</span></span>
9. <span data-ttu-id="c3205-116">Clique em Adicionar nova linha.</span><span class="sxs-lookup"><span data-stu-id="c3205-116">Click Add line.</span></span>
10. <span data-ttu-id="c3205-117">No campo Tipo de facilidade, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c3205-117">In the Facility type field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="c3205-118">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="c3205-118">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="c3205-119">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c3205-119">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="c3205-120">No campo Limitar, insira o valor de recurso que foi negociado com o banco.</span><span class="sxs-lookup"><span data-stu-id="c3205-120">In the Limit field, enter the facility amount that was negotiated with the bank.</span></span>
14. <span data-ttu-id="c3205-121">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="c3205-121">Click Save.</span></span>
15. <span data-ttu-id="c3205-122">Clique em Estender para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="c3205-122">Click Extend to open the drop dialog.</span></span>
16. <span data-ttu-id="c3205-123">No campo Número de contrato novo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c3205-123">In the New agreement number field, type a value.</span></span>
17. <span data-ttu-id="c3205-124">No campo de data Finalizar, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="c3205-124">In the End date field, enter a date and time.</span></span>
18. <span data-ttu-id="c3205-125">Clique em Estender.</span><span class="sxs-lookup"><span data-stu-id="c3205-125">Click Extend.</span></span>
19. <span data-ttu-id="c3205-126">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c3205-126">Close the page.</span></span>

