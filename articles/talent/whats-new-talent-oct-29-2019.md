---
title: Novidades ou alterações no Dynamics 365 Talent (29 de outubro de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/29/2019
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
ms.search.validFrom: 2019-10-29
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 09d53c82b4244f20d0d7f301691b01263258a32f
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529675"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-29-2019"></a>Novidades ou alterações no Dynamics 365 Talent (29 de outubro de 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Alterações no Attract

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Alterações de Integração

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Alterações no Core HR

As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2586. Os números em parênteses em alguns cabeçalhos referem-se aos números de suporte no Microsoft Dynamics Lifecycle Services (LCS).

### <a name="delete-parties-with-no-roles-should-be-on-by-default-371233"></a>Excluir participantes sem funções deve estar ativado por padrão (371233)

Quando você provisiona um novo ambiente no Talent, **Excluir participantes se não houver funções** é ativado por padrão. Quando você exclui um trabalhador, o participante associado ao trabalhador não é removido, a menos que essa configuração esteja ativada. Essa alteração limitará os registros duplicados no catálogo de endereços global quando você precisar importar, alterar ou reimportar trabalhadores.

### <a name="draft-and-cancelled-leave-requests-should-be-allowed-to-be-deleted-in-common-data-service-376999"></a>As solicitações de licença em rascunho ou canceladas devem poder ser excluídas no Common Data Service (376999)

Com essa alteração, agora você pode excluir solicitações de licença com um status **Rascunho** ou **Cancelada** no Common Data Service.

### <a name="additional-list-values-in-custom-fields-arent-reflected-in-common-data-service-after-clicking-apply-on-the-custom-fields-form-379599"></a>Os valores de lista adicionais em campos personalizados não são refletidos no Common Data Service após clicar em Aplicar ao formulário Campos personalizados (379599)

Quando você adicionar novos valores de lista a um campo personalizado existente que já foi sincronizado com o Common Data Service, agora eles estão disponíveis no Common Data Service depois que você aplicar as alterações ao formulário **Campos personalizados**.

### <a name="apply-onboarding-checklists-across-legal-entities-when-more-than-one-employment-exists-371270"></a>Aplicar listas de verificação de integração em entidades legais quando houver mais de um emprego (371270)

Na versão desta semana, é possível aplicar listas de verificação a funcionários com mais de um emprego em **formulário Trabalhador > Listas de verificação**.

### <a name="benefits-open-enrollment-preview-feature-has-been-removed"></a>A versão prévia do recurso de inscrição aberta de benefícios foi removida

Junto com o comunicado na postagem do blog [Investimentos estratégicos em Core HR levam à excelência operacional](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence), a Microsoft removeu o recurso de inscrição aberta de benefícios da versão prévia pública. Uma nova funcionalidade será lançada no futuro. O uso em produção do recurso de inscrição aberta de benefícios não tem suporte.

## <a name="coming-soon"></a>Em breve

### <a name="print-performance-reviews"></a>Imprima avaliações de desempenho

Consulte [Revisões de desempenho de impressão](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) no plano da onda 2 da versão 2019 do Dynamics 365.

### <a name="feature-management-workspace"></a>Espaço de trabalho do gerenciamento de recursos

Os recursos são adicionados e atualizados em cada versão. A experiência de gerenciamento de recursos fornece um espaço de trabalho no qual você pode exibir uma lista dos recursos que foram entregues em cada versão. Por padrão, os novos recurso estão desativados. Você pode usar o espaço de trabalho para ativá-los e exibir a documentação deles.

Para saber mais sobre as mudanças que acompanham o gerenciamento de recursos, consulte [Visão geral do gerenciamento de recursos](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview)


[!INCLUDE[footer-include](../includes/footer-banner.md)]