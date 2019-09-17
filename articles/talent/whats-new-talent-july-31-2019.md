---
title: Novidades ou alterações no Dynamics 365 for Talent (31 de julho de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 7/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 1fffe1bd8739723294c027c174d5e959c1c6010a
ms.sourcegitcommit: 4ff8c2c2f3705d8045df66f2c4393253e05b49ed
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2019
ms.locfileid: "1864570"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-july-30-2019"></a>Novidades ou alterações no Dynamics 365 for Talent (30 de julho de 2019)

[!include [banner](includes/banner.md)]

Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Alterações no Attract
Esta versão inclui correções de bug menores para Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Alterações de Integração
Esta versão inclui correções de bug menores para Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Alterações no Core HR
As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2409.


### <a name="region-support-for-canada-and-southeast-asia"></a>Suporte regional ao Canadá e ao sudeste da Ásia

Temos o prazer de anunciar que as regiões do Canadá e do sudeste da Ásia estarão disponíveis para o Microsoft Dynamics 365 for Talent em 1º de agosto de 2019. Com essa alteração, você pode criar ambientes nas regiões do Canadá e da Ásia, e todos os dados do Talent serão mantidos apenas dentro desses locais. Você pode criar um ambiente nessas novas regiões selecionando o local na caixa de diálogo Novo ambiente e usar esse ambiente para provisionar o Talent no LCS conforme descrito em [Provisionar o Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).

Não há suporte para a migração de dados de projetos existentes de outras regiões para as regiões canadense e asiática. Somente os novos projetos podem ser provisionados a essas novas regiões com suporte.

### <a name="new-active-positions-list-page"></a>Nova página da lista de cargos ativos

As opções para listas com base em cargos agora incluem: **Todos os cargos**, **Cargos ativos**, **Cargos abertos** e **Cargos inativos**. A nova página da lista **Cargos ativos** exibe apenas os cargos abertos ou preenchidos que estão ativos a partir da data atual. 

### <a name="allow-course-participants-to-be-added-to-open-courses"></a>Permitir que os participantes do curso sejam adicionados aos cursos abertos

As alterações desta semana corrigem um problema em que apenas os subordinados diretos podem ser registrados para cursos abertos.

### <a name="fte-analysis-displaying-incorrect-fte-number"></a>A análise FTE exibe o número FTE incorreto

**A análise FTE** foi corrigida na guia **Análise** do **Gerenciamento pessoal**.

### <a name="final-comments-label-translation"></a>Tradução do rótulo dos comentários finais

O rótulo **Comentários finais** agora está traduzido no formulário de revisão.

## <a name="in-preview"></a>Em visualização

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Os recursos de visualização estão habilitados somente em instâncias da área restrita

Quando você provisiona uma nova instância do Talent, pode especificar se o tipo de instância é **Produção** ou **Área restrita**. As instâncias do tipo **Área restrita** permitem testes antecipados de novos recursos. Todas as instâncias do Talent existentes serão atualizadas para o tipo de instância de **Produção**. Se desejar que uma de suas instâncias existentes sejam atualizadas para o tipo de instância **Área restrita**, fale com o [Suporte](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) para iniciar a solicitação de alteração.

Para obter mais informações sobre como as alterações são publicadas, consulte [Provisionar o Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Exiba informações estendidas de desempenho no autoatendimento de gerente

Uma nova opção permitirá que gerentes exibam o desempenho de seus relatórios diretos e de seus relatórios estendidos. Atualmente, os gerentes de linha podem atribuir e atualizar metas de desempenho e emitir novas revisões. Além disso, os gerentes diretos e seus funcionários podem manter e atualizar diários de desempenho para ajudar a garantir que o processo de avaliação de desempenho corra bem. Quando essa alteração for implementada, gerentes poderão exibir e manter informações de desempenho para seus relatórios estendidos além de seus relatórios diretos.
