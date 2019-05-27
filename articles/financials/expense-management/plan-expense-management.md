---
title: Configurar gerenciamento de despesas
description: Este artigo descreve as considerações e as decisões que você deve tomar durante o processo de planejamento, antes de configurar o gerenciamento de Despesa no Microsoft Dynamics 365 for Finance and Operations.
author: KimANelson
manager: AnnBe
ms.date: 08/29/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: GlobalCategory, ProjCategory, TrvLocations, TrvParameters, TrvPaymethod, TrvPerDiems
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 23001
ms.assetid: aa3fd14d-7e94-4603-985f-ca26d6f860ea
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ac9959a4ee66e52ead5050897403602e407ca10
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1570612"
---
# <a name="configure-expense-management"></a><span data-ttu-id="ad915-103">Configurar gerenciamento de despesas</span><span class="sxs-lookup"><span data-stu-id="ad915-103">Configure expense management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ad915-104">Este tópico descreve as considerações e as decisões que você deve tomar durante o processo de planejamento, antes de configurar o gerenciamento de Despesa no Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ad915-104">This topic describes the considerations and the decisions that you must make during the planning process before you configure Expense management in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="ad915-105">No gerenciamento de Despesa, é possível armazenar informações sobre métodos de pagamento, requisições de viagem, relatórios de despesas, políticas etc.</span><span class="sxs-lookup"><span data-stu-id="ad915-105">In Expense management, you can store information about payment methods, travel requisitions, expense reports, policies, and so on.</span></span>

<span data-ttu-id="ad915-106">Como muitas das decisões que você toma ao planejar sua configuração do gerenciamento de despesas são baseadas na hierarquia da sua organização e na estrutura financeira, você deve consultar os documentos de planejamento para essas áreas.</span><span class="sxs-lookup"><span data-stu-id="ad915-106">Because many of the decisions that you make when you plan your configuration for Expense management are based on your organization’s hierarchy and financial structure, you must refer to the planning documents for those areas.</span></span>

## <a name="intercompany-expenses"></a><span data-ttu-id="ad915-107">Despesas intercompanhia</span><span class="sxs-lookup"><span data-stu-id="ad915-107">Intercompany expenses</span></span>

<span data-ttu-id="ad915-108">Quando você habilita as despesas intercompanhia, você permite que as entidades legais e os funcionários incorram despesas em nome de outra entidade legal e coletem pagamentos da entidade legal de emprego dentro de sua organização.</span><span class="sxs-lookup"><span data-stu-id="ad915-108">When you enable intercompany expenses, you allow legal entities and employees to incur expenses on behalf of another legal entity, and collect payment from the legal entity of employment within your organization.</span></span> <span data-ttu-id="ad915-109">Por exemplo, um funcionário na entidade legal A conclui um projeto da entidade legal B e o projeto incorrem em despesas de viagem relacionadas.</span><span class="sxs-lookup"><span data-stu-id="ad915-109">For example, an employee in legal entity A completes a project for legal entity B, and the project incurs travel related expenses.</span></span> <span data-ttu-id="ad915-110">Se as despesas intercompanhia forem habilitadas, o funcionário poderá arquivar um relatório de despesa que lançará a despesa na entidade legal B e a despesa deverá então ser paga pela entidade legal A. Se sua organização não tiver várias entidades legais, você não terá que habilitar as despesas intercompanhias.</span><span class="sxs-lookup"><span data-stu-id="ad915-110">If intercompany expenses are enabled, the employee can then file an expense report that will post the expense to legal entity B, and the expense must then be paid by legal entity A. If your organization doesn’t have multiple legal entities, you don’t have to enable intercompany expenses.</span></span>

<span data-ttu-id="ad915-111">**Decisão:** Você deseja habilitar as despesas intercompanhia?</span><span class="sxs-lookup"><span data-stu-id="ad915-111">**Decision:** Do you want to enable intercompany expenses?</span></span>

## <a name="financial-management"></a><span data-ttu-id="ad915-112">Gerenciamento financeiro</span><span class="sxs-lookup"><span data-stu-id="ad915-112">Financial management</span></span>

