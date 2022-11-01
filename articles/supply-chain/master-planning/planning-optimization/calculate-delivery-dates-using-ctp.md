---
title: Calcular datas de entrega da ordem de venda usando CTP
description: A funcionalidade CTP (capacidade de comprometimento) permite que você forneça as datas reais de clientes para quando puder prometer mercadorias específicas. Este artigo descreve como configurar e usar o CTP para cada mecanismo de planejamento (otimização de planejamento e o mecanismo integrado).
author: t-benebo
ms.date: 07/20/2022
ms.topic: article
ms.search.form: SalesAvailableDlvDates, SalesTable, CustParameters, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-07-20
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 3b8e3dc9f0e7aaf019aa4d7284458206e7daadb2
ms.sourcegitcommit: 86c0562ce1ecdf7937125c0f5a6771f178b459e7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2022
ms.locfileid: "9714851"
---
# <a name="calculate-sales-order-delivery-dates-using-ctp"></a>Calcular datas de entrega da ordem de venda usando CTP

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

A funcionalidade CTP (capacidade de comprometimento) permite que você forneça as datas reais de clientes para quando puder prometer mercadorias específicas. Para cada linha de venda, você pode fornecer uma data que considera o estoque disponível existente, a capacidade da produção e os tempos de transporte.

O CTP estende a funcionalidade [disponível para promessa](../../sales-marketing/delivery-dates-available-promise-calculations.md) (ATP) considerando as informações sobre capacidade. Enquanto ATP considera apenas a disponibilidade de materiais e pressupõe recursos de capacidade infinitas, o CTP considera a disponibilidade de materiais e capacidade. Portanto, ele fornece uma imagem mais realista sobre a possibilidade da demanda ser cumprida em um determinado período.

A opção CTP comporta-se um pouco diferente dependendo do mecanismo de planejamento mestre que você está usando (otimização de planejamento ou o mecanismo integrado). Este artigo descreve como configurá-lo para cada mecanismo. O CTP para otimização de planejamento atualmente oferece suporte somente a um subconjunto de cenários do CTP para os quais o mecanismo integrado oferece suporte.

## <a name="turn-on-ctp-for-planning-optimization"></a>Ative o CTP para Otimização de Planejamento

O CTP para o mecanismo de planejamento mestre embutido está sempre disponível. No entanto, se você deseja usar o CTP para otimização de planejamento, ele deve ser ativado para o seu sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Planejamento mestre*
- **Nome do recurso:** *(Versão preliminar) CTP para Otimização de Planejamento*

## <a name="how-ctp-compares-to-atp"></a>Como o CTP compara a ATP

O CTP e a ATP são semelhantes, mas o CTP geralmente pode fornecer um resultado mais preciso, como mostra o exemplo a seguir.

O item A é um item composto de itens B e C, e a quantidade disponível do item A é 0 (zero). Se você fizer uma verificação ATP que considere somente materiais, a quantidade ATP também será 0 (zero). No entanto, se você fizer uma verificação do CTP, o sistema verificará a disponibilidade dos itens B e C, verificará os recursos necessários para criá-los no item A e calculará a quantidade de itens que podem ser criados. Além disso, o cálculo do CTP pode verificar os recursos e os materiais necessários para criar mais itens B e C e usá-los para criar mais itens A.

Um cálculo de CTP que considera os materiais e os recursos deve mostrar uma quantidade maior do que um cálculo que verifica somente materiais, principalmente quando o item verificado é um item de montagem sob encomenda. Em outras palavras, a funcionalidade CTP se baseia na função de detalhamento e pode ser executada para uma linha de ordem de venda selecionada para calcular a data de entrega esperada.

## <a name="how-ctp-differs-depending-on-the-master-planning-engine-that-you-use"></a>O CTP varia de acordo com o mecanismo de planejamento mestre usado

A tabela a seguir resume as diferenças entre o CTP para Otimização do Planejamento e o CTP para o mecanismo de planejamento mestre interno.

