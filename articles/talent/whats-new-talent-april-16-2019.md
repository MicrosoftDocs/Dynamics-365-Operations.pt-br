---
title: Novidades ou alterações no Dynamics 365 Talent (16 de abril de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/16/2019
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
ms.search.validFrom: 2019-04-16
ms.dyn365.ops.version: Talent
ms.openlocfilehash: a37436eb15ee4c561d5d0c15c90e37815cb80860
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897916"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-16-2019"></a>Novidades ou alterações no Dynamics 365 Talent (16 de abril de 2019)

Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Alterações no Attract

### <a name="process-auditing"></a>Processar auditoria

Agora você pode rastrear as alterações feitas a candidatos, oportunidades de emprego e solicitações de emprego. Para obter mais informações, consulte [Rastrear alterações nos dados de recrutamento](process-auditing.md).

## <a name="changes-in-onboard"></a>Alterações de Integração

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Alterações no Core HR

As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2239. Números entre parênteses referem-se a números no Lifecycle Services (LCS).

### <a name="compensation-region-compensation-level-benefit-option-and-skill-type-entities-in-common-data-service-updated-to-include-customer-field-support"></a>Região de compensação, nível de compensação, opção de benefício e entidades de tipo de habilidade no Common Data Service atualizado para incluir suporte ao campo do cliente

Com essa versão, essas entidades do Common Data Service foram atualizadas para incluir a capacidade de incluir campo personalizado adicionado por meio do Talent: Core HR.

### <a name="new-common-data-service-entity-support-for-compensation-vesting-rules-compensation-variable-plan-variable-compensation"></a>Novo suporte de entidade Common Data Service para: regras de benefício proporcional diferido de remuneração, plano de remuneração variável, remuneração variável

Com essa versão, entidades de regras de benefício proporcional diferido de remuneração, plano de remuneração variável, remuneração variável foram adicionadas ao Common Data Service. Essas entidades também oferecem suporte a campos personalizados adicionados por meio do Talent: Core HR.

### <a name="powerbi-refresh-issues-314342"></a>Problemas de atualização PowerBI (314342)

Esta alteração corrige um problema com os relatórios do PowerBI, atualizando corretamente.

### <a name="unable-to-click-directly-through-on-transition-tasks-in-employee-self-service-303309"></a>Não foi possível clicar diretamente por meio das tarefas de transição no autoatendimento do funcionário (303309)

Esta alteração permite que os usuários com a função de funcionário selecionem e atualizem tarefas de transação a partir da lista de tarefas do Talent.

### <a name="performance-feedback-email-message-updated-309615"></a>Mensagem de e-mail de comentários de desempenho atualizada (309615)

Com esta alteração, uma mensagem de confirmação é exibida quando os comentários são enviados com sucesso.

### <a name="missing-tables-in-word-template-308048"></a>Tabelas ausentes no modelo do Word (308048)

Com esta alteração, ao criar um modelo do Word com informações do funcionário e de habilidade, apenas as habilidades do funcionário selecionado aparecem no documento Word.

### <a name="when-applying-an-offboarding-checklist-an-error-is-displayed-299877"></a>Ao aplicar uma lista de verificação offboarding um erro é exibido. (299877)

Essa alteração corrige um problema ao aplicar uma lista de verificação offboarding diretamente do formulário de trabalho.

## <a name="in-preview"></a>Em visualização

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Permitir que os códigos de motivo sejam especificados nos tipos de licença

As organizações podem precisar de informações adicionais sobre solicitações de folga. Agora você pode especificar os códigos de motivo para os tipos de licença e permitir que os funcionários selecionem um código de motivo em suas solicitações de folga.

### <a name="require-reason-codes-for-certain-leave-types-on-time-off-requests"></a>Exigir códigos de motivo para determinados tipos de licença em solicitações de folga

As organizações podem exigir códigos de motivo para tipos de licença específicos quando os funcionários enviam pedidos de folga. Isso pode ser devido a uma diretiva da empresa ou a requisitos regulatórios. Agora você pode especificar que tipos de licença exigem um código de motivo e pode exigir que os funcionários informem um código de motivo para o tipo de licença em suas solicitações de folga.

### <a name="provide-leave-and-absence-transaction-list-for-hr"></a>Fornecer a lista de transações de licença e de ausência para o RH

Monitorar as folgas dos funcionários e entender como elas são calculadas não somente ajuda o RH a responder dúvidas dos funcionários, como também garante que os funcionários recebam prêmios de folga precisos. Agora o RH tem uma nova exibição em transações (subsídios, competências, ajustes e solicitações) para considerar os motivos por trás dos saldos.

## <a name="coming-soon"></a>Em breve

### <a name="improvements-to-the-user-interface-for-duplicate-employee-check"></a>Melhorias na interface de usuário para verificação de funcionários duplicados

Com esta alteração, as duplicatas são detectadas conforme você digita nos campos de nome, e um status exibe o número de duplicatas localizado. Você pode selecionar o link fornecido para abrir uma nova página a fim de avaliar se deve usar ou não a correspondência detectada. Para evitar a interrupção da entrada de dados, as duplicatas não são abertas automaticamente.

### <a name="email-support-for-alerts"></a>Suporte de email para alertas

Com a atualização de plataforma 25 do Finance and Operations, os usuários podem criar regras de alerta que enviem automaticamente notificações por email a contatos quando notificações são disparadas por um evento.


