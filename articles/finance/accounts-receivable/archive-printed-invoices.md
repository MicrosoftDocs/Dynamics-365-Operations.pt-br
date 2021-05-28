---
title: Arquivar faturas de clientes impressas com números de hash
description: Este tópico explica como habilitar o arquivamento a fim de armazenar faturas de clientes impressas com números de hash.
author: ilyako
ms.date: 03/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 841e6059f5b0d70dbd1fe12a1f8910bbb31ddc86
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018969"
---
# <a name="archive-printed-customer-invoices-with-hash-numbers"></a><span data-ttu-id="ddd63-103">Arquivar faturas de clientes impressas com números de hash</span><span class="sxs-lookup"><span data-stu-id="ddd63-103">Archive printed customer invoices with hash numbers</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="ddd63-104">Em alguns países, há um requisito legal de armazenar números de hash calculados no sistema juntamente com impressões de alguns documentos.</span><span class="sxs-lookup"><span data-stu-id="ddd63-104">In some countries, there is a legal requirement to store calculated hash numbers in the system together with printouts of some documents.</span></span> <span data-ttu-id="ddd63-105">Os números de hash podem ser usados para relatar autoridades e durante auditorias.</span><span class="sxs-lookup"><span data-stu-id="ddd63-105">Hash numbers can be used for reporting to authorities and during audits.</span></span>

<span data-ttu-id="ddd63-106">Este tópico explica como configurar o arquivamento a fim de armazenar faturas de clientes impressas com números de hash.</span><span class="sxs-lookup"><span data-stu-id="ddd63-106">This topic explains how to configure archiving in order to store printed customer invoices with hash numbers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ddd63-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="ddd63-107">Prerequisites</span></span>

- <span data-ttu-id="ddd63-108">No espaço de trabalho **Gerenciamento de recursos**, ative o recurso, **Arquivar faturas de clientes impressas com números de hash**.</span><span class="sxs-lookup"><span data-stu-id="ddd63-108">In the **Feature management** workspace, turn on the feature, **Archive printed customer invoices with hash numbers**.</span></span> <span data-ttu-id="ddd63-109">Para obter mais informações, consulte [Visão geral do Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ddd63-109">For more information, see [Feature management overview](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
- <span data-ttu-id="ddd63-110">Configure os formatos imprimíveis dos documentos necessários em **Gerenciamento de impressão**.</span><span class="sxs-lookup"><span data-stu-id="ddd63-110">Configure the printable formats of required documents in **Print management**.</span></span>

<span data-ttu-id="ddd63-111">Essa funcionalidade é aplicável aos documentos a seguir.</span><span class="sxs-lookup"><span data-stu-id="ddd63-111">This functionality is applicable to the following documents.</span></span>

<span data-ttu-id="ddd63-112">**Contas a receber**</span><span class="sxs-lookup"><span data-stu-id="ddd63-112">**Accounts receivable**</span></span>
- <span data-ttu-id="ddd63-113">Fatura de cliente</span><span class="sxs-lookup"><span data-stu-id="ddd63-113">Customer invoice</span></span>
- <span data-ttu-id="ddd63-114">Nota de crédito de clientes</span><span class="sxs-lookup"><span data-stu-id="ddd63-114">Customer credit note</span></span>
- <span data-ttu-id="ddd63-115">Fatura de texto livre</span><span class="sxs-lookup"><span data-stu-id="ddd63-115">Free text invoice</span></span>
- <span data-ttu-id="ddd63-116">Nota de crédito em texto livre</span><span class="sxs-lookup"><span data-stu-id="ddd63-116">Free text credit note</span></span>

<span data-ttu-id="ddd63-117">**Gerenciamento e contabilidade do projeto**</span><span class="sxs-lookup"><span data-stu-id="ddd63-117">**Project management and accounting**</span></span>
- <span data-ttu-id="ddd63-118">Fatura de projeto</span><span class="sxs-lookup"><span data-stu-id="ddd63-118">Project invoice</span></span>
- <span data-ttu-id="ddd63-119">Nota de crédito do projeto</span><span class="sxs-lookup"><span data-stu-id="ddd63-119">Project credit note</span></span>

## <a name="configure-customer-master-data"></a><span data-ttu-id="ddd63-120">Configurar dados mestres do cliente</span><span class="sxs-lookup"><span data-stu-id="ddd63-120">Configure customer master data</span></span>
<span data-ttu-id="ddd63-121">Conclua as etapas a seguir para configurar os dados do cliente e ativar a capacidade de salvar automaticamente as faturas impressas como anexos.</span><span class="sxs-lookup"><span data-stu-id="ddd63-121">Complete the following steps to configure customer data and turn on the ability to automatically save printed invoices as attachments.</span></span>

1. <span data-ttu-id="ddd63-122">Acesse **Contas recebíveis** > **Todos os clientes**.</span><span class="sxs-lookup"><span data-stu-id="ddd63-122">Go to **Accounts receivable** > **All customers**.</span></span> 
2. <span data-ttu-id="ddd63-123">Selecione um cliente e, na Guia Rápida **Fatura e entrega**, na seção **FATURA ELETRôNICA**, no campo **Anexo da fatura eletrônica**, selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="ddd63-123">Select a customer, and on the **Invoice and delivery** FastTab, in the **E-INVOCE** section, in the **eInvoice attachment** field, select **Yes**.</span></span>

## <a name="print-invoices"></a><span data-ttu-id="ddd63-124">Imprimir faturas</span><span class="sxs-lookup"><span data-stu-id="ddd63-124">Print invoices</span></span>
<span data-ttu-id="ddd63-125">Você pode lançar e imprimir qualquer fatura do projeto, de cliente e de texto livre para o cliente configurado no procedimento anterior.</span><span class="sxs-lookup"><span data-stu-id="ddd63-125">You can post and print any free text, customer, and project invoice or credit note for the customer configured in the previous procedure.</span></span>

<span data-ttu-id="ddd63-126">Abra a página **Anexos** da fatura impressa.</span><span class="sxs-lookup"><span data-stu-id="ddd63-126">Open the **Attachments** page for the printed invoice.</span></span> <span data-ttu-id="ddd63-127">Na Guia Rápida **Anexo**, no grupo de campos **Detalhes adicionais**, no campo **Número de hash do documento**, localize o número do hash armazenado calculado para a fatura impressa.</span><span class="sxs-lookup"><span data-stu-id="ddd63-127">On the **Attachment** FastTab, in the **Additional details** field group, in **Document hash number** field, find the stored hash number calculated for the printed invoice.</span></span>

![Número hash do anexo](media/attach-hash-num.jpg)