<span data-ttu-id="ad915-113">O gerenciamento de despesas é integrado com o gerenciamento financeiro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="ad915-113">Expense management is tightly integrated with the financial management of your organization.</span></span> <span data-ttu-id="ad915-114">Muitas das configurações do gerenciamento de despesas serão baseadas nas decisões tomadas sobre as finanças da empresa.</span><span class="sxs-lookup"><span data-stu-id="ad915-114">Lots of your configuration for Expense management will be based on the decisions that you’ve made about your organization’s finances.</span></span> <span data-ttu-id="ad915-115">As seções a seguir descrevem as várias áreas que exigem o planejamento e as decisões com base nas decisões financeiras da organização e na orientação da equipe de liderança.</span><span class="sxs-lookup"><span data-stu-id="ad915-115">The following sections describe the various areas that require planning and decisions, based on your organization’s financial decisions and guidance from your leadership team.</span></span>

### <a name="per-diems"></a><span data-ttu-id="ad915-116">Diárias</span><span class="sxs-lookup"><span data-stu-id="ad915-116">Per diems</span></span>

<span data-ttu-id="ad915-117">Você deve definir as diárias de funcionário que sua organização fornece.</span><span class="sxs-lookup"><span data-stu-id="ad915-117">You must define the employee per diems that your organization provides.</span></span> <span data-ttu-id="ad915-118">Como as diárias normalmente são usadas para cobrir despesas como refeições, hospedagem, e outras despesas extraordinárias, você pode criar regras para as permissões de diária que sua organização oferece.</span><span class="sxs-lookup"><span data-stu-id="ad915-118">Because per diems are typically used to cover expenses such as meals, lodging, and other incidental expenses, you can create rules for the per diem allowances that your organization offers.</span></span> <span data-ttu-id="ad915-119">As taxas de diária podem ser baseadas na época do ano, no local de viagem ou em ambos.</span><span class="sxs-lookup"><span data-stu-id="ad915-119">per diem rates can be based on the time of year, the travel location, or both.</span></span> <span data-ttu-id="ad915-120">Quando você define uma regra de diária, você pode especificar que uma porcentagem da taxa de diária será retida se o trabalhador receber refeições ou serviços gratuitos.</span><span class="sxs-lookup"><span data-stu-id="ad915-120">When you define a per diem rule, you can specify that a percentage of the per diem rate will be withheld if a worker receives complimentary meals or services.</span></span> <span data-ttu-id="ad915-121">Você também pode definir as camadas de taxa de diária para definir o número mínimo e máximo de horas que a taxa de diária pode ser aplicada ao deslocamento do funcionário.</span><span class="sxs-lookup"><span data-stu-id="ad915-121">You can also define per diem rate tiers to set the minimum and maximum number of hours that the per diem rate can be applied to a worker’s travel.</span></span>

<span data-ttu-id="ad915-122">**Decisões:**</span><span class="sxs-lookup"><span data-stu-id="ad915-122">**Decisions:**</span></span>

- <span data-ttu-id="ad915-123">As regras de diária padrão para o primeiro e último dia:</span><span class="sxs-lookup"><span data-stu-id="ad915-123">Default per diem rules for the first and last days:</span></span>

    - <span data-ttu-id="ad915-124">Qual o número mínimo de horas que um funcionário pode reivindicar para um dia e ainda receber uma diária?</span><span class="sxs-lookup"><span data-stu-id="ad915-124">What is the minimum number of hours that an employee can claim for a day and still receive a per diem?</span></span>
    - <span data-ttu-id="ad915-125">Há uma redução no valor que é oferecido para refeições para o primeiro e o último dia?</span><span class="sxs-lookup"><span data-stu-id="ad915-125">Is there a reduction in the amount that is offered for meals for the first day and last day?</span></span> <span data-ttu-id="ad915-126">Se houver uma redução, qual é o percentual de redução?</span><span class="sxs-lookup"><span data-stu-id="ad915-126">If there is a reduction, what is the percentage of the reduction?</span></span>
    - <span data-ttu-id="ad915-127">Há uma redução no valor que é oferecido para hotel para o primeiro e o último dia?</span><span class="sxs-lookup"><span data-stu-id="ad915-127">Is there a reduction in the amount that is offered for a hotel for the first day and last day?</span></span> <span data-ttu-id="ad915-128">Se houver uma redução, qual é o percentual de redução?</span><span class="sxs-lookup"><span data-stu-id="ad915-128">If there is a reduction, what is the percentage of the reduction?</span></span>
    - <span data-ttu-id="ad915-129">Há uma redução no valor que é oferecido para outras despesas incorridas no primeiro e último dia?</span><span class="sxs-lookup"><span data-stu-id="ad915-129">Is there a reduction in the amount that is offered for other expenses that are incurred on the first day and last day?</span></span> <span data-ttu-id="ad915-130">Se houver uma redução, qual é o percentual de redução?</span><span class="sxs-lookup"><span data-stu-id="ad915-130">If there is a reduction, what is the percentage of the reduction?</span></span>

