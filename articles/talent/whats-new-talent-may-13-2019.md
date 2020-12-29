---
title: Novidades ou alterações no Dynamics 365 Talent (13 de maio de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 05/13/2019
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
ms.search.validFrom: 2019-05-13
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 11c9f03f4b3915d81b624115a1d97a0c7bc31709
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529723"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-may-13-2019"></a>Novidades ou alterações no Dynamics 365 Talent (13 de maio de 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Talent.

## <a name="coming-soon-in-attract"></a>Em breve no Attract

### <a name="job-approvals-on-home-page"></a>Aprovações de trabalho na página inicial

As aprovações aparecem em uma seção **Aprovações** no painel. Os aprovadores podem revisar suas aprovações em **Atribuída(s) a você**, que exibe a ID do trabalho, título, outros aprovadores e a data atribuída. Os usuários que enviam um trabalho para aprovação podem revisar seus trabalhos em **Solicitado por você**, que exibe os aprovadores que ainda precisam aprovar o trabalho enviado.

## <a name="changes-in-onboard"></a>Alterações de Integração

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Alterações no Core HR

As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2297. Os números em parênteses em alguns cabeçalhos referem-se aos números de suporte no Microsoft Dynamics Lifecycle Services (LCS).

### <a name="indicate-instance-type-when-provisioning-talent"></a>Indica o tipo da instância ao provisionar o Talent

Ao provisionar uma nova instância do Talent, você poderá indicar se o tipo de instância é **Produção** ou **Área restrita**, para testes antecipados de novos recursos. Todas as instâncias do Talent existentes serão atualizadas para o tipo de instância de **Produção**. Se quiser que uma de suas instâncias existentes sejam atualizadas para o tipo de instância de **Área restrita**, entre em contato com o [Suporte](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) para iniciar a solicitação de alteração.

### <a name="common-data-service-entity-support-for-custom-fields"></a>A entidade Common Data Service oferece suporte a campos personalizados

Na versão dessa semana, as entidades do Common Data Service a seguir agora oferecem suporte aos campos personalizados: Emprego, Frequência de cálculo de benefícios, Taxa de cálculo de benefícios, Calendário de trabalho de feriados e Tipo de identificação.

### <a name="common-data-service-integration-page"></a>Página de integração ao Common Data Service

Essa versão fornece uma nova opção em **Administração do sistema > Links > Integrações > Configuração do Common Data Service**. A opção **Configuração do Common Data Service** fornece a um administrador ou administrador de gerenciamento de dados alguma flexibilidade e insights com o Common Data Service. Com essa opção, você pode habilitar ou desabilitar a integração ao Common Data Service com uma instância do Talent e visualizar os detalhes de sincronização entre a instância do Talent e o Common Data Service.

### <a name="import-performance-data-with-final-employee-rating-316710"></a>Importar dados de desempenho com classificação final do funcionário (316710)

Nesta versão, você pode importar dados históricos de classificação de funcionários. O campo **FinalEmployeeRatingId** agora tem permissão de gravação.

### <a name="cant-create-worker-address-in-common-data-service-and-sync-it-with-talent-317555"></a>Não é possível criar o endereço do trabalhador no Common Data Service e sincronizá-lo com o Talent (317555)

Essa alteração permite que os dados de endereço criados no Common Data Service sejam sincronizados com o Talent.

## <a name="in-preview"></a>Em visualização

### <a name="new-page-to-validate-position-hierarchy-data"></a>Nova página para validar dados de hierarquia de posição

Recursos humanos (RH) e administradores podem validar a hierarquia administrativa para quaisquer referências circulares que podem ter sido, inadvertidamente, importadas. Você pode acessar essa nova página em **Administração organizacional > Links > Posições > Validação de hierarquia de posição**.

### <a name="specify-reason-codes-on-leave-types"></a>Especifique códigos de motivo em tipos de licença

As organizações podem precisar de informações adicionais sobre solicitações de folga. Agora você pode especificar os códigos de motivo para os tipos de licença e permitir que os funcionários selecionem um código de motivo em suas solicitações de folga.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Exigir códigos de motivo para específicos tipos de licença em solicitações de folga

As organizações podem exigir códigos de motivo para tipos de licença específicos quando os funcionários enviam solicitações de folga. Essa necessidade pode existir por conta de uma política de empresa ou requisitos regulatórios. Você pode especificar que tipos de licença exigem um código de motivo e pode exigir que os funcionários informem um código de motivo para o tipo de licença em suas solicitações de folga.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Fornecer uma lista de transações de licença e de ausência para o RH

A habilidade de rastrear as folgas dos funcionários e entender como elas são calculadas não somente ajuda o RH a responder dúvidas dos funcionários, como também ajuda a garantir que os funcionários recebam prêmios de folga precisos. Agora o RH tem uma nova exibição em transações (subsídios, competências, ajustes e solicitações), para que a equipe do RH possa ver os motivos por trás dos saldos de folgas.
