---
title: Configurar tipos de eventos de vida
description: O Microsoft Dynamics 365 Human Resources usa tipos de eventos de vida para definir eventos em que é válido atualizar a inscrição de benefícios do funcionário.
author: andreabichsel
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 821e11d6ee22cb560b3d23017c7c332f80d41c18
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6057637"
---
# <a name="configure-life-event-types"></a>Configurar tipos de eventos de vida

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

O Dynamics 365 Human Resources usa tipos de eventos de vida para definir eventos em que é válido atualizar a inscrição de benefícios do funcionário, como casar-se ou ter um filho. Cada ID de tipo de evento de vida só pode ser associada a um tipo de evento de vida. Por exemplo, se você criar uma ID de evento da vida útil chamada Alteração de endereço associada ao tipo de evento de vida Alteração de endereço de funcionário, não poderá criar outra ID rotulada Alteração de endereço de funcionário e associá-la ao tipo de evento de vida Alteração do endereço do funcionário. Se um tipo de evento de vida não estiver associado a um tipo de plano, o tipo de evento da vida não disparará um evento de vida. Para obter mais informações, consulte [Criar tipos de plano](hr-benefits-setup-plan-types.md).

## <a name="create-a-life-event-type"></a>Criar um tipo de evento de vida

1. No espaço de trabalho **Gerenciamento de benefícios**, em **Configuração**, selecione **Tipos de eventos de vida**.

2. Selecione **Novo**.

3. Especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- |
   | **ID do tipo de evento de vida** | O identificador exclusivo do tipo de evento de vida. |
   | **Descrição** | Uma descrição do tipo de evento de vida. |
   | **Tipo de evento de vida** | Um catalisador para atualizar a inscrição em benefícios de um funcionário. Para obter uma lista de eventos de vida, consulte [Eventos de vida](hr-benefits-setup-payment-frequencies.md?life-events) a seguir. |

4. Selecione **Salvar**.

## <a name="view-attached-plans"></a>Exibir planos anexados

Você pode ver uma lista de planos que estão anexados ao tipo de evento de vida selecionado. Os eventos de vida são associados a um tipo de plano e os tipos de plano são associados a um plano.

1. No espaço de trabalho **Gerenciamento de benefícios**, em **Configuração**, selecione **Tipos de eventos de vida**.

2. Selecione **Ações**.

3. Selecione **Planos anexados**.

## <a name="life-events"></a>Eventos de vida

Você pode escolher entre os seguintes eventos de vida ao criar um tipo de evento de vida:

