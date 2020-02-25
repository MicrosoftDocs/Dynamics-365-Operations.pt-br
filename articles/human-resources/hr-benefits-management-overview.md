---
title: Visão geral do Gerenciamento de benefícios
description: Visão geral da versão prévia do recurso de Gerenciamento de benefícios no Dynamics 365 Human Resources. Ofereça opções de benefícios estendidos aos seus funcionários com uma experiência online fácil de usar.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 63db1b55bae9150dd87d9981136b96d72ffd0c59
ms.sourcegitcommit: 523049c363a999050c58d20695f1c7d151b3fd3e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029454"
---
# <a name="benefits-management-overview"></a>Visão geral do Gerenciamento de benefícios

[!include [banner](includes/preview-feature.md)]

Para permanecer em um mercado competitivo, é necessário oferecer um conjunto amplo de benefícios para atrair e reter os melhores funcionários. Além dos benefícios padrão, como plano de saúde e odontológico, ofereça serviços expandidos, como assistência à adoção, programas de recreação e auxílio-vestimenta. A versão prévia do recurso de Gerenciamento de benefícios do Microsoft Dynamics 365 Human Resources oferece uma solução flexível compatível com uma ampla variedade de opções de benefícios. O Human Resources também inclui uma experiência para funcionários fácil de usar e que mostra as ofertas.

- Os planos de benefícios aprimorados permitem criar e gerenciar planos de benefícios exclusivos e oferecem suporte a tabelas de taxas de benefícios complexas e camadas aninhadas. Você pode facilmente criar programas e pacotes de benefícios, além de regras de inscrição automática nos benefícios para facilitar a experiência dos funcionários.

- Os programas de crédito flexível permitem ratear para oferecer suporte à aposentadoria e outros eventos de vida.

- As regras de elegibilidade extensivas garantem a disponibilização dos benefícios apropriados para os funcionários certos.

- A inscrição online nos benefícios permite uma experiência fácil para os funcionários.

- O processamento de evento de vida qualificado é integrado ao Autoatendimento para funcionários e também oferece suporte para eventos de vida futuros.

Se deseja acessar os dados de demonstração, será necessário implementar novamente o ambiente de área restrita.

Você pode fornecer um feedback direto ou relatar problemas em: D365BenefitsPreview@microsoft.com.

## <a name="benefits-management-known-issues"></a>Problemas conhecidos do gerenciamento de benefícios

### <a name="eligibility-processing"></a>Processamento de elegibilidade

Ao executar a elegibilidade para benefícios que usam 1-5X Salário, % do Salário e o valor de cobertura do Valor Simples, é necessário definir a data dos **Detalhes dos benefícios** como a **Data de início do funcionário** no **Histórico de empregos**. Também é necessário incluir **Horas trabalhadas**, **Frequência de pagamento** e **Valor do salário de benefícios anual**. Se o trabalhador tiver uma remuneração fixa, insira **Horas trabalhadas** e **Frequência de pagamento**. O valor do salário anual será calculado. Se o funcionário for assalariado, não será necessário inserir **Horas trabalhadas**. Recomendamos que, ao criar novos trabalhadores, insira a remuneração fixa primeiro. Para atualizar o registro dos detalhes dos benefícios, navegue até **Trabalhador > Histórico do trabalhador > Detalhes do emprego**. Ajuste a data para a data de início do trabalhador.

### <a name="employee-self-service"></a>Autoatendimento para funcionários

O valor do funcionário não é calculado ao atualizar o valor da cobertura do seguro de vida. Por exemplo, quando um funcionário é oferecido a um plano de seguro de vida, ele pode selecionar até US$ 50.000 em cobertura a um custo de US$ 0,36 por US$ 1.000 de cobertura.  Quando o funcionário atualiza o valor da cobertura, o custo associado do funcionário permanece em zero.

Para um plano de benefícios que permite somente uma única seleção desse tipo de plano, o usuário receberá uma mensagem de erro se tentar cancelar um plano após selecioná-lo. Por exemplo, um usuário seleciona um plano médico e o coloca em seu carrinho. O usuário seleciona **Renunciar** a outro plano médico. O usuário receberá uma mensagem de erro.

## <a name="enable-benefits-management"></a>Habilitar o Gerenciamento de benefícios

O Gerenciamento de benefícios é uma versão prévia do recurso e está disponível somente em ambientes de **Área restrita**. Esses artigos descrevem como acionar a versão prévia de recursos no Human Resources. Eles também informam quais recursos existentes no Human Resources são substituídos pelo Gerenciamento de benefícios ou quais são desabilitados após ativar o Gerenciamento de recursos.

- [Gerenciar recursos](hr-admin-manage-features.md)
- [Recurso de visualização: Gerenciamento de benefícios](hr-admin-manage-features.md?preview-feature-benefits-management)

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
- [Criar planos de benefícios do trabalhador](hr-benefits-plans-worker.md)
- [Configurar programas de crédito flexível](hr-benefits-plans-flex-credit-programs.md)
- [Configurar eventos de vida futuros](hr-benefits-plans-future-life-events.md)

## <a name="process-benefit-plans"></a>Processar planos de benefícios

É necessário processar algumas alterações para ativá-las.

- [Processar qualificação da inscrição](hr-benefits-process-enrollment-eligibility.md)
- [Processar eventos de vida](hr-benefits-process-life-events.md)
- [Processar alterações de eventos de vida](hr-benefits-process-life-event-changes.md)
- [Processar qualificação para eventos de vida](hr-benefits-process-life-event-eligibility.md)
- [Processar alterações de taxa](hr-benefits-process-rate-changes.md)