- <span data-ttu-id="ad915-131">Regras padrão de diária:</span><span class="sxs-lookup"><span data-stu-id="ad915-131">Default per diem rules:</span></span>

    - <span data-ttu-id="ad915-132">Há uma redução percentual na bonificação de diária para cada refeição se, por exemplo, a refeição for complementar?</span><span class="sxs-lookup"><span data-stu-id="ad915-132">Is there a percentage reduction in the per diem allowance for each meal if, for example, the meal is complimentary?</span></span> <span data-ttu-id="ad915-133">Se houver uma redução, qual é o percentual de redução para cada refeição?</span><span class="sxs-lookup"><span data-stu-id="ad915-133">If there is a reduction, what is the reduction percentage for each meal?</span></span>
    - <span data-ttu-id="ad915-134">A redução de refeição é calculada por dia, por viagem, ou por número de refeições por dia?</span><span class="sxs-lookup"><span data-stu-id="ad915-134">Is the meal reduction calculated per day, per trip, or by the number of meals per day?</span></span>
    - <span data-ttu-id="ad915-135">Os valores da diária devem ser arredondados de maneira regular ou arredondados?</span><span class="sxs-lookup"><span data-stu-id="ad915-135">Should per diem amounts be rounded in the regular manner or rounded up?</span></span>
    - <span data-ttu-id="ad915-136">As diárias são calculadas em um período de 24 horas ou em um dia do calendário?</span><span class="sxs-lookup"><span data-stu-id="ad915-136">Are per diems calculated on a 24-hour period or on a calendar day?</span></span>

- <span data-ttu-id="ad915-137">As regras de diária são baseadas em localização:</span><span class="sxs-lookup"><span data-stu-id="ad915-137">Per diem rules that are based on location:</span></span>

    - <span data-ttu-id="ad915-138">As taxas de diária variam de acordo com local?</span><span class="sxs-lookup"><span data-stu-id="ad915-138">Do per diem rates vary according to location?</span></span> <span data-ttu-id="ad915-139">Quais locais serão incluídos?</span><span class="sxs-lookup"><span data-stu-id="ad915-139">What locations are included?</span></span>
    - <span data-ttu-id="ad915-140">Se as taxas de diárias variam de acordo com o local, para cada local, qual valor de porcentagem será fornecido para os seguintes tipos de despesas:</span><span class="sxs-lookup"><span data-stu-id="ad915-140">If per diem rates vary according to location, for each location, what percentage amount is provided for the following types of expenses:</span></span>

        - <span data-ttu-id="ad915-141">Refeições</span><span class="sxs-lookup"><span data-stu-id="ad915-141">Meals</span></span>
        - <span data-ttu-id="ad915-142">Hotel</span><span class="sxs-lookup"><span data-stu-id="ad915-142">Hotel</span></span>
        - <span data-ttu-id="ad915-143">Outras despesas</span><span class="sxs-lookup"><span data-stu-id="ad915-143">Other expenses</span></span>

### <a name="expense-management-journals-and-accounts"></a><span data-ttu-id="ad915-144">Diários e contas de gerenciamento de despesa</span><span class="sxs-lookup"><span data-stu-id="ad915-144">Expense management journals and accounts</span></span>

<span data-ttu-id="ad915-145">O gerenciamento de despesas exige que você use vários diários e contas.</span><span class="sxs-lookup"><span data-stu-id="ad915-145">Expense management requires that you use multiple journals and accounts.</span></span> <span data-ttu-id="ad915-146">Você deve decidir se, por exemplo, a mesma conta será usada para adiantamentos de dinheiro e contestações de cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="ad915-146">You must decide, for example, whether the same account is used for cash advances and credit card disputes.</span></span>

<span data-ttu-id="ad915-147">**Decisões:**</span><span class="sxs-lookup"><span data-stu-id="ad915-147">**Decisions:**</span></span>

