---
title: "Sequências numéricas"
description: "As sequências numéricas são usadas para gerar identificadores exclusivos legíveis para registros de dados mestres e registros de transações que exigem identificadores."
author: MargoC
manager: AnnBe
ms.date: 08/17/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: NumberSequenceTableListPage, NumberSequenceConfiguration
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 15461
ms.assetid: 6e19bd1d-192b-4da2-8573-84f6e1ce98ef
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 58069d79f92ce015fe4b11b50fb3348722bca4f8
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="number-sequences"></a><span data-ttu-id="20773-103">Sequências numéricas</span><span class="sxs-lookup"><span data-stu-id="20773-103">Number sequences</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="20773-104">As sequências numéricas são usadas para gerar identificadores exclusivos legíveis para registros de dados mestres e registros de transações que exigem identificadores.</span><span class="sxs-lookup"><span data-stu-id="20773-104">Number sequences are used to generate readable, unique identifiers for master data records and transaction records that require identifiers.</span></span> <span data-ttu-id="20773-105">Um registro de dados mestres ou um registro de transação que exige um identificador é conhecido como *referência*.</span><span class="sxs-lookup"><span data-stu-id="20773-105">A master data record or transaction record that requires an identifier is referred to as a *reference*.</span></span>

<span data-ttu-id="20773-106">Antes de criar novos registros para referência, é necessário configurar uma sequência numérica e associá-la à referência.</span><span class="sxs-lookup"><span data-stu-id="20773-106">Before you can create new records for a reference, you must set up a number sequence and associate it with the reference.</span></span> <span data-ttu-id="20773-107">É recomendável usar as páginas em **Administração da organização** para configurar sequências numéricas.</span><span class="sxs-lookup"><span data-stu-id="20773-107">We recommend that you use the pages in **Organization administration** to set up number sequences.</span></span> <span data-ttu-id="20773-108">Se as configurações específicas do módulo forem necessárias, você poderá usar a página de parâmetros em um módulo para especificar as sequências numéricas para as referências no módulo.</span><span class="sxs-lookup"><span data-stu-id="20773-108">If module-specific settings are required, you can use the parameters page in a module to specify number sequences for the references in that module.</span></span> <span data-ttu-id="20773-109">Por exemplo, em **Contas a receber** e em **Contas a pagar**, você pode configurar grupos de sequências numéricas para alocar sequências numéricas específicas para clientes e fornecedores específicos.</span><span class="sxs-lookup"><span data-stu-id="20773-109">For example, in **Accounts receivable** and **Accounts payable**, you can set up number sequence groups to allocate specific number sequences to specific customers or vendors.</span></span> 

<span data-ttu-id="20773-110">Ao configurar uma sequência numérica, você deve especificar um escopo, que define que organização usará a sequência numérica.</span><span class="sxs-lookup"><span data-stu-id="20773-110">When you set up a number sequence, you must specify a scope, which defines which organization uses the number sequence.</span></span> <span data-ttu-id="20773-111">O escopo pode ser **Compartilhado**, **Empresa**, **Entidade legal** ou **Unidade operacional**.</span><span class="sxs-lookup"><span data-stu-id="20773-111">The scope can be **Shared**, **Company**, **Legal entity**, or **Operating unit**.</span></span> <span data-ttu-id="20773-112">Os escopos **Entidade legal** e **Empresa** também podem ser combinados com **Período de calendário fiscal** para criar sequências numéricas ainda mais específicas.</span><span class="sxs-lookup"><span data-stu-id="20773-112">**Legal entity** and **Company** scopes can be combined with **Fiscal calendar period** to create even more specific number sequences.</span></span> 

