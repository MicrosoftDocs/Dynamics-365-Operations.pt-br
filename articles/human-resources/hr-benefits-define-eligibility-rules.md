---
title: Definir regras e políticas de qualificação para o benefício
description: O artigo mostra como é possível criar regras e políticas de qualificação para o benefício e atribuir regras a benefícios.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: 046b045fbdda125c5a2259783c0347f687453528
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053144"
---
# <a name="define-benefit-eligibility-rules-and-policies"></a>Definir regras e políticas de qualificação para o benefício

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

O tópico mostra como é possível criar regras e políticas de qualificação para o benefício e atribuir regras a benefícios.  

## <a name="create-benefit-eligibility-policy-rule-type"></a>Crie tipos de regras de política de qualificação para benefícios

1. Vá para **Recursos humanos > Benefícios > Qualificação > Tipos de regras de política de qualificação para o benefício**.
2. Selecione **Novo**.
3. No campo **Nome da regra**, insira um valor.
4. No campo **Descrição**, insira um valor.
5. No campo **Nome da consulta**, selecione o botão suspenso para abrir a pesquisa.
6. Na lista, selecione o link na linha selecionada.
7. Selecione **Salvar**.
8. Feche a página.

## <a name="benefit-eligibility-policy"></a>Política de qualificação para o benefício

1. Vá para **Recursos humanos > Benefícios > Qualificação > Políticas de qualificação para o benefício**.
2. Selecione uma diretiva existente de benefício.
3. Na lista, selecione o link na linha selecionada.
4. Alterne a expansão das seções de **Organizações de política**. Você poderá adicionar ou remover as organizações que desejar incluir na política.
5. Expanda ou recolha a seção de **Regras de política**.
6. Na lista, localize a regra de política criada previamente.
7. Selecione **Criar regra de política**.
8. No campo **Data efetiva**, insira a data na qual deseja que a política entre em vigor.
    * Definir datas finais efetivas permite que você faça alterações futuras em regras de política para que não precise voltar à política quando desejar que essas alterações sejam aplicadas.  
9. Se necessário, adicione uma cláusula where ao campo **Adicionar condição**.
    * Por exemplo, para que a regra se aplicasse somente aos Gerentes de vendas, você poderia criar a cláusula where para indicar: a descrição da posição de where equivale ao Gerente de vendas. Você pode adicionar várias instruções where juntas na regra.  
10. Selecione **OK**.
11. Feche a página.

## <a name="assign-rule-to-benefit"></a>Atribuir regra ao benefício

1. Acesse **Recursos humanos > Benefícios > Benefícios**.
2. Na lista, localize e selecione o registro desejado.
3. Na lista, selecione o link na linha selecionada.
4. Expanda ou recolha a seção **Regras de qualificação**.
5. Selecione **Editar**.
6. No campo **Qualificação**, selecione a regra.
7. No campo **Tipo de regra**, selecione a regra que você criou anteriormente.
9. Na lista, selecione o link na linha selecionada.
10. Selecione **Salvar**.
11. Feche o formulário.



[!INCLUDE[footer-include](../includes/footer-banner.md)]