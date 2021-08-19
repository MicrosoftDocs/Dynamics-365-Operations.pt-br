---
title: Separação em excesso para ordens de venda e ordens de transferência
description: Este tópico explica como habilitar a separação em excesso para ordens de venda e ordens de transferência.
author: GalynaFedorova
ms.date: 07/06/2021
ms.topic: article
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-07-06
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 3c6f9d386f79754edce38e4e2cf4c9bfefbce69bdb252e8754f39d909827fa02
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722142"
---
# <a name="over-picking-for-sales-orders-and-transfer-orders"></a>Separação em excesso para ordens de venda e ordens de transferência

[!include [banner](../includes/banner.md)]

Este tópico apresenta um cenário que mostra como habilitar um trabalhador específico ou todos os trabalhadores para realizarem separação em excesso. O processo de separação em excesso permite a separação em excesso controlada durante o trabalho de separação.

A separação em excesso do depósito é um conceito simples. O sistema permite que os trabalhadores escolham mais itens do que o especificado para uma ordem. No entanto, ele ainda considera o limite de entrega excedente definido no nível da linha para a ordem de transferência ou para a ordem de venda. Se esse limite for excedido, o aplicativo Warehouse Management notificará os trabalhadores que estão excedendo o limite de entrega excedente.

O recurso de separação em excesso ajuda a minimizar a manutenção e também ajuda a manter a flexibilidade da sua configuração. Você pode definir um ou mais itens de menu de dispositivo móvel e habilitar a separação em excesso para apenas alguns deles. Você também pode impedir que os trabalhadores realizem separação em excesso de ordens de venda e/ou ordens de transferência sem precisar alterar os itens de menu. Em vez disso, você pode desativar um ou ambos os recursos nas configurações de trabalhador relevantes.

O recurso de separação em excesso pode ajudar os trabalhadores a poupar tempo e esforço ao separar e enviar itens. Por exemplo, o recurso permite que os funcionários executem estas tarefas:

- Compensar a redução durante a separação ou a remessa.
- Evitar a descompactação de algum material de embalagem durante o processo de separação.
- Compensar o dano ao item durante o transporte.
- Enviar uma variação de quantidade ou de unidade de medida.
- Minimizar a divisão de quantidades por placas de licença.
- Evitar desperdício de material e escassez de materiais caros.
- Medir a quantidade separada após a separação (por exemplo, por meio de pesagem Lorry).

> [!IMPORTANT]
> O recurso de separação em excesso se aplica apenas a separação e processamento de ordem de venda e de ordem de transferência. O reabastecimento não oferece suporte à separação em excesso. Quando o trabalho de reabastecimento é executado, o sistema não permite que os usuários façam a separação em excesso.

Este tópico apresenta um cenário que mostra como configurar e usar o recurso de separação em excesso.

## <a name="scenario-prerequisite-make-demo-data-available"></a>Pré-requisitos do cenário: disponibilizar dados de demonstração

O cenário neste tópico faz referência a valores e registros incluídos nos dados de demonstração padrão que são fornecidos para o Microsoft Dynamics 365 Supply Chain Management. Se você deseja usar os valores fornecidos aqui ao fazer os exercícios, procure trabalhar em um ambiente no qual os dados de demonstração estejam instalados e defina a entidade legal como *USMF* antes de começar.

## <a name="scenario-setup"></a>Configuração de cenário

Antes de trabalhar no cenário de exemplo, você deve habilitar a separação em excesso para o trabalhador relevante e para o item de menu relevante.

### <a name="set-up-a-worker-to-allow-for-over-picking"></a>Configurar um trabalhador para permitir a separação em excesso

Este é o procedimento geral para configurar um trabalhador para habilitar a separação em excesso para ordens de venda e ordens de transferência separadamente. Essa configuração controla qual trabalhador de separação pode fazer a separação em excesso e se esse trabalhador pode fazer a separação em excesso das ordens de transferência e das ordens de venda.

1. Acesse **Gerenciamento de depósito \> Configuração \> Trabalhador**.
1. No painel da lista, selecione **Julia Funderburk**.
1. Na Guia Rápida **Usuários**, selecione a linha que tem os valores a seguir. Se nenhuma linha existente tiver esses valores, crie-a.

    - **Identificação de usuário:** *24*
    - **Nome de usuário:** *WH 24*
    - **Depósito padrão:** *24*
    - **Nome do menu:** *Principal*

1. Na Guia Rápida **Trabalho**, defina os seguintes valores para o usuário *24* se eles ainda não estiverem definidos:

    - **Permitir separação em excesso de vendas:** *Sim*
    - **Permitir separação em excesso de ordem de transferência:** *Sim*

### <a name="set-up-a-mobile-device-menu-item-to-allow-for-over-picking"></a>Configurar um item de menu do dispositivo para permitir separação em excesso

Este é o procedimento geral para configurar um item de menu de dispositivo móvel para habilitar a separação em excesso. Dependendo das necessidades comerciais para o nível de permissão do trabalhador que usará o menu do dispositivo móvel, alguns parâmetros podem ser ativados ou desativados.

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
1. No painel da lista, selecione o registro chamado *Separação de vendas*. Se nenhum registro existente tiver esse nome, crie-o. Confirme ou defina os seguintes valores para o registro:

    - **Nome do item de menu:** *separação de vendas*
    - **Título:** *separação de vendas*
    - **Modo:** *Trabalho*
    - **Usar trabalho existente:** *Sim*
    - **Direcionado por:** *direcionado pelo usuário*
    - **Substituir placa de licença de destino:** *Sim*
    - **Substituir placa de licença durante put:** *Sim*
    - **Manter trabalho bloqueado pelo usuário:** *Sim*
    - **Permitir separação em excesso:** *Sim*

