---
title: Criar regras para o Optimization advisor
description: Este tópico discute como adicionar novas regras ao Optimization advisor.
author: roxanadiaconu
manager: AnnBe
ms.date: 02/04/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SelfHealingWorkspace
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: sericks
ms.search.validFrom: 2017-12-01
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 67e740a1e00c425f0e09b5f0fc960cf2778efd89
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568277"
---
# <a name="create-rules-for-optimization-advisor"></a>Criar regras para o Optimization advisor

[!include [banner](../includes/banner.md)]

Este tópico explica como criar novas regras para o **Optimization advisor**. Por exemplo, você pode criar uma nova regra que identifique quais casos de solicitação de cotações (RFQ) possuem um título vazio. Usar títulos em casos facilita sua identificação e pesquisa. Embora relativamente simples, esse exemplo mostra o que pode ser obtido com regras de otimização. 

Uma *regra* é uma verificação em dados de aplicativo. Se a condição que a regra avalia é atendida, oportunidades de otimizar processos ou melhorar dados são criadas. É possível agir em relação às oportunidades e, opcionalmente, o impacto das ações pode ser medido. 

Para criar uma nova regra para o **Optimization advisor**, adicione uma nova classe que estenda a classe abstrata **SelfHealingRule**, implemente a interface **IDiagnosticsRule** e seja decorada pelo atributo **DiagnosticRule**. A classe também deve possuir um método decorado com o atributo **DiagnosticsRuleSubscription**. Por convenção, isso é feito no método **opportunityTitle**, que será discutido posteriormente. Essa nova classe pode ser adicionada a um modelo personalizado com uma dependência no modelo **SelfHealingRules**. No exemplo a seguir, a regra que está sendo implementada é chamada **RFQTitleSelfHealingRule**.

```xpp
[DiagnosticsRule] 
public final class RFQTitleSelfHealingRule extends SelfHealingRule implements IDiagnosticsRule 
{ 
… 
} 
```

A classe abstrata **SelfHealingRule** contém métodos abstratos que devem ser implementados em classes de herança. O principal é o método **avaliar**, que retorna uma lista das oportunidades identificadas pela regra. As oportunidades podem ser por entidade legal ou podem ser aplicadas ao sistema inteiro.

```xpp
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

O método mostrado acima executa um loop sobre empresas e seleciona casos de RFQ com títulos vazios no método **findRFQCasesWithEmptyTitle**. Se pelo menos um caso do tipo for encontrado, então uma oportunidade específica a uma empresa é criada com o método **getOpportunityForCompany**. Observe que o campo **Dados** na tabela **SelfHealingOpportunity** é do tipo **Contêiner** e, portanto, pode conter quaisquer dados relevantes para a lógica específica a esta regra. A configuração de **OpportunityDate** com o carimbo de data/hora atual registra a hora da última avaliação da oportunidade.  

As oportunidades também podem ser interempresariais. Nesse caso, o loop sobre empresas não é necessário e a oportunidade deve ser criada com o método **getOpportunityAcrossCompanies**. 

O código a seguir mostra o método **findRFQCasesWithEmptyTitle**, que retorna as IDs dos casos de RFQ que têm títulos vazios.

```xpp
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

Outros dois métodos que devem ser implementados são **opportunityTitle** e **opportunityDetails**. O primeiro retorna um título curto para a oportunidade, o último retorna uma descrição detalhada da oportunidade, que também pode incluir dados.

O título retornado por **opportunityTitle** aparece na coluna **Oportunidade de otimização** no espaço de trabalho do **Optimization advisor**. Ele também aparece como o cabeçalho do painel lateral mostrando mais informações sobre a oportunidade. Por convenção, esse método é decorado com o atributo **DiagnosticRuleSubscription**, que usa os seguintes argumentos: 

* **Área de diagnóstico** – uma enumeração do tipo **DiagnosticArea** que descreve a qual área do aplicativo a regra pertence, como **DiagnosticArea::SCM**. 

* **Nome da regra** – uma sequência de caracteres com o nome da regra. Isso aparecerá na coluna **Nome da regra** no formulário **Regra validação de diagnóstico** (**DiagnosticsValidationRuleMaintain**). 

* **Frequência de execução** – uma enumeração do tipo **DiagnosticRunFrequency** que descreve a frequência de execução da regra, como **DiagnosticRunFrequency::Daily**. 

* **Descrição da regra** – uma sequência de caracteres com uma descrição mais detalhada da regra. Isso aparecerá na coluna **Descrição da regra** no formulário **Regra validação de diagnóstico** (**DiagnosticsValidationRuleMaintain**). 

> [!NOTE]
> O atributo **DiagnosticRuleSubscription** é necessário para o funcionamento da regra. Normalmente, é usado no **opportunityTitle**, mas pode decorar qualquer método da classe.

Segue uma implementação de exemplo. Sequências de caracteres brutas são usadas para simplicidade, mas uma implementação correta requer rótulos. 