- <span data-ttu-id="ad915-148">Em qual diário-razão os relatórios de despesas aprovados são lançados?</span><span class="sxs-lookup"><span data-stu-id="ad915-148">Which ledger journal are approved expense reports posted to?</span></span>
- <span data-ttu-id="ad915-149">Qual conta é utilizada para adiantamentos de dinheiro?</span><span class="sxs-lookup"><span data-stu-id="ad915-149">Which account is used for cash advances?</span></span>
- <span data-ttu-id="ad915-150">Os adiantamentos de dinheiro devem ser lançados imediatamente?</span><span class="sxs-lookup"><span data-stu-id="ad915-150">Should cash advances be posted immediately?</span></span>

### <a name="payment-methods"></a><span data-ttu-id="ad915-151">Meios de pagamento</span><span class="sxs-lookup"><span data-stu-id="ad915-151">Payment methods</span></span>

<span data-ttu-id="ad915-152">Ao permitir que os funcionários incorram despesas em nome de sua empresa, você deve definir os métodos de pagamento que os funcionários têm permissão de usar.</span><span class="sxs-lookup"><span data-stu-id="ad915-152">When you allow employees to incur expenses on behalf of your business, you must define the payment methods that employees are allowed to use.</span></span> <span data-ttu-id="ad915-153">Por exemplo, você pode permitir que os funcionários usem dinheiro ou um cartão de crédito corporativo.</span><span class="sxs-lookup"><span data-stu-id="ad915-153">For example, you might allow employees to use cash or a corporate credit card.</span></span> <span data-ttu-id="ad915-154">Você também pode permitir que os funcionários usem cartões de crédito pessoais e, em seguida, reembolsá-los.</span><span class="sxs-lookup"><span data-stu-id="ad915-154">You might also allow employees to use personal credit cards, and then reimburse the employees.</span></span> <span data-ttu-id="ad915-155">É necessário realizar as seguintes alterações para cada método de pagamento que você permitir.</span><span class="sxs-lookup"><span data-stu-id="ad915-155">You must make the following decisions for each payment method that you allow.</span></span>

<span data-ttu-id="ad915-156">**Decisões:**</span><span class="sxs-lookup"><span data-stu-id="ad915-156">**Decisions:**</span></span>

- <span data-ttu-id="ad915-157">Quais métodos de pagamento são permitidos?</span><span class="sxs-lookup"><span data-stu-id="ad915-157">What payment methods are allowed?</span></span>
- <span data-ttu-id="ad915-158">Quem é o proprietário das despesas do método de pagamento?</span><span class="sxs-lookup"><span data-stu-id="ad915-158">Who owns the payment method expenses?</span></span>
- <span data-ttu-id="ad915-159">Há um tipo de contrapartida?</span><span class="sxs-lookup"><span data-stu-id="ad915-159">Is there an offset account type?</span></span> <span data-ttu-id="ad915-160">Se houver um tipo de contrapartida, que é isso?</span><span class="sxs-lookup"><span data-stu-id="ad915-160">If there is an offset account type, what is it?</span></span>
- <span data-ttu-id="ad915-161">Se houver uma contrapartida, que é a conta?</span><span class="sxs-lookup"><span data-stu-id="ad915-161">If there is an offset account, what is the account?</span></span>
- <span data-ttu-id="ad915-162">Se o método de pagamento for um cartão de crédito, o método de pagamento deverá ser usado somente em transações importadas?</span><span class="sxs-lookup"><span data-stu-id="ad915-162">If the payment method is a credit card, should the payment method be used only with imported transactions?</span></span>

### <a name="expense-categories-and-shared-categories"></a><span data-ttu-id="ad915-163">Categorias de despesa e categorias compartilhadas</span><span class="sxs-lookup"><span data-stu-id="ad915-163">Expense categories and shared categories</span></span>

