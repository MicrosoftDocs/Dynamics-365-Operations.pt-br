---
title: Definir e manter canais de varejo
description: "Este artigo fornece uma visão geral do processo para configurar as lojas tradicionais, que são referidas como lojas de varejo no Microsoft Dynamics 365 for Retail. Inclui informações sobre as tarefas que devem ser concluídas antes e depois de você configurar uma loja de varejo."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailStoreTable, RetailStoreTableListPagePreviewPane
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 16481
ms.assetid: 14496d96-1c72-43ce-a2e7-8467bab4ae46
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: 3f0b566963574569cb40b72550e2337c9ba8a2ce
ms.contentlocale: pt-br
ms.lasthandoff: 06/20/2017

---

# <a name="define-and-maintain-retail-channels"></a>Definir e manter canais de varejo

[!include[banner](includes/banner.md)]


Este artigo fornece uma visão geral do processo para configurar as lojas tradicionais, que são referidas como lojas de varejo no Microsoft Dynamics 365 for Retail. Inclui informações sobre as tarefas que devem ser concluídas antes e depois de você configurar uma loja de varejo.

O Dynamics 365 for Retail dá suporte a vários canais de varejo, como lojas online, call centers e lojas tradicionais. Uma loja física é chamada de loja de varejo. Cada loja de varejo pode ter seus próprios métodos de pagamento, grupos de preços, terminais de pontos de venda (PDV), contas de receita e despesa e equipe. Você deve configurar todos esses elementos para uma loja de varejo antes de criá-la. Depois de criar a loja de varejo, você atribui os produtos que deseja que a loja contenha. Você também atribui funcionários, registradoras e clientes à loja. Por fim, você adiciona a nova loja a uma hierarquia da organização.

## <a name="setting-up-retail-stores"></a>Configurando lojas de varejo
Antes de configurar uma loja de varejo no Dynamics 365 for Retail, você deve concluir algumas tarefas necessárias. É possível criar a loja de varejo e adicionar detalhes.

### <a name="prerequisites"></a>Pré-requisitos

Você deve concluir as seguintes tarefas antes de poder configurar uma loja de varejo:

1.  Configure a estrutura de sua organização e configure hierarquias da organização para classificações, reabastecimento e relatório de varejo.
2.  Configurar um depósito que representa a loja de varejo.
3.  Configure sequências numéricas para lojas de varejo, as instruções de armazenamento e os comprovantes do demonstrativo.
4.  Configurar parâmetros para varejo.
5.  Configurar os métodos de pagamento que a loja aceita.
6.  Para processar transações de cartão de crédito em terminais de PDV, você também pode configurar os serviços de pagamento.
7.  Configurar grupos de impostos.
8.  Configurar produtos de varejo. Como parte desta tarefa, você também pode configurar hierarquias de produtos de varejo, variantes de produto, e classificações de produtos.
9.  Configurar grupos de preços de produtos.
10. Configure preços de produtos de varejo. Como parte desta tarefa, você também pode configurar ajustes de preço, descontos, e períodos de desconto.
11. Configurar membros da equipe. **Observação:** Você também deve atribuir permissões apropriadas para trabalhadores, de modo que eles possam se conectar e executar as tarefas usando o Microsoft Dynamics 365 for Retail para o sistema Retail POS.
12. Configure os perfis do Retail POS a serem atribuídos à loja. Essa tarefa inclui várias tarefas como configurar registros, perfis offline e formatos e perfis de recebimento.

Examine todas as tarefas incluídas no pré-requisito, e conclua apenas as tarefas que se aplicam a você.

### <a name="set-up-a-retail-store"></a>Configurar uma loja de varejo

Depois de concluir as tarefas necessárias, conclua estas tarefas para configurar os detalhes da loja de varejo:

1.  Crie uma loja de varejo.
2.  Atribua um grupo de impostos à loja.
3.  Atribuir os métodos de pagamento aceitos à loja.
4.  Adicione detalhes às descrições do produto para os produtos que você oferece em suas lojas de varejo. Por exemplo, você pode adicionar rich text e imagens. Esses detalhes de produto aparecem em vários contextos, como na registradora de PDV ou rótulos impressos.
5.  Adicione a loja a uma hierarquia organizacional padrão que tem por finalidade **Sortimento de varejo**, **Reabastecimento de varejo**, ou **Relatório de varejo**.

### <a name="after-you-set-up-a-retail-store"></a>Após configurar uma loja de varejo

Depois de inserir os detalhes da loja de varejo, conclua estas tarefas para enviar os dados da nova loja de varejo para o Retail POS:

1.  Configurar terminais de PDV para a loja.
2.  Atribuir classificações de produtos à loja.
3.  Processe as classificações para gerar a lista de produtos que são incluídos na classificação e para disponibilizar os disponíveis na loja de varejo.
4.  Envie dados como sequências numéricas, perfis de hardware, layouts de tela de PDV para as registradoras do Retail POS.
5.  Publique a loja de varejo para enviar dados da loja para o Retail POS..
6.  Execute os trabalhos para enviar os dados da loja para o Retail POS.

## <a name="organization-hierarchies"></a>Hierarquias da organização
O Retail usa hierarquias da organização para estruturar canais de varejo. As hierarquias da organização representam os relacionamentos entre as organizações que compõem sua empresa. Ao configurar lojas, você pode adicioná-las a uma hierarquia da organização. As lojas compartilham dados usados para classificações, reabastecimento e relatórios.




