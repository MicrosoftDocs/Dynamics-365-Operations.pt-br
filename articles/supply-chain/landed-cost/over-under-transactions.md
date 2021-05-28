---
title: Transações excedentes/insuficientes
description: Este tópico fornece informações que ajudarão você a configurar os detalhes das políticas de transações excedentes/insuficientes, de forma que o sistema possa determinar como gerenciar o processamento excessivo e insuficiente de mercadorias no momento do recebimento.
author: sherry-zheng
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMOverUnderTrans, ITMOverUnderToleranceTable, ITMOverUnderReasonTable, ITMOverUnderToleranceGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 53b1ebf27a58b1c16c6c249ca044fd746cce1436
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020902"
---
# <a name="overunder-transactions"></a>Transações excedentes/insuficientes

[!include [banner](../../includes/banner.md)]

Quando as ordens em uma viagem são processadas, o sistema espera a quantidade de itens recebida no depósito do destino final para que o consumo corresponda à quantidade especificada nas linhas da ordem de compra associadas à viagem. No entanto, como a quantidade exata nas linhas da ordem de compra nem sempre é recebida no depósito, o módulo **Custo de entrega** define um conjunto de regras que são usadas para lidar com o recebimento excessivo e insuficiente de mercadorias. Essas regras são especialmente importantes porque a ordem de compra original foi faturada e não pode mais ser modificada. Ao configurar os detalhes das políticas de transações excedentes/insuficientes, você habilita o sistema a determinar como gerenciar o processamento excessivo e insuficiente de mercadorias no momento do recebimento. Você também pode gerenciar manualmente o estoque excedente e insuficiente usando a página **Transações excedentes/insuficientes**.

## <a name="overunder-tolerances"></a>Tolerâncias excedentes/insuficientes

Você define as tolerâncias de entrega excedente e insuficiente para especificar as quantidades ou os volumes excedentes e insuficientes que podem ser processados em uma viagem sem causar erros. Se o recebimento da linha de viagem estiver fora dessas tolerâncias, ele deverá ser modificado e resolvido antes que a linha de viagem possa ser fechada para processamento adicional.

Para configurar as tolerâncias, vá para **Custo de entrega \> Configuração excedente/insuficiente \> Tolerâncias excedentes/insuficientes**. Lá, você pode exibir, editar, adicionar e remover registros de tolerância. A tabela a seguir descreve os campos disponíveis para cada registro.

| Campo | descrição |
|---|---|
| Código da conta | <p>Defina o escopo de fornecedores ao qual a tolerância se aplica, selecionando um dos seguintes valores:</p><ul><li>**Tabela** – A tolerância excedente/insuficiente se aplica somente ao fornecedor selecionado para a linha.</li><li>**Grupo** – A tolerância excedente/insuficiente se aplica a todos os fornecedores no grupo de tolerância de fornecedores selecionado para a linha.</li><li>**Todos** – A tolerância excedente/insuficiente se aplica a todos os fornecedores.</li></ul> |
| Relação de conta | Selecione o fornecedor ou o grupo de fornecedores ao qual a tolerância excedente/insuficiente se aplica, dependendo do valor selecionado no campo **Código da conta**. |
| Código do item | <p>Defina o escopo de itens ao qual a tolerância se aplica, selecionando um dos seguintes valores:</p><ul><li>**Tabela** – A tolerância excedente/insuficiente se aplica somente ao item selecionado para a linha.</li><li>**Grupo** – A tolerância excedente/insuficiente se aplica a todos os itens no grupo de tolerância de itens selecionado para a linha.</li><li>**Todos** – A tolerância excedente/insuficiente se aplica a todos os itens.</li></ul> |
| Relação de item | Selecione o item ou o grupo de itens ao qual a tolerância excedente/insuficiente se aplica, dependendo do valor selecionado no campo **Código do item**. |
| Tolerância de valor | Insira a tolerância de valor que deve ser aplicada a uma ordem de compra inteira. |
| Tolerância de percentual | Insira a tolerância de percentual que deve ser aplicada a uma linha individual da ordem de compra. |

## <a name="overunder-reasons"></a>Motivos excedentes/insuficientes

Quando uma quantidade excedente ou insuficiente é associada a uma linha de viagem recebida, talvez seja necessário identificar o motivo da quantidade excedente ou insuficiente. Nesse caso, você pode selecionar o motivo de entrega excedente ou insuficiente na linha de recebimento quando as mercadorias forem recebidas.

Para configurar motivos de entrega excedente e insuficiente, vá para **Custo de entrega \> Configuração excedente/insuficiente \> Motivos excedentes/insuficientes**. Lá, você pode exibir, editar, adicionar e remover os motivos de entrega excedente e insuficiente disponíveis. A tabela a seguir descreve os campos disponíveis para cada motivo.

