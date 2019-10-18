---
title: Novidades ou alterações no Dynamics 365 Talent (18 de junho de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 06/18/2019
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
ms.search.validFrom: 2019-06-18
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 059a0bad2f56b97a1708b64eab9d2adda6d2c8ad
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2019
ms.locfileid: "2009044"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-june-18-2019"></a>Novidades ou alterações no Dynamics 365 Talent (18 de junho de 2019)

[!include [banner](includes/banner.md)]

Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Alterações no Attract

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Attract.

## <a name="coming-soon-in-attract"></a>Em breve no Attract

### <a name="job-approvals-appear-on-the-home-page"></a>As aprovações de trabalho aparecem na página inicial

As aprovações aparecem em uma seção **Aprovações** no painel. Os aprovadores podem revisar suas aprovações em **Atribuída(s) a você**, que mostra a ID do trabalho, o cargo, outros aprovadores e a data em que o trabalho foi atribuído. Os usuários que enviam um trabalho para aprovação podem revisar seus trabalhos em **Solicitado por você**, que mostra os aprovadores que ainda precisam aprovar o trabalho enviado.

## <a name="changes-in-onboard"></a>Alterações de Integração

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Alterações no Core HR

As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2347.

### <a name="confirmation-of-course-participants-causes-an-error"></a>A confirmação dos participantes do curso gera um erro

A caixa de diálogo para imprimir o relatório sobre os participantes do curso foi removida. Este relatório não tem suporte no Talent.

### <a name="the-compensation-section-of-the-transfer-worker-page-isnt-available-in-some-scenarios"></a>A seção Remuneração da página Transferir trabalhador não está disponível em alguns cenários

Esta alteração permite que os usuários insiram dados de remuneração ao preencherem a página **Transferir trabalhador**.

## <a name="in-preview"></a>Em visualização

### <a name="preview-features-will-be-enabled-only-in-sandbox-environments"></a>Recursos de visualização serão habilitados somente em ambientes de área restrita

Para obter mais informações sobre como as alterações são publicadas, consulte [Provisionar o Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

Quando você provisiona uma nova instância do Talent, pode indicar se o tipo de instância é **Produção** ou **Área restrita**. O tipo de instância **Área restrita** permite testes antecipados de novos recursos. Todas as instâncias do Talent existentes serão atualizadas para o tipo de instância de **Produção**. Se desejar que uma de suas instâncias existentes sejam atualizadas para o tipo de instância **Área restrita**, fale com o [Suporte](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) para iniciar a solicitação de alteração.

### <a name="restrict-the-leave-types-in-time-off-requests"></a>Restringir os tipos de licença em solicitações de folga

As organizações podem oferecer muitos tipos de licenças aos funcionários. Entretanto, talvez não seja apropriado para os funcionários enviar solicitações de folga para alguns tipos de licença. Esses tipos de licença podem ser gerenciadas pelo RH. Nessa versão, você pode configurar para que tipos de licença os funcionários podem enviar solicitações de folga. 

## <a name="coming-soon-in-core-hr"></a>Em breve no Core HR

### <a name="common-data-service-entity-support-for-custom-fields"></a>A entidade Common Data Service oferece suporte a campos personalizados

As seguintes entidades darão suporte a campos personalizados: Código de ganhos de folha de pagamento e Ponto de referência de remuneração. 

### <a name="new-common-data-service-entities"></a>Novas entidades do Common Data Service

A entidade Códigos de motivo será adicionada ao Common Data Service.

### <a name="view-performance-information-for-direct-and-extended-reports-in-manager-self-service"></a>Exiba informações de desempenho para relatórios diretos e estendidos no autoatendimento de gerente

Uma nova opção permitirá que gerentes exibam o desempenho de seus relatórios diretos e de seus relatórios estendidos. Atualmente, os gerentes de linha podem atribuir e atualizar metas de desempenho e emitir novas revisões. Além disso, os gerentes diretos e seus funcionários podem manter e atualizar diários de desempenho para ajudar a garantir que o processo de avaliação de desempenho corra bem. Quando essa alteração for implementada, gerentes poderão exibir e manter informações de desempenho para seus relatórios estendidos além de seus relatórios diretos.

### <a name="print-performance-reviews"></a>Imprima avaliações de desempenho

Funcionários, gerentes e RH poderão imprimir a avaliação de desempenho de um funcionário.
