---
title: Perguntas frequentes sobre mesclagem de infraestrutura do Dynamics 365 Human Resources
description: Este artigo responde a perguntas frequentes sobre a mesclagem de infraestrutura para o Microsoft Dynamics 365 Human Resources e os aplicativos de finanças e operações.
author: twheeloc
ms.date: 08/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fd71d728f9c97dc9e2c44a7e7a0e773be891b818
ms.sourcegitcommit: 6d9fcb52d723ac5022a3002e0ced8e7b56e9bc2a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9203189"
---
# <a name="dynamics-365-human-resources-infrastructure-merge-faq"></a>Perguntas frequentes sobre mesclagem de infraestrutura do Dynamics 365 Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="what-is-dynamics-365-human-resources"></a>O que é o Dynamics 365 Human Resources?

O Microsoft Dynamics 365 Human Resources fornece ferramentas que ajudam as equipes de RH a aumentar a agilidade organizacional, transformar a experiência do funcionário e otimizar os programas de RH para criar um local de trabalho onde as pessoas e a empresa possam prosperar. Para saber mais sobre o Dynamics 365 Human Resources, consulte [Dynamics 365 Human Resources](https://dynamics.microsoft.com/human-resources/overview/).

- **Transformar experiências de funcionários.** Manter os principais executores permitindo que os gerentes e funcionários conectem experiências de auto-atendimento que impulsionam o envolvimento e o crescimento.
- **Otimizar os programas de RH.** Diminuir os custos operacionais e criar programas de licença e ausência, benefício e gerenciamento de remuneração centrada em pessoas.
- **Aumentar a agilidade organizacional.** Habilite o RH para operar com a destreza que os negócios exigem usando Dataverse e Microsoft Power Platform para centralizar os dados de pessoal e estender facilmente o Dynamics 365 Human Resources.
- **Descobrir as informações da força de trabalho.** Tome decisões controladas por dados com a capacidade de analisar e visualizar dados de pessoas em painéis avançados que estão disponíveis em qualquer dispositivo.

## <a name="value-and-benefits-of-the-infrastructure-merge"></a>Valor e benefícios da mesclagem de infraestrutura

### <a name="what-is-the-dynamics-365-human-resources-infrastructure-merge"></a>O que é a mesclagem de infraestrutura do Dynamics 365 Human Resources?

No momento, há dois conjuntos separados de recursos de RH em duas infraestruturas diferentes no Dynamics 365:

- **Dynamics 365 Human Resources** – Um aplicativo autônomo que é executado em uma infraestrutura independente. Quando esse aplicativo foi iniciado, a infraestrutura foi separada de outros aplicativos de operações do Dynamics 365. Nossos clientes usam esse aplicativo para aumentar a agilidade organizacional, otimizar programas de RH, transformar experiências de funcionários e obter informações da força de trabalho.
- **Módulo de RH** – um conjunto herdado de recursos que anteriormente era parte da unidade de manutenção de estoque (SKU) do licenciamento de Operações Unificadas. O módulo HR é executado na infraestrutura do aplicativo de finanças e operações, que é a mesma em todos os aplicativos de operações. Esses aplicativos incluem Dynamics 365 Finance, Dynamics 365 Project Operations e Dynamics 365 Supply Chain Management. Os clientes receberam os recursos de RH como parte do Dynamics 365 Finance ou Dynamics 365 Supply Chain Management.

Nos últimos três anos, a Microsoft não adicionou novos recursos nem aperfeiçoamentos ao módulo de RH. Em vez disso, nossos investimentos em roteiros concentram-se no aplicativo do Dynamics 365 Human Resources.

Ao colocar esses dois conjuntos de recursos na mesma infraestrutura, ajudaremos os clientes a obter os seguintes benefícios:

- Melhorias que foram adicionadas ao Dynamics 365 Human Resources ao longo dos últimos três anos, incluindo licença e ausência avançada, gerenciamento de benefícios e relatórios.
- Melhor extensibilidade por meio do Microsoft Power Platform e capacidade de estender a lógica comercial para personalizar páginas.
- Implantação, atualizações e manutenção aprimoradas que são consistentes em termos de gerenciamento do ciclo de vida do aplicativo (ALM), serviços do ciclo de vida, disponibilidade geográfica e muito mais.
- Mais inovações tecnológicas que a nossa equipe de engenharia usa serviços compartilhados, ferramentas e custos de plataforma reduzidos.

Essa transição afetará os clientes que estão usando o Dynamics 365 Human Resources ou o módulo de RH herdado.

## <a name="glossary-of-terms-used-in-this-faq"></a>Glossário dos termos usados nestas Perguntas frequentes

- **Dynamics 365 Human Resources** – Nosso produto atual e futuro que oferece recursos de RH ao mercado.
- **Módulo de RH** – um conjunto herdado de recursos que anteriormente foi licenciado com a oferta das Operações Unificadas. Os recursos são habilitados quando um cliente pertence ao Dynamics 365 Finance ou ao Dynamics 365 Supply Chain Management.
- **Infra-estrutura do aplicativo de finanças e operações** – a arquitetura de desenvolvimento usada pelo portfólio de operações, incluindo o Dynamics 365 Finance, Dynamics 365 Supply Chain Management e o Dynamics 365 Project Operations. Essa infraestrutura que será usada no futuro. Nestas Perguntas frequentes, o termo *infraestrutura mesclada* refere-se ao ambiente do aplicativo de finanças e operações.
- **Infraestrutura do Human Resources** – a arquitetura de desenvolvimento que foi usada historicamente para o aplicativo Dynamics 365 Human Resources. O projeto de mesclagem da infraestrutura colocará o Dynamics 365 Human Resources na infraestrutura do aplicativo de finanças e operações. A infraestrutura autônoma será descontinuada.

## <a name="general-questions-about-the-infrastructure-merge"></a>Perguntas gerais sobre a mesclagem de infraestrutura

### <a name="will-customers-lose-any-features-or-capabilities"></a>Os clientes perderão recursos ou funcionalidades?

Nosso objetivo é minimizar o impacto que essa transição tem nos clientes. Não vamos remover recursos nem funcionalidades. Haverá paridade funcional entre o Dynamics 365 Human Resources e o módulo de RH. Nos casos em que existe um recurso nas duas infraestruturas, a experiência do Dynamics 365 Human Resources será usada.

### <a name="will-the-user-experience-change"></a>A experiência será alterada?

A experiência do usuário será consistente com a experiência da plataforma padrão do Dynamics 365. Embora a experiência geral para o painel e os menus continuem parecidas, ela será alinhada com a experiência do aplicativo do Dynamics 365 Finance. A navegação incluirá módulos e espaços de trabalho, permitirá favoritos e muito mais. Os espaços de trabalho do Dynamics 365 Human Resources, como **Gerenciamento de pessoal** e **Pessoas** serão mesclados na infraestrutura dos aplicativos de finanças e operações. No futuro, novos recursos serão fornecidos por meio do gerenciamento de Recursos que permite que os clientes exibam novos recursos e decidam quais deles desejam usar. Para obter mais informações, consulte [Visão geral do gerenciamento de recursos](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e [Documentação da interface do usuário](../fin-ops-core/fin-ops/get-started/user-interface-elements.md?toc=/dynamics365/human-resources/toc.json).

### <a name="when-will-the-dynamics-365-human-resources-infrastructure-merge-be-completed"></a>Quando a mesclagem da infraestrutura do Dynamics 365 Human Resources será concluída?

A mesclagem de infraestrutura é acumulada em fases, de forma a fornecer aos clientes tempo para planejar e concluir as etapas necessárias. Começamos a lançar recursos no ciclo de lançamentos 2 do Dynamics 2021. Planejamos preencher todos os esforços de desenvolvimento de produtos deste projeto no final do ciclo de lançamentos 2 de 2022. Observe que as linhas do tempo estão sujeitas a alterações. Para obter informações atualizadas, consulte [planos de versão](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-finance).

### <a name="what-training-and-resources-will-be-available-to-help-with-the-infrastructure-merge"></a>Quais treinamentos e recursos estarão disponíveis para ajudar na mesclagem da infraestrutura?

Forneceremos documentação que descreve cada etapa do processo de mesclagem da infraestrutura em detalhes. Forneceremos recursos de treinamento adicionais, como vídeos e workshops, conforme a necessidade, para ajudar os clientes e parceiros com uma transição suave.

### <a name="will-there-be-changes-in-development-capabilities-after-the-infrastructure-merge-is-completed"></a>Ocorrerão alterações nos recursos de desenvolvimento depois que a mesclagem de infraestrutura for concluída?

Para saber mais sobre os recursos de desenvolvimento, consulte [Desenvolver e personalizar a home page](../fin-ops-core/dev-itpro/dev-tools/developer-home-page.md).

## <a name="feature-availability-questions"></a>Perguntas sobre disponibilidade de recurso

### <a name="will-the-linkedin-talent-hub-integration-work-on-the-finance-and-operations-infrastructure"></a>A integração do LinkedIn Talent Hub funcionará na infraestrutura do aplicativo de finanças e operações?

Não, a integração do LinkedIn Talent Hub não fará parte da infraestrutura mesclada. As APIs (interfaces de programação de aplicativo) públicas estão disponíveis para criar integrações com soluções de recrutamento e acompanhamento de candidatos. Os clientes que planejam usar o LinkedIn Talent Hub devem trabalhar com seu parceiro Microsoft para se integrarem usando as APIs fornecidas. Para obter mais informações sobre APIs de integração do ATS (Sistema de Acompanhamento de Candidatos), consulte [introdução à API de integração do Sistema de Acompanhamento de Candidatos](./hr-admin-integration-ats-api-introduction.md).

### <a name="will-the-capabilities-that-are-currently-available-only-in-dynamics-365-human-resources-for-example-leave-management-and-benefits-management-be-available-after-the-merge-is-completed"></a>Os recursos que estarão disponíveis no momento somente no Dynamics 365 Human Resources (por exemplo, gerenciamento de licença e gerenciamento de benefícios) estarão disponíveis após a conclusão da mesclagem?

Sim. Todos os recursos de aplicativos do Dynamics 365 Human Resources estão sendo trazidos para a infraestrutura de finanças e operações. Os recursos serão disponibilizados em uma abordagem em fases. Para obter informações atualizadas sobre a disponibilidade de recursos para a infraestrutura mesclada, examine regularmente os [planos de versão](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-finance).

### <a name="will-ceridian-integrations-with-dynamics-365-human-resources-be-available-after-the-infrastructure-merge-is-completed"></a>As integrações do Ceridian com o Dynamics 365 Human Resources estarão disponíveis após a conclusão da mesclagem da infraestrutura?

Ceridian está no processo de criação de uma integração V2 com o Dynamics 365 Human Resources que aproveita as APIs da Folha de Pagamento. A integração baseada no arquivo que existe atualmente no Dynamics 365 Human Resources não será migrada para a infraestrutura do aplicativo de finanças e operações. Para obter mais informações, consulte [Introdução à API da folha de pagamento](./hr-admin-integration-payroll-api-introduction.md).

### <a name="will-applicant-tracking-or-onboardingoffboarding-of-employees-functionality-be-included"></a>O rastreamento do candidato ou a integração/remoção da funcionalidade do funcionário serão incluídas?

Em versões anteriores, criamos a API de integração de ATS para permitir que parceiros e clientes criem integrações de ATS com o Human Resources. A funcionalidade adicional relacionada a ATS foi disponibilizada no ciclo1 de 2022. Continuaremos a melhorar essas APIs em versões futuras.

A funcionalidade de RH que existe no momento na infraestrutura do aplicativo de finanças e operações inclui algumas funcionalidades de gerenciamento de recrutamento que não existem no Dynamics 365 Human Resources. Quando a mesclagem da infraestrutura for concluída, esta funcionalidade ficará disponível a todos os clientes do Human Resources. Essa funcionalidade fornece funcionalidade de ATS leves. No entanto, não pretendemos expandir essa funcionalidade no futuro. Os clientes que exigem mais funcionalidade avançada podem aproveitar as integrações de ATS de parceiros. Para obter mais informações sobre APIs de integração do ATS (Sistema de Acompanhamento de Candidatos), consulte [introdução às APIs de integração do Sistema de Acompanhamento de Candidatos](./hr-admin-integration-ats-api-introduction.md).

### <a name="will-the-dynamics-ax-2012-upgrade-tools-be-used-to-upgrade-the-hr-module-in-ax-2012-to-the-dynamics-365-human-resources-app"></a>As ferramentas de atualização do Dynamics AX 2012 serão usadas para atualizar o módulo de RH no AX 2012 para o aplicativo Dynamics 365 Human Resources?

Sim. Uma atualização do Dynamics AX 2012 para o Dynamics 365 Human Resources usará o mesmo caminho de atualização e as mesmas ferramentas que são usadas para atualizar para a versão mais recente de outros aplicativos de operações do Dynamics 365, como Dynamics 365 Finance ou Dynamics 365 Supply Chain Management.

Para obter mais informações sobre a migração para a infraestrutura do aplicativo de finanças e operações, consulte [Perguntas frequentes sobre a migração do cliente do Human Resources](./customer-migration.md).
