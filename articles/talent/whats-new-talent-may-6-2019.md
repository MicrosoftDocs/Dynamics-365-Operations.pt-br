---
title: Novidades ou alterações no Dynamics 365 Talent (6 de maio de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 05/06/2019
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
ms.search.validFrom: 2019-05-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: f06d989ea4e927111729dfbd4bb7700745a16a54
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897502"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-may-6-2019"></a>Novidades ou alterações no Dynamics 365 Talent (6 de maio de 2019)

Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Alterações no Attract

### <a name="select-optional-documents-upon-offer-creation"></a>Selecione documentos opcionais até a criação da oferta

Ao selecionar um modelo de pacote de oferta, o Attract agora pede para você selecionar os documentos opcionais aplicáveis a partir desse modelo de pacote. É possível adicionar outros documentos opcionais ao preparar a oferta.

## <a name="changes-in-onboard"></a>Alterações de Integração

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Alterações no Core HR

As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2282. Os números em parênteses em alguns cabeçalhos referem-se aos números de suporte no Microsoft Dynamics Lifecycle Services (LCS).

### <a name="platform-update-26-for-finance-and-operations"></a>Atualização de plataforma 26 do Finance and Operations

Para obter detalhes adicionais sobre a Atualização de plataforma 26 do Finance and Operations, consulte [Recursos de visualização na atualização de plataforma 26 do Dynamics 365 Finance and Operations (maio de 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-26). 

### <a name="common-data-service-entity-support-for-custom-fields"></a>A entidade Common Data Service oferece suporte a campos personalizados

Na versão dessa semana, as entidades a seguir agora oferecem suporte aos campos personalizados: Beneficiar frequência de cálculo, Beneficiar taxa de cálculo, Beneficiar tipo, Calendário de trabalho, Calendário de trabalho de feriados, Ciclo de pagamento e Tipos de identificação de trabalhador.

### <a name="leave-mass-enrollment-changing-the-tier-basis-to-seniority-date-doesnt-refresh-the-initial-accrual-rate-318526"></a>Deixe a inscrição em massa, mudar a base de camada para "Aniversário de tempo de serviço" não atualiza a taxa inicial de competência (318526)

Quando você insere os funcionários em massa e muda a base de camada, a competência inicial agora reflete a base de camada que você selecionou.

### <a name="workflow-showing-duplicate-place-holders-313636"></a>Fluxo de trabalho exibindo espaços reservados duplicados (313636)

Alterações nesta versão eliminam a duplicação de espaços reservados quando as notificações de fluxo de trabalho são enviadas.

### <a name="dimension-fields-arent-updated-when-using-open-in-excel-176261"></a>Os campos de dimensão não serão atualizados ao usar “Abrir no Excel” (176261)

Com essa versão, agora você pode atualizar a dimensão financeira usando **Abrir no Excel** da página **Trabalhador**. 

### <a name="worker-address-created-in-common-data-service-isnt-synced-to-talent-317555"></a>O endereço de trabalhador criado em Common Data Service não é sincronizado com o Talent (317555)

Com esta alteração, os endereços criados no Common Data Service são atualizados no Talent: Core HR.


## <a name="in-preview"></a>Em visualização

### <a name="new-page-to-validate-position-hierarchy-data"></a>Nova página para validar dados de hierarquia de posição

Recursos humanos (RH) e administradores agora podem validar a hierarquia administrativa para quaisquer referências circulares que podem ter sido, inadvertidamente, importadas. Você pode acessar essa nova página em **Administração organizacional > Links > Posições > Validação de hierarquia de posição**.

### <a name="specify-reason-codes-on-leave-types"></a>Especifique códigos de motivo em tipos de licença

As organizações podem precisar de informações adicionais sobre solicitações de folga. Agora você pode especificar os códigos de motivo para os tipos de licença e permitir que os funcionários selecionem um código de motivo em suas solicitações de folga.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Exigir códigos de motivo para específicos tipos de licença em solicitações de folga

As organizações podem exigir códigos de motivo para tipos de licença específicos quando os funcionários enviam solicitações de folga. Essa necessidade pode existir por conta de uma política de empresa ou requisitos regulatórios. Agora você pode especificar que tipos de licença exigem um código de motivo e pode exigir que os funcionários informem um código de motivo para o tipo de licença em suas solicitações de folga.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Fornecer uma lista de transações de licença e de ausência para o RH

A habilidade de rastrear as folgas dos funcionários e entender como elas são calculadas não somente ajuda o RH a responder dúvidas dos funcionários, como também ajuda a garantir que os funcionários recebam prêmios de folga precisos. Agora o RH tem uma nova exibição em transações (subsídios, competências, ajustes e solicitações), para que a equipe do RH possa ver os motivos por trás dos saldos.

## <a name="coming-soon"></a>Em breve

### <a name="indicate-instance-type-when-provisioning-talent"></a>Indica o tipo da instância ao provisionar o Talent

A provisionar uma nova instância do Talent, poderá indicar se o tipo de instância é **Produção** ou **Área restrita**, para testes antecipados de novos recursos. Todas as instâncias do Talent existentes serão atualizadas para o tipo de instância de Produção. Se quiser que uma de suas instâncias existentes sejam atualizadas para o tipo de instância de Área restrita, entre em contato com o Suporte para iniciar a solicitação de alteração.
