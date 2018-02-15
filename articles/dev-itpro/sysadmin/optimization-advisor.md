---
title: Criar regras para o Optimization advisor
description: "Este tópico discute como adicionar novas regras ao Optimization advisor."
author: roxanadiaconu
manager: AnnBe
ms.date: 01/23/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SelfHealingWorkspace
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core (Operations, Core)
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: roxanad
ms.search.validFrom: 2017-12-01
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: 9cb9343028acacc387370e1cdd2202b84919185e
ms.openlocfilehash: 88739298405343a36ae5bc11f51c666c414e7157
ms.contentlocale: pt-br
ms.lasthandoff: 01/23/2018

---

# <a name="create-rules-for-optimization-advisor"></a><span data-ttu-id="b1814-103">Criar regras para o Optimization advisor</span><span class="sxs-lookup"><span data-stu-id="b1814-103">Create rules for Optimization advisor</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="b1814-104">Este tópico explica como criar novas regras para o **Optimization advisor**.</span><span class="sxs-lookup"><span data-stu-id="b1814-104">This topic explains how to create new rules for **Optimization advisor**.</span></span> <span data-ttu-id="b1814-105">Por exemplo, você pode criar uma nova regra que identifique quais casos de solicitação de cotações (RFQ) possuem um título vazio.</span><span class="sxs-lookup"><span data-stu-id="b1814-105">For example, you can create a new rule that identifies which Request for Quotations (RFQ) cases have an empty title.</span></span> <span data-ttu-id="b1814-106">Usar títulos em casos facilita sua identificação e pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b1814-106">Using titles on cases makes them easily identifiable and searchable.</span></span> <span data-ttu-id="b1814-107">Embora relativamente simples, esse exemplo mostra o que pode ser obtido com regras de otimização.</span><span class="sxs-lookup"><span data-stu-id="b1814-107">While quite simple, this example shows what can be achieved with optimization rules.</span></span> 

<span data-ttu-id="b1814-108">Uma *regra* é uma verificação em dados de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b1814-108">A *rule* is a check on application data.</span></span> <span data-ttu-id="b1814-109">Se a condição que a regra avalia é atendida, oportunidades de otimizar processos ou melhorar dados são criadas.</span><span class="sxs-lookup"><span data-stu-id="b1814-109">If the condition that the rule evaluates is met, opportunities to optimize processes or improve data are created.</span></span> <span data-ttu-id="b1814-110">É possível agir em relação às oportunidades e, opcionalmente, o impacto das ações pode ser medido.</span><span class="sxs-lookup"><span data-stu-id="b1814-110">The opportunities can be acted upon and, optionally, the impact of the actions can be measured.</span></span> 

<span data-ttu-id="b1814-111">Para criar uma nova regra para o **Optimization advisor**, adicione uma nova classe que estenda a classe abstrata **SelfHealingRule**, implemente a interface **IDiagnosticsRule** e seja decorada pelo atributo **DiagnosticRule**.</span><span class="sxs-lookup"><span data-stu-id="b1814-111">To create a new rule for the **Optimization advisor**, add a new class that extends the **SelfHealingRule** abstract class, implements the **IDiagnosticsRule** interface, and is decorated by the **DiagnosticRule** attribute.</span></span> <span data-ttu-id="b1814-112">A classe também deve possuir um método decorado com o atributo **DiagnosticsRuleSubscription**.</span><span class="sxs-lookup"><span data-stu-id="b1814-112">The class must also have a method decorated with the **DiagnosticsRuleSubscription** attribute.</span></span> <span data-ttu-id="b1814-113">Por convenção, isso é feito no método **opportunityTitle**, que será discutido posteriormente.</span><span class="sxs-lookup"><span data-stu-id="b1814-113">By convention, that is done on the **opportunityTitle** method, which will be discussed later.</span></span> <span data-ttu-id="b1814-114">Essa nova classe pode ser adicionada a um modelo personalizado com uma dependência no modelo **SelfHealingRules**.</span><span class="sxs-lookup"><span data-stu-id="b1814-114">This new class can be added to a custom model with a dependency on the **SelfHealingRules** model.</span></span> <span data-ttu-id="b1814-115">No exemplo a seguir, a regra que está sendo implementada é chamada **RFQTitleSelfHealingRule**.</span><span class="sxs-lookup"><span data-stu-id="b1814-115">In the following example, the rule being implemented is called **RFQTitleSelfHealingRule**.</span></span>

