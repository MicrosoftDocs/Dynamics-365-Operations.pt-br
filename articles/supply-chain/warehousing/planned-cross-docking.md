---
title: Distribuição integrada planejada
description: Este artigo descreve a distribuição integrada planejada avançada, na qual a quantidade de estoque necessária para uma ordem é direcionada diretamente do recebimento ou da criação para a área de preparo ou doca de saída correta. Todo o estoque restante da origem de entrada é direcionado para o local de armazenamento correto por meio do processo normal de armazenamento.
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSCrossDockingTemplate, WHSLoadPostMethod, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSPlannedCrossDocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: b530cc1403458775fd330e826a32417d3b03bf25
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334555"
---
# <a name="planned-cross-docking"></a>Distribuição integrada planejada

[!include [banner](../includes/banner.md)]

Este artigo descreve a distribuição integrada planejada avançada. A distribuição integrada é um processo de depósito no qual a quantidade de estoque necessária para uma ordem é direcionada diretamente do recebimento ou da criação para a área de preparo ou doca de saída correta. Todo o estoque restante da origem de entrada é direcionado para o local de armazenamento correto por meio do processo normal de armazenamento.

A distribuição integrada permite aos trabalhadores ignorar o armazenamento de entrada e a separação de saída de um estoque que já esteja marcado para uma ordem de saída. Portanto, o número de vezes que o estoque é tocado é minimizado, sempre que possível. Além disso, como há menos interação com o sistema, a economia de tempo e espaço no chão de fábrica do depósito aumenta.

Antes de executar a distribuição integrada, você deve configurar um novo modelo de distribuição integrada, no qual a fonte de fornecimento e outros conjuntos de requisitos para distribuição integrada sejam especificados. Conforme a ordem de saída é criada, a linha deve ser marcada em relação a uma ordem de entrada que contenha o mesmo item. Você pode selecionar o campo de código de diretriz no modelo de distribuição integrada, semelhante à forma como configura reabastecimento e ordens de compra.

No momento do recebimento da ordem de entrada, a configuração da distribuição integrada identifica automaticamente a necessidade de distribuição integrada e cria o trabalho de movimento para a quantidade necessária, com base na configuração da diretiva de localização.

> [!NOTE]
> As transações de estoque *não* têm seu registro cancelado quando o trabalho de distribuição integrada é cancelado, mesmo que a configuração para esse recurso esteja ativada nos Parâmetros de gerenciamento de depósito.

## <a name="turn-on-the-planned-cross-docking-features"></a>Ativar os recursos de distribuição integrada planejada

