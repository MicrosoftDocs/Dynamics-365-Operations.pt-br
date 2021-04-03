---
title: Configurar tipos de eventos de vida
description: O Microsoft Dynamics 365 Human Resources usa tipos de eventos de vida para definir eventos em que é válido atualizar a inscrição de benefícios do funcionário.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7b1f2fd953c1678a5099f4f3b5cf08fa6674f4db
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466029"
---
# <a name="configure-life-event-types"></a>Configurar tipos de eventos de vida

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

O Dynamics 365 Human Resources usa tipos de eventos de vida para definir eventos em que é válido atualizar a inscrição de benefícios do funcionário. Por exemplo, se você se casar ou tiver um filho. Cada ID de tipo de evento de vida só pode ser associada a um tipo de evento de vida. Por exemplo, se você criar uma ID de evento da vida útil chamada Alteração de endereço associada ao tipo de evento de vida Alteração de endereço de funcionário, não poderá criar outra ID rotulada Alteração de endereço de funcionário e associá-la ao tipo de evento de vida Alteração do endereço do funcionário. 

Depois de criar os tipos de eventos de vida, você precisa associá-los a tipos de plano. Para obter mais informações, consulte [Criar tipos de plano](hr-benefits-setup-plan-types.md).

   > [!NOTE]
   > Ao criar um evento de vida, você precisa associá-lo a um tipo de plano. Para obter mais informações, consulte [Criar tipos de plano](hr-benefits-setup-life-event-types.md).

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
| **Alteração do status do emprego** | <ul><li>Trabalhador > Emprego</li><li>Página de histórico de emprego</li></ul> | Alterar no status de emprego |
| **Alteração de endereço do funcionário** | <ul><li>Trabalhador > Perfil > Endereços </li><li>Trabalhador > Informações pessoais > Contatos pessoais > Endereço</li></ul> Endereço adicionado, editado ou excluído |
| **Alteração de dependente** | <ul><li>Trabalhador > Perfil > Informações pessoais > Contatos pessoais > Adicionar ou excluir um dependente</li><li>Autoatendimento para funcionários</li></ul> | Dependente adicionado ou excluído. O relacionamento de contato pessoal deve ser filho, cônjuge, parceiro doméstico ou ex-cônjuge. A atualização de **Válido a partir de** dispara o evento de vida. Se você não atualizar essa data, nenhum evento de vida será disparado. |
| **Nascimento ou adoção (dependente)** | <ul><li>Trabalhador > Perfil > Informações pessoais > Contatos pessoais > Detalhes do dependente</li><li>Autoatendimento para funcionários</li></ul> | Campo **Data da adoção** preenchido. A data de nascimento do filho é necessária. |
| **Perda de cobertura (cônjuge/parceiro doméstico)** | Trabalhador > Perfil > Informações pessoais > Contatos pessoais > Detalhes do dependente > Perda de cobertura | **Perda de cobertura** selecionada para um contato pessoal, junto com **Data de efetivação** |
| Alteração de emprego do parceiro doméstico | Trabalhador > Perfil > Informações pessoais > Contatos pessoais > Detalhes do dependente > Empregado. | <ul><li>Registro de detalhes de dependentes criado e caixa **Contato pessoal empregado** = Sim</li><li>Caixa **Contato pessoal empregado** alterada (Sim ou não)</li></ul> |
| **Licença (cônjuge/parceiro doméstico)** | Trabalhador > Perfil > Informações pessoais > Contatos pessoais > Detalhes do dependente > Licença | <ul><li>Registro de detalhes de dependentes criado e **EhrLOAEffectiveDate** preenchido</li><li>**personPrivateDetails.EhrIsLOA** é alterado (Sim ou não)</li><li>**personPrivateDetails.EhrLOAEffectiveDate** é alterado</li></ul> |
| **Alteração na cobertura (posição)** | <ul><li>Trabalhador > Atribuição de Posição > Atribuições da posição do trabalhador</li><li>Posições > Posições</li></ul> | <ul><li>Alterar para a posição nos registros de atribuições de posição do trabalhador</li><li>Altere a atribuição do trabalhador na posição</li></ul> |
| **Medicare (funcionário/dependente)** | Trabalhador > Perfil > Informações pessoais > Contatos pessoais > Detalhes do dependente > Data de efetivação do Medicare | Não é disparado automaticamente quando um contato pessoal insere uma data de efetivação. |
| **Suporte ordenado por tribunal** | Trabalhador > Perfil > Informações pessoais > Contatos pessoais > Dependente > Suporte ordenado pelo tribunal (QMSCO/QDRO) e datas de efetivação | Não dispara atualizações automáticas. Isso não afeta a qualificação; registra um evento de vida. |
| **Falecimento** | Trabalhador > Perfil > Informações pessoais > Data de falecimento | Uma data de falecimento é inserida |
| **Evidência de seguro** | <ul><li>Trabalhador > Trabalhador > Versões > Histórico de emprego > Gerenciador de datas > Detalhes do benefício</li><li> Trabalhador > Emprego > Detalhes do benefício > Data de verificação</li></ul> | <ul><li>Um trabalhador insere uma data de verificação</li><li>Um trabalhador define o campo EvidenceOfInsurability como **Sim**</li></ul> |
| **Beneficiário** | Trabalhador > Perfil > Informações pessoais > Contatos pessoais | Um contato pessoal é adicionado e as caixas **Beneficiário** e **Data de efetivação** são preenchidas. O contato pessoal deve ser do tipo **Criança**, **Cônjuge**, **DomesticPartner**, **Irmão**, **FamilyContact**, **OtherContact**, **Pai**, **BeneficiaryEstate**, **BeneficiaryOrg** ou **BeneficiaryTrust**. |
| **Medicare do Funcionário** | Trabalhador > Trabalhador > Versões > Histórico de emprego > Gerenciador de datas > Detalhes do benefício | <ul><li>**EhrMedicareEligibilityDate** alterado</li><li>**MedicareEligibile** é definido como **Sim**</li></ul> |
| **Data de nascimento** | Trabalhador > Perfil > Informações pessoais > Contatos pessoais > Detalhes do dependente > Data de nascimento | Uma data de nascimento é adicionada ou atualizada (não após o processamento da alteração do evento de vida). Exemplo: se as **Opções de qualificação para o contato pessoal** de uma criança estiverem definidas como idade: 26 em Instalação > Benefícios > Opções de qualificação para contato pessoal e se o processamento de alteração de evento da vida do pessoal de RH for executado qualquer dia depois que o dependente fizer 26 anos de idade, uma mensagem será exibida alertando que o dependente não está mais qualificado para cobertura. |
| **Alteração da qualificação para trabalhador (não específica dos EUA)** | <ul><li>Trabalhador > Emprego</li><li>Trabalhador > Trabalhador > Versões > Histórico de emprego</li></ul> | <ul><li>Tipo de funcionário, categoria de emprego ou os cinco campos de qualificação definidos pelo usuário mudam</li><li>Alterações em **HcmEmploymentDetail.EhrEmploymentType** (processadas somente ara registros de detalhes de emprego *alterados*, não processadas para *novos* registros de emprego, como recontratação e demissão)</li></ul> |
| **Nova substituição de qualificação (não específica dos EUA)** | Recursos humanos avançados > Benefícios > Planos > Benefícios > Substituição de regra de qualificação | Usando o processamento de eventos de vida | EhrBenefitEligibilityRuleOverride.ValidFrom |
| **Alteração da substituição de regra de qualificação (não específica dos EUA)** | Recursos humanos avançados > Benefícios > Planos > Benefícios > Substituição de regra de qualificação | Usando o processamento de eventos de vida (só captura alterações nos campos **ValidFrom** e **ValidTo** na substituição da regra de qualificação) |
| **Expiração da substituição de regra de qualificação (não específica dos EUA)** | Recursos humanos avançados > Benefícios > Planos > Benefícios > Substituição de regra de qualificação | Usando o processamento de alteração de eventos de vida. Por exemplo, se você editar uma regra de qualificação do plano, a data de vencimento da substituição deverá ser hoje às 17:00h, a qualquer momento após 17:00h ou nos seguintes dias. Depois, ocorrerá o processamento de alteração do evento de vida. Será exibida uma mensagem informando que a substituição da regra de qualificação expirou. |
| **Novo plano de benefícios (não específico dos EUA)** | Recursos humanos avançados > Benefícios > Planos > Novo | <ul><li>As opções de qualificação são adicionadas a um plano atual</li><li>Um novo plano com opções de qualificação anexadas foi adicionado</li></ul></br></br>O pessoal de RH deve executar o processamento da qualificação do evento de vida nessa instância. |
| **Alteração de regra de qualificação (não específica dos EUA)** | Recursos humanos avançados > Benefícios > Regras/opções > Regras de qualificação | Usando o processamento de elegibilidade de eventos de vida. Registrado quando os registros **EhrBenefitEligibilityRule** têm os seguintes valores alterados: **UseEmplCategory**, **UseEmplStatus** ou **UseEmplType**. Atualiza somente as transações de evento de vida que já existem para uma regra alterada ou critérios de qualificação. |


[!INCLUDE[footer-include](../includes/footer-banner.md)]