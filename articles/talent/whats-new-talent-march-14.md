---
title: Novidades ou alterações no Dynamics 365 Talent (14 de março de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/14/2019
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
ms.search.validFrom: 2019-03-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: a3bb5792e6395e6fe593691f050cae03362cf659
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528612"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-march-14-2019"></a>Novidades ou alterações no Dynamics 365 Talent (14 de março de 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tópico descreve os recursos novos ou alterados no Talent.

## <a name="changes-in-attract"></a>Alterações no Attract
Correção de bug menores estão incluídas nesta versão.

## <a name="changes-in-onboarding"></a>Alterações de Integração
Correção de bug menores estão incluídas nesta versão.

## <a name="changes-in-core-hr"></a>Alterações no Core HR
**Compilação 8.1.2186**

### <a name="performance-management-not-working-in-all-scenarios-when-using-duplicate-security-roles"></a>Gerenciamento de desempenho que não está funcionando em todos os cenários ao usar funções de segurança duplicadas
As alterações feitas nesta versão habilitam cenários de gerenciamento de desempenho ao usar as funções duplicadas ou prontas.

### <a name="mass-assign-checklists-to-workers"></a>Listas de verificação em massa para funcionários
Com essa alteração, agora você pode selecionar vários funcionários e realizar uma atribuição em massa de uma ou mais listas de verificação aos funcionários. 

### <a name="platform-update-24-for-finance-and-operations"></a>Atualização de plataforma 24 para o Finance and Operations
Para obter detalhes adicionais sobre a atualização da Plataforma 24 do Finance and Operations, consulte [Novidades ou alterações na atualização da Plataforma 24 do Finance and Operations (março de 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24). Alterações significativas na platform 24 incluem: 

- Os alertas estão habilitados no Talent.
- A barra de navegação atualizada agora se alinha com o cabeçalho do escritório.

### <a name="office-location-update-switches-the-context-to-the-top-of-the-worker-list"></a>A atualização local do escritório alterna o contexto para a parte superior da lista de trabalhadores
Com a versão atual, alterar o local do escritório não alternará mais o contexto do trabalhador que você estava vendo quando atribuiu um local do escritório.

### <a name="position-assignment-end-date-doesnt-display-correctly-on-worker-hire-and-transfer-actions"></a>A data final da atribuição de posição não é exibida corretamente em ações de transferência e contratação de trabalhador
As datas finais de atribuição de posição agora são exibidas corretamente com base no fuso horário preferencial do usuário quando ele usa as ações.

### <a name="common-data-service-job-entity-doesnt-allow-job-type-and-job-function-fields-to-update"></a>A entidade de trabalho do Common Data Service não permite que os campos Tipo de trabalho e Função de trabalho sejam atualizados
As entidades do Common Data Service agora são sincronizadas corretamente quando são atualizadas usando-se o Common Data Service.

## <a name="coming-soon"></a>Em breve

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Segurança de compensação avançada (fixa e variável)
Em muitas organizações, os gerentes de remuneração e benefícios só podem ter acesso a alguns tipos de registro de remuneração. Esses registros podem ser para funcionários executivos ou regionais. Com esta alteração, o RH pode gerenciar e manter os planos de remuneração para grupos de funcionários diferentes na organização. Você pode atribuir funções de segurança para planos fixos e variáveis que determinem o acesso a planos e dados de funcionário relacionados aos planos, como registros de bônus ou salário. Apenas as funções com o acesso permitido podem processar a remuneração desses funcionários.

###  <a name="email-support-for-alerts"></a>Suporte de email para alertas
Com a atualização de Plataforma 24 do Finance and Operations, os usuários podem criar regras de alerta que expedem automaticamente notificações por email a contatos quando disparadas por um evento.

### <a name="duplicate-employee-check-interface-changes"></a>Verificações de funcionários duplicados: alterações da interface
Com esta alteração, as duplicatas são detectadas conforme você digita nos campos de nome, e um status exibe quantos foram localizados. Você pode selecionar o link fornecido para abrir uma nova página a fim de avaliar se deve usar ou não a correspondência detectada. As duplicatas não são abertas automaticamente para evitar a interrupção da entrada de dados.
