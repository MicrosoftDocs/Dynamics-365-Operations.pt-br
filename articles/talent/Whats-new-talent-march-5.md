---
title: Novidades ou alterações no Dynamics 365 Talent (5 de março de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-03-05
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 115d7cd3d71eaddce2434cb1939c503d36bccdf8
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527281"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-march-5-2019"></a>Novidades ou alterações no Dynamics 365 Talent (5 de março de 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tópico descreve os recursos novos ou alterados no Talent.

## <a name="changes-in-attract"></a>Alterações no Attract

### <a name="extending-option-sets-in-attract"></a>Extensão dos conjuntos de opção no Attract

No Attract, há vários campos que são conjuntos de opções dentro do Common Data Service. Novas funcionalidades foram apresentadas para estender os conjuntos de opção, começando com os campos Motivo de **Rejeição**, **Tipo de emprego** e **Tipo de senioridade**.

> [!IMPORTANT]
> A postagem de trabalho na funcionalidade do LinkedIn requer o uso de campos **Tipo de emprego** e **Tipo de senioridade** na página **Detalhes de trabalho**. Os valores padrão nesses campos são compatíveis com LinkedIn e são exibidos quando o trabalho é postado. Se estiver postando trabalhos no LinkedIn e modificar os valores de conjunto de opção existentes para esses campos, o trabalho será postado, mas o LinkedIn não exibirá os valores **Tipo de trabalho** e **Tipo de senioridade** personalizados.

## <a name="changes-in-onboarding"></a>Alterações de Integração

### <a name="private-preview-for-onboard-teams"></a>Visualização privada de equipes de integração
Agora você pode facilmente compartilhar e colaborar em modelos entre toda a organização. Para obter mais informações, consulte [Compartilhar melhores práticas entre sua organização usando Equipes de integração](https://docs.microsoft.com/business-applications-release-notes/April19/dynamics365-talent/onboard/share-best-practices-teams).

### <a name="private-preview-for-assignee-placeholders"></a>Visualização privada dos espaços reservados do destinatário
Você pode enriquecer seus modelos atribuindo atividades a funções em vez de indivíduos. Funções são atribuídas a pessoas no momento da criação da guia. Para obter mais informações, consulte [Simplificar administração de guia atribuindo atividades a funções](https://docs.microsoft.com/business-applications-release-notes/April19/dynamics365-talent/onboard/assign-activities-roles).

## <a name="changes-in-core-hr"></a>Alterações no Core HR
**Compilação 8.1.2178**

### <a name="configure-workflow-to-auto-approve-or-follow-workflow-when-an-hr-or-line-manager-submits-or-updates-time-off-requests"></a>Configure fluxos de trabalho para aprovar automaticamente ou seguir fluxos de trabalho quando um RH ou gerente de linha enviar ou atualizar solicitações de folgas
Novas condições de fluxo de trabalho foram adicionadas para permitir que solicitações sejam aprovadas automaticamente se enviadas por um gerente de funcionário ou por um RH. Uma forma de obter essa aprovação automática em um fluxo de trabalho é habilitar uma ação automática na aprovação do fluxo de trabalho.

As condições que foram adicionadas incluem:

- Enviado por - Usado para avaliar o ID de usuário do sistema do usuário que enviou a solicitação para fluxo de trabalho.
- Enviado em nome de - Usado para avaliar se a solicitação foi enviada em nome de um trabalhador associado à solicitação.
- Enviado por recursos humanos - Usado para avaliar se o usuário do sistema que enviou a solicitação para o fluxo de trabalho está em uma função de Recursos Humanos.
- Enviado pelo gerente - Usado para avaliar se o usuário que enviou a solicitação para o fluxo de trabalho é um gerente de hierarquia de linha do trabalhador associado à solicitação.

### <a name="enable-employee-fixed-compensation-for-future-position-assignments"></a>Habilitar remuneração fixa de funcionário para atribuições de cargo futuras
É normal que funcionários entrem em uma organização com uma data de início futura. Esta alteração permite a definição de remuneração fixa para funcionários com atribuições de cargo futuras.

### <a name="position-payroll-fields-are-blank-when-editing-the-position"></a>Campos de posição de folha de pagamento estão em branco ao editar o cargo
Com esta alteração, ao solicitar alterações a posições existentes, os campos de folha de pagamento agora mudarão para padrão com valores atuais.

### <a name="other-miscellaneous-bug-fixes"></a>Outras correções de bugs diversos
Outras correções de bugs diversos estão incluídas nesta versão.

### <a name="upgrade-to-common-data-service"></a>Fazer upgrade para o Common Data Service
Os prazos finais para atualizar para o Common Data Service se aproximam rapidamente. Entre na central de administração do Power Apps para determinar se sua base de dados precisa ser atualizada. Para obter mais informações sobre os prazos finais e as etapas necessárias para atualizar, consulte [Fazer upgrade para o Common Data Service](https://docs.microsoft.com/common-data-service/upgradecds/introduction-upgrade-cds).

## <a name="coming-soon"></a>Em breve

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Segurança de compensação avançada (fixa e variável)
Em muitas organizações, gerentes de compensação e benefícios só podem acessar certos registros de compensação, como registros de funcionários executivos ou regionais. Com esta alteração, você pode gerenciar e manter os planos de compensação para populações de funcionário diferentes na organização. Planos fixos e variáveis podem receber funções de segurança, que determinarão o acesso de planos e os dados de funcionário relacionados aos planos, como salário ou registros de bônus. Apenas as funções com acesso determinado poderão processar compensação para esses funcionários.

###  <a name="platform-update-24-for-finance-and-operations"></a>Atualização de plataforma 24 para o Finance and Operations
Para obter detalhes adicionais sobre a atualização da Plataforma 24 do Finance and Operations, consulte [Novidades ou alterações na atualização da Plataforma 24 do Finance and Operations (março de 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24).