| Campo | descrição |
|---|---|
| Motivo excedente/insuficiente | Insira um nome exclusivo para o motivo da transação de recebimento excedente ou insuficiente. |
| descrição | Insira uma descrição do motivo excedente/insuficiente. |
| Movimentação | Selecione o diário de movimentação associado ao motivo excedente/insuficiente. Este campo lista todos os diários disponíveis aos quais um tipo de diário de *Movimentação* está associado na página **Nomes de diários de estoque** (**Configuração de gerenciamento de estoque \> Nomes de diários \> Estoque**). |

## <a name="item-overunder-tolerance-groups"></a>Grupos de tolerâncias excedentes/insuficientes de item

Os itens que têm tolerâncias semelhantes podem ser agrupados. Dessa forma, você pode definir a tolerância excedente/insuficiente para todos os itens do grupo ao mesmo tempo.

Para configurar grupos de tolerâncias excedentes/insuficientes de item, vá para **Custo de entrega \> Configuração excedente/insuficiente \> Grupos de tolerâncias excedentes/insuficientes de item**. Lá, você pode exibir, editar, adicionar e remover registros de grupos de tolerâncias excedentes/insuficientes. A tabela a seguir descreve os campos disponíveis para cada registro.

| Campo | descrição |
|---|---|
| Grupo de tolerâncias excedentes/insuficientes | Insira um nome exclusivo para o grupo. Escolha um nome que descreva a tolerância, por exemplo, *1% Var*. |
| descrição | Insira uma descrição do grupo. |

## <a name="vendor-overunder-tolerance-groups"></a>Grupos de tolerâncias excedentes/insuficientes de fornecedor

É possível agrupar os fornecedores que realizam entregas excedentes ou insuficientes regularmente. Em seguida, você pode definir a tolerância excedente/insuficiente por grupo.

Para configurar grupos de tolerâncias excedentes/insuficientes de fornecedor, vá para **Custo de entrega \> Configuração excedente/insuficiente \> Grupos de tolerâncias excedentes/insuficientes de fornecedor**. Lá, você pode exibir, editar, adicionar e remover registros de grupos de tolerâncias excedentes/insuficientes. A tabela a seguir descreve os campos disponíveis para cada registro.

| Campo | descrição |
|---|---|
| Grupos excedentes/insuficientes | Insira um nome exclusivo para o grupo. Escolha um nome que descreva o tipo de fornecedores que pertencem ao grupo. |
| descrição | Insira uma descrição do grupo. |

## <a name="view-and-process-overunder-transactions"></a>Exibir e processar transações excedentes/insuficientes

As transações excedentes/insuficientes são geradas quando a quantidade de mercadorias armazenada não corresponde à quantidade inicializada. A quantidade no diário de entrada deve ser atualizada somente com a quantidade armazenada.

Quando o recebimento das linhas de viagem é processado, as tolerâncias excedentes/insuficientes podem ser definidas para um fornecedor. Os itens então serão revisados e validados. A tolerância pode ser definida como uma porcentagem, um valor local ou ambos.

Se um item recebido estiver dentro da tolerância, o sistema gerará um diário de movimentação. Esse diário pode ser especificado na página de parâmetros de viagem. Além disso, uma transação excedente/insuficiente será criada. Por exemplo, o valor da ordem é US$ 100, o valor de recebimento é US$ 99 e esses valores satisfazem as regras de tolerância. Nesse caso, será criado um diário de movimentação negativo para a quantidade com recebimento insuficiente.

Se um item recebido estiver fora da tolerância, o sistema gerará uma transação excedente/insuficiente para a diferença de quantidade.

Para exibir e processar transações excedentes/insuficientes, vá para **Custo de entrega \> Consultas \> Transações excedentes/insuficientes**. Lá, uma transação excedente/insuficiente será associada a todos os itens em uma viagem com recebimento excedente ou insuficiente. É recomendável usar a página **Transações excedentes/insuficientes** para resolver todas as transações excedentes/insuficientes associadas a viagens. Também é recomendável **não** usar diários de movimentação ou de contagem para resolver manualmente transações de depósito com entrega insuficiente. Em vez disso, você deve usar a página **Transações excedentes/insuficientes** para gerenciar as quantidades de depósito com entrega insuficiente.

### <a name="upper-overview-tab"></a>Guia Visão geral superior

Para exibir suas transações excedentes/insuficientes, selecione a guia **Visão geral** na parte superior da página **Transações excedentes/insuficientes**. A tabela a seguir descreve os campos disponíveis na grade.

