---
title: Usar códigos de disposição em lotes para marcar os lotes como disponíveis ou indisponíveis
description: Este artigo descreve como configurar e usar códigos de disposição em lotes para marcar os lotes como disponíveis ou indisponíveis para uso no planejamento mestre, na reserva, na separação e/ou na remessa.
author: t-benebo
ms.date: 09/16/2022
ms.topic: article
ms.search.form: PdsDispositionMaster, InventBatch
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-09-16
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: cfb0743a573550de93d75063df517e0c143f2568
ms.sourcegitcommit: 20ce54cb40290dd116ab8b157c0a02d6757c13f5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2022
ms.locfileid: "9542463"
---
# <a name="use-batch-disposition-codes-to-mark-batches-as-available-or-unavailable"></a>Usar códigos de disposição em lotes para marcar os lotes como disponíveis ou indisponíveis

Este artigo descreve como configurar e usar *códigos de disposição em lotes*. Cada código de disposição em lotes tem um status de *Disponível* ou *Indisponível*. Os códigos de disposição em lotes são atribuídos aos lotes de estoque para indicar se cada lote está disponível para planejamento mestre, reserva, separação e/ou remessa.

Para usar códigos de disposição em lotes, você deve configurá-los e atribuí-los aos lotes que deseja gerenciar.

## <a name="set-up-batch-disposition-codes"></a>Configurar códigos de disposição em lotes

Você deve configurar cada código de disposição em lotes que deseja usar no seu sistema. Você pode criar quantos códigos quiser. (Por exemplo, você pode criar códigos para identificar os diferentes motivos pelos quais um lote pode estar disponível ou indisponível). No entanto, você geralmente terá apenas dois códigos: um para *disponível* e outro para *indisponível*. Você também pode criar códigos personalizados que permitam que um lote seja usado para algumas operações, mas não para outras.

Siga estas etapas para configurar códigos de disposição em lotes.

1. Acesse **Gerenciamento de estoque \> Configuração \> Lote \> Disposição em lotes principal**.
1. A página **Disposição em lotes principal** lista os códigos de disposição em lotes atuais e permite a criação, exclusão e edição dos códigos. Siga uma destas etapas:

    - Para editar um código existente, selecione-o no painel da lista.
    - Para criar uma código, selecione **Novo** no Painel de Ações.

1. Defina os seguintes campos no cabeçalho do código novo ou selecionado:

    - **Código de disposição em lotes** – insira o nome de exibição para o código.
    - **Descrição** – descreva como o código deve ser usado.
    - **Status da disposição em lotes** – selecione o status aplicável aos lotes aos qual o código está atribuído:

        - *Indisponível* – os lotes não podem ser usados para planejamento mestre, reserva, separação ou remessa. Quando você seleciona esse valor, todas as opções de **Boqueio** na Guia Rápida **Configuração** são definidas como *Sim* e todas as opções **Líquido** são definidas como *Não*. No entanto, algumas dessas configurações podem ser alteradas para a adição de exceções.
        - *Disponível* – os lotes não podem ser usados para planejamento mestre, reserva, separação e/ou remessa. Quando você seleciona esse valor, todas as opções de **Boqueio** na Guia Rápida **Configuração** são definidas como *Não* e todas as opções **Líquido** são definidas como *Sim*. Essas configurações serão somente leitura enquanto o campo **Status da disposição em lotes** estiver definido como *Disponível*.

1. Se definir o campo **Status da disposição em lotes** como *Indisponível*, você poderá personalizar o status de bloqueio de cada operação (reserva, separação e remessa) para cada tipo de ordem (venda, transferência e produção). Para ordens de produção, você pode optar por bloquear ou desbloquear o diário de separação de produção. Você também pode optar por bloquear ou desbloquear o planejamento mestre. Use as opções da Guia Rápida **Configuração** para bloquear ou desbloquear cada operação conforme necessário. Defina a opção **Líquido** como *Sim* para habilitar o planejamento mestre ou configure-a como *Não* para bloquear o planejamento mestre.

## <a name="assign-batch-disposition-codes-to-batches"></a>Atribuir códigos de disposição em lotes aos lotes

Depois de definir os códigos de disposição de lotes necessários, siga estas etapas para atribuí-los aos lotes.

1. Acesse **Gerenciamento de depósito \> Configuração \> Estoque \> Lotes**.
1. Selecione um ou mais lotes aos quais atribuir um código de disposição em lotes.
1. No Painel de Ações, na guia **Redefinir**, selecione **Redefinir código de disposição em lotes**.
1. Na caixa de diálogo **Altera as restrições do lote de estoque**, defina o campo **Novo código de disposição em lotes** como o nome do código que você deseja atribuir.
1. Selecione **OK** para aplicar a nova configuração e fechar a caixa de diálogo.

    Na página **Lotes**, os valores nas colunas **Código de disposição em lotes** e **Status da disposição em lotes** são atualizados de forma que reflitam as novas configurações dos lotes selecionados.

## <a name="master-planning-example"></a>Exemplo de planejamento mestre

Este exemplo mostra como os códigos de disposição em lotes podem afetar o planejamento mestre.

Neste exemplo, os códigos de disposição em lotes estão configurados da seguinte maneira:

- *P-Disponível:*

    - **Status da disposição em lotes:** *Disponível*
    - **Líquido:** *Sim*

- *P-Indisponível:*

    - **Status da disposição em lotes:** *Indisponível*
    - **Líquido:** *Não*

Há um produto (*Produto-1*) que tem dois lotes: *Lote-A* e *Lote-B*. Esses lotes estão configurados da seguinte maneira:

- *Lote-A:*

    - **Código de disposição em lotes:** *P-Disponível*
    - **Quantidade disponível:** 1

- *Lote-B:*

    - **Código de disposição em lotes:** *P-Indisponível*
    - **Quantidade disponível:** 1

Existe uma ordem de venda (*SO1*) para uma quantidade de 2 do produto *Produto-1*. A data de entrega é de três dias a partir de hoje.

Você executa o planejamento mestre e define os valores a seguir que são relevantes para este exemplo:

- **Ordem planejada:** *Ordem de compra*
- **Estratégia de reabastecimento:** *Requisito*
- **Prazo:** *0*

Como resultado da execução do planejamento, o sistema usa o lote disponível (*Lote-A*) para cobrir a quantidade de 1 do produto *Produto-1* para a ordem de venda *SO1*. No entanto, ele não pode usar o lote *Lote-B* porque esse lote está marcado como indisponível para planejamento. Portanto, para cobrir a quantidade restante, o sistema cria uma ordem de compra planejada (*PPO1*) para um novo lote do produto *Produto-1*.

A ilustração a seguir mostra uma linha do tempo para o resultado do planejamento.

![Exemplo que mostra como os códigos de disposição em lotes podem afetar o planejamento mestre.](media/batch-codes-planning-example.png "Exemplo que mostra como os códigos de disposição em lotes podem afetar o planejamento mestre")
