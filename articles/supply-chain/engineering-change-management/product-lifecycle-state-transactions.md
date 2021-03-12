---
title: Estados e transações de ciclo de vida do produto
description: Este tópico explica como você pode controlar quais transações são permitidas para cada estado do ciclo de vida conforme um produto de engenharia passa pelo seu ciclo de vida.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgEcoResProductLifecycleStateChange
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 989cfd3846e4921d24f5dcf809f1735d2cf62dbb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005318"
---
# <a name="product-lifecycle-states-and-transactions"></a>Estados e transações de ciclo de vida do produto

[!include [banner](../includes/banner.md)]

Conforme um produto de engenharia passa pelo ciclo de vida, é importante que você consiga controlar quais transações são permitidas para cada estado do ciclo de vida. Por exemplo, os produtos que ainda não estão em um estado maduro não devem ser colocados em uma ordem de venda. Como alternativa, se um produto atingir seu estado de fim da vida útil, talvez você queira controlar o fluxo do produto.

Para um produto de engenharia, as alterações no estado do ciclo de vida são associadas às versões de engenharia do produto. Portanto, o estado do ciclo de vida do produto também pode ser conectado às suas versões de engenharia. Quando o estado do ciclo de vida do produto é conectado a uma versão de engenharia, você pode usar o estado do ciclo de vida para controlar quais transações são permitidas para a versão de engenharia.

## <a name="create-and-manage-product-lifecycle-states"></a>Criar e gerenciar estados do ciclo de vida do produto

Para trabalhar com estados do ciclo de vida de produtos, vá para **Gerenciamento de alteração de engenharia \> Configuração \> Estado de ciclo de vida de produtos**. Siga uma destas etapas.

- Para criar um novo estado do ciclo de vida, selecione **Novo** no Painel de ações e defina os campos conforme descrito nas subseções a seguir.
- Para editar um estado do ciclo de vida existente, selecione-o no painel de listas, selecione **Novo** no Painel de ações e defina os campos conforme descrito nas subseções a seguir.
- Para excluir um estado de ciclo de vida existente, selecione-o no painel de lista e, em seguida, selecione **Excluir** no Painel de ações.

> [!NOTE]
> Os produtos de engenharia usam os mesmos estados de ciclo de vida do produto que os produtos padrão (não-engenharia). Você também pode abrir a página **Estado de ciclo de vida do produto** descrita neste tópico acessando **Gerenciamento de informações de produto \> Configurações \> Estado de ciclo de vida do produto**. Para obter mais informações sobre estados de ciclo de vida do produto, para produtos de engenharia e produtos padrão, consulte [Visão geral do estado do ciclo de vida do produto](../pim/product-lifecycle.md).

### <a name="header"></a>Cabeçalho

Defina os campos a seguir no cabeçalho de um estado do ciclo de vida do produto.

| Campo | descrição |
|---|---|
| Estadual | Insira um nome para o estado do ciclo de vida do produto. |
| descrição | Insira uma descrição do estado do ciclo de vida do produto. |

### <a name="general-fasttab"></a>FastTab Geral

Defina os campos a seguir na Guia rápida **Geral**.

| Campo | descrição |
|---|---|
| Padrão quando liberado para uma entidade legal | Para produtos padrão, defina esta opção como *Sim* se esse estado do ciclo de vida for aplicado a todos os produtos por padrão quando eles forem liberados pela primeira vez. Defina como *Não* se esse estado de ciclo de vida for aplicado manualmente mais tarde.<p>Esta configuração não é aplicável a produtos de engenharia. O estado do ciclo de vida de uma versão do produto de engenharia após sua criação na empresa de engenharia é especificado na categoria de alteração de engenharia. Quando o produto é liberado para uma empresa operacional, o estado do ciclo de vida do produto é copiado. Em outras palavras, quando um produto de engenharia é liberado para uma empresa operacional, ele tem o mesmo estado do ciclo de vida que tinha na empresa de engenharia. O estado do ciclo de vida pode ser substituído na empresa operacional.</p> |
| Está ativo para planejar | Defina esta opção como *Sim* para incluir produtos que estão neste estado do ciclo de vida em cálculos nos níveis planejamento mestre e lista de materiais (BOM). Defina como *Não* para excluir produtos que estão neste estado do ciclo de vida dos cálculos. |

### <a name="enabled-business-processes-fasttab"></a>Guia rápida de processos comerciais habilitado

Use a guia **Processos comerciais habilitados** para controlar os processos comerciais disponíveis que podem ser usados com produtos do estado atual do ciclo de vida. Os processos listados nesta FastTab são automaticamente encontrados da seguinte maneira:

- Na primeira vez que você salva um novo estado do ciclo de vida, a página carrega os processos comerciais que estão disponíveis no momento.
- Se você adicionar novos processos comerciais ao sistema, poderá atualizar a lista na Guia rápida **Processos comerciais habilitados** para um estado de ciclo de vida existente selecionando **Verificar se há atualizações** no Painel de ações.

Os campos a seguir estão disponíveis para cada processo listado na Guia rápida **Processos comerciais habilitados**.

| Campo | descrição |
|---|---|
| Processar | Este campo somente leitura mostra o nome de um processo comercial existente. |
| Área do processo | Este campo somente leitura mostra o nome de um processo de área existente. |
| Apólice | Selecione um dos seguintes valores para controlar se e como o processo atual será permitido para produtos que estão neste estado do ciclo de vida:<ul><li>**Habilitado** – O processo comercial é permitido.</li><li>**Bloqueado** – O processo não é permitido. Se um usuário tentar usar o processo em um produto que esteja neste estado do ciclo de vida, o sistema bloqueará a tentativa e mostrará um erro. Por exemplo, você pode bloquear a compra de produtos de fim de vida útil.</li><li>**Habilitado com aviso** – O processo é permitido, mas um aviso será exibido. Por exemplo, você pode querer que um produto protótipo seja colocado em uma ordem de produção criada pelo departamento de pesquisa e desenvolvimento. No entanto, outros departamentos devem estar cientes de que ainda não devem produzir o produto.</li></ul> |

Se você estiver adicionando mais regras de estado do ciclo de vida como uma personalização, poderá exibir essas regras na interface do usuário, selecionando **Atualizar processos** no painel superior. O botão **Atualizar processos** está disponível somente para administradores.