> [!IMPORTANT]
> Depois que os parâmetros relevantes para o item de menu do trabalhador e dispositivo móvel estiverem habilitados, a separação em excesso poderá ser processada somente pelo dispositivo móvel.

## <a name="example-scenario"></a>Cenário de exemplo

Depois que a configuração de pré-requisitos, configuração do trabalhador e itens de menu estiverem corretas, você estará pronto para trabalhar com o recurso.

### <a name="create-a-sales-order-that-allows-for-overdelivery"></a>Criar uma ordem de venda que permita entrega em excesso

1. Acesse **Vendas e Marketing \> Ordens de venda \> Todas as ordens de venda**.
1. Selecione **Nova** para criar uma nova ordem de venda.
1. Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:

    - **Conta de cliente:** *US-001*
    - **Depósito:** *24*

1. Selecione **OK**.
1. A nova ordem de venda é aberta. Na guia rápida **Linhas da ordem de venda**, adicione uma linha que tenha as seguintes configurações:

    - **Número de item:** *A0001*
    - **Quantidade:** *10*

1. Na FastTab **Detalhes da linha**, na guia **Entrega**, defina o campo **Entrega excedente** como *10*.
1. Na FastTab **Linhas da ordem de venda**, selecione **Estoque \> Reserva**.
1. Na página **Reserva**, no Painel de Ação, selecione **Reservar lote** para reservar o estoque.
1. Feche a página **Reserva**.
1. No Painel de Ações, na guia **Depósito**, selecione **Liberar para o depósito**.

Quando a liberação é concluída, você recebe mensagens informativas que mostram as IDs do ciclo e da carga que foram criadas.

### <a name="get-the-work-id-and-license-plate-number-for-the-new-order"></a>Obter a ID de trabalho e o número da placa de licença da nova ordem

Quando você liberou a ordem de venda para o depósito, o sistema deveria ter criado uma nova ID de trabalho que tenha uma linha de separação. Siga estas etapas para localizar a ID de trabalho e a atribuição da placa de licença.

1. Acesse **Gerenciamento de depósito \> Trabalho \> Detalhes do trabalho**.
1. Na grade **Visão geral**, procure na coluna **Número da ordem** as duas ordens de venda recém-criadas. Para essa ordem de venda, anote a ID de trabalho correspondente.
1. Selecione a linha da nova ordem de venda para mostrar as informações relacionadas na grade **Linhas**. Anote o local de onde o item será separado.
1. Acesse **Gerenciamento de estoque \> Consultas e relatórios \> Lista disponível**.
1. No Painel de Ação, selecione **Dimensões**.
1. Na caixa de diálogo **Exibição de dimensão**, verifique se as caixas de seleção **Placa de licença**, **Depósito** e **Número do item** estão marcadas e, em seguida, selecione **OK**.
1. No painel **Filtro**, defina os seguintes filtros:

    - **Número do item** - **é um de** – *A0001*
    - **Depósito** – **começa com** – *24*

1. Selecione **Aplicar**.
1. Anote os valores da **Placa de licença** que são exibidos.

### <a name="over-pick-the-order-by-using-the-warehouse-management-mobile-app"></a>Separar em excesso a ordem usando o aplicativo móvel de Warehouse Management

1. Entre no aplicativo móvel do Gerenciamento de Depósito como um usuário no depósito *24*.
1. Acesse **Saída \> Separação de Venda**.
1. No campo **Digitalizar ID do trabalho ou placa de licença**, insira a ID de trabalho criada para a ordem de venda.
1. Selecione **OK** (símbolo de marca de seleção).
1. Selecione **Separação em excesso**.
1. Defina o campo **Qtde. de separação** como *14*.
1. Selecione **OK** (símbolo de marca de seleção).

    Na página **Separação em excesso**, você recebe a seguinte mensagem: "a entrega em excesso da linha é 40%, mas a entrega em excesso permitida é apenas 10%". Esta mensagem indica que a quantidade separada que você inseriu excede o limite de entrega excedente. O limite de entrega excedente para a linha da ordem de venda é de 10%. Portanto, para uma quantidade especificada de 10, você só pode separar por 1, resultando em uma quantidade de separação total igual a 11.

1. Defina o campo **Qtde. de separação** como *11*.
1. Selecione **OK** (símbolo de marca de seleção).
1. No campo **Placa de licença**, insira a placa de licença que você anotou na seção anterior.
1. No campo **Placa de licença de destino**, insira a placa de licença de destino. Observe que são exibidos o local de separação (*FLOOR-001*), o item (*A0001*) e a quantidade (*11 pacotes*).
1. Selecione **OK** (símbolo de marca de seleção).
1. Examine as informações na página **Ordens de venda - Colocar**. O campo **Loc** deve indicar que os itens separados vão para o local de *BAYDOOR*.
1. Selecione **OK** (símbolo de marca de seleção).

Na página **Digitalizar uma ID de trabalho/ID de placa de licença**, você receberá a mensagem "Trabalho Concluído". Esta mensagem indica que a ID de trabalho da ordem de venda foi concluída, e a quantidade separada em excesso não excede o limite de entrega excedente de 10%.
