---
title: Novidades ou alterações no Dynamics 365 Talent (11 de junho de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 06/11/2019
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
ms.search.validFrom: 2019-06-11
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 20dc0768463d9a5d6762cb062deb0bdbe4d53fe3
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528660"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-june-11-2019"></a>Novidades ou alterações no Dynamics 365 Talent (11 de junho de 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Alterações no Attract

### <a name="search-engine-optimization-for-job-posts"></a>Otimização do mecanismo de pesquisa para lançamentos de trabalho

Após você ativar **Otimização do Mecanismo de Pesquisa** no Dynamics 365 Talent: Attract - Centro de administração, o Attract informará a interface de programação de aplicativos (API) de Indexação do Google para rastrear a página da Web sempre que você ativar e lançar um novo trabalho ou atualizar um trabalho existente. Assim, o trabalho aparecerá nos resultados de pesquisa do Google e de outros mecanismos de pesquisa.

Da mesma forma, sempre que você não lançar um trabalho, o Attract informará a API de Indexação. Assim, o trabalho não lançado deixará de aparecer nos resultados da pesquisa.

> [!NOTE]
> Os rastreadores da Web não têm um período definido para rastrear páginas da Web ou atualizar resultados de pesquisa.

## <a name="coming-soon-in-attract"></a>Em breve no Attract

### <a name="job-approvals-appear-on-the-home-page"></a>As aprovações de trabalho aparecem na página inicial

As aprovações aparecem em uma seção **Aprovações** no painel. Os aprovadores podem revisar suas aprovações em **Atribuída(s) a você**, que mostra a ID do trabalho, o cargo, outros aprovadores e a data em que o trabalho foi atribuído. Os usuários que enviam um trabalho para aprovação podem revisar seus trabalhos em **Solicitado por você**, que mostra os aprovadores que ainda precisam aprovar o trabalho enviado.

## <a name="changes-in-onboard"></a>Alterações de Integração

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Alterações no Core HR

As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2337.

### <a name="platform-update-27-for-finance-and-operations"></a>Atualização de plataforma 27 para o Finance and Operations

Para obter mais detalhes sobre a atualização de Plataforma 27 do Finance and Operations, consulte [Exibição de recursos na atualização de plataforma 27 do Dynamics 365 Finance and Operations (junho de 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-27).

### <a name="feature-management-workspace-in-talent"></a>Espaço de trabalho de gerenciamento de recursos no Talent

O espaço de trabalho **Gerenciamento de recursos** em **Administração do sistema** permite exibir, habilitar, desabilitar e agendar recursos que foram entregues em cada versão. Por padrão, os novos recurso estão desativados. Você pode usar o espaço de trabalho **Gerenciamento de recursos** para ativá-los e exibir a documentação deles.

### <a name="common-data-service-entity-support-for-custom-fields"></a>A entidade Common Data Service oferece suporte a campos personalizados

A entidade Agência emissora agora dá suporte a campos personalizados.

### <a name="new-common-data-service-entities"></a>Novas entidades do Common Data Service

A entidade Grupo de tarefas foi adicionada.

## <a name="in-preview"></a>Em visualização

### <a name="preview-features-will-be-enabled-only-in-sandbox-environments"></a>Recursos de visualização serão habilitados somente em ambientes de área restrita

Para obter mais informações sobre como as alterações são publicadas, consulte [Provisionar o Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

Quando você provisiona uma nova instância do Talent, pode indicar se o tipo de instância é Produção ou Área restrita. O tipo de instância Área restrita permite testes antecipados de novos recursos. Todas as instâncias do Talent existentes serão atualizadas para o tipo de instância de **Produção**. Se desejar que uma de suas instâncias existentes sejam atualizadas para o tipo de instância **Área restrita**, fale com o [Suporte](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) para iniciar a solicitação de alteração.

### <a name="restrict-the-leave-types-in-time-off-requests"></a>Restringir os tipos de licença em solicitações de folga

As organizações podem oferecer muitos tipos de licenças aos funcionários. Entretanto, talvez não seja apropriado para os funcionários enviar solicitações de folga para alguns tipos de licença. Esses tipos de licença podem ser gerenciadas pelo RH. Nessa versão, você pode configurar para que tipos de licença os funcionários podem enviar solicitações de folga. 

## <a name="coming-soon-in-core-hr"></a>Em breve no Core HR

### <a name="view-extended-information-about-report-performance-in-manager-self-service"></a>Exiba informações estendidas sobre o desempenho do relatório no autoatendimento de gerente

Uma nova opção permitirá que gerentes exibam o desempenho de seus relatórios diretos e de seus relatórios estendidos. Atualmente, os gerentes de linha podem atribuir e atualizar metas de desempenho e emitir novas revisões. Além disso, os gerentes diretos e seus funcionários podem manter e atualizar diários de desempenho para ajudar a garantir que o processo de avaliação de desempenho corra bem. Quando essa alteração for implementada, gerentes poderão exibir e manter informações de desempenho para seus relatórios estendidos além de seus relatórios diretos.

### <a name="print-performance-reviews"></a>Imprima avaliações de desempenho

Funcionários, gerentes e RH poderão imprimir a avaliação de desempenho de um funcionário.


[!INCLUDE[footer-include](../includes/footer-banner.md)]