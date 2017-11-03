---
title: "Processamento do diário geral"
description: "Este artigo descreve os recursos do Microsoft Dynamics 365 for Finance and Operations, edição Enterprise que podem ajudar a facilitar o processamento de diário geral, bem como ajudar a garantir que os dados corretos sejam capturados e o controle interno não esteja comprometido."
author: twheeloc
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 76386f7ab8033075f9db4cadc697f3a2a997163e
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="general-journal-processing"></a><span data-ttu-id="595f2-103">Processamento do diário geral</span><span class="sxs-lookup"><span data-stu-id="595f2-103">General journal processing</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="595f2-104">Este artigo descreve os recursos do Microsoft Dynamics 365 for Finance and Operations, edição Enterprise que podem ajudar a facilitar o processamento de diário geral, bem como ajudar a garantir que os dados corretos sejam capturados e o controle interno não esteja comprometido.</span><span class="sxs-lookup"><span data-stu-id="595f2-104">This articles describes capabilities in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition that can help make general journal processing easier, and that can also help guarantee that correct data is captured and internal control isn't compromised.</span></span>  

<span data-ttu-id="595f2-105">Nomes de diário</span><span class="sxs-lookup"><span data-stu-id="595f2-105">Journal names</span></span>

<span data-ttu-id="595f2-106">Uma das áreas mais importantes para a configuração é nomes de diário.</span><span class="sxs-lookup"><span data-stu-id="595f2-106">One of the most important areas to set up is journal names.</span></span> <span data-ttu-id="595f2-107">Convém definir nomes do diário específicos para cada objetivo, como ajuste intercompanhia, acumulado e correção de erro.</span><span class="sxs-lookup"><span data-stu-id="595f2-107">It's a good idea to define specific journal names for each purpose, such as intercompany, accrual adjustment, and error correction.</span></span> <span data-ttu-id="595f2-108">Você pode personalizar cada nome de diário para ajudar a tornar a entrada de dados fácil e segura para cada objetivo.</span><span class="sxs-lookup"><span data-stu-id="595f2-108">You can tailor each journal name to help make data entry for each purpose easy and secure.</span></span> 

<span data-ttu-id="595f2-109">Na página **Nomes de diário**, você pode configurar os seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="595f2-109">On the **Journal names** page, you can set up the following elements:</span></span>

-   <span data-ttu-id="595f2-110">**Aprovação do fluxo de trabalho** – Para aumentar o controle interno, defina fluxos de trabalho do diário que estabeleçam limites de materialidade para as etapas de análise e aprovação, com base em critérios como o valor de débito total.</span><span class="sxs-lookup"><span data-stu-id="595f2-110">**Workflow approval** – To increase internal control, define journal workflows that establish materiality limits for review and approval steps, based on criteria such as total debit amount.</span></span> <span data-ttu-id="595f2-111">Você configura fluxos de trabalho para os diários gerais na página **Fluxos de trabalho de contabilidade**.</span><span class="sxs-lookup"><span data-stu-id="595f2-111">You set up workflows for the general journals on the** General ledger workflows** page.</span></span>
-   <span data-ttu-id="595f2-112">**Valores padrão** – Selecione valores padrão para contrapartidas, moeda e dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="595f2-112">**Default values** – Select default values for offset accounts, currency, and financial dimensions.</span></span>
-   <span data-ttu-id="595f2-113">**Controle de diário** – Você pode configurar restrições da empresa e o tipo de conta, e também os valores do segmento.</span><span class="sxs-lookup"><span data-stu-id="595f2-113">**Journal control** – You can set up restrictions on the company and account type, and also the segment values.</span></span> 

<span data-ttu-id="595f2-114">**Exemplos**</span><span class="sxs-lookup"><span data-stu-id="595f2-114">**Examples**</span></span>

