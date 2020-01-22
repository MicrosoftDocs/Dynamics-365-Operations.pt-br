---
title: Novidades ou alterações no Dynamics 365 for Talent (10 de setembro de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 9/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-09-10
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 14e3482f366319851bed84b6cdd6135f0bcd1e80
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897319"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-september-10-2019"></a>Novidades ou alterações no Dynamics 365 for Talent (10 de setembro de 2019)

Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Alterações no Attract

### <a name="candidate-e-mail-login"></a>Login de email do candidato

Agora, os candidatos podem usar qualquer endereço de email para criar uma conta e fazer login em um site de carreiras do Talent para se candidatar a empregos e procurar seu status de solicitação de emprego. Além de já ser possível fazer logon no site de carreiras do Talent usando suas contas da rede social ou credenciais da organização.

### <a name="job-activation-and-posting"></a>Ativação e lançamento de trabalho

Fizemos algumas alterações na ativação e no lançamento de trabalhos. Você precisa ativar os trabalhos antes de publicá-los no site de carreiras do Talent ou em qualquer quadro de trabalhos externo, inclusive o LinkedIn ou o Broadbean.

## <a name="changes-in-onboard"></a>Alterações de Integração

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Alterações no Core HR

As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2482. Os números em parênteses em alguns cabeçalhos referem-se aos números de suporte no Microsoft Dynamics Lifecycle Services (LCS).

### <a name="you-can-enable-preview-features-in-sandbox-and-trial-environments"></a>Você pode ativar os recursos de visualização nos ambientes de área restrita e de avaliação

Quando você provisiona uma nova instância do Talent, pode especificar se o tipo de instância é Produção ou Área restrita. As instâncias do tipo Área restrita permitem testes antecipados de novos recursos. Se desejar que uma de suas instâncias existentes sejam atualizadas para o tipo de instância Área restrita, fale com o Suporte para iniciar a solicitação de alteração.

Para obter mais informações sobre como as alterações são publicadas, consulte [Provisionar o Talent](./provisioning-talent.md).

### <a name="platform-update-29"></a>Update 29 para plataforma

Para obter mais detalhes sobre a atualização de Plataforma 29, consulte [Exibição de recursos na atualização de plataforma 29 do Dynamics 365 for Finance and Operations (outubro de 2019)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-29).

### <a name="new-job-base-entity-available-in-data-management-framework-347202"></a>Nova entidade base de trabalho disponível na estrutura de gerenciamento de dados (347202)

Com esta versão, uma nova entidade base de trabalho está disponível para importação/exportação de dados. 

### <a name="worker-advanced-security-policy-incorrectly-displays-positions-in-position-hierarchy-354868"></a>A política de segurança avançada do trabalhador exibe incorretamente posições na Hierarquia de cargos (354868)

Com esta versão, os cargos não são mais exibidos abertos com um trabalhador "em branco" quando os usuários têm acesso restrito.

### <a name="job-form-close-box-wont-close-form-in-certain-situations-342467"></a>Caixa do formulário próximo trabalho não fechará o formulário em certas situações (342467)

Esta versão inclui uma alteração que permite ao formulário de trabalho se feche todos nos cenários.

### <a name="new-case-on-employee-record-is-locked-for-human-resources-manager-role-337111"></a>Novo caso no registro de funcionários está bloqueado para a função de gerente de Recursos Humanos (337111)

Com esta alteração, o formulário de gerenciamento de caso não está mais bloqueado ao acessá-lo no formulário do funcionário.

### <a name="employment-end-date-always-defaults-to-235959-351492"></a>A data de término do emprego sempre assume como padrão 23:59:59 (351492)

Com esta alteração, você pode alterar a data do emprego para um horário diferente de 23:59:59 ao encerrar um emprego manualmente.

### <a name="unable-to-set-up-expiration-date-on-an-earning-code-through-data-management-336604"></a>Não foi possível configurar a data de vencimento em um código de ganhos por meio do gerenciamento de dados (336604)

Nesta versão, você pode configurar códigos de ganhos que expiram por meio da entidade **PayrollWorkerPositionEarningCodeEntity**.

### <a name="employee-development-analytic-report-doesnt-display-data-348737"></a>O relatório analítico de desenvolvimento de funcionários não exibe dados (348737)

Na versão desta semana, a análise das habilidades dos funcionários foi atualizada para fornecer relatórios precisos.

### <a name="terms-of-employment-datetime-dont-default-to-beginning-of-day-349101"></a>A data/hora do contrato de trabalho não é padronizada para o início do dia (349101)

Com esta alteração, agora a data/hora de início é o início do dia e a data/hora de término é o final do dia.

### <a name="changing-the-employment-end-date-on-worker-action-form-displays-an-error-354092"></a>Alterar a data de término do emprego no formulário de ação do trabalhador exibe um erro (354092) 

Esta alteração corrige um problema ao modificar a data de término do emprego como parte da ação do trabalhador.

### <a name="applying-onboarding-checklists-across-companies-338433"></a>Aplicar listas de verificação de integração entre empresas (338433)

Agora, esta versão oferece a capacidade de aplicar listas de verificação para funcionários empregados em entidades legais que não sejam a entidade legal conectada.

## <a name="in-preview"></a>Em visualização

### <a name="streamlined-employee-entry-and-navigation"></a>Entrada e navegação simplificada de funcionário

Esta funcionalidade agora está disponível em ambientes de área restrita. Para ativar este recurso, navegue até **Administração do sistema > Links > Configuração > Parâmetros do sistema > Recursos de visualização**. Selecione **Formulário e a navegação aprimorados do Trabalhador**. Isso habilitará estas alterações para todos os usuários. Você pode desativar esta opção a qualquer momento.

Para obter mais informações, consulte [Entrada e navegação simplificada de funcionário](./streamlined-employee-entry.md).