```
[DiagnosticsRule] 
public final class RFQTitleSelfHealingRule extends SelfHealingRule implements IDiagnosticsRule 
{ 
… 
} 
```

<span data-ttu-id="b1814-116">A classe abstrata **SelfHealingRule** contém métodos abstratos que devem ser implementados em classes de herança.</span><span class="sxs-lookup"><span data-stu-id="b1814-116">The **SelfHealingRule** abstract class has abstract methods that must be implemented in inheriting classes.</span></span> <span data-ttu-id="b1814-117">O principal é o método **avaliar**, que retorna uma lista das oportunidades identificadas pela regra.</span><span class="sxs-lookup"><span data-stu-id="b1814-117">The core is the **evaluate** method, which returns a list of the opportunities identified by the rule.</span></span> <span data-ttu-id="b1814-118">As oportunidades podem ser por entidade legal ou podem ser aplicadas ao sistema inteiro.</span><span class="sxs-lookup"><span data-stu-id="b1814-118">Opportunities can be per legal entity or can apply to the whole system.</span></span>

```
protected List evaluate() 
{ 
    List results = new List(Types::Record); 
    
    DataArea dataArea; 

    while select id from dataArea 
        where !dataArea.isVirtual 
    { 
        changecompany(dataArea.id) 
        { 
            container result = this.findRFQCasesWithEmptyTitle(); 

            if (conLen(result) > 0) 
            { 
                SelfHealingOpportunity opportunity = this.getOpportunityForCompany(dataArea.Id); 
                opportunity.EvaluationState = SelfHealingEvaluationState::Evaluated; 
                opportunity.Data = result; 
                opportunity.OpportunityDate = DateTimeUtil::utcNow(); 
                
                results.addEnd(opportunity); 
            } 
        } 
    } 
    
    return results; 
} 
```

<span data-ttu-id="b1814-119">O método mostrado acima executa um loop sobre empresas e seleciona casos de RFQ com títulos vazios no método **findRFQCasesWithEmptyTitle**.</span><span class="sxs-lookup"><span data-stu-id="b1814-119">The method shown above loops over companies and selects RFQ cases with empty titles in the **findRFQCasesWithEmptyTitle** method.</span></span> <span data-ttu-id="b1814-120">Se pelo menos um caso do tipo for encontrado, então uma oportunidade específica a uma empresa é criada com o método **getOpportunityForCompany**.</span><span class="sxs-lookup"><span data-stu-id="b1814-120">If at least one such case is found, then a company-specific opportunity is created with the **getOpportunityForCompany** method.</span></span> <span data-ttu-id="b1814-121">Observe que o campo **Dados** na tabela **SelfHealingOpportunity** é do tipo **Contêiner** e, portanto, pode conter quaisquer dados relevantes para a lógica específica a esta regra.</span><span class="sxs-lookup"><span data-stu-id="b1814-121">Notice that the field **Data** in the **SelfHealingOpportunity** table is of type **Container**, and can therefore contain any data relevant to the logic specific to this rule.</span></span> <span data-ttu-id="b1814-122">A configuração de **OpportunityDate** com o carimbo de data/hora atual registra a hora da última avaliação da oportunidade.</span><span class="sxs-lookup"><span data-stu-id="b1814-122">Setting **OpportunityDate** with the current timestamp registers the time of the latest evaluation of the opportunity.</span></span>  

<span data-ttu-id="b1814-123">As oportunidades também podem ser interempresariais.</span><span class="sxs-lookup"><span data-stu-id="b1814-123">Opportunities can also be cross-company.</span></span> <span data-ttu-id="b1814-124">Nesse caso, o loop sobre empresas não é necessário e a oportunidade deve ser criada com o método **getOpportunityAcrossCompanies**.</span><span class="sxs-lookup"><span data-stu-id="b1814-124">In this case, the loop over companies is not necessary and the opportunity must be created with the **getOpportunityAcrossCompanies** method.</span></span> 

<span data-ttu-id="b1814-125">O código a seguir mostra o método **findRFQCasesWithEmptyTitle**, que retorna as IDs dos casos de RFQ que têm títulos vazios.</span><span class="sxs-lookup"><span data-stu-id="b1814-125">The following code shows the **findRFQCasesWithEmptyTitle** method, which returns the IDs of the RFQ cases that have empty titles.</span></span>