<span data-ttu-id="595f2-115">Um nome de diário pode ser usado somente para ajustes.</span><span class="sxs-lookup"><span data-stu-id="595f2-115">A journal name can be used only for adjustments.</span></span> <span data-ttu-id="595f2-116">Nesse caso, você pode especificar qual apenas o tipo de conta **Razão** é válido em todas as empresas.</span><span class="sxs-lookup"><span data-stu-id="595f2-116">In this case, you can specify that only the **Ledger** account type is valid across all companies.</span></span> <span data-ttu-id="595f2-117">[![Tipos de contas de controle de diário](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)</span><span class="sxs-lookup"><span data-stu-id="595f2-117">[![Journal control account types](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)</span></span>

<span data-ttu-id="595f2-118">Um nome de diário pode ser usado somente para um segmento específico ou para um intervalo de contas principais.</span><span class="sxs-lookup"><span data-stu-id="595f2-118">A journal name can be used only for a specific segment or for a range for main accounts.</span></span> <span data-ttu-id="595f2-119">[![Segmento de controle de diário](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)</span><span class="sxs-lookup"><span data-stu-id="595f2-119">[![Journal control segment](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)</span></span>

<span data-ttu-id="595f2-120">A opção **Estorno automático** está disponível em diários gerais.</span><span class="sxs-lookup"><span data-stu-id="595f2-120">The **Automatic reversal** option is available in general journals.</span></span> <span data-ttu-id="595f2-121">Por exemplo, você tem um ajuste de competência em que o documento real ainda não foi processado, conforme mostrado na ilustração.</span><span class="sxs-lookup"><span data-stu-id="595f2-121">For example, you have an accrual adjustment where the actual document hasn't yet been processed, as shown in the following illustration.</span></span>
<span data-ttu-id="595f2-122">[![Processamento do Diário geral](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png)</span><span class="sxs-lookup"><span data-stu-id="595f2-122">[![General journal reversing](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png)</span></span> 

<span data-ttu-id="595f2-123">O suplemento do Microsoft Excel para a entrada de diário fornece um nível adicional de automação e facilita a entrada de dados.</span><span class="sxs-lookup"><span data-stu-id="595f2-123">The Microsoft Excel add-in for journal entry provides an additional level of automation and makes data entry easier.</span></span> <span data-ttu-id="595f2-124">A ação **Abrir linhas no Excel** está disponível nas páginas **Diário geral** e **Comprovante de diário**.</span><span class="sxs-lookup"><span data-stu-id="595f2-124">The **Open lines in Excel** action is available on the **General journal** and **Journal voucher** pages.</span></span> 

<span data-ttu-id="595f2-125">Na página **Diários periódicos**, você pode configurar diários de devolução para automatizar o processamento do diário.</span><span class="sxs-lookup"><span data-stu-id="595f2-125">On the **Periodic journals** page, you can set up recurring journals to automate journal processing.</span></span> 

<span data-ttu-id="595f2-126">Você pode usar modelos de comprovante a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="595f2-126">You can use voucher templates at any time.</span></span> <span data-ttu-id="595f2-127">Na página **Diários gerais**, as ações **Salvar** e **Selecionar modelo de comprovante** estão na página **Comprovante de diário**, em **Funções** para as linhas do comprovante.</span><span class="sxs-lookup"><span data-stu-id="595f2-127">On the **General journals** page, the **Save** and **Select voucher template** actions are found on the **Journal voucher** page, under **Functions** for the voucher lines.</span></span>

## <a name="related-setup"></a><span data-ttu-id="595f2-128">Configuração relacionada</span><span class="sxs-lookup"><span data-stu-id="595f2-128">Related setup</span></span>
<span data-ttu-id="595f2-129">A configuração a seguir não é específica de diários gerais, mas ajudará a garantir que a entrada de dados seja fácil e com dados corretos.</span><span class="sxs-lookup"><span data-stu-id="595f2-129">The following setup isn't specific to general journals, but will help guarantee that data entry is correct data and easy.</span></span>

### <a name="main-account"></a><span data-ttu-id="595f2-130">Conta principal</span><span class="sxs-lookup"><span data-stu-id="595f2-130">Main account</span></span>

<span data-ttu-id="595f2-131">A configuração da conta principal fornece várias opções para o processamento do diário geral:</span><span class="sxs-lookup"><span data-stu-id="595f2-131">The main account setup provides many options for general journal processing:</span></span>

-   <span data-ttu-id="595f2-132">**Necessidade de DC/CR** – Use esta opção se uma conta principal for limitada a transações de débito ou de crédito.</span><span class="sxs-lookup"><span data-stu-id="595f2-132">**DC/CR requirement** – Use this option if a main account is limited to debit or credit transactions.</span></span> <span data-ttu-id="595f2-133">A configuração é verificada quando um diário é validado ou lançado.</span><span class="sxs-lookup"><span data-stu-id="595f2-133">The setup is verified when a journal is validated or posted.</span></span>
-   <span data-ttu-id="595f2-134">**Contrapartida padrão**</span><span class="sxs-lookup"><span data-stu-id="595f2-134">**Default offset account**</span></span>
-   <span data-ttu-id="595f2-135">**Suspenso** – Suspender um conta principal para a entrada de dados em todas as empresas ou para uma empresa específica/entidades legais.</span><span class="sxs-lookup"><span data-stu-id="595f2-135">**Suspended** – Suspend a main account for data entry across all companies or for a specific company/legal entities.</span></span>
-   <span data-ttu-id="595f2-136">**Não permitir entrada manual** – Impedir que usuários insiram manualmente um valor para a conta em diários.</span><span class="sxs-lookup"><span data-stu-id="595f2-136">**Do not allow manual entry** – Prevent users from manually entering a value for the account in journals.</span></span>
-   <span data-ttu-id="595f2-137">**Padrão/Validar moeda**</span><span class="sxs-lookup"><span data-stu-id="595f2-137">**Default/Validate currency**</span></span>
-   <span data-ttu-id="595f2-138">**Substituição da entidade legal** – Esta configuração é específica da empresa/entidade legal definida:</span><span class="sxs-lookup"><span data-stu-id="595f2-138">**Legal entity override** – This setup is specific to the defined company/legal entity:</span></span>
    -   <span data-ttu-id="595f2-139">**Padrão/Validar imposto**</span><span class="sxs-lookup"><span data-stu-id="595f2-139">**Default/Validate sales tax**</span></span>
    -   <span data-ttu-id="595f2-140">**Dimensão padrão** – **Não fixo** ou **Valor fixo**.</span><span class="sxs-lookup"><span data-stu-id="595f2-140">**Default dimension** – **Not fixed** or **Fixed value**.</span></span> <span data-ttu-id="595f2-141">**Valor fixo** ajudará a garantir que todas as postagens para esta conta principal usem sempre um valor de dimensão configurado como **Fixo**.</span><span class="sxs-lookup"><span data-stu-id="595f2-141">**Fixed value** will help guarantee that all postings for this main account always use any dimension value that is set up as **Fixed**.</span></span>
-   <span data-ttu-id="595f2-142">**Validação de lançamento**</span><span class="sxs-lookup"><span data-stu-id="595f2-142">**Posting validation**</span></span>
    -   <span data-ttu-id="595f2-143">**Validação do usuário** – Esta opção controla quais usuários têm permissão para lançar em uma conta principal.</span><span class="sxs-lookup"><span data-stu-id="595f2-143">**User validation** – This option controls which users are allowed to post to a main account.</span></span>
    -   <span data-ttu-id="595f2-144">**Validação de tipo de lançamento** – Esta opção controla os tipos de lançamento com permissão para uma conta principal.</span><span class="sxs-lookup"><span data-stu-id="595f2-144">**Posting type validation** – This option controls which posting types are allowed for a main account.</span></span>

### <a name="accounting-structures-and-advanced-rules-structures"></a><span data-ttu-id="595f2-145">Estruturas de contabilidade e estruturas de regras avançadas</span><span class="sxs-lookup"><span data-stu-id="595f2-145">Accounting structures and advanced rules structures</span></span>

<span data-ttu-id="595f2-146">As estruturas de contabilidade e as estruturas de regras avançadas são muito importantes para garantir que os dados necessários para relatórios financeiros e rastreamento de desempenho sejam capturados durante o processamento do diário geral e em qualquer outra documentação.</span><span class="sxs-lookup"><span data-stu-id="595f2-146">Accounting structures and advanced rules structures are extremely important for guaranteeing that the data that is required for financial reporting and performance tracking is captured during general journal processing and any documentation.</span></span> <span data-ttu-id="595f2-147">As estruturas de contabilidade e as estruturas de regras avançadas permitem personalizar a experiência da entrada de dados.</span><span class="sxs-lookup"><span data-stu-id="595f2-147">Accounting structures and advanced rules structures let you tailor the data entry experience.</span></span> <span data-ttu-id="595f2-148">Você pode permitir a entrada de dados somente para as dimensões financeiras que são relevantes para cada situação, e também pode forçar a exigência de captura de dados obrigatórios e corretos.</span><span class="sxs-lookup"><span data-stu-id="595f2-148">You can allow data entry only for financial dimensions that are relevant in each situation, and can also enforce the requirement that mandatory and correct data always be captured.</span></span>

<span data-ttu-id="595f2-149">Para obter mais informações, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="595f2-149">For more information, see the following topics:</span></span>
- <span data-ttu-id="595f2-150">[Planejamento: plano de contas](plan-chart-of-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="595f2-150">[Planning: Chart of accounts](plan-chart-of-accounts.md).</span></span> 
- [<span data-ttu-id="595f2-151">Criar regras avançadas para diários</span><span class="sxs-lookup"><span data-stu-id="595f2-151">Create advanced rules for journals</span></span>](tasks/create-advanced-rules-journals.md)
- [<span data-ttu-id="595f2-152">Criar uma entrada de diário usando um modelo</span><span class="sxs-lookup"><span data-stu-id="595f2-152">Create a journal entry using a template</span></span>](tasks/create-journal-entry-template.md)
- [<span data-ttu-id="595f2-153">Criar e validar diários</span><span class="sxs-lookup"><span data-stu-id="595f2-153">Create and validate journals</span></span>](tasks/create-validate-journals.md)
- [<span data-ttu-id="595f2-154">Lançar diários periódicos</span><span class="sxs-lookup"><span data-stu-id="595f2-154">Post periodic journals</span></span>](tasks/post-periodic-journals.md)
- [<span data-ttu-id="595f2-155">Processar diário de alocação do razão</span><span class="sxs-lookup"><span data-stu-id="595f2-155">Process ledger allocation journal</span></span>](tasks/process-ledger-allocation-journal.md)



