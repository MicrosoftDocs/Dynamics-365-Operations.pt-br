---
title: Definir e manter canais de varejo
description: Este tópico apresenta uma visão geral do processo de configurar lojas físicas, também chamadas de lojas no Dynamics 365 Commerce. Inclui informações sobre as tarefas que devem ser realizadas antes e depois de você configurar uma loja.
author: mugunthanm
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreTableListPagePreviewPane
audience: Application User
ms.reviewer: josaw
ms.custom: 16481
ms.assetid: 14496d96-1c72-43ce-a2e7-8467bab4ae46
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: a2ac4a4a42447e4ee57d24548a79f43b88b03927
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213689"
---
# <a name="define-and-maintain-retail-channels"></a>Definir e manter canais de varejo

[!include [banner](includes/banner.md)]

Este tópico apresenta uma visão geral do processo de configurar lojas físicas, também chamadas de lojas no Dynamics 365 Commerce. Inclui informações sobre as tarefas que devem ser realizadas antes e depois de você configurar uma loja.

O Commerce dá suporte para vários canais, como lojas online, call centers e lojas físicas. Uma loja física é chamada de loja. Cada loja pode ter seus próprios métodos de pagamento, grupos de preços, registradoras de ponto de venda (POS), contas de renda e de despesa, e equipe. Você deve configurar todos esses elementos de uma loja antes de criá-la. Depois de criar a loja, você atribui os produtos que deseja que ela tenha. Você também atribui funcionários, registradoras e clientes à loja. Por fim, você adiciona a nova loja a uma hierarquia da organização.

## <a name="setting-up-stores"></a>Configurando armazenamentos

Para configurar uma loja no Commerce, você deve executar algumas tarefas necessárias. É possível criar a loja e adicionar detalhes.

### <a name="prerequisites"></a>Pré-requisitos

Você deve executar as seguintes tarefas antes de configurar uma loja:

1. Configure a estrutura de sua organização e configure hierarquias da organização para classificações, reabastecimento e relatório de varejo.
2. Configure um depósito que represente a loja.
3. Configure sequências numéricas para lojas, demonstrativos de loja e comprovantes de demonstrativo.
4. Configure parâmetros para o Commerce.
5. Configurar os métodos de pagamento que a loja aceita.
6. Para processar transações de cartão de crédito em terminais de PDV, você também pode configurar os serviços de pagamento.
7. Configurar grupos de impostos.
8. Configure produtos. Como parte desta tarefa, você também pode configurar hierarquias, grades e classificações de produtos.
9. Configurar grupos de preços de produtos.
10. Configure os preços dos produtos. Como parte desta tarefa, você também pode configurar ajustes de preço, descontos, e períodos de desconto.
11. Configurar membros da equipe.

    > [!NOTE]
    > Você também deve atribuir permissões apropriadas aos trabalhadores para que eles possam se conectar e executar tarefas usando o sistema POS.

12. Configure os perfis de PDV a serem atribuídos à loja. Essa tarefa inclui várias tarefas como configurar registros, perfis offline e formatos e perfis de recebimento.

Examine todas as tarefas incluídas nos pré-requisitos e execute somente as que se aplicam a você.

### <a name="set-up-a-store"></a>Configurar uma loja

Depois de concluir as tarefas necessárias, execute estas tarefas para configurar os detalhes da loja:

1. Crie uma loja.
2. Atribua um grupo de impostos à loja.
3. Atribuir os métodos de pagamento aceitos à loja.
4. Adicione detalhes às descrições dos produtos que você oferece em suas lojas. Por exemplo, você pode adicionar rich text e imagens. Esses detalhes de produto aparecem em vários contextos, como na registradora de PDV ou rótulos impressos.
5. Adicione a loja à hierarquia organizacional padrão que tem por finalidade **Sortimento de varejo**, **Reabastecimento de varejo** ou **Relatório de varejo**.

### <a name="after-you-set-up-a-store"></a>Depois de configurar uma loja

Depois de inserir os detalhes da loja, execute estas tarefas para enviar os dados da nova loja ao PDV:

1. Configurar terminais de PDV para a loja.
2. Atribuir classificações de produtos à loja.
3. Processe as classificações para gerar a lista de produtos incluídos na classificação e disponibilizar os produtos na loja.
4. Envie dados, como sequências numéricas, perfis de hardware, layouts de tela de PDV, para os terminais do PDV.
5. Publique a loja para enviar dados da loja ao PDV.
6. Execute os trabalhos para enviar os dados da loja ao PDV.

## <a name="organization-hierarchies"></a>Hierarquias da organização

O Commerce usa hierarquias da organização para estruturar canais. As hierarquias da organização representam os relacionamentos entre as organizações que compõem sua empresa. Ao configurar lojas, você pode adicioná-las a uma hierarquia da organização. As lojas compartilham dados usados para classificações, reabastecimento e relatórios.

> [!NOTE]
> Para usar a funcionalidade de vendas do Commerce, a chave de configuração **Diversos endereços de remessa** deve estar habilitada. Essa chave de configuração pode ser encontrada nas chaves **Configuração de troca** em **Administração do sistema**\> **Configuração** \> **Configurações do sistema**. Isso é necessário devido a várias validações com base no endereço de entrega configurado no nível da linha da ordem de venda.



[!INCLUDE[footer-include](../includes/footer-banner.md)]