<span data-ttu-id="ad915-164">Quando os funcionários criam um relatório de despesas, cada despesa que eles registram deve estar associada a uma categoria de despesa.</span><span class="sxs-lookup"><span data-stu-id="ad915-164">When employees create an expense report, each expense that they record must be associated with an expense category.</span></span> <span data-ttu-id="ad915-165">As categorias de despesa são derivadas de categorias compartilhadas que podem ser compartilhadas entre as entidades legais na sua organização.</span><span class="sxs-lookup"><span data-stu-id="ad915-165">Expense categories are derived from shared categories that can be shared across the legal entities in your organization.</span></span> <span data-ttu-id="ad915-166">Essas categorias também podem ser compartilhadas no gerenciamento de projetos e na contabilidade do jeito que sua organização está definida.</span><span class="sxs-lookup"><span data-stu-id="ad915-166">These categories can also be shared in Project management and accounting, depending on the way that your organization is defined.</span></span> <span data-ttu-id="ad915-167">Baseado na definição da organização e na orientação da equipe de implementação, determine se as categorias usadas no gerenciamento de despesas devem serão usadas somente no gerenciamento de despesas ou se devem ser compartilhadas entre o gerenciamento de projetos e na contabilidade e o gerenciamento de despesas.</span><span class="sxs-lookup"><span data-stu-id="ad915-167">Based on the definition of your organization and guidance from the implementation team, determine whether the categories that are used in Expense management will be used only in Expense management, or whether they should be shared between Project management and accounting and Expense management.</span></span> <span data-ttu-id="ad915-168">Observe que essas categorias podem ser compartilhadas entre projeto e despesa ou projeto e produção, mas não entre despesa e produção.</span><span class="sxs-lookup"><span data-stu-id="ad915-168">Note that these categories can be shared between Project and Expense or Project and Production, but not between Expense and Production.</span></span> <span data-ttu-id="ad915-169">Você deve realizar as seguintes alterações para cada categoria de despesa.</span><span class="sxs-lookup"><span data-stu-id="ad915-169">You must make the following decisions for each expense category.</span></span>

<span data-ttu-id="ad915-170">**Decisões:**</span><span class="sxs-lookup"><span data-stu-id="ad915-170">**Decisions:**</span></span>

- <span data-ttu-id="ad915-171">Qual é a categoria de despesa?</span><span class="sxs-lookup"><span data-stu-id="ad915-171">What is the expense category?</span></span> <span data-ttu-id="ad915-172">Exemplos incluem categorias para voos, hotel ou quilometragem.</span><span class="sxs-lookup"><span data-stu-id="ad915-172">Examples include categories for flights, hotel, or mileage.</span></span>
- <span data-ttu-id="ad915-173">Essa categoria de despesa também pode ser usada no gerenciamento de projeto e contabilidade?</span><span class="sxs-lookup"><span data-stu-id="ad915-173">Can the expense category also be used in Project management and accounting?</span></span>
- <span data-ttu-id="ad915-174">Qual é o tipo de despesa?</span><span class="sxs-lookup"><span data-stu-id="ad915-174">What is the expense type?</span></span>
- <span data-ttu-id="ad915-175">Qual é o método de pagamento padrão da categoria de despesa?</span><span class="sxs-lookup"><span data-stu-id="ad915-175">What is the default payment method for the expense category?</span></span>
- <span data-ttu-id="ad915-176">As despesas na categoria de despesas devem ser especificadas?</span><span class="sxs-lookup"><span data-stu-id="ad915-176">Do expenses in the expense category have to be itemized?</span></span>
- <span data-ttu-id="ad915-177">Qual é a conta padrão principal para a categoria de despesa?</span><span class="sxs-lookup"><span data-stu-id="ad915-177">What is the main default account for the expense category?</span></span>
- <span data-ttu-id="ad915-178">Qual é o grupo padrão de imposto sobre vendas de item para a categoria de despesa?</span><span class="sxs-lookup"><span data-stu-id="ad915-178">What is the default item sales tax group for the expense category?</span></span>
- <span data-ttu-id="ad915-179">São permitidos métodos de pagamento adicionais para a categoria de despesa?</span><span class="sxs-lookup"><span data-stu-id="ad915-179">Are additional payment methods allowed for the expense category?</span></span> <span data-ttu-id="ad915-180">Se os métodos de pagamento adicionais são permitidos, o que são eles?</span><span class="sxs-lookup"><span data-stu-id="ad915-180">If additional payment methods are allowed, what are they?</span></span>
- <span data-ttu-id="ad915-181">Há subcategorias dentro dessa categoria de despesa?</span><span class="sxs-lookup"><span data-stu-id="ad915-181">Are there subcategories in this expense category?</span></span> <span data-ttu-id="ad915-182">Se houver subcategorias, você também deve tomar as seguintes decisões:</span><span class="sxs-lookup"><span data-stu-id="ad915-182">If there are subcategories, you must also make the following decisions:</span></span>

    - <span data-ttu-id="ad915-183">Algumas das subcategorias são excluídas da restituição de imposto?</span><span class="sxs-lookup"><span data-stu-id="ad915-183">Are any of the subcategories excluded from tax recovery?</span></span>
    - <span data-ttu-id="ad915-184">Qual é o grupo de imposto sobre vendas de item das subcategorias?</span><span class="sxs-lookup"><span data-stu-id="ad915-184">What is the item sales tax group of the subcategories?</span></span>