```
private container findRFQCasesWithEmptyTitle() 
{ 
    container result; 

    PurchRFQCaseTable rfqCase; 
    while select RFQCaseId from rfqCase 
        where rfqCase.Name == '' 
    { 
        result += rfqCase.RFQCaseId; 
    } 
    
    return result; 
} 
```

<span data-ttu-id="b1814-126">Outros dois métodos que devem ser implementados são **opportunityTitle** e **opportunityDetails**.</span><span class="sxs-lookup"><span data-stu-id="b1814-126">Two more methods that must be implemented are **opportunityTitle** and **opportunityDetails**.</span></span> <span data-ttu-id="b1814-127">O primeiro retorna um título curto para a oportunidade, o último retorna uma descrição detalhada da oportunidade, que também pode incluir dados.</span><span class="sxs-lookup"><span data-stu-id="b1814-127">The former returns a short title for the opportunity, the latter returns a detailed description of the opportunity, which can also include data.</span></span>

<span data-ttu-id="b1814-128">O título retornado por **opportunityTitle** aparece na coluna **Oportunidade de otimização** no espaço de trabalho do **Optimization advisor**.</span><span class="sxs-lookup"><span data-stu-id="b1814-128">The title returned by **opportunityTitle** appears under the **Optimization opportunity** column in the **Optimization advisor** workspace.</span></span> <span data-ttu-id="b1814-129">Ele também aparece como o cabeçalho do painel lateral mostrando mais informações sobre a oportunidade.</span><span class="sxs-lookup"><span data-stu-id="b1814-129">It also appears as the header of the side pane showing more information about the opportunity.</span></span> <span data-ttu-id="b1814-130">Por convenção, esse método é decorado com o atributo **DiagnosticRuleSubscription**, que usa os seguintes argumentos:</span><span class="sxs-lookup"><span data-stu-id="b1814-130">By convention, this method is decorated with the **DiagnosticRuleSubscription** attribute, which takes the following arguments:</span></span> 

* <span data-ttu-id="b1814-131">**Área de diagnóstico** – uma enumeração do tipo **DiagnosticArea** que descreve a qual área do aplicativo a regra pertence, como **DiagnosticArea::SCM**.</span><span class="sxs-lookup"><span data-stu-id="b1814-131">**Diagnostic area** – An enum of type **DiagnosticArea** that describes what area of the application the rule belongs to, such as **DiagnosticArea::SCM**.</span></span> 

* <span data-ttu-id="b1814-132">**Nome da regra** – uma sequência de caracteres com o nome da regra.</span><span class="sxs-lookup"><span data-stu-id="b1814-132">**Rule name** – A string with the rule name.</span></span> <span data-ttu-id="b1814-133">Isso aparecerá na coluna **Nome da regra** no formulário **Regra validação de diagnóstico** (**DiagnosticsValidationRuleMaintain**).</span><span class="sxs-lookup"><span data-stu-id="b1814-133">This will appear under the **Rule name** column in the **Dianostics validation rule** form (**DiagnosticsValidationRuleMaintain**).</span></span> 

* <span data-ttu-id="b1814-134">**Frequência de execução** – uma enumeração do tipo **DiagnosticRunFrequency** que descreve a frequência de execução da regra, como **DiagnosticRunFrequency::Daily**.</span><span class="sxs-lookup"><span data-stu-id="b1814-134">**Run frequency** – An enum of type **DiagnosticRunFrequency** that describes how often the rule should be run, such as **DiagnosticRunFrequency::Daily**.</span></span> 

* <span data-ttu-id="b1814-135">**Descrição da regra** – uma sequência de caracteres com uma descrição mais detalhada da regra.</span><span class="sxs-lookup"><span data-stu-id="b1814-135">**Rule description** – A string with a more detailed description of the rule.</span></span> <span data-ttu-id="b1814-136">Isso aparecerá na coluna **Descrição da regra** no formulário **Regra validação de diagnóstico** (**DiagnosticsValidationRuleMaintain**).</span><span class="sxs-lookup"><span data-stu-id="b1814-136">This will appear under the **Rule description** column in the **Dianostics validation rule** form (**DiagnosticsValidationRuleMaintain**).</span></span> 

