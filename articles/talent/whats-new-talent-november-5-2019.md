---
title: Novidades ou alterações no Dynamics 365 Talent (5 de novembro de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 11/05/2019
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
ms.search.validFrom: 2019-11-05
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 48de07178acfaccf11e0a02b2848bf24e6ccc117
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2896764"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-november-5-2019"></a>Novidades ou alterações no Dynamics 365 Talent (5 de novembro de 2019)

Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Alterações no Attract

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Alterações de Integração

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Alterações no Core HR

As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2598. Os números em parênteses em alguns cabeçalhos referem-se aos números de suporte no Microsoft Dynamics Lifecycle Services (LCS).

### <a name="copy-a-core-hr-instance"></a>Copiar uma instância do Core HR

Na versão desta semana, é possível usar o Microsoft Dynamics Lifecycle Services (LCS) para copiar um banco de dados do Microsoft Dynamics 365 Talent: Core HR para um ambiente de área restrita. Se houver outro ambiente de área restrita, você também poderá copiar o banco de dados daquele ambiente para um ambiente de área restrita direcionado. Para obter mais informações, consulte:

- [Gerenciamento de ambiente mais amplo](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/broader-environment-management) no plano da onda 2 da versão 2019 do Dynamics 365.

- [Copiar uma instância Core HR](hr-copy-instance.md) na documentação do Talent

### <a name="common-data-service-integration-batch-jobs-arent-created-when-common-data-service-integration-is-enabled-388030"></a>Os trabalhos em lotes da integração do Common Data Service não são criados quando a integração do Common Data Service está habilitada (388030)

Esta alteração criará trabalhos em lotes para a integração do Common Data Service quando ele estiver habilitado.

### <a name="the-hcmpersonimageentity-doesnt-resize-the-person-image-when-uploaded-369469"></a>A HcmPersonImageEntity não redimensiona a imagem da pessoa no upload (369469)

A versão desta semana altera a forma como as imagens são redimensionadas para melhorar o desempenho quando importadas por meio do gerenciamento de dados.

### <a name="a-positions-available-for-assignment-date-can-be-earlier-than-the-activation-date-340103"></a>Uma Data disponível para atribuição da posição pode ser anterior à Data de ativação (340103)

Com essa alteração, um aviso será exibido se você selecionar uma **Data disponível para atribuição** anterior à **Data de ativação** da posição.

### <a name="cant-create-a-compensation-change-request-in-employee-self-service-for-step-based-plans-376872"></a>Não é possível criar uma solicitação de alteração de compensação no auto-atendimento do funcionário para os planos baseados em etapas (376872)

Essa versão corrige um problema na solicitação de alterações de compensação por meio do auto-atendimento para funcionário em planos baseados em etapas. 

### <a name="reason-code-doesnt-sync-to-common-data-service-if-the-description-is-longer-than-30-characters-core-hr-allows-60-352682"></a>O código do motivo não será sincronizado com o Common Data Service se a descrição tiver mais de 30 caracteres, o Core HR permite 60 (352682)

Com essa alteração, os códigos de motivo com mais de 30 caracteres serão atualizados no Common Data Service. As alterações feitas no Common Data Service também serão refletidas no Talent.

### <a name="address-integration-from-talent-to-finance-and-operations-351961"></a>Integração de endereço do Talent ao Finance and Operations (351961)

Essa versão corrige um problema em que os endereços atualizados no Talent não estavam sendo atualizados no Finance and Operations. As alterações feitas nos blocos de endereço serão atualizadas agora.

## <a name="coming-soon"></a>Em breve

### <a name="print-performance-reviews"></a>Imprima avaliações de desempenho

Consulte [Revisões de desempenho de impressão](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) no plano da onda 2 da versão 2019 do Dynamics 365.

### <a name="feature-management-workspace"></a>Espaço de trabalho do gerenciamento de recursos

Os recursos são adicionados e atualizados em cada versão. A experiência de gerenciamento de recursos fornece um espaço de trabalho no qual você pode exibir uma lista dos recursos que foram entregues em cada versão. Por padrão, os novos recurso estão desativados. Você pode usar o espaço de trabalho para ativá-los e exibir a documentação deles.

Para saber mais sobre as mudanças que acompanham o gerenciamento de recursos, consulte [Visão geral do gerenciamento de recursos](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview)
