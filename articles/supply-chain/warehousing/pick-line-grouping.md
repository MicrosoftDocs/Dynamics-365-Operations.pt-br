---
title: Agrupamento de linhas de separação
description: Este tópico oferece uma visão geral de agrupamento de linhas de separação.
author: Mirzaab
manager: tfehr
ms.date: 12/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 7ab8cdd7cad5420aca0de53e59220da9e230d411
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234624"
---
# <a name="pick-line-grouping"></a>Agrupamento de linhas de separação

[!include [banner](../includes/banner.md)]

O agrupamento de linhas de separação permite que várias linhas de trabalho que têm o mesmo item e local podem ser combinadas em uma única separação que é apresentada ao usuário em um dispositivo móvel. Portanto, os trabalhadores de depósito podem receber as instruções mais eficientes possíveis, mas a separação necessária de linhas de trabalho (para diferentes contêineres, ordens etc.) ainda pode ser mantida no sistema.

## <a name="turn-on-the-pick-line-grouping-feature"></a>Ativar o recurso de agrupamento de linhas de separação

Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema. Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo se necessário. Nesse caso, o recurso é listado da seguinte maneira:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *Agrupamento de linhas de separação*

## <a name="set-up-pick-line-grouping"></a>Configurar agrupamento de linhas de separação

### <a name="create-a-mobile-device-menu-item"></a>Criar um item de menu de dispositivo móvel

1. Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
1. No Painel de Ações, selecione **Novo**.
1. No campo **Nome do item de menu** digite *Separação de linhas do grupo de vendas*.
1. No campo **Título**, digite *Separação de linhas do grupo de vendas*. Esse título será exibido no menu do dispositivo móvel.
1. No campo **Modo**, selecione *Trabalho*.
1. Defina a opção **Usar trabalho existente** para *Sim*.
1. Na FastTab **Geral**, defina os seguintes valores:

    - No campo **Direcionado por**, selecione *Direcionado pelo usuário*.
    - Defina a opção **Gerar placa de licença** como *Sim*.
    - Defina a opção **Separação por grupo** como *Sim*.
    - Aceite os valores padrão para as opções restantes.

1. Siga estas etapas para configurar as classes de trabalho válidas para o item de menu do dispositivo móvel:

    1. Na FastTab **Classes de trabalho**, escolha **Novo**.
    2. No campo **ID da classe de trabalho**, você pode selecionar *Vendas* ou *Separação de OV*, dependendo do depósito que você usará. Para esse cenário, selecione *Separação de OV*.

        O campo **Tipo de ordem de serviço** é automaticamente definido como *Ordens de venda*.

### <a name="set-up-a-mobile-device-menu"></a>Configura um menu de dispositivo móvel

Siga estas etapas para adicionar o item de menu recém-criado ao menu **Saída**.

1. Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Menu do dispositivo móvel**.
1. No Painel de Ações, selecione **Editar**.
1. O painel de lista mostra todos os menus de dispositivos móveis existentes. Selecione *Saída* na lista.
1. Na lista **Menus e itens de menu disponíveis**, localize e selecione o item de menu *Separação de linhas do grupo de vendas* que você criou.
1. Selecione o botão de seta para a direita a fim de mover o item de menu *Separação de linhas do grupo de vendas* para a lista **Estrutura de menu**.
1. Use os botões de seta para cima e para baixo para mover o item de menu para a posição desejada na estrutura de menu.
1. No Painel de ações, selecione **Salvar**.

### <a name="set-up-a-work-template"></a>Configurar um modelo de trabalho

1. Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelo de trabalho**.
1. No campo **Tipo de ordem de trabalho**, selecione *Ordens de compra*.
1. Na grade **Visão geral**, localize e selecione o modelo de trabalho que deve ser usado com essa função. Para esse cenário, selecione o modelo *51 Estágio de separação*.
1. No Painel de Ações, selecione **Editar consulta**.
1. Na caixa de diálogo do editor, na guia **Classificação**, selecione **Adicionar** e defina os seguintes valores para a nova linha:

    - No campo **Tabela** coluna, selecione *Transações de trabalho temporário*.
    - Na coluna **Tabela derivada**, selecione *Transações de trabalho temporário*.
    - Na coluna **Campo**, selecione *Número do item*.
    - Na coluna **Direção da pesquisa**, selecione *Crescente*.

1. Selecione **OK** para fechar a caixa de diálogo e salvar a seleção.
1. Você receberá a seguinte mensagem: "O agrupamento será redefinido. Deseja continuar?" Selecione **Sim** para continuar.

> [!IMPORTANT]
> Para que a funcionalidade agrupamento de linhas de separação funcione, as linhas de trabalho devem ser classificadas por ID do item. Se as linhas que têm os mesmos itens não forem sequenciadas uma após a outra, elas não serão agrupadas.

## <a name="example"></a>Exemplo

### <a name="create-picking-work"></a>Criar trabalho de separação