<span data-ttu-id="20773-113">Os formatos de sequências numéricas são compostos de segmentos.</span><span class="sxs-lookup"><span data-stu-id="20773-113">Number sequence formats consist of segments.</span></span> <span data-ttu-id="20773-114">As sequências numéricas com um escopo diferente de **Compartilhado** podem conter os segmentos que correspondem ao escopo.</span><span class="sxs-lookup"><span data-stu-id="20773-114">Number sequences with a scope other than **Shared** can contain segments that correspond to the scope.</span></span> <span data-ttu-id="20773-115">Por exemplo, uma sequência numérica com um escopo **Entidade legal** pode conter um segmento da entidade legal.</span><span class="sxs-lookup"><span data-stu-id="20773-115">For example, a number sequence with a scope of **Legal entity** can contain a legal entity segment.</span></span> <span data-ttu-id="20773-116">Ao incluir um segmento de escopo no formato de sequência numérica, você pode identificar o escopo de um registro específico examinando seu número.</span><span class="sxs-lookup"><span data-stu-id="20773-116">By including a scope segment in the number sequence format, you can identify the scope of a particular record by looking at its number.</span></span> 

<span data-ttu-id="20773-117">Além dos segmentos que correspondem a escopos, os formatos de sequências numéricas podem conter os segmentos **Constante** e **Alfanumérico**.</span><span class="sxs-lookup"><span data-stu-id="20773-117">In addition to segments that correspond to scopes, number sequence formats can contain **Constant** and **Alphanumeric segments**.</span></span> <span data-ttu-id="20773-118">Um segmento **Constante** contém um conjunto de letras, de números ou de símbolos que não muda.</span><span class="sxs-lookup"><span data-stu-id="20773-118">A **Constant** segment contains a set of letters, numbers, or symbols that does not change.</span></span> <span data-ttu-id="20773-119">Um segmento **Alfanumérico** contém um conjunto de letras ou de números incrementado sempre que um número é usado.</span><span class="sxs-lookup"><span data-stu-id="20773-119">An **Alphanumeric** segment contains a set of letters or numbers that increment every time that a number is used.</span></span> <span data-ttu-id="20773-120">Use um sinal numérico (\#) para representar o incremento de números e um e comercial (&) para representar o incremento de letras.</span><span class="sxs-lookup"><span data-stu-id="20773-120">Use a number sign (\#) to represent incrementing numbers and an ampersand (&) to represent incrementing letters.</span></span> <span data-ttu-id="20773-121">Por exemplo, o formato \#\#\#\#\#\_2017 cria a sequência 00001\_2017, 00002\_2017, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="20773-121">For example, the format \#\#\#\#\#\_2017 creates the sequence 00001\_2017, 00002\_2017, and so on.</span></span>

<a name="number-sequence-examples"></a><span data-ttu-id="20773-122">Exemplos de sequências numéricas</span><span class="sxs-lookup"><span data-stu-id="20773-122">Number sequence examples</span></span>
------------------------

<span data-ttu-id="20773-123">Os exemplos a seguir mostram como usar segmentos para criar formatos da sequência numérica.</span><span class="sxs-lookup"><span data-stu-id="20773-123">The following examples show how to use segments to create number sequence formats.</span></span> <span data-ttu-id="20773-124">Particularmente, os exemplos demonstram os efeitos de usar segmentos de escopo.</span><span class="sxs-lookup"><span data-stu-id="20773-124">In particular, the examples demonstrate the effects of using scope segments.</span></span>

### <a name="expense-report-numbers"></a><span data-ttu-id="20773-125">Números do relatório de despesas</span><span class="sxs-lookup"><span data-stu-id="20773-125">Expense report numbers</span></span>

<span data-ttu-id="20773-126">No exemplo a seguir, os números de relatório de despesas são configurados para a entidade legal chamada **CS**.</span><span class="sxs-lookup"><span data-stu-id="20773-126">In the following example, expense report numbers are set up for the legal entity that is titled **CS**.</span></span> 

- <span data-ttu-id="20773-127">**Área:** Viagem e despesas</span><span class="sxs-lookup"><span data-stu-id="20773-127">**Area:** Travel and expense</span></span> 
- <span data-ttu-id="20773-128">**Referência:** Número do relatório de despesas</span><span class="sxs-lookup"><span data-stu-id="20773-128">**Reference:** Expense report number</span></span> 
- <span data-ttu-id="20773-129">**Escopo:** Entidade legal</span><span class="sxs-lookup"><span data-stu-id="20773-129">**Scope:** Legal entity</span></span> 
- <span data-ttu-id="20773-130">**Entidade legal:** CS</span><span class="sxs-lookup"><span data-stu-id="20773-130">**Legal entity:** CS</span></span>

| <span data-ttu-id="20773-131">Segmentos</span><span class="sxs-lookup"><span data-stu-id="20773-131">Segments</span></span>  | <span data-ttu-id="20773-132">Tipo de segmento</span><span class="sxs-lookup"><span data-stu-id="20773-132">Segment type</span></span> | <span data-ttu-id="20773-133">Valor</span><span class="sxs-lookup"><span data-stu-id="20773-133">Value</span></span>     |
|-----------|--------------|-----------|
| <span data-ttu-id="20773-134">Segmento 1</span><span class="sxs-lookup"><span data-stu-id="20773-134">Segment 1</span></span> | <span data-ttu-id="20773-135">Pessoa jurídica em geral</span><span class="sxs-lookup"><span data-stu-id="20773-135">Legal entity</span></span> | <span data-ttu-id="20773-136">CS</span><span class="sxs-lookup"><span data-stu-id="20773-136">CS</span></span>        |
| <span data-ttu-id="20773-137">Segmento 2</span><span class="sxs-lookup"><span data-stu-id="20773-137">Segment 2</span></span> | <span data-ttu-id="20773-138">Constante</span><span class="sxs-lookup"><span data-stu-id="20773-138">Constant</span></span>     | <span data-ttu-id="20773-139">-DESPESA-</span><span class="sxs-lookup"><span data-stu-id="20773-139">-EXPENSE-</span></span> |
| <span data-ttu-id="20773-140">Segmento 3</span><span class="sxs-lookup"><span data-stu-id="20773-140">Segment 3</span></span> | <span data-ttu-id="20773-141">Alfanumérico</span><span class="sxs-lookup"><span data-stu-id="20773-141">Alphanumeric</span></span> | \#\#\#\#  |

<span data-ttu-id="20773-142">**Exemplo de número formatado**: CS-DESPESA-0039</span><span class="sxs-lookup"><span data-stu-id="20773-142">**Example of formatted number**: CS-EXPENSE-0039</span></span> 

<span data-ttu-id="20773-143">Você pode configurar um formato semelhante de sequência numérica para outras entidades legais.</span><span class="sxs-lookup"><span data-stu-id="20773-143">You can set up a similar number sequence format for other legal entities.</span></span> <span data-ttu-id="20773-144">Por exemplo, para uma entidade legal denominada **RW**, se você alterar somente o valor do segmento da entidade legal, o número formatado será RW-DESPESA-0039.</span><span class="sxs-lookup"><span data-stu-id="20773-144">For example, for a legal entity that is named **RW**, if you change only the value of the legal entity segment, the formatted number is RW-EXPENSE-0039.</span></span> <span data-ttu-id="20773-145">Você também pode alterar o formato de sequência numérica inteira para outras entidades legais.</span><span class="sxs-lookup"><span data-stu-id="20773-145">You can also change the whole number sequence format for other legal entities.</span></span> <span data-ttu-id="20773-146">Por exemplo, você pode omitir o segmento de escopo da entidade legal para criar um número formatado como Exp-0001.</span><span class="sxs-lookup"><span data-stu-id="20773-146">For example, you can omit the legal entity scope segment to create a formatted number such as Exp-0001.</span></span>

### <a name="sales-order-numbers"></a><span data-ttu-id="20773-147">Números da ordem de venda</span><span class="sxs-lookup"><span data-stu-id="20773-147">Sales order numbers</span></span>

<span data-ttu-id="20773-148">No exemplo a seguir, os números da ordem de venda são configurados para a ID da empresa **CEU**.</span><span class="sxs-lookup"><span data-stu-id="20773-148">In the following example, sales order numbers are set up for the company ID **CEU**.</span></span> 

- <span data-ttu-id="20773-149">**Área:** Vendas</span><span class="sxs-lookup"><span data-stu-id="20773-149">**Area:** Sales</span></span> 
- <span data-ttu-id="20773-150">**Referência:** Ordem de venda</span><span class="sxs-lookup"><span data-stu-id="20773-150">**Reference:** Sales order</span></span> 
- <span data-ttu-id="20773-151">**Escopo:** Empresa</span><span class="sxs-lookup"><span data-stu-id="20773-151">**Scope:** Company</span></span> 
- <span data-ttu-id="20773-152">**Empresa:** CEU</span><span class="sxs-lookup"><span data-stu-id="20773-152">**Company:** CEU</span></span>

| <span data-ttu-id="20773-153">Segmentos</span><span class="sxs-lookup"><span data-stu-id="20773-153">Segments</span></span>  | <span data-ttu-id="20773-154">Tipo de segmento</span><span class="sxs-lookup"><span data-stu-id="20773-154">Segment type</span></span> | <span data-ttu-id="20773-155">Alíquota</span><span class="sxs-lookup"><span data-stu-id="20773-155">Value</span></span>    |
|-----------|--------------|----------|
| <span data-ttu-id="20773-156">Segmento 1</span><span class="sxs-lookup"><span data-stu-id="20773-156">Segment 1</span></span> | <span data-ttu-id="20773-157">Constante</span><span class="sxs-lookup"><span data-stu-id="20773-157">Constant</span></span>     | <span data-ttu-id="20773-158">OV-</span><span class="sxs-lookup"><span data-stu-id="20773-158">SO-</span></span>      |
| <span data-ttu-id="20773-159">Segmento 2</span><span class="sxs-lookup"><span data-stu-id="20773-159">Segment 2</span></span> | <span data-ttu-id="20773-160">Alfanumérico</span><span class="sxs-lookup"><span data-stu-id="20773-160">Alphanumeric</span></span> | \#\#\#\# |

<span data-ttu-id="20773-161">**Exemplo de número formatado**: SO-0029</span><span class="sxs-lookup"><span data-stu-id="20773-161">**Example of formatted number**: SO-0029</span></span> 

<span data-ttu-id="20773-162">Mesmo que um segmento de escopo não seja incluído no formato, a numeração é reiniciada para cada ID da empresa</span><span class="sxs-lookup"><span data-stu-id="20773-162">Even though a scope segment is not included in the format, numbering restarts for each company ID.</span></span> <span data-ttu-id="20773-163">Se você usar o mesmo formato para todas as IDs da empresa, os mesmos números serão usados em cada empresa.</span><span class="sxs-lookup"><span data-stu-id="20773-163">If you use the same format for all company IDs, the same numbers are used in each company.</span></span> <span data-ttu-id="20773-164">Por exemplo, o número da ordem de venda SO-0029 é usado em cada empresa.</span><span class="sxs-lookup"><span data-stu-id="20773-164">For example, sales order number SO-0029 is used in each company.</span></span> <span data-ttu-id="20773-165">Você também pode alterar o formato de sequência numérica inteira para outras IDs da empresa.</span><span class="sxs-lookup"><span data-stu-id="20773-165">You can also change the whole number sequence format for other company IDs.</span></span>

### <a name="purchase-requisition-numbers"></a><span data-ttu-id="20773-166">Números de requisição de compra</span><span class="sxs-lookup"><span data-stu-id="20773-166">Purchase requisition numbers</span></span>

<span data-ttu-id="20773-167">No exemplo a seguir, os números de requisição de compra destinam-se à organização inteira.</span><span class="sxs-lookup"><span data-stu-id="20773-167">In the following example, purchase requisition numbers are organization-wide.</span></span> 

- <span data-ttu-id="20773-168">**Área:** Compra</span><span class="sxs-lookup"><span data-stu-id="20773-168">**Area:** Purchase</span></span> 
- <span data-ttu-id="20773-169">**Referência:** Requisição de compra</span><span class="sxs-lookup"><span data-stu-id="20773-169">**Reference:** Purchase requisition</span></span> 
- <span data-ttu-id="20773-170">**Escopo:** Compartilhado</span><span class="sxs-lookup"><span data-stu-id="20773-170">**Scope:** Shared</span></span>

| <span data-ttu-id="20773-171">Segmentos</span><span class="sxs-lookup"><span data-stu-id="20773-171">Segments</span></span>  | <span data-ttu-id="20773-172">Tipo de segmento</span><span class="sxs-lookup"><span data-stu-id="20773-172">Segment type</span></span> | <span data-ttu-id="20773-173">Alíquota</span><span class="sxs-lookup"><span data-stu-id="20773-173">Value</span></span>    |
|-----------|--------------|----------|
| <span data-ttu-id="20773-174">Segmento 1</span><span class="sxs-lookup"><span data-stu-id="20773-174">Segment 1</span></span> | <span data-ttu-id="20773-175">Constante</span><span class="sxs-lookup"><span data-stu-id="20773-175">Constant</span></span>     | <span data-ttu-id="20773-176">Solic.</span><span class="sxs-lookup"><span data-stu-id="20773-176">Req</span></span>      |
| <span data-ttu-id="20773-177">Segmento 2</span><span class="sxs-lookup"><span data-stu-id="20773-177">Segment 2</span></span> | <span data-ttu-id="20773-178">Alfanumérico</span><span class="sxs-lookup"><span data-stu-id="20773-178">Alphanumeric</span></span> | \#\#\#\# |

<span data-ttu-id="20773-179">**Exemplo de número formatado**: Req0052</span><span class="sxs-lookup"><span data-stu-id="20773-179">**Example of formatted number**: Req0052</span></span> 

<span data-ttu-id="20773-180">Como o escopo é **Compartilhado**, o formato da sequência numérica é usado na organização inteira.</span><span class="sxs-lookup"><span data-stu-id="20773-180">Because the scope is **Shared**, the number sequence format is used across the organization.</span></span> <span data-ttu-id="20773-181">Não é possível configurar formatos de sequência numérica para diferentes partes da organização.</span><span class="sxs-lookup"><span data-stu-id="20773-181">You cannot set up different number sequence formats for different parts of the organization.</span></span> 

<a name="performance-considerations-for-number-sequences"></a><span data-ttu-id="20773-182">Considerações de desempenho para sequências numéricas</span><span class="sxs-lookup"><span data-stu-id="20773-182">Performance considerations for number sequences</span></span>
-----------------------------------------------

<span data-ttu-id="20773-183">Considere as seguintes informações sobre como a configuração de sequências numéricas pode afetar o desempenho do sistema antes da configuração de sequências numéricas.</span><span class="sxs-lookup"><span data-stu-id="20773-183">Consider the following information about how the configuration of number sequences can affect system performance before you set up number sequences.</span></span>

### <a name="continuous-and-non-continuous-number-sequences"></a><span data-ttu-id="20773-184">Sequências numéricas contínuas e não contínuas</span><span class="sxs-lookup"><span data-stu-id="20773-184">Continuous and non-continuous number sequences</span></span>

<span data-ttu-id="20773-185">As sequências numéricas podem ser contínuas ou não contínuas.</span><span class="sxs-lookup"><span data-stu-id="20773-185">Number sequences can be continuous or non-continuous.</span></span> <span data-ttu-id="20773-186">Uma sequência numérica contínua não ignora nenhum número, mas os números podem não ser usados sequencialmente.</span><span class="sxs-lookup"><span data-stu-id="20773-186">A continuous number sequence does not skip any numbers, but numbers may not be used sequentially.</span></span> <span data-ttu-id="20773-187">Os números de uma sequência numérica não contínua são usados sequencialmente, mas a sequência numérica pode ignorar números.</span><span class="sxs-lookup"><span data-stu-id="20773-187">Numbers from a non-continuous number sequence are used sequentially, but the number sequence may skip numbers.</span></span> <span data-ttu-id="20773-188">Por exemplo, se um usuário cancela uma transação, um número é gerado, mas não usado.</span><span class="sxs-lookup"><span data-stu-id="20773-188">For example, if a user cancels a transaction, a number is generated, but not used.</span></span> <span data-ttu-id="20773-189">Em uma sequência numérica contínua, esse número é reciclado posteriormente.</span><span class="sxs-lookup"><span data-stu-id="20773-189">In a continuous number sequence, that number is recycled later.</span></span> <span data-ttu-id="20773-190">Em uma sequência numérica não contínua, o número não é usado.</span><span class="sxs-lookup"><span data-stu-id="20773-190">In a non-continuous number sequence, the number is not used.</span></span> 

<span data-ttu-id="20773-191">As sequências numéricas contínuas normalmente são necessárias em documentos externos, como ordens de compra, ordens de venda e faturas.</span><span class="sxs-lookup"><span data-stu-id="20773-191">Continuous number sequences are typically required for external documents, such as purchase orders, sales orders, and invoices.</span></span> <span data-ttu-id="20773-192">Entretanto, as sequências numéricas contínuas podem ter um impacto negativo no tempo de resposta do sistema porque o sistema deve solicitar um número do banco de dados sempre que um novo documento ou um registro for criado.</span><span class="sxs-lookup"><span data-stu-id="20773-192">However, continuous number sequences can adversely affect system response times because the system must request a number from the database every time that a new document or record is created.</span></span> 

<span data-ttu-id="20773-193">Se você usar uma sequência numérica não contínua, poderá habilitar **Pré-alocação** na Guia Rápida **Desempenho** da página **Sequências numéricas**.</span><span class="sxs-lookup"><span data-stu-id="20773-193">If you use a non-continuous number sequence, you can enable **Preallocation** on the **Performance** FastTab of the **Number sequences** page.</span></span> <span data-ttu-id="20773-194">Quando você especifica uma quantidade de números a serem pré-alocados, o sistema seleciona esses números e os armazena na memória.</span><span class="sxs-lookup"><span data-stu-id="20773-194">When you specify a quantity of numbers to preallocate, the system selects those numbers and stores them in memory.</span></span> <span data-ttu-id="20773-195">Os novos números serão solicitados do banco de dados somente depois que a quantidade pré-alocada tiver sido usada.</span><span class="sxs-lookup"><span data-stu-id="20773-195">New numbers are requested from the database only after the preallocated quantity has been used.</span></span> 

<span data-ttu-id="20773-196">A menos que haja um requisito de regulamentação para usar sequências numéricas contínuas, é recomendável usar sequências numéricas não contínuas para obter um desempenho melhor.</span><span class="sxs-lookup"><span data-stu-id="20773-196">Unless there is a regulatory requirement that you use continuous number sequences, we recommend that you use non-continuous number sequences for better performance.</span></span>

### <a name="automatic-cleanup-of-number-sequences"></a><span data-ttu-id="20773-197">Limpeza automática das sequências numéricas</span><span class="sxs-lookup"><span data-stu-id="20773-197">Automatic cleanup of number sequences</span></span>

<span data-ttu-id="20773-198">No caso de uma falha de energia, de um erro de aplicativo ou de outra falha inesperada, o sistema não pode reciclar números automaticamente para sequências numéricas contínuas.</span><span class="sxs-lookup"><span data-stu-id="20773-198">In case of a power failure, an application error, or other unexpected failure, the system cannot recycle numbers automatically for continuous number sequences.</span></span> <span data-ttu-id="20773-199">Você pode executar o processo de limpeza de forma manual ou automática para recuperar os números perdidos.</span><span class="sxs-lookup"><span data-stu-id="20773-199">You can run the cleanup process manually or automatically to recover the lost numbers.</span></span> 

<span data-ttu-id="20773-200">Considere cuidadosamente o uso do servidor ao planejar o processo de limpeza.</span><span class="sxs-lookup"><span data-stu-id="20773-200">Carefully consider server usage when you plan the cleanup process.</span></span> <span data-ttu-id="20773-201">Recomendamos que você execute a limpeza como um trabalho em lotes fora do horário de pico.</span><span class="sxs-lookup"><span data-stu-id="20773-201">We recommend that you perform the cleanup as a batch job during non-peak hours.</span></span>






