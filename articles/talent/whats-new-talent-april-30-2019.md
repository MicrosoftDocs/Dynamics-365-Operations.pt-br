---
title: Novidades ou alterações no Dynamics 365 Talent (30 de abril de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/30/2019
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
ms.search.validFrom: 2019-04-30
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 38158948dbcf8966edf49bcce5b1e5da7eddb8dc
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/24/2019
ms.locfileid: "2026020"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-30-2019"></a>Novidades ou alterações no Dynamics 365 Talent (30 de abril de 2019)

[!include [banner](includes/banner.md)]

Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Alterações no Attract

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Alterações de Integração

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Alterações no Core HR

As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2270. Os números em parênteses em alguns cabeçalhos referem-se aos números de suporte no Microsoft Dynamics Lifecycle Services (LCS).

### <a name="provide-feedback"></a>Fornecer comentários

A opção para fornecer comentários está localizada no menu **Ajuda** (**?**) no Talent. Esse menu fornece acesso aos seguintes recursos:

- Comentários
- Ajuda
- Introdução
- Suporte
- Ideias
- Sobre

### <a name="improvements-to-the-user-interface-for-duplicate-employee-detection"></a>Melhorias na interface de usuário para detecção de funcionários duplicados

Devido a essa alteração, as duplicatas agora são detectadas conforme você define os campos de nome, e um indicador de status exibe o número de duplicatas que foram detectadas. Um link que é fornecido abre uma página onde você pode avaliar se deve usar uma das duplicatas. Para evitar a interrupção de entrada de dados, a página duplicada não é aberta automaticamente. Você deve selecionar o link para abrir a página.

### <a name="common-data-service-entity-support-for-custom-fields"></a>A entidade Common Data Service oferece suporte a campos personalizados

Na versão dessa semana, as entidades a seguir agora oferecem suporte a campos personalizados: emprego, tipo de benefício e ciclo de pagamento.

### <a name="an-error-occurs-when-an-off-boarding-checklist-is-assigned-299877"></a>Um erro ocorre quando uma lista de verificação transferência é atribuída (299877)

Essa alteração corrige uma mensagem de erro que aparece quando você atribui uma lista de verificação offboarding a um trabalhador fora do processo de demissão.

### <a name="the-exited-workers-link-opens-the-wrong-worker-309939"></a>O link dos funcionários que saíam é aberto no trabalhador errado (309939)

Essa alteração corrige um problema que ocorre quando você contrata novamente um funcionário de outra entidade legal e tenta ir para o trabalhador a partir de uma lista de trabalhadores que saíram.

### <a name="the-employee-self-service-compensation-card-doesnt-show-summary-values-when-advanced-security-is-turned-on-315231"></a>O cartão de remuneração de autoatendimento para funcionário não mostrará valores resumidos quando a segurança avançada é ativada (315231)

Essa alteração corrige um problema que acontece quando você usa segurança de remuneração avançada. Quando a segurança avançada está ativa, o autoatendimento de funcionário agora exibe os valores de remuneração resumidos para funcionários e gerentes. Antes dessa alteração, os valores resumidos aparecem como 0 (zero).

### <a name="if-a-position-without-a-title-is-created-in-common-data-service-no-position-is-created-in-talent-314562"></a>Se uma posição sem um título é criada no Common Data Service, nenhuma posição é criada no Talent (314562)

As alterações dessa semana corrigem um problema que ocorre quando você cria posições no Common Data Service, mas não oferece um título.

### <a name="error-message-in-performance-journal-entries-in-employee-self-service-314134"></a>Mensagem de erro sobre entradas de diário de desempenho no autoatendimento de funcionário (314134)

Essa alteração corrige um problema que ocorre quando você anexa objetivos de desempenho a entradas de diário de desempenho no autoatendimento do funcionário.

## <a name="in-preview"></a>Em visualização

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Permitir que os códigos de motivo sejam especificados nos tipos de licença

As organizações podem precisar de informações adicionais sobre solicitações de folga. Agora você pode especificar os códigos de motivo para os tipos de licença e permitir que os funcionários selecionem um código de motivo em suas solicitações de folga.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Exigir códigos de motivo para específicos tipos de licença em solicitações de folga

As organizações podem exigir códigos de motivo para tipos de licença específicos quando os funcionários enviam solicitações de folga. Essa necessidade pode existir por conta de uma política de empresa ou requisitos regulatórios. Agora você pode especificar que tipos de licença exigem um código de motivo e pode exigir que os funcionários informem um código de motivo para o tipo de licença em suas solicitações de folga.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Fornecer uma lista de transações de licença e de ausência para o RH

A habilidade de rastrear as folgas dos funcionários e entender como elas são calculadas não somente ajuda o Recursos Humanos (RH) a responder dúvidas dos funcionários, como também ajuda a garantir que os funcionários recebam prêmios de folga precisos. Agora o RH tem uma nova exibição em transações (subsídios, competências, ajustes e solicitações), para que a equipe do RH possa ver os motivos por trás dos saldos.

## <a name="coming-soon"></a>Em breve

### <a name="email-support-for-alerts"></a>Suporte de email para alertas

Na atualização de plataforma 26 do Finance and Operations, os usuários podem criar regras de alerta que enviem automaticamente notificações por email a contatos quando notificações são disparadas por um evento.