<span data-ttu-id="ad915-185">Se a categoria de despesa também for usada no gerenciamento de projetos e na contabilidade, responda às perguntas restantes.</span><span class="sxs-lookup"><span data-stu-id="ad915-185">If the expense category is also used in Project management and accounting, answer the remaining questions.</span></span> <span data-ttu-id="ad915-186">Caso contrário, vá para a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="ad915-186">Otherwise, move on to the next section.</span></span>

- <span data-ttu-id="ad915-187">Quais contas de custo serão usadas para a seguinte despesa?</span><span class="sxs-lookup"><span data-stu-id="ad915-187">Which cost accounts will be used for the following expenses?</span></span>

    - <span data-ttu-id="ad915-188">Custo</span><span class="sxs-lookup"><span data-stu-id="ad915-188">Cost</span></span>
    - <span data-ttu-id="ad915-189">Alocação de folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="ad915-189">Payroll allocation</span></span>
    - <span data-ttu-id="ad915-190">WIP - Valor de custo</span><span class="sxs-lookup"><span data-stu-id="ad915-190">WIP-cost value</span></span>
    - <span data-ttu-id="ad915-191">Custo de item</span><span class="sxs-lookup"><span data-stu-id="ad915-191">Cost-item</span></span>
    - <span data-ttu-id="ad915-192">WIP - Valor de custo - Item</span><span class="sxs-lookup"><span data-stu-id="ad915-192">WIP-cost value-item</span></span>
    - <span data-ttu-id="ad915-193">Perda acumulada</span><span class="sxs-lookup"><span data-stu-id="ad915-193">Accrued loss</span></span>
    - <span data-ttu-id="ad915-194">WIP - Perda acumulada</span><span class="sxs-lookup"><span data-stu-id="ad915-194">WIP-accrued loss</span></span>

- <span data-ttu-id="ad915-195">Quais contas de receita serão usadas para o seguinte?</span><span class="sxs-lookup"><span data-stu-id="ad915-195">Which revenue accounts will be used for the following?</span></span>

    - <span data-ttu-id="ad915-196">Receita faturada</span><span class="sxs-lookup"><span data-stu-id="ad915-196">Invoiced revenue</span></span>
    - <span data-ttu-id="ad915-197">Receita acumulada - valor de venda</span><span class="sxs-lookup"><span data-stu-id="ad915-197">Accrued revenue-sales value</span></span>
    - <span data-ttu-id="ad915-198">WIP - Valor de venda</span><span class="sxs-lookup"><span data-stu-id="ad915-198">WIP-sales value</span></span>
    - <span data-ttu-id="ad915-199">Receita acumulada - Produção</span><span class="sxs-lookup"><span data-stu-id="ad915-199">Accrued revenue-production</span></span>
    - <span data-ttu-id="ad915-200">WIP - Produção</span><span class="sxs-lookup"><span data-stu-id="ad915-200">WIP-production</span></span>
    - <span data-ttu-id="ad915-201">Receita acumulada - Lucro</span><span class="sxs-lookup"><span data-stu-id="ad915-201">Accrued revenue-profit</span></span>
    - <span data-ttu-id="ad915-202">WIP - Lucro</span><span class="sxs-lookup"><span data-stu-id="ad915-202">WIP-profit</span></span>
    - <span data-ttu-id="ad915-203">Receita acumulada - Subscrição</span><span class="sxs-lookup"><span data-stu-id="ad915-203">Accrued revenue-subscription</span></span>
    - <span data-ttu-id="ad915-204">WIP - Subscrição</span><span class="sxs-lookup"><span data-stu-id="ad915-204">WIP-subscription</span></span>

### <a name="taxes"></a><span data-ttu-id="ad915-205">Impostos</span><span class="sxs-lookup"><span data-stu-id="ad915-205">Taxes</span></span>

