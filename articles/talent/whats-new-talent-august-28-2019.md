---
title: Novidades ou alterações no Dynamics 365 for Talent (27 de agosto 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 8/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: andreabichsel
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-08-27
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 1f19049b362070e2573db769bf7070ace0028406
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3005931"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-august-27-2019"></a>Novidades ou alterações no Dynamics 365 for Talent (27 de agosto 2019)

Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Alterações no Attract

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Alterações de Integração

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Alterações no Core HR

As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2447. Os números em parênteses em alguns cabeçalhos referem-se aos números de suporte no Microsoft Dynamics Lifecycle Services (LCS).

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Os recursos de visualização estão habilitados somente em instâncias da área restrita

Quando você provisiona uma nova instância do Talent, pode especificar se o tipo de instância é Produção ou Área restrita. As instâncias do tipo Área restrita permitem testes antecipados de novos recursos. Todas as instâncias do Talent existentes serão atualizadas para o tipo de instância de Produção. Se desejar que uma de suas instâncias existentes sejam atualizadas para o tipo de instância Área restrita, fale com o Suporte para iniciar a solicitação de alteração.

Para obter mais informações sobre como as alterações são publicadas, consulte [Provisionar o Talent](./provisioning-talent.md).

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Exiba informações estendidas de desempenho no autoatendimento de gerente

Uma nova opção permitirá que gerentes exibam o desempenho de seus relatórios diretos e de seus relatórios estendidos. Atualmente, os gerentes de linha podem atribuir e atualizar metas de desempenho e emitir novas revisões. Além disso, os gerentes diretos e seus funcionários podem manter e atualizar diários de desempenho para ajudar a garantir que o processo de avaliação de desempenho corra bem. Quando essa alteração for implementada, gerentes poderão exibir e manter informações de desempenho para seus relatórios estendidos além de seus relatórios diretos.

### <a name="deleting-legal-entities-isnt-allowed-if-employees-exist-within-the-company-339849"></a>Não é permitido excluir entidades legais se existirem funcionários na empresa (339849)

Com essa alteração, você não poderá remover ou excluir empresas se existirem funcionários e outros dados relacionados para a entidade legal.

### <a name="compensation-management-business-intelligence-analytics-dont-match-on-the-compensation-workspace-322493"></a>As análises de business intelligence de gerenciamento de compensação não correspondem no espaço de trabalho de compensação (322493)

Nesta versão, as análises de compensação foram ajustadas para refletir com precisão os planos atribuídos aos funcionários.

### <a name="workflow-placeholder-company-displays-dat-when-hiring-employees-through-workflow-343905"></a>O espaço reservado do fluxo de trabalho %company% exibe DAT ao contratar funcionários por meio do fluxo de trabalho (343905)

Com esta versão, o espaço reservado da empresa exibe a entidade legal que está associada ao emprego do novo funcionário.

### <a name="the-cdsjobposition-entity-displays-an-error-when-valid-to-date-is-set-349387"></a>A entidade CDSJobPosition exibe um erro quando a data válida é configurada (349387)

Nesta versão, as fontes de dados dos **Detalhes do cargo** e da **Duração do cargo** na entidade **CDSJobPosition** permitem edições do Common Data Service nos campos **Data de efetivação**. 

### <a name="for-employee-termination-the-last-day-worked-is-populated-on-assignment-end-date-332496"></a>Para a rescisão de funcionário, o último dia trabalhado é preenchido na Data final da atribuição (332496)

Agora, esta alteração padroniza o cargo **Data final da atribuição** como a **Data final do emprego**. É possível alterar esses padrões ao inserir dados.

### <a name="legal-entities-arent-limited-with-hire-338871"></a>As entidades legais não se limitam à contratação (338871)
 
Esta alteração restringe o processo de contratação para mostrar apenas as entidades legais às quais o usuário tem acesso.  

## <a name="in-preview"></a>Em visualização

### <a name="streamlined-employee-entry-and-navigation"></a>Entrada e navegação simplificada de funcionário

Esta funcionalidade agora está disponível em ambientes de área restrita e de avaliação. Para ativar este recurso, navegue até **Administração do sistema > Links > Configuração > Parâmetros do sistema > Recursos de visualização**. Selecione **Formulário e a navegação aprimorados do Trabalhador**. Isso permite estas alterações para todos os usuários. Você pode desativar esta opção a qualquer momento.

Para obter mais informações, consulte [Entrada e navegação simplificada de funcionário](./streamlined-employee-entry.md).

## <a name="coming-soon"></a>Em breve

### <a name="platform-update-29"></a>Update 29 para plataforma

Para obter mais detalhes sobre a atualização de Plataforma 29, consulte [Exibição de recursos na atualização de plataforma 29 do Dynamics 365 for Finance and Operations (outubro de 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-29).
