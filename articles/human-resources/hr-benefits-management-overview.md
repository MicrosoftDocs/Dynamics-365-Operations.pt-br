---
title: Visão geral do Gerenciamento de benefícios
description: Visão geral do recurso de Gerenciamento de benefícios no Dynamics 365 Human Resources. Ofereça opções de benefícios estendidos aos seus funcionários com uma experiência online fácil de usar.
author: andreabichsel
manager: AnnBe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1043fb18c33e5ec0cde13008b168fd317c7c7be6
ms.sourcegitcommit: 9dc5c7dd5877cc6e7cd0059d173bcd8052ba13bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/16/2020
ms.locfileid: "3599371"
---
# <a name="benefits-management-overview"></a>Visão geral do Gerenciamento de benefícios

Para permanecer em um mercado competitivo, é necessário oferecer um conjunto amplo de benefícios para atrair e reter os melhores funcionários. Além dos benefícios padrão, como plano de saúde e odontológico, ofereça serviços expandidos, como assistência à adoção, programas de recreação e auxílio-vestimenta. O Gerenciamento de benefícios do Microsoft Dynamics 365 Human Resources oferece uma solução flexível compatível com uma ampla variedade de opções de benefícios. O Human Resources também inclui uma experiência para funcionários fácil de usar e que mostra as ofertas.

- Os planos de benefícios aprimorados permitem criar e gerenciar planos de benefícios exclusivos e oferecem suporte a tabelas de taxas de benefícios complexas e camadas aninhadas. Você pode facilmente criar programas e pacotes de benefícios, além de regras de inscrição automática nos benefícios para facilitar a experiência dos funcionários.

- Os programas de crédito flexível permitem ratear para oferecer suporte à aposentadoria e outros eventos de vida.

- As regras de elegibilidade extensivas garantem a disponibilização dos benefícios apropriados para os funcionários certos.

- A inscrição online nos benefícios permite uma experiência fácil para os funcionários.

- O processamento de eventos de vida útil é compatível com eventos de vida futuros.

Se deseja acessar os dados de demonstração, será necessário implementar novamente o ambiente de área restrita.

## <a name="benefits-management-known-issues"></a>Problemas conhecidos do gerenciamento de benefícios

### <a name="flex-credit-programs"></a>Programas de crédito flexível

O valor de crédito total definido para um programa de crédito flexível não é exibido no formulário **Planos de benefícios do trabalhador**. Além disso, se você definir um programa de crédito flexível para ter uma regra de rateio de **Nenhum**, você recebe um erro no formulário **Plano de benefício do trabalhador** ao selecionar e confirmar planos.

## <a name="enable-benefits-management"></a>Habilitar o Gerenciamento de benefícios

Este artigo descreve como acionar os recursos no Human Resources. Ele também informa quais recursos existentes no Human Resources são substituídos pelo Gerenciamento de benefícios ou quais são desabilitados após ativar o Gerenciamento de recursos.

> [!IMPORTANT]
> Depois de habilitar o gerenciamento de benefícios em um ambiente de **Produção** você pode desativá-lo. É recomendável habilitar e testar o gerenciamento de benefícios em um ambiente de **Área restrita** antes de ativá-lo em um ambiente de **Produção**. Há diferenças significativas entre a funcionalidade de benefício herdada e a nova funcionalidade de gerenciamento de benefícios que exigem configuração adicional e devem ser testadas antes de serem colocadas em produção.

- [Gerenciar recursos](hr-admin-manage-features.md)

## <a name="configure-employee-information"></a>Configurar informações do funcionário

Para poder inscrever funcionários em benefícios, você deve fornecer as informações necessárias. Você deve registrar um funcionário em um **Plano de compensação fixa** em sua data de início, e você deve selecionar uma **Frequência de pagamento de benefício** em **Detalhes de emprego** no formulário **Trabalhador**.

Se você tem um funcionário que recebe remuneração suplementar, como comissões, é possível adicionar um valor de **Salário de benefícios anual** do registro do funcionário. O Human Resources usará o valor do **Salário de benefícios anual** para determinar valores de cobertura em vez do valor anual da remuneração fixa. O **Salário de benefícios anual** deve ser válido a partir da data de início do funcionário ou do início do período de benefício, dos dois o que for mais recente. Se um valor de salário de benefícios anual e remuneração fixa for registrado para um funcionário, o salário de benefícios anual será usado para determinar os valores de cobertura.

Quando você cria um plano de benefícios que usa taxas baseadas em sexo ou idade, você deve inserir uma data de nascimento e um sexo para que o funcionário calcule o custo de benefício.

## <a name="configure-benefits-management"></a>Configurar Gerenciamento de benefícios

Antes de criar os planos de benefícios para seus funcionários, é necessário configurar as opções dos planos.

- [Definir parâmetros de gerenciamento de benefícios](hr-benefits-setup-parameters.md)
- [Configurar regras e opções de qualificação](hr-benefits-setup-eligibility-rules.md)
- [Configurar opções de qualificação para contato pessoal](hr-benefits-setup-contact-eligibility-options.md)
- [Criar opções de cobertura](hr-benefits-setup-coverage-options.md)
- [Definir frequência de pagamento](hr-benefits-setup-payment-frequencies.md)
- [Configurar tipos de eventos de vida](hr-benefits-setup-life-event-types.md)
- [Criar tipos de plano](hr-benefits-setup-plan-types.md)
- [Configurar códigos de motivo](hr-benefits-setup-reason-codes.md)
- [Configurar códigos de camada](hr-benefits-setup-tier-codes.md)
- [Configurar taxas](hr-benefits-setup-rates.md)
- [Configurar deduções](hr-benefits-setup-deductions.md)
- [Configurar dias de espera](hr-benefits-setup-waiting-days.md)
- [Configurar períodos de espera](hr-benefits-setup-waiting-periods.md)
- [Configurar regras de arredondamento](hr-benefits-setup-rounding-rules.md)
- [Criar categorias de emprego](hr-benefits-setup-employment-categories.md)
- [Configurar tipos de emprego](hr-benefits-setup-employment-types.md)
- [Configurar autoatendimento para funcionários](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a>Criar planos de benefícios

Esses artigos mostram como criar planos de benefícios, incluindo pacotes e programas de crédito flexível.

- [Configurar planos de benefícios](hr-benefits-plans-setup.md)
- [Configurar programas de crédito flexível](hr-benefits-plans-flex-credit-programs.md)

## <a name="process-benefit-plans"></a>Processar planos de benefícios

É necessário processar algumas alterações para ativá-las.

- [Processar qualificação da inscrição](hr-benefits-process-enrollment-eligibility.md)
- [Processar eventos de vida](hr-benefits-process-life-events.md)
- [Processar alterações de eventos de vida](hr-benefits-process-life-event-changes.md)
- [Processar qualificação para eventos de vida](hr-benefits-process-life-event-eligibility.md)
- [Processar alterações de taxa](hr-benefits-process-rate-changes.md)