| Elemento | Otimização do Planejamento | Mecanismo de planejamento mestre interno |
|---|---|---|
| Configuração de **Controle da data de entrega** para ordens, linhas de ordem e produtos | *CTP para Otimização de Planejamento* | *CTP* |
| Hora do cálculo | O cálculo é disparado pela execução de um plano dinâmico como uma tarefa agendada. | O cálculo é disparado imediatamente toda vez que você insere ou atualiza uma linha da ordem de venda. |
| Valor do campo **Status do CTP para Otimização de Planejamento** | <p>Um valor *Não está pronto* é mostrado para ordens e linhas de ordem em que o plano dinâmico não é executado desde a criação ou última atualização das ordens e linhas.</p><p>O valor *Pronto* é mostrado para ordens e linhas em que o CTP foi usado para calcular as datas de entrega confirmadas executando o plano dinâmico.</p> | O valor *Pronto* é sempre mostrado. |

## <a name="set-default-delivery-date-control-methods"></a><a name="default-methods"></a>Definir métodos de controle da data de entrega padrão

O sistema pode usar um dos vários métodos para calcular as estimativas de datas de entrega para cada ordem e linha de ordem. Você deve definir o método de controle da data de entrega que deseja usar com mais frequência como o método padrão global. Também pode definir substituições individuais para cada produto. Posteriormente, você poderá substituir os métodos padrão para cada ordem e/ou linha da ordem, conforme necessário.

### <a name="set-the-global-default-delivery-date-control"></a><a name="global-default"></a>Definir o controle da data de entrega padrão global

O método de controle da data de entrega padrão será aplicado a todas as novas linhas da ordem em que uma substituição não se aplica. Para selecionar um, siga estas etapas.

1. Acesse **Contas a receber \> Configuração \> Parâmetros de contas a receber**.
1. Na guia **Remessas**, na FastTab **Controle de entrega**, no campo **Controle da data de entrega**, selecione o método que você deseja usar como o método padrão para sua empresa:

    - *Nenhum*: não calcule datas de entrega.
    - *Prazo de entrega das vendas*: prazo de entrega das vendas é o tempo entre a criação da ordem de venda e a remessa dos itens. O cálculo de data de entrega baseia-se em um número padrão de dias e não considera a disponibilidade de estoque, a demanda conhecida, ou o fornecimento planejado.
    - *ATP*: ATP é a quantidade de um item disponível e pode ser prometida a um cliente em uma data específica. O cálculo de ATP inclui o estoque não confirmado, prazos de entrega, recebimentos planejados, e saídas.
    - *Margem de saída + ATP*: a data de remessa é igual a data de ATP acrescida da margem de saída do item. A margem de saída é o tempo necessário para preparar os itens para remessa.
    - *CTP*: use o cálculo do CTP fornecido pelo mecanismo de planejamento mestre interno. Se você estiver usando a otimização de planejamento, o método de controle da data de entrega do *CTP* não estará disponível e, se for selecionado, causará um erro quando o cálculo for executado.
    - *CTP para otimização de planejamento*: use o cálculo do CTP fornecido pela otimização do planejamento. Essa opção não tem efeito se você estiver usando o mecanismo de planejamento mestre integrado.

### <a name="set-delivery-date-control-overrides-for-individual-products"></a>Definir substituições de controle da data de entrega para produtos individuais