```xpp
[DiagnosticsRuleSubscription(DiagnosticsArea::SCM, 
                             'Assign titles to Request for Quotation cases', 
                             DiagnosticsRunFrequency::Daily,  
                             'This rule detects Requests for Quotation with empty titles.')] 
public str opportunityTitle() 
{ 
    return 'Assign titles to Request for Quotation cases'; 
} 
```

A descrição retornada por **opportunityDetails** aparecerá no painel lateral mostrando mais informações sobre a oportunidade. Isso usa o argumento **SelfHealingOpportunity**, que é o campo **Dados** que pode ser usado para fornecer mais detalhes sobre a oportunidade. No exemplo, o método retorna as IDs dos casos de RFQ com um título vazio. 

```xpp
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

Os dois métodos abstratos restantes para implementar são **provideHealingAction** e **securityMenuItem**. 

O **provideHealingAction** retorna verdadeiro se uma ação de cura é fornecida, caso contrário, retorna falso. Se o retorno for verdadeiro, o método **performAction** deve ser implementado ou um erro será lançado. O método **performAction** usa um argumento **SelfHealingOpportunity**, no qual os dados podem ser usados para a ação. No exemplo, a ação abre o **PurchRFQCaseTableListPage** para correção manual. 

```xpp
public boolean providesHealingAction() 
{ 
    return true; 
} 

protected void performAction(SelfHealingOpportunity _opportunity) 
{ 
    new MenuFunction(menuItemDisplayStr(PurchRFQCaseTableListPage), MenuItemType::Display).run(); 
} 
```

Dependendo das especificações da regra, pode ser possível executar uma ação automática usando os dados da oportunidade. Nesse exemplo, o sistema poderia gerar títulos para casos de RFQ automaticamente. 

O **securityMenuItem** retorna o nome de um item de menu de ação, de forma que a regra fique visível apenas a usuários com acesso a ele. A segurança pode exigir que regras e oportunidades específicas sejam acessíveis somente para usuários autorizados. No exemplo, somente os usuários com acesso ao **PurchRFQCaseTitleAction** podem visualizar a oportunidade. Observe que esse item de menu de ação foi criado para esse exemplo e foi adicionado como um ponto de entrada para o privilégio de segurança **PurchRFQCaseTableMaintain**. 

> [!NOTE]
> O item de menu deve ser um item do menu de ação para que a segurança funcione corretamente. Outros tipos de itens de menu, como **Itens do menu de exibição** não funcionarão corretamente.

```xpp
public MenuName securityMenuItem() 
{ 
    return menuItemActionStr(PurchRFQCaseTitleAction); 
}
```

Após a compilação da regra, execute o seguinte trabalho para exibi-la na interface do usuário (UI).

```xpp
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

A regra será exibida no formulário **Regra validação de diagnóstico**, disponível em **Administração do sistema** > **Tarefas periódicas** > **Manter regra validação de diagnóstico**. Para avaliá-la, vá para **Administração do sistema** > **Tarefas periódicas** > **Agendar regra validação de diagnóstico**, selecione a frequência da regra, como **Diariamente**. Clique em **OK**. Vá para **Administração do sistema** > **Optimization advisor** para exibir a nova oportunidade. 

Veja a seguir o exemplo de um trecho de código com o esqueleto de uma regra incluindo todos os métodos e atributos necessários. Ele ajuda você a começar a gravar novas regras. Os rótulos e itens do menu de ação usados no exemplo são somente para fins de demonstração.

```xpp
[DiagnosticsRuleAttribute]
public final class SkeletonSelfHealingRule extends SelfHealingRule implements IDiagnosticsRule
{
    [DiagnosticsRuleSubscription(DiagnosticsArea::SCM,
                                 "@SkeletonRuleLabels:SkeletonRuleTitle", // Label with the title of the rule
                                 DiagnosticsRunFrequency::Monthly,
                                 "@SkeletonRuleLabels:SkeletonRuleDescription")] // Label with a description of the rule
    public str opportunityTitle()
    {
        // Return a label with the title of the opportunity
        return "@SkeletonRuleLabels:SkeletonOpportunityTitle";
    }

    public str opportunityDetails(SelfHealingOpportunity _opportunity)
    {
        str details = "";

        // Use _opportunity.data to provide details on the opportunity

        return details;
    }

    protected List evaluate()
    {
        List results = new List(Types::Record);

        // Write here the core logic of the rule

        // When creating an opportunity, use:
        //     * this.getOpportunityForCompany() for company specific opportunities
        //     * this.getOpportunityAcrossCompanies() for cross-company opportunities

        return results;
    }

    public boolean providesHealingAction()
    {
        return true;
    }

    protected void performAction(SelfHealingOpportunity _opportunity)
    {
        // Place here the code that performs the healing action

        // To open a form, use the following:
        // new MenuFunction(menuItemDisplayStr(SkeletonRuleDisplayMenuItem), MenuItemType::Display).run();
    }

    public MenuName securityMenuItem()
    {
        return menuItemActionStr(SkeletonRuleActionMenuItem);
    }

}
```

Para obter mais informações, assista a este breve vídeo no YouTube: [Optimization advisor in Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=MRsAzgFCUSQ)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]