<span data-ttu-id="ad915-206">Para impostos relacionados a despesas, você deve determinar o que é incluído ou habilitado em relatórios de despesas.</span><span class="sxs-lookup"><span data-stu-id="ad915-206">For expense-related taxes, you must determine what is included or enabled on expense reports.</span></span>

<span data-ttu-id="ad915-207">**Decisões:**</span><span class="sxs-lookup"><span data-stu-id="ad915-207">**Decisions:**</span></span>

- <span data-ttu-id="ad915-208">O imposto sobre vendas está incluso nos valores de despesa?</span><span class="sxs-lookup"><span data-stu-id="ad915-208">Is sales tax included in the expense amounts?</span></span>
- <span data-ttu-id="ad915-209">A restituição de imposto deve ser habilitada nas despesas?</span><span class="sxs-lookup"><span data-stu-id="ad915-209">Should tax recovery be enabled on expenses?</span></span>

    > [!NOTE]
    > <span data-ttu-id="ad915-210">Quando estiver planejando a contabilidade, se optar por aplicar o imposto dos EUA e usar as regras de imposto, você não pode habilitar a restituição de imposto nas despesas.</span><span class="sxs-lookup"><span data-stu-id="ad915-210">When you were planning the general ledger, if you decided to apply U.S. sales tax and use tax rules, you can’t enable tax recovery on expenses.</span></span> <span data-ttu-id="ad915-211">(Para aplicar as regras de imposto e de imposto dos EUA, defina a opção **Aplicar regras de tributação de imposto** como **Sim**.)</span><span class="sxs-lookup"><span data-stu-id="ad915-211">(To apply U.S. sales tax and use tax rules, set the **Apply sales tax taxations rules** option to **Yes**.)</span></span>

## <a name="policies"></a><span data-ttu-id="ad915-212">Políticas</span><span class="sxs-lookup"><span data-stu-id="ad915-212">Policies</span></span>

<span data-ttu-id="ad915-213">Criando políticas do relatório de despesa, você pode ajudar sua organização a economizar tempo e dinheiro quando os funcionários arcarem com despesas em seu nome.</span><span class="sxs-lookup"><span data-stu-id="ad915-213">By creating expense report policies, you can help your organization save time and money when employees incur expenses on its behalf.</span></span> <span data-ttu-id="ad915-214">As políticas ajudam a garantir que os funcionários fiquem no orçamento, forneçam todas as informações necessárias e apenas gastem o dinheiro, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="ad915-214">Policies help guarantee that employees stay in budget, provide all required information, and spend money only as they require it.</span></span> <span data-ttu-id="ad915-215">Você deve tomar as decisões a seguir para cada política de relatório de despesas e cada política de aprovação de relatório de despesas que você criar.</span><span class="sxs-lookup"><span data-stu-id="ad915-215">You must make the following decisions for each expense report policy and each expense report approval policy that you create.</span></span>

<span data-ttu-id="ad915-216">**Decisões:**</span><span class="sxs-lookup"><span data-stu-id="ad915-216">**Decisions:**</span></span>

- <span data-ttu-id="ad915-217">Qual é o nome da política?</span><span class="sxs-lookup"><span data-stu-id="ad915-217">What is the name of the policy?</span></span>
- <span data-ttu-id="ad915-218">A que se destina a política de despesa?</span><span class="sxs-lookup"><span data-stu-id="ad915-218">What is the expense policy for?</span></span>
- <span data-ttu-id="ad915-219">Se você decidiu anteriormente habilitar as despesas intercompanhia, a quais empresas de sua organização essa política se aplica?</span><span class="sxs-lookup"><span data-stu-id="ad915-219">If you previously decided to enable intercompany expenses, which companies in your organization will this policy apply to?</span></span>
- <span data-ttu-id="ad915-220">Quando a política entra em vigor?</span><span class="sxs-lookup"><span data-stu-id="ad915-220">When does the policy become effective?</span></span>
- <span data-ttu-id="ad915-221">Quando a política expira?</span><span class="sxs-lookup"><span data-stu-id="ad915-221">When does the policy expire?</span></span>
- <span data-ttu-id="ad915-222">Qual é a regra de política?</span><span class="sxs-lookup"><span data-stu-id="ad915-222">What is the policy rule?</span></span>
- <span data-ttu-id="ad915-223">Qual é o resultado da regra de política?</span><span class="sxs-lookup"><span data-stu-id="ad915-223">What is the outcome of the policy rule?</span></span>