| Campo | descrição |
|---|---|
| Número de transações excedentes/insuficientes | O nome exclusivo do registro de transação excedente/insuficiente criado automaticamente quando o diário de entrada foi processado. |
| Viagem | A viagem à qual a linha de compra foi anexada. |
| Contêiner de remessa | O contêiner ao qual a linha de compra foi anexada. |
| Diário de entrada | O diário de entrada do qual a linha excedente/insuficiente foi gerada. |
| Demonstrativo | Uma referência para a ordem de compra ou a ordem de transferência associadas à transação excedente/insuficiente. |
| Número | A ordem de compra referenciada na transação excedente/insuficiente. |
| Conta de Fornecedor | O fornecedor ao qual a transação excedente ou insuficiente está relacionada. |
| Número de mercadorias em trânsito | O número de mercadorias em trânsito, se aplicável. |
| Nº de itens | O número de itens ao qual a transação excedente ou insuficiente está relacionada. |
| Quantidade original | A quantidade original da linha da ordem de compra associada à remessa. |
| Quantidade recebida | A quantidade realmente recebida. |
| Diferença | A diferença entre o valor esperado do diário de entrada e o valor lançado no diário de entrada. Um valor negativo indica uma entrega excedente de mercadorias. |
| Quantidade pendente | A quantidade que permanece na linha do diário de entrada. |
| Entrega excedente/insuficiente | Um valor que indica se a quantidade recebida é excedente ou insuficiente. |
| Status | O status da transação excedente/insuficiente. Dependendo das configurações na página **[Parâmetros de custo de entrega](landed-cost-parameters.md)**, a entrega excedente pode criar automaticamente um diário de movimentação para o valor de entrega excedente e lançar o diário. Nesse caso, a transação excedente/insuficiente terá o status *Concluído*. Se for necessária uma ação para mover as mercadorias do depósito de entrega insuficiente, o registro terá o status *Em andamento*. |
| Motivo excedente/insuficiente | O motivo associado à transação excedente/insuficiente. |
| Outras dimensões de estoque | Você pode mostrar colunas para dimensões adicionais na grade, conforme necessário. Essas dimensões incluem o número do lote, o status do estoque e o depósito. No Painel de Ações, selecione **Estoque \> Exibir dimensões** para abrir uma caixa de diálogo na qual é possível selecionar as dimensões a serem incluídas. |

### <a name="upper-general-tab"></a>Guia Geral superior

Para exibir mais informações sobre a linha atualmente selecionada na guia **Visão geral** superior, selecione a guia **Geral** na parte superior da página **Transações excedentes/insuficientes**. As informações nesta guia incluem os valores de todas as dimensões disponíveis. Essas informações são obtidas da ordem de compra original.

### <a name="lower-overview-tab"></a>Guia Visão geral inferior

Para exibir o tipo de documento da linha selecionada na guia **Visão geral** superior, selecione a guia **Visão geral** na parte inferior da página **Transações excedentes/insuficientes**. A tabela a seguir descreve os campos disponíveis.

| Campo | descrição |
|---|---|
| Novo tipo de documento | Este campo é definido como *Diário de movimentação* ou *Ordem de compra*, dependendo da ação mostrada na linha selecionada da transação excedente/insuficiente. |
| Número | Uma referência e um link para a ordem de compra ou o diário de movimentação associados à linha selecionada da transação excedente/insuficiente. |
| Motivo excedente/insuficiente | O motivo associado à linha selecionada da transação excedente/insuficiente. |
| Quantidade | A quantidade selecionada para a ordem de compra ou o diário de movimentação associados à linha selecionada da transação excedente/insuficiente. |

### <a name="lower-general-tab"></a>Guia Geral inferior

Para exibir o número da transação excedente/insuficiente, a ID do lote e o número da dimensão associados à linha selecionada da transação excedente/insuficiente, selecione a guia **Geral** na parte inferior da página **Transações excedentes/insuficientes**. 

### <a name="process-overunder-transactions"></a>Processar transações excedentes/insuficientes

O Painel de Ações na página **Transações excedentes/insuficientes** fornece os comandos a seguir para processar as transações selecionadas na página. Cada comando permite escolher como processar cada transação.

- **Criar \> Movimentação** – Crie e lance um diário de movimentação para a transação selecionada. Em transações insuficientes, um diário de movimentação é criado e lançado automaticamente para a diferença entre a quantidade recebida esperada e real. Selecione este comando para transações excedentes se quiser que o fornecedor perceba a diferença de custo.
- **Criar \> Ordem de compra** – Crie uma ordem de compra para a diferença entre a quantidade recebida esperada e real da transação selecionada. Selecione este comando para transações excedentes se a sua organização for perceber a diferença de custo.
- **Criar \> Transferir para o destino** – Este comando se aplica somente a ordens de transferência. Selecione-o se quiser transferir a quantidade excedente/insuficiente para o depósito de destino.
- **Criar \> Transferir para a origem** – Este comando se aplica somente a ordens de transferência. Selecione-o se quiser transferir a quantidade excedente/insuficiente para o depósito de origem.