Antes de configurar o agrupamento de linhas de separação, você deve criar algum trabalho de saída qualificado.

1. Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. Selecione **Novo** para criar uma ordem de venda.
1. No campo **Conta do cliente**, selecione *US-004*.
1. Na Guia Rápida **Geral**, no campo **Depósito**, selecione *51*.
1. Selecione **OK**.
1. Na FastTab **Linhas de ordem de venda**, adicione as seguintes seis linhas:

    - **Linha 1:** No campo **Número do item**, selecione *M9200*. No campo **Quantidade**, insira *3*.
    - **Linha 2:** No campo **Número do item**, selecione *M9201*. No campo **Quantidade**, insira *3*.
    - **Linha 3:** No campo **Número do item**, selecione *M9202*. No campo **Quantidade**, insira *2*.
    - **Linha 4:** No campo **Número do item**, selecione *M9200*. No campo **Quantidade**, insira *1*.
    - **Linha 5:** No campo **Número do item**, selecione *M9200*. No campo **Quantidade**, insira *3*.
    - **Linha 6:** No campo **Número do item**, selecione *M9202*. No campo **Quantidade**, insira *7*.

    Aqui está um resumo das quantidades totais de cada item:

    - **Item M9200:** *7* cada
    - **Item M9201:** *3* cada
    - **Item M9202:** *9* cada

1. Antes de liberar as ordens para o depósito, você deve verificar se os locais de separação têm estoque suficiente para todos os itens em todas as ordens. Revise a configuração **Diretiva de localização** para determinar quais locais de separação são usadas para separação da ordem de venda. Se estiver usando o ambiente de dados de demonstração da Contoso para o depósito *51*, confirme se há estoque disponível.

    Agora reserve o estoque para cada linha.

1. Na FastTab **Linhas de ordem de venda**, selecione uma das linhas que devem ser reservadas.
1. No menu **Estoque** acima da grade, selecione **Reserva**.
1. Na página **Reserva**, no Painel de Ações, selecione **Reservar lote** para aplicar a reserva. Depois feche a página.
1. Repita as etapas 8 a 10 para as linhas restantes que devem ser reservadas.

    Agora é necessário liberar a ordem de venda para o depósito.

1. No Painel de Ações, na guia **Depósito**, selecione **Liberar para o depósito**.

    Você receberá uma mensagem informando que uma remessa e um ciclo foram criados e que o ciclo foi enviado para execução em lote.

    Quando o ciclo e todos os trabalhos downstream tiverem sido concluídos, uma ID de trabalho será criada para o trabalho com seis linhas. As linhas são classificadas por número de item.

1. Acesse **Gerenciamento de depósito \> Trabalho \> Todos os trabalhos** para exibir o trabalho criado. Anote o valor da **ID do Trabalho**, pois precisará usá-lo no próximo procedimento.

### <a name="initiate-picking-from-the-mobile-device"></a>Iniciar a separação no dispositivo móvel

1. Entre no dispositivo móvel como um usuário configurado para o depósito *51*.
1. No dispositivo móvel, selecione o menu que inclui o novo item de menu do dispositivo móvel. Para esse cenário, selecione **Saída**.
1. Selecione o item de menu **Separação de linhas do grupo de vendas** para iniciar a separação.
1. Insira o valor **ID do Trabalho** que anotou no procedimento anterior.

    Você verá uma etapa de separação em que todas as linhas de separação do item *M9200* são agrupadas e será instruído a separar *7* de cada item *M9200*.

    > [!IMPORTANT]
    > No dispositivo móvel, o trabalho de separação para as três linhas de trabalho de separação foi agregado em uma etapa de separação para o usuário.

1. Confirme a etapa de separação.
1. Vá para a página do trabalho para obter a ID do trabalho e observe que todas as três linhas de separação do item *M9200* foram fechadas simultaneamente.
1. Volte para o dispositivo móvel e continue separando. A linha de trabalho 4 do item *M9201* deve ser apresentada. Como havia apenas uma linha de trabalho na ordem, não há nada a ser agregado.
1. Confirme a etapa de separação.
1. A última etapa de separação no dispositivo móvel agrega as duas últimas linhas de separação da ordem de trabalho.
1. Conclua a etapa para separar *9* de cada um dos itens *M9202*.
1. Confirme a etapa Put e os pares Separar/Colocar adicionais para concluir o trabalho.

> [!IMPORTANT]
>
> - As linhas de trabalho podem ser agrupadas somente se estiverem em sequência.
> - A seguinte funcionalidade não é suportada:
>
>   - Itens de peso variável
>
>    Se houver itens de peso variável no trabalho, você receberá uma mensagem de erro antes de começar a separar.
>
>   - Separação de peças
>   - Linhas de trabalho que têm trabalho de reabastecimento não concluído
>   - Separação em excesso
>   - Separação insuficiente com realocação de item


[!INCLUDE[footer-include](../../includes/footer-banner.md)]