> [!NOTE]
> <span data-ttu-id="b1814-137">O atributo **DiagnosticRuleSubscription** é necessário para o funcionamento da regra.</span><span class="sxs-lookup"><span data-stu-id="b1814-137">The **DiagnosticRuleSubscription** attribute is required for the rule to work.</span></span> <span data-ttu-id="b1814-138">Normalmente, é usado no **opportunityTitle**, mas pode decorar qualquer método da classe.</span><span class="sxs-lookup"><span data-stu-id="b1814-138">Typically, it is used on **opportunityTitle**, but it can decorate any method of the class.</span></span>

<span data-ttu-id="b1814-139">Segue uma implementação de exemplo.</span><span class="sxs-lookup"><span data-stu-id="b1814-139">The following is an example implementation.</span></span> <span data-ttu-id="b1814-140">Sequências de caracteres brutas são usadas para simplicidade, mas uma implementação correta requer rótulos.</span><span class="sxs-lookup"><span data-stu-id="b1814-140">Raw strings are used for simplicity, but a correct implementation requires labels.</span></span> 

```
[DiagnosticsRuleSubscription(DiagnosticsArea::SCM, 
                             'Assign titles to Request for Quotation cases', 
                             DiagnosticsRunFrequency::Daily,  
                             'This rule detects Requests for Quotation with empty titles.')] 
public str opportunityTitle() 
{ 
    return 'Assign titles to Request for Quotation cases'; 
} 
```

<span data-ttu-id="b1814-141">A descrição retornada por **opportunityDetails** aparecerá no painel lateral mostrando mais informações sobre a oportunidade.</span><span class="sxs-lookup"><span data-stu-id="b1814-141">The description returned by **opportunityDetails** appears on the side pane showing more information about the opportunity.</span></span> <span data-ttu-id="b1814-142">Isso usa o argumento **SelfHealingOpportunity**, que é o campo **Dados** que pode ser usado para fornecer mais detalhes sobre a oportunidade.</span><span class="sxs-lookup"><span data-stu-id="b1814-142">This takes the **SelfHealingOpportunity** argument, which is **Data** field that can be used to provide more details about the opportunity.</span></span> <span data-ttu-id="b1814-143">No exemplo, o método retorna as IDs dos casos de RFQ com um título vazio.</span><span class="sxs-lookup"><span data-stu-id="b1814-143">In the example, the method returns the IDs of the RFQ cases with an empty title.</span></span> 

```
public str opportunityDetails(SelfHealingOpportunity _opportunity) 
{ 
    str details = ''; 
    container opportunityData = _opportunity.Data; 
    int affectedRFQCasesCount = conLen(opportunityData); 

    if (affectedRFQCasesCount != 0) 
    { 
        details = 'The following Request for Quotation cases have an empty title:\n'; 
        for (int i = 1; i <= affectedRFQCasesCount ; i++) 
        { 
            PurchRFQCaseId rfqCaseId = conPeek(opportunityData, i); 
            details += rfqCaseId + '\n'; 
        } 
    } 

    return details; 
}
```

<span data-ttu-id="b1814-144">Os dois métodos abstratos restantes para implementar são **provideHealingAction** e **securityMenuItem**.</span><span class="sxs-lookup"><span data-stu-id="b1814-144">The two remaining abstract methods to implement are **provideHealingAction** and **securityMenuItem**.</span></span> 

<span data-ttu-id="b1814-145">O **provideHealingAction** retorna verdadeiro se uma ação de cura é fornecida, caso contrário, retorna falso.</span><span class="sxs-lookup"><span data-stu-id="b1814-145">**provideHealingAction** returns true if a healing action is provided, otherwise, it returns false.</span></span> <span data-ttu-id="b1814-146">Se o retorno for verdadeiro, o método **performAction** deve ser implementado ou um erro será lançado.</span><span class="sxs-lookup"><span data-stu-id="b1814-146">If true is returned, the method **performAction** must be implemented, or an error will be thrown.</span></span> <span data-ttu-id="b1814-147">O método **performAction** usa um argumento **SelfHealingOpportunity**, no qual os dados podem ser usados para a ação.</span><span class="sxs-lookup"><span data-stu-id="b1814-147">The **performAction** method takes a **SelfHealingOpportunity** argument, in which the data can be used for the action.</span></span> <span data-ttu-id="b1814-148">No exemplo, a ação abre o **PurchRFQCaseTableListPage** para correção manual.</span><span class="sxs-lookup"><span data-stu-id="b1814-148">In the example, the action opens the **PurchRFQCaseTableListPage**, for manual correction.</span></span> 