É possível atribuir substituições para produtos específicos em que você deseja usar um método de controle de data de entrega diferente daquele definido como o método padrão global.

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Selecione o produto que você desejar configurar.
1. No Painel de ações da guia **Gerenciar estoque**, no grupo **Configurações da ordem**, selecione **Configurações padrão da ordem**.
1. Na página **Configurações padrão da ordem**, na FastTab **Ordem de venda**, defina a opção **Substituir controle de entrega** como *Sim*.
1. No campo **Controle da data de entrega**, selecione o método a ser usado para o produto selecionado. As mesmas opções descritas na seção [Definir o controle da data de entrega padrão global](#global-default) estão disponíveis.

## <a name="schedule-ctp-for-planning-optimization-calculations"></a><a name="batch-job"></a>Agendar o CTP para cálculos de Otimização de Planejamento

Ao usar o CTP para Otimização de Planejamento, você deve executar um plano dinâmico para disparar o sistema a fim de fazer os cálculos de CTP e, depois, definir as datas de remessa e de recebimento confirmadas para todas as ordens relevantes. O plano deve incluir todos os itens para os quais as datas de remessa e de recebimento confirmadas são necessárias. (Quando você usa o CTP para o mecanismo de planejamento interno, os cálculos do CTP são imediatamente feitos localmente. Portanto, não é necessário executar um plano dinâmico para ver os resultados do CTP.

Para garantir que as datas estejam disponíveis a tempo para todos os usuários, é recomendável configurar trabalhos em lotes para executar os planos relevantes periodicamente. Por exemplo, um trabalho em lotes configurado para executar um plano dinâmico a cada 30 minutos definirá as datas de remessa e recebimento confirmadas a cada 30 minutos. Portanto, os usuários que inserirem e importarem ordens precisarão esperar, no máximo, 30 minutos para obter as datas de remessa e recebimento confirmadas.

Para configurar um trabalho em lotes para executar um plano dinâmico em uma agenda regular, siga estas etapas.

1. Acesse **Planejamento mestre \> Planejamento mestre \> Executar \> Planejamento mestre**.
1. Na caixa de diálogo **Planejamento mestre**, na FastTab **Parâmetros**, defina o campo **Plano mestre** como o plano dinâmico que você deseja executar.
1. Na FastTab **Executar em segundo plano**, defina a opção **Processamento em lotes** como *Sim*.
1. Selecione **Recorrência** e configure a agenda, conforme necessário.
1. Selecione **OK** para salvar a agenda.
1. Selecione **OK** para criar o trabalho em lotes e fechar a caixa de diálogo.

## <a name="use-ctp-for-built-in-master-planning"></a>Use o CTP para o planejamento mestre interno

### <a name="create-a-new-order-by-using-ctp-for-built-in-master-planning"></a>Criar uma nova ordem usando o CTP para planejamento mestre interno

Toda vez que você adiciona uma nova ordem de venda ou linha de ordem, o sistema atribui um método de controle de data de entrega padrão. O cabeçalho da ordem sempre começa com o método padrão global. Se uma substituição for atribuída a um item encomendado, a nova linha da ordem usará essa substituição. Caso contrário, a nova linha da ordem também usará o método global padrão. Portanto, você deve definir métodos padrão para que coincidam com o método de controle da data de entrega que deseja usar com mais frequência como o método padrão global. Depois de criar uma ordem, você pode substituir o método padrão no cabeçalho da ordem e/ou no nível da linha da ordem, conforme necessário. Para obter mais informações, consulte [Definir métodos padrão de controle da data de entrega](#default-methods) e [Alterar ordens de venda existentes para usar o CTP](#change-orders).

### <a name="view-confirmed-delivery-dates-when-you-use-ctp-for-built-in-master-planning"></a>Exibir datas de entrega confirmadas ao usar o CTP para planejamento mestre interno

Se você estiver usando o mecanismo de planejamento mestre interno, os cálculos do CTP serão aplicados a ordens e/ou linhas de ordem em que o campo **Controle da data de entrega** será definido como *CTP*.

Para linhas de venda que usam CTP para planejamento mestre interno, o sistema define automaticamente os campos **Data de remessa confirmada** e **Data de recebimento confirmada** toda vez que você salva uma linha de venda. Se, posteriormente, você fizer uma alteração relevante em uma linha de venda (por exemplo, alterar a quantidade ou o site), as datas serão recalculadas imediatamente.

- Para exibir as datas de entrega confirmadas para uma linha da ordem de venda, abra a ordem de venda e selecione a linha de venda. Na FastTab **Detalhes da linha**, na guia **Entrega**, reveja os valores **Data de remessa confirmada** e **Data de recebimento confirmada**.
- Para exibir as datas de entrega confirmadas para uma ordem inteira, abra a ordem de venda e selecione a exibição de **Cabeçalho**. Na FastTab **Entrega**, reveja os valores **Data de remessa confirmada** e **Data de recebimento confirmada**.

## <a name="use-ctp-for-planning-optimization"></a>Usar CTP para Otimização de Planejamento

### <a name="create-a-new-order-by-using-ctp-for-planning-optimization"></a>Criar uma nova ordem usando o CTP para Otimização de Planejamento

Toda vez que você adiciona uma nova ordem de venda ou linha de ordem, o sistema atribui um método de controle de data de entrega padrão. O cabeçalho da ordem sempre começa com o método padrão global. Se uma substituição for atribuída a um item encomendado, a nova linha da ordem usará essa substituição. Caso contrário, a nova linha da ordem também usará o método global padrão. Portanto, você deve definir métodos padrão para que coincidam com o método de controle da data de entrega que deseja usar com mais frequência como o método padrão global. Depois de criar uma ordem, você pode substituir o método padrão no cabeçalho da ordem e/ou no nível da linha da ordem, conforme necessário. Para obter mais informações, consulte [Definir métodos padrão de controle da data de entrega](#default-methods) e [Alterar ordens de venda existentes para usar o CTP](#change-orders).

### <a name="view-confirmed-delivery-dates-when-using-ctp-for-planning-optimization"></a>Exibir datas de entrega confirmadas ao usar o CTP para Otimização de Planejamento

Se você estiver usando a Otimização de Planejamento, os cálculos do CTP serão aplicados a ordens e/ou linhas de ordem em que o campo **Controle da data de entrega** será definido como *CTP para Otimização de Planejamento*.

Para linhas de venda que usam CTP para Otimização de Planejamento, os campos **Data de remessa confirmada** e **Data de recebimento confirmada** ficarão em branco até que você execute o plano dinâmico apropriado (normalmente, usando um trabalho em lotes periódico). Eles são definidos automaticamente. Para obter mais informações, consulte [Agendar o CTP para cálculos de Otimização de Planejamento](#batch-job).

O campo **tatus do CTP para Otimização de Planejamento** indica se as datas confirmadas foram calculadas ainda para cada linha que usa CTP para Otimização de Planejamento. O campo mostra o valor *Não está pronto* para linhas e ordens nas quais as datas de entrega confirmadas ainda não foram calculadas ou não são mais válidas devido a outras alterações. Ele mostra um valor de *Pronto* para linhas e ordens que foram calculadas. Você pode exibir o status de cada linha e para a ordem inteira.

- Para exibir o status para uma linha da ordem de venda, abra a ordem de venda e selecione a linha de venda. Em seguida, na FastTab **Detalhes da linha**, na guia **Entrega**, revise o valor do **Status do CTP para Otimização de Planejamento**. Os campos **Data de remessa confirmada** e **Data de recebimento confirmada** para a linha também são mostrados nesta guia após serem calculados.
- Para exibir o status de uma ordem inteira, abra a ordem de venda e selecione a exibição de **Cabeçalho**. Na FastTab **Entrega**, revise o valor do **Status do CTP para Otimização de Planejamento**. Os campos **Data de remessa confirmada** e **Data de recebimento confirmada** para a ordem também são mostrados nesta guia após serem calculados.

<!-- KFM: The following text may be untrue and needs to be reviewed with the PM for next revision:

The sales orders that are *Ready* or *Not ready* are shown in the **All sales orders** list page. You can check the sales order that are *Ready* or *Not ready* from the sales order list page by filtering on this new status field.

-->

> [!NOTE]
> - Se você atualizar uma linha da ordem de venda depois que o CTP para Otimização de Planejamento tiver calculado as datas confirmadas, o sistema limpará essas datas até a próxima vez que o plano dinâmico apropriado for executado.
> - Se você editar uma configuração relacionada que possa afetar as datas confirmadas existentes (por exemplo, alterando prazos de entrega, reservas ou marcas), limpe as datas confirmadas para as ordens existentes relevantes. Esta ação causará a alteração do status de cada linha relevante para *Não está pronto*. Essa alteração, por sua vez, fará com que o sistema recalcule as datas confirmadas na próxima vez em que executar o plano dinâmico.

## <a name="change-existing-sales-orders-so-that-they-use-ctp"></a><a name="change-orders"></a>Alterar ordens de venda existentes para que usem o CTP

Você pode alterar o valor de **Controle da data de entrega** para qualquer ordem em aberto a qualquer momento. Você pode alterar o valor no nível de cabeçalho e/ou para cada linha, conforme necessário.

### <a name="change-to-ctp-at-the-order-header-level"></a>Alterar para CTP no nível do cabeçalho da ordem

<!-- KFM: Would be nice to mention how changing this setting on the header affects the individual lines. -->

Para alterar uma ordem de forma que ela use o CTP no nível do cabeçalho da ordem, siga estas etapas.

1. Acesse **Contas a receber \> Ordens \> Todas as ordens de venda**.
1. Abra a ordem de venda que deseja configurar ou crie uma.
1. Selecione **Cabeçalho** para abrir informações do cabeçalho na página **Detalhes da ordem de venda**.
1. Na FastTab **Entrega**, defina o campo **Controle da data de entrega** como um dos seguintes valores, de acordo com o mecanismo de planejamento utilizado:

    - *CTP*: use o cálculo do CTP fornecido pelo mecanismo de planejamento mestre interno. Se você estiver usando a Otimização de Planejamento, o método de controle da data de entrega *CTP* não será permitido. Portanto, se você selecionar este valor, ocorrerá um erro quando o cálculo for executado.
    - *CTP para otimização de planejamento*: use o cálculo do CTP fornecido pela otimização do planejamento. Essa configuração não terá efeito se você estiver usando o mecanismo de planejamento mestre integrado.

<!-- KFM: Additional dialogs are shown here. Review these with the PM and expand this procedure at next revision. -->
1. Selecione **OK** para aplicar as alterações.

### <a name="change-to-ctp-at-the-order-line-level"></a>Alterar para CTP no nível de linha da ordem

Se você criou uma linha da ordem usando um método de controle da data de entrega diferente, poderá alterar para o CTP a qualquer momento. As alterações feitas no nível de linha não afetam outras linhas. No entanto, elas podem fazer com que as datas de entrega de ordens gerais se movam para frente ou para trás, dependendo de como cada cálculo de linha atualizado é alterado. <!-- KFM: Confirm this intro at next revision -->

Para alterar uma ordem de forma que ela use o CTP para planejamento mestre integrado no nível do linha, siga estas etapas.

1. Acesse **Contas a receber \> Ordens \> Todas as ordens de venda**.
1. Abra a ordem de venda que deseja configurar ou crie uma.
1. Na página **Detalhes da ordem de venda**, na FastTab **Linha da ordem de venda**, selecione a linha da ordem de venda que deseja configurar.
1. Na FastTab **Detalhes da linha**, na guia **Entrega**, defina o campo **Controle da data de entrega** com um dos seguintes valores, de acordo com o mecanismo de planejamento utilizado:

    - *CTP*: use o cálculo do CTP fornecido pelo mecanismo de planejamento mestre interno. Se você estiver usando a Otimização de Planejamento, o método de controle da data de entrega *CTP* não será permitido. Portanto, se você selecionar este valor, ocorrerá um erro quando o cálculo for executado.
    - *CTP para otimização de planejamento*: use o cálculo do CTP fornecido pela otimização do planejamento. Essa configuração não terá efeito se você estiver usando o mecanismo de planejamento mestre integrado.

    A caixa de diálogo **Datas de remessa e de recebimento disponíveis** é exibida e mostra as datas de remessa e de recebimento disponíveis. Esta caixa de diálogo funciona da mesma forma com as linhas da ordem, como no cabeçalho da ordem, conforme descrito na seção anterior.

1. No Painel de ações, selecione **Salvar**.