| Evento de vida | Local | Disparador |
| --- | --- | --- |
| **Alteração do estado civil** | Trabalhador > Perfil > Informações pessoais > Estado civil| Alterar no estado civil |
| **Alteração do status do emprego** | Trabalhador > Emprego<br>Página de histórico de emprego | Para um trabalhador com um detalhe de emprego existente, a criação de um novo detalhe de emprego com outro status de emprego disparará um evento de vida.  Atualizar um detalhe de emprego existente com outro status de emprego também disparará um evento de vida.  |
| **Alteração de endereço do funcionário** | Trabalhador > Perfil > Endereços<br>Trabalhador > Informações pessoais > Contatos pessoais > Endereço | Alteração no endereço. O endereço deve ser principal para disparar um evento de vida. |
| **Alteração de dependente** | Trabalhador > Perfil > Informações pessoais > Contatos pessoais<br>Autoatendimento para funcionários | Adicione um contato pessoal especificando-o como um dependente e definindo **Válido a partir de**. Atualize informações **Válida até** de um dependente de contato pessoal. O relacionamento de contato pessoal deve ser filho, cônjuge, parceiro doméstico ou ex-cônjuge.  |
| **Nascimento ou adoção (dependente)** | Trabalhador > Perfil > Informações pessoais > Contatos pessoais<br>Autoatendimento para funcionários > Editar detalhes pessoais > Contatos pessoais | **Data de nascimento** ou **Data de adoção** é adicionada ou atualizada. A **Data de nascimento** do filho é necessária. |
| **Perda de cobertura (cônjuge/parceiro doméstico)** | Trabalhador > Perfil > Informações pessoais > Contatos pessoais > Detalhes do dependente > Perda de cobertura | **Perda de cobertura** selecionada para um contato pessoal, junto com **Data de efetivação** |
| Alteração de emprego do parceiro doméstico | Trabalhador > Perfil > Informações pessoais > Contatos pessoais > Detalhes do dependente > Empregado | Criar um contato pessoal e definir **Empregado** como **Sim**. Atualizar um contato pessoal e alterar **Empregado**.  |
| **Licença (cônjuge/parceiro doméstico)** | Trabalhador > Perfil > Informações pessoais > Contatos pessoais > Detalhes do dependente > Licença | O contato pessoal foi criado e **Data de efetivação de licença** foi definida. A **Licença** do contato pessoal é atualizada. A **Data de efetivação da licença** do contato pessoal é atualizada.  |
| **Alteração na cobertura (posição)** | Trabalhador > Atribuição de Posição > Atribuições da posição do trabalhador<br>Posições > Posições | Altere para a posição nos registros de atribuições de posição do trabalhador. Altere a atribuição do trabalhador na posição. |
| **Alteração na cobertura (salário)** | Trabalhador > Remuneração > Plano fixo<br>Trabalhador > Informações pessoais > Salário de benefícios anual | Se Gerenciamento de benefícios > Parâmetros compartilhados de recursos humanos > Benefícios > Salário de benefícios anual não estiver habilitado, a atualização de Trabalhador > Remuneração > Plano fixo criará um evento de vida. Se Gerenciamento de benefícios > Parâmetros compartilhados de recursos humanos > Benefícios > Salário de benefícios anual estiver habilitado, a atualização de Trabalhador > Informações pessoais > Salário de benefícios anual criará um evento de vida. |
| **Medicare (funcionário/dependente)** | Trabalhador > Perfil > Informações pessoais > Contatos pessoais > Detalhes do dependente > Data de efetivação do Medicare | Adicionar ou atualizar **Data de efetivação do Medicare** de um contato pessoal cria este evento de vida. |
| **Suporte ordenado por tribunal** | Trabalhador > Perfil > Informações pessoais > Contatos pessoais > Dependente > Suporte ordenado pelo tribunal (QMSCO/QDRO) e datas de efetivação | Ao criar um contato pessoal, um evento de vida será criado se o **Suporte ordenado por tribunal** for **Sim**. Atualizar **Suporte ordenado por tribunal** ou **Data de vencimento ordenada por tribunal** também disparará um evento de vida. |
| **Falecimento** | Trabalhador > Perfil > Informações pessoais > Data de falecimento | Uma data de falecimento é inserida ou atualizada. |
| **Evidência de seguro** | Trabalhador > Trabalhador > Versões > Histórico de emprego > Gerenciador de datas > Detalhes do benefício | A **Evidência de segurabilidade** é definida como **Sim**. A **Data de verificação da evidência de segurabilidade** é definida. |
| **Beneficiário** | Trabalhador > Perfil > Informações pessoais > Contatos pessoais | Um contato pessoal é adicionado e as caixas **Beneficiário** e **Data de efetivação** são preenchidas. O contato pessoal deve ser do tipo **Criança**, **Cônjuge**, **DomesticPartner**, **Irmão**, **FamilyContact**, **OtherContact** ou **Pai**. |
| **Medicare do Funcionário** | Trabalhador > Trabalhador > Versões > Histórico de emprego > Gerenciador de datas > Detalhes do benefício | **Qualificado para Medicare** é definido como **Sim**. A **Data da qualificação para Medicare** é alterada. |
| **Data de nascimento** | Gerenciamento de benefícios > Processamento de alteração de eventos de vida | Esses eventos de vida são criados a partir do **Processamento de alteração de eventos de vida**. O processo analisa o período e a entidade legal escolhidos e localiza trabalhadores associados. Ele calcula o último aniversário e cria um evento de vida de aniversário, caso ainda não tenha sido criado. |
| **Alteração da qualificação para trabalhador (não específica dos EUA)** | Trabalhador > Emprego<br>Trabalhador > Trabalhador > Versões > Histórico de emprego | Cria um evento de vida quando:<br><ul><li>Cria um novo emprego, e há um emprego anterior, e o tipo de trabalhador muda.</li><li>Cria um novo detalhe de emprego, e há um detalhe de emprego anterior, e o tipo de emprego ou a categoria de emprego muda.</li><li>Atualiza um registro de emprego e um tipo de trabalhador diferente é definido.</li><li>Atualiza um registro de detalhe de emprego e um tipo de emprego ou categoria diferente é especificado.</li></ul> |
| **Nova substituição de qualificação (não específica dos EUA)** | Recursos humanos avançados > Benefícios > Planos > Benefícios > Substituição de regra de qualificação | Usar o processamento de eventos de vida<br>A criação de uma nova substituição de qualificação do plano de benefícios para um trabalhador dispara este evento de vida.<br>BenefitEligibilityRuleOverride.ValidFrom. |
| **Alteração da substituição de regra de qualificação (não específica dos EUA)** | Recursos humanos avançados > Benefícios > Planos > Benefícios > Substituição de regra de qualificação | Atualizar **Válido a partir de** ou **Válido até** em uma substituição de qualificação de plano de benefícios dispara este evento de vida. |
| **Expiração da substituição de regra de qualificação (não específica dos EUA)** | Gerenciamento de benefícios > Processamento de alteração de eventos de vida  | Esses eventos de vida são criados a partir do **Processamento de alteração de eventos de vida**. O processo analisa o período e a entidade legal escolhidos e localiza substituições de qualificação de plano de benefícios associadas. Ele criará eventos de vida se as substituições expirarem. |
| **Novo plano de benefícios (não específico dos EUA)** | Recursos humanos avançados > Benefícios > Planos > Novo | As opções de qualificação são adicionadas a um plano atual. Um novo plano com opções de qualificação anexadas foi adicionado.</br></br>O pessoal de RH deve executar o processamento da qualificação do evento de vida nessa instância. |
| **Alteração de regra de qualificação (não específica dos EUA)** | Gerenciamento de benefícios > Regras de qualificação | Usando o processamento de elegibilidade de eventos de vida. Registrado quando registros **BenefitEligibilityRule** têm os seguintes valores alterados: **UseEmplCategory**, **UseEmplStatus** ou **UseEmplType**. Atualiza somente as transações de evento de vida que já existem para uma regra alterada ou critérios de qualificação. |


[!INCLUDE[footer-include](../includes/footer-banner.md)]