```
public boolean providesHealingAction() 
{ 
    return true; 
} 

protected void performAction(SelfHealingOpportunity _opportunity) 
{ 
    new MenuFunction(menuItemDisplayStr(PurchRFQCaseTableListPage), MenuItemType::Display).run(); 
} 
```

<span data-ttu-id="b1814-149">Dependendo das especificações da regra, pode ser possível executar uma ação automática usando os dados da oportunidade.</span><span class="sxs-lookup"><span data-stu-id="b1814-149">Depending on the specifics of the rule, it might be possible to take an automatic action using the opportunity data.</span></span> <span data-ttu-id="b1814-150">Nesse exemplo, o sistema poderia gerar títulos para casos de RFQ automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b1814-150">In this example, the system could generate titles for RFQ cases automatically.</span></span> 

<span data-ttu-id="b1814-151">O **securityMenuItem** retorna o nome de um item de menu de ação, de forma que a regra fique visível apenas a usuários com acesso a ele.</span><span class="sxs-lookup"><span data-stu-id="b1814-151">**securityMenuItem** returns the name of an action menu item such that the rule is only visible to users who can access the action menu item.</span></span> <span data-ttu-id="b1814-152">A segurança pode exigir que regras e oportunidades específicas sejam acessíveis somente para usuários autorizados.</span><span class="sxs-lookup"><span data-stu-id="b1814-152">Security might require that specific rules and opportunities are accessible only to authorized users.</span></span> <span data-ttu-id="b1814-153">No exemplo, somente os usuários com acesso ao **PurchRFQCaseTitleAction** podem visualizar a oportunidade.</span><span class="sxs-lookup"><span data-stu-id="b1814-153">In the example, only users with access to **PurchRFQCaseTitleAction** can view the opportunity.</span></span> <span data-ttu-id="b1814-154">Observe que esse item de menu de ação foi criado para esse exemplo e foi adicionado como um ponto de entrada para o privilégio de segurança **PurchRFQCaseTableMaintain**.</span><span class="sxs-lookup"><span data-stu-id="b1814-154">Notice that this action menu item was created for this example, and was added as an entry point for the **PurchRFQCaseTableMaintain** security privilege.</span></span> 

```
public MenuName securityMenuItem() 
{ 
    return menuItemActionStr(PurchRFQCaseTitleAction); 
}
```

<span data-ttu-id="b1814-155">Após a compilação da regra, execute o seguinte trabalho para exibi-la na interface do usuário (UI).</span><span class="sxs-lookup"><span data-stu-id="b1814-155">After the rule has compiled, execute the following job to have it display in the user interface (UI).</span></span>

```
class ScanNewRulesJob 
{         
    public static void main(Args _args) 
    {         
        SysExtensionCache::clearAllScopes(); 
        var controller = new DiagnosticsRuleController(); 
        controller.runOperation(); 
    } 
} 
```

<span data-ttu-id="b1814-156">A regra será exibida no formulário **Regra validação de diagnóstico**, disponível em **Administração do sistema** > **Tarefas periódicas** > **Manter regra validação de diagnóstico**.</span><span class="sxs-lookup"><span data-stu-id="b1814-156">The rule will display in the **Diagnostics validation rule** form, available from **System administration** > **Periodic tasks** > **Maintain diagnostics validation rule**.</span></span> <span data-ttu-id="b1814-157">Para avaliá-la, vá para **Administração do sistema** > **Tarefas periódicas** > **Agendar regra validação de diagnóstico**, selecione a frequência da regra, como **Diariamente**.</span><span class="sxs-lookup"><span data-stu-id="b1814-157">To have it evaluated, go to **System administration** > **Periodic tasks** > **Schedule diagnostics validation rule**, select the frequency of the rule, such as **Daily**.</span></span> <span data-ttu-id="b1814-158">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1814-158">Click **OK**.</span></span> <span data-ttu-id="b1814-159">Vá para **Administração do sistema** > **Optimization advisor** para exibir a nova oportunidade.</span><span class="sxs-lookup"><span data-stu-id="b1814-159">Go to **System administration** > **Optimization advisor** to view the new opportunity.</span></span> 

<span data-ttu-id="b1814-160">Para obter mais informações, assista ao vídeo curto no YouTube:</span><span class="sxs-lookup"><span data-stu-id="b1814-160">For more information, watch the short YouTube video:</span></span>

> [!Video https://www.youtube.com/embed/MRsAzgFCUSQ]