Se você estiver executando o Supply Chain Management versão 10.0.28 ou anterior, talvez precise habilitar a distribuição integrada planejada para poder usá-lo. Vá para [Gerenciamento de recurso](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e ative os seguintes recursos na seguinte ordem:

1. *Distribuição integrada planejada*<br>(A partir do Supply Chain Management versão 10.0.29, este recurso é obrigatório e não pode ser desativado.)
1. *Modelos de distribuição integrada com diretivas de localização*<br>(A partir do Supply Chain Management versão 10.0.29, este recurso está ativado por padrão.)
    > [!NOTE]
    > Este recurso permite que o campo **Código de diretriz** seja especificado no modelo de distribuição integrada, semelhante à forma como você configura os modelos de reabastecimento. Habilitar esse recurso impedirá que você adicione um código de diretriz nas linhas do modelo de trabalho de distribuição integrada para a última linha *Colocar*. Isso garante que o local colocado final possa ser determinado durante a criação do trabalho antes de considerar os modelos de trabalho.

## <a name="setup"></a>Configurar

### <a name="regenerate-load-posting-methods"></a>Regenerar métodos de lançamento da carga

A distribuição integrada planejada é implementada como um método de lançamento da carga. Depois de ativar o recurso, você deve regenerar os métodos.

1. Acesse **Gerenciamento de depósito \> Configuração \> Métodos de lançamento da carga**.
1. No Painel de Ação, selecione **Regenerar métodos**.

    Após a conclusão da regeneração, você deverá ver um método com um valor *planCrossDocking* em **Nome do método**.

1. Feche a página.

### <a name="create-a-cross-docking-template"></a>Criar um modelo de distribuição integrada

1. Acesse **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelos de distribuição integrada**.
1. No Painel de Ação, selecione **Novo** para criar um modelo.
1. No cabeçalho, defina os seguintes valores:

    - **Sequência:** *1*

        Este campo define a ordem em que os modelos são avaliados.

    - **ID do modelo de distribuição integrada:** *51*
    - **Descrição:** *Depósito 51*
    - **Política de liberação de demanda:** *Antes do recebimento de fornecimento*
    - **Depósito:** *51*

1. A configuração na FastTab **Planejamento** controla como o modelo funciona. Defina os seguintes valores:

    - **Requisitos de demanda:** *Nenhum*

        Este campo define os requisitos do estoque de demanda. Se a demanda precisar ser vinculada ao fornecimento antes da liberação, selecione *Marcação*. Se a demanda tiver que ser reservada para a ordem em relação ao fornecimento antes da liberação, selecione *Reserva da ordem*.

    - **Tipo de localização:** *Locais de remessa*

        Este campo define se o trabalho de distribuição integrada deve usar os locais de preparo/carga da remessa ou se deve usar diretivas de localização para localizar seus próprios locais de preparo/carga.

    - **Modelo de trabalho:** Deixar este campo em branco.

        Este campo define o modelo de trabalho que deve ser usado quando o trabalho de distribuição integrada é criado.

    - **Revalidar no recebimento de fornecimento:** *Não*

        Esta opção define se o fornecimento deve ser revalidado durante o recebimento. Se essa opção estiver definida como *Sim*, a janela de tempo máximo e o intervalo de dias para o vencimento serão verificados.

    - **Código de diretiva:** deixe este campo em branco

        Esta opção é habilitada pelo recurso *Modelos de distribuição integrada com diretivas de localização* (a partir do Supply Chain Management versão 10.0.29, o recurso é ativado por padrão). O sistema usa diretivas de localização para ajudar a determinar o melhor local de destino para o estoque de distribuição integrada. Você pode configurá-la atribuindo um código de diretiva a cada modelo de distribuição integrada relevante. Se um código de diretiva estiver definido, o sistema pesquisará diretivas de localização por código de diretiva quando o trabalho for gerado. Dessa forma, você pode limitar as diretivas de localização usadas para um modelo de distribuição integrada específico.

    - **Validar janela de tempo:** *Sim*

        Esta opção define se a janela de tempo máximo deve ser avaliada quando uma fonte de fornecimento é selecionada. Se essa opção estiver definida como *Sim*, os campos relacionados às janelas de tempo máximo e mínimo serão disponibilizados.

    - **Janela de tempo máximo:** *5*

        Este campo define o período máximo permitido entre a chegada do fornecimento e a saída da demanda.

    - **Unidade da janela de tempo máximo:** *Dias*
    - **Janela de tempo mínimo:** *0*

        Este campo define o período mínimo permitido entre a chegada do fornecimento e a saída da demanda.

    - **Unidade da janela de tempo mínimo:** *Dias*
    - **Intervalo de dias para o vencimento:** *0*

        *Critérios de FEFO (primeiro a vencer, primeiro a sair):* Este campo define o número máximo de dias entre a data de vencimento do primeiro lote a vencer atualmente no depósito e do lote que está sendo recebido.

1. Na FastTab **Fontes de fornecimento**, especifique os tipos de fornecimento válidos para o modelo. Selecione **Novo** e defina os valores a seguir:

    - **Número de sequência:** *1*
    - **Fonte de fornecimento:** *Ordem de compra*

> [!NOTE]
> Você pode configurar uma consulta para determinar quando um modelo de distribuição integrada específico será usado. A consulta para modelos de distribuição integrada tem somente a tabela *InventTable* (itens) e a tabela interna conjunta *WHSInventTable* (itens WMS). Se quiser adicionar outras tabelas à consulta, você poderá associá-las usando somente *existir junções* ou *não existir junções*. Ao filtrar pelas tabelas conjuntas, um registro da tabela principal é recuperado para cada registro correspondente na tabela conjunta. Se o tipo de junção for *existir junções*, a pesquisa terminará depois que a primeira correspondência for encontrada. Por exemplo, se você unir a tabela de linha da ordem de venda à tabela de itens, o sistema validará e retornará os itens para os quais pelo menos uma linha da ordem de venda tem a condição definida. Basicamente, os dados são recuperados da tabela pai (itens), e não da tabela filho (linha da ordem de venda). Portanto, a filtragem por documentos de origem, como linhas de ordem de venda ou clientes, não pode ser realizada.

### <a name="create-a-work-class"></a>Criar uma classe de trabalho

1. Acesse **Gerenciamento de depósito \> Configuração \> Trabalho \> Classes de trabalho**.
1. No Painel de Ação, selecione **Novo** para criar uma classe de trabalho.
1. Defina os seguintes valores:

    - **ID da classe de trabalho:** *CrossDock*
    - **Descrição:** *Distribuição Integrada*
    - **Tipo de ordem de serviço:** *Distribuição integrada*

### <a name="create-a-work-template"></a>Criar um modelo de trabalho

1. Acesse **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelo de trabalho**.
1. Defina o campo **Tipo de ordem de serviço** como *Distribuição integrada*.
1. No Painel de Ação, selecione **Novo** para adicionar uma linha à guia **Visão geral**.
1. Na nova linha, defina os valores a seguir:

    - **Número de sequência:** *1*
    - **Modelo de trabalho:** *Distribuição Integrada 51*
    - **Descrição do modelo de trabalho:** *Distribuição Integrada 51*

1. Selecione **Salvar** para disponibilizar a FastTab **Detalhes do Modelo de Trabalho**.
1. Na FastTab **Detalhes do Modelo de Trabalho**, selecione **Novo** para adicionar uma linha à grade.
1. Na nova linha, defina os valores a seguir:

    - **Tipo de trabalho:** *Separar*
    - **ID da classe de trabalho:** *CrossDock*

1. Selecione **Novo** para adicionar outra linha e defina os seguintes valores nela:

    - **Tipo de trabalho:** *Colocar*
    - **ID da classe de trabalho:** *CrossDock*

1. Selecione **Salvar** e confirme se a caixa de seleção **Válido** está marcada para o modelo *Distribuição Integrada 51*.
1. Opcional: selecione **Editar consulta** se quiser definir critérios para controlar quando e onde o modelo de trabalho será usado.

    Você pode configurar uma consulta para determinar quando um modelo de trabalho em particular será usado. Por exemplo, você pode especificar que um modelo possa ser usado para trabalhar somente em um local específico. Se quiser que o modelo de trabalho de distribuição integrada seja aplicado em um local específico, você deverá filtrar o campo **Local inicial**, não o campo **Local**, porque a criação de trabalho para os processos de entrada (compra, distribuição integrada e reabastecimento) inicia a partir da linha put. Quando o trabalho é criado, a diretiva de localização define o campo **Local** para o local de put. No entanto, a localização de separação é armazenada no campo **Local inicial**.

> [!NOTE]
> As IDs de classe de trabalho dos tipos de trabalho *Separar* e *Colocar* devem ser as mesmas.

### <a name="create-location-directives"></a>Criar diretivas de localização

1. Acesse **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.
1. No painel esquerdo, defina o campo **Tipo de ordem de serviço** como *Distribuição integrada*.
1. No Painel de Ação, selecione **Novo** e defina os valores a seguir:

    - **Número de sequência:** *1*
    - **Nome:** *Colocar Distribuição Integrada 51*
    - **Tipo de trabalho:** *Colocar*
    - **Local:** *5*
    - **Depósito:** *51*

1. Selecione **Salvar** para disponibilizar a FastTab **Linhas**.
1. Na FastTab **Linhas**, selecione **Novo** para adicionar uma linha à grade.
1. Na nova linha, defina os valores a seguir:

    - **Quantidade inicial:** *1*
    - **Quantidade final:** *1000000*

1. Selecione **Salvar** para disponibilizar a FastTab **Ações de Diretiva de Localização**.
1. Na FastTab **Ações de Diretiva de Localização**, selecione **Novo** para adicionar uma linha à grade.
1. Na nova linha, defina os valores a seguir:

    - **Nome:** *Porta da baía*
    - **Uso de localização fixa:** *Localizações fixas e não fixas*

1. Selecione **Salvar** para disponibilizar o botão **Editar consulta** na barra de ferramentas **Ações de Diretiva de Localização**.
1. Selecione **Editar consulta** para abrir o editor de consultas.
1. Na guia **Intervalo**, verifique se as duas linhas a seguir foram configuradas:

    - Linha 1:

        - **Tabela:** *Localizações*
        - **Tabela Derivada:** *Localizações*
        - **Campo:** *Depósito*
        - **Critérios:** *51*

    - Linha 2:

        - **Tabela:** *Localizações*
        - **Tabela Derivada:** *Localizações*
        - **Campo:** *Localização*
        - **Critérios:** *Porta da baía*

1. Selecione **OK** para fechar o editor de consultas.

### <a name="create-a-mobile-device-menu-item"></a>Criar um item de menu de dispositivo móvel

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
1. Na lista de itens de menu no painel esquerdo, selecione **Armazenamento de compra**.
1. Selecione **Editar**.
1. Na FastTab **Classes de trabalho**, selecione **Novo** para adicionar uma linha à grade.
1. Na nova linha, defina os valores a seguir:

    - **ID da classe de trabalho:** *CrossDock*
    - **Tipo de ordem de serviço:** *Distribuição integrada*

1. Selecione **Salvar**.

## <a name="scenario"></a>Cenário

### <a name="create-a-purchase-order"></a>Criar uma ordem de compra

Siga estas etapas para criar uma ordem de compra como fonte de fornecimento.

1. Acesse **Compras \> Ordens de compra \> Todas ordens de compra**.
1. No Painel de Ações, selecione **Novo**.
1. Na caixa de diálogo **Criar ordem de compra**, defina os seguintes valores:

    - **Conta do fornecedor:** *104*
    - **Depósito:** *51*

1. Selecione **OK** e anote o número da ordem.
1. Uma nova linha é adicionada à FastTab **Linhas da ordem de compra**. Nessa linha, defina os seguintes valores:

    - **Número de item:** *A0001*
    - **Quantidade:** *5*

### <a name="create-a-sales-order"></a>Criar uma ordem de venda

Siga estas etapas para criar uma ordem de venda como origem de demanda.

1. Acesse **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. No Painel de Ações, selecione **Novo**.
1. Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:

    - **Conta de cliente:** *US-002*
    - **Depósito:** *51*

1. Selecione **OK**.
1. Uma nova linha é adicionada à FastTab **Linhas da ordem de venda**. Nessa linha, defina os seguintes valores:

    - **Número de item:** *A0001*
    - **Quantidade:** *3*

### <a name="create-planned-cross-docking"></a>Criar distribuição integrada planejada

Siga estas etapas para criar a distribuição integrada planejada com base na ordem de venda.

1. Na página **Detalhes da ordem de venda** referente à ordem de venda que você acabou de criar, no Painel de Ação, na guia **Depósito**, no grupo **Ações**, selecione **Liberar para o depósito**.

    A ação de liberação para o depósito cria uma linha de remessa e carga para a linha da ordem de venda e tenta alocar o estoque.
    
    Você receberá uma mensagem informativa. Você também receberá a seguinte mensagem de aviso: "Nenhum trabalho foi criado para a onda XXXX. Consulte o log de histórico de criação de trabalho para obter detalhes." Esse comportamento é esperado, pois não há estoque no depósito.

1. Na FastTab **Linhas da ordem de venda**, no menu **Depósito**, selecione **Detalhes da remessa**.

    A página **Detalhes da remessa** é exibida e mostra a remessa que foi criada para a ordem de venda.

1. Na FastTab **Linhas de carga**, observe que o campo **Quantidade da Distribuição integrada planejada** está definido como *3*. Como não havia estoque disponível no depósito, mas uma fonte de fornecimento válida será recebida na janela de tempo definida no modelo de distribuição integrada, a quantidade de distribuição integrada foi criada.
1. Na FastTab **Linhas de carga**, selecione **Distribuição integrada planejada** para exibir os detalhes da distribuição integrada que foi criada.

## <a name="process-the-cross-docking"></a>Processar a distribuição integrada

### <a name="purchase-order-receiving-on-the-warehousing-mobile-app"></a>Recebimento de ordem de compra no aplicativo móvel de depósito

O sistema receberá a quantidade de 5 da ordem de compra no local de recebimento e criará dois itens de trabalho.

Na primeira ID de trabalho criada, o **Tipo de ordem de serviço** tem o valor *Distribuição integrada* e está vinculado à ordem de venda. Ela tem uma quantidade de 3 e é direcionada para o local de remessa final de modo que possa ser remetida imediatamente.

Na segunda ID de trabalho criada, o **Tipo de ordem de serviço** tem o valor *Ordens de compra* e está vinculado à ordem de compra. Ela tem a quantidade restante de 2 que não passou por distribuição integrada e é direcionada para o armazenamento.

1. Entre no dispositivo móvel como um usuário no depósito *51*.
1. Acesse **Entrada \> Recebimento de Compra**.
1. No campo **PONum**, insira o número da ordem de compra.
1. No campo **Qtd.**, insira *5*.
1. Selecione **OK**.
1. Na página seguinte, defina o campo **Item** como *A0001*.
1. Selecione **OK**.
1. Na página seguinte, confirme os valores de **PONum**, **Item** e **Qtd.** selecionando **OK**.

    Você receberá uma mensagem "Trabalho Concluído".

1. Selecione **Cancelar** para sair.

### <a name="put-away-to-cross-docking-and-bulk"></a>Armazenamento para distribuição integrada e em massa

No momento, ambas as IDs de trabalho têm a mesma placa de licença de destino. Para concluir as próximas etapas, você deve obter a ID de trabalho e a ID da placa de licença de destino. É possível obter essas informações nos detalhes do trabalho da linha de ordem de compra e da linha de ordem de venda. Como alternativa, você pode acessar **Gerenciamento de depósito \> Trabalho \> Detalhes do trabalho** e filtrar trabalhos em que o valor de **Depósito** seja *51*.

1. No dispositivo móvel, Acesse **Entrada \> Armazenamento de compra** e insira a placa de licença de destino do trabalho.
1. No campo **ID**, insira a ID da placa de licença de destino nos detalhes do trabalho.

    A página de separação da distribuição integrada mostra o local de separação (*RECV*), a placa de licença de destino (*placa de licença*), o item (*A0001*) e a quantidade (*3*).

1. Selecione **OK**.
1. No campo **LP de destino**, insira uma placa de licença de destino para a ID da placa de licença que deve ser colocada (passar por distribuição integrada) no local de remessa. Você pode selecionar qualquer ID de placa de licença.
1. Selecione **OK**.
1. Na página seguinte, no campo **ID**, insira a ID da placa de licença de destino.
1. Selecione **OK**.
1. Confirme o trabalho para separar a quantidade restante de 2 e selecione **OK**.
1. Na página seguinte, selecione **Concluído** para finalizar o processo de separação e iniciar o processo de armazenamento.

    O aplicativo móvel apresenta a localização e a placa de licença onde colocar o item.

1. Confirme o armazenamento em massa **Colocar** selecionando **OK**.
1. Na página seguinte, confirme **Colocar** da distribuição integrada selecionando **OK**.

    Você receberá uma mensagem "Trabalho Concluído".

1. Selecione **Cancelar** para sair.

A ilustração a seguir mostra como o trabalho de distribuição integrada concluído pode aparecer no Microsoft Dynamics 365 Supply Chain Management.

![Trabalho de distribuição integrada concluído.](media/PlannedCrossDockingWork.png "Trabalho de distribuição integrada concluído")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
