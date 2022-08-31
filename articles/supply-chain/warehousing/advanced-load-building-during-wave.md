---
title: Criação de carga avançada durante um ciclo
description: Este artigo contém informações sobre a criação avançada de carga de ciclo, o que automaticamente atribui remessas a ciclos existentes durante a execução de ciclos. Por essa razão, você pode criar cargas significativas que representem caminhões sem precisar usar a bancada de planejamento de carga.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSPostMethod,WHSWaveTemplateTable,WHSLoadMixGroup,WHSLoadBuildTemplate, WHSWaveTableListPage, TMSLoadBuildTemplateApply, TMSLoadBuildTemplates, TMSLoadBuildTemplateCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: c9d41645531fa4318289f32a564c34f0f92681df
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335830"
---
# <a name="advanced-load-building-during-wave"></a>Criação de carga avançada durante ondas

[!include [banner](../includes/banner.md)]

A criação avançada de carga de onda automaticamente atribui remessas a ondas existentes durante a execução de uma onda. Por essa razão, você pode criar cargas significativas que representem caminhões sem precisar usar a bancada de planejamento de carga. Este recurso é útil para empresas que desejam usar o conceito de cargas para rastrear e planejar a remessa de mercadorias em um caminhão/trailer, mas que não querem criar essas cargas manualmente todos os dias.

Durante o processamento de ondas, o sistema normalmente cria uma nova carga para cada remessa para a qual não há uma carga atribuída. No entanto, quando a criação avançada de carga de onda está ativada, o sistema atribui cada remessa não atribuída a uma carga existente (se houver uma carga apropriada), e novas cargas serão criadas somente quando necessário. A criação avançada de carga de onda cria as novas cargas automaticamente com base nos critérios por você definidos.

Para usar o recurso, é necessário configurar o sistema da seguinte maneira:

- Crie *modelos de onda* que incluam o novo método **buildLoads**. Esse método torna a criação avançada de carga de onda disponível para ondas que usam esses modelos.
- Configure *modelos de criação de carga*, cada um vinculado a um método e a um modelo de onda específicos. Os modelos de criação de carga controlam à qual carga (existente ou nova) as linhas de carga que estão na onda devem ser adicionadas. Você pode combinar ou separar remessas com base em critérios como o modelo de carga, o equipamento e outros valores de campo na linha de carga.
- Defina *grupos mistos de carga* para controlar quais itens devem e não devem ser combinados em uma única carga. Também é possível especificar se a restrição deve gerar um aviso ou um erro e se é necessário avaliar a restrição volumétrica do modelo de carga.

## <a name="turn-on-advanced-wave-load-building-in-your-system"></a>Ativar a criação avançada de carga de onda no sistema

Para poder usar a criação avançada de carga de ciclo, dois recursos devem estar ativados no sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status desses recursos e ativá-los se necessário. No espaço de trabalho **Gerenciamento de recursos**, os recursos estão listados da seguinte forma:

- Recurso de criação de carga de onda:

    - **Módulo:** *Gerenciamento de Depósito*
    - **Nome do recurso:** *Recurso de criação de carga de onda*

- Código da etapa da onda em toda a organização:

    - **Módulo:** *Gerenciamento de Depósito*
    - **Nome do recurso:** *Código da etapa da onda em toda a organização*

### <a name="make-sample-data-available"></a>Disponibilizar dados de exemplo

Para trabalhar com essa demonstração usando os registros e valores de exemplo especificados aqui, você deve usar um sistema em que os [dados de demonstração](../../fin-ops-core/fin-ops/get-started/demo-data.md) padrão estejam instalados. Além disso, você deve selecionar a entidade legal **USMF** antes de começar.

Você também pode usar esta demonstração como orientação para usar o recurso ao trabalhar em um sistema de produção. No entanto, nesse caso, você deve substituir seus próprios valores e talvez não tenha alguns tipos de registros necessários fornecidos pelos dados de demonstração padrão.

### <a name="make-sure-that-the-scenario-setup-includes-enough-available-inventory"></a>Verificar se a configuração do cenário inclui estoque disponível suficiente

Se você estiver trabalhando com os dados de demonstração da **USMF**, primeiro deverá se certificar de que o sistema está configurado de maneira que haja estoque suficiente em cada local relevante. Para esta demonstração, a expectativa é de que o seguinte estoque esteja disponível no depósito *62*:

- **Item A0001:** 10 pacotes
- **Item A0002:** 10 pacotes
- **Item M9200:** 10 unidades

O **Item M9200** deve ser adicionado ao depósito. Execute os procedimentos nas subseções a seguir para adicionar o estoque do item.

#### <a name="create-a-new-license-plate-id"></a>Criar uma nova ID de placa de licença

1. Acesse **Gerenciamento de depósito** \> **Configuração** \> **Depósito** \> **Placas de licença**.
1. No Painel de Ações, selecione **Novo**.
1. Na nova linha, no campo **Placa de licença**, digite *LP6203*.
1. Selecione **Salvar**.

#### <a name="create-a-standard-cost-for-item-m9200-in-site-6"></a>Criar um custo padrão para o item M9200 no site 6

1. Acesse **Gerenciamento de informações do produto** \> **Produtos** \> **Produtos liberados**.
1. Pesquise **M9200**.
1. Selecione a linha do item e, no Painel de Ação, na guia **Gerenciar custos**, no grupo **Configurar**, selecione **Preço do item**.
1. Na página **Preço do item**, selecione a guia **Preços pendentes**.
1. No Painel de Ações, selecione **Novo**.
1. Na nova linha, defina os valores a seguir:

    - **Tipo de custos:** *Custo padrão*
    - **Tipo de preço:** *Custo*
    - **Versão:** *10*
    - **Local:** *6*
    - **Preço:** *1,60*

1. No Painel de ações, selecione **Salvar**.
1. No Painel de Ação, selecione **Ativar preço(s) pendente(s)**.
1. Selecione a guia **Ativar preços** para verificar se o novo preço de custo para o site *6* foi adicionado.

#### <a name="create-inventory-in-warehouse-62"></a>Ciar estoque no depósito 62

1. Acesse **Gerenciamento de estoque** \> **Entradas de diário** \> **Itens** \> **Ajuste de estoque**.
1. No Painel de Ações, selecione **Novo**.
1. Na caixa de diálogo **Criar diário do estoque**, na FastTab **Visão geral**, no campo **Depósito**, insira *62*. Aceite os valores padrão em todos os demais campos.
1. Selecione **OK** para fechar a caixa de diálogo.
1. A página **Ajuste de estoque** é aberta. Na FastTab **Linhas do diário**, selecione **Novo** para adicionar uma linha.
1. Na nova linha, defina os valores a seguir. Aceite os valores padrão em todos os demais campos.

    - **Número de item:** *M9200*
    - **Local:** *massa-003*
    - **Quantidade:** mude o valor para *10*.

1. No Painel de ações, selecione **Salvar**.
1. No Painel de Ação, selecione **Validar** para verificar se há erros.
1. Na caixa de diálogo **Verificar diário**, selecione **OK** para iniciar a verificação. Você receberá uma mensagem quando a verificação for concluída.
1. No Painel de Ação, selecione **Lançar** para confirmar o ajuste de estoque.
1. Na caixa de diálogo **Lançar diário**, selecione **OK** para começar a lançar. Você receberá uma mensagem quando o lançamento for concluído.

## <a name="set-up-advanced-wave-load-building"></a>Configurar a criação avançada de carga de onda

### <a name="regenerate-wave-process-methods"></a>Regenerar métodos do processo de onda

Pode ser necessário regenerar seus métodos do processo de onda para tornar o método de criação de carga (**buildLoads**) disponível.

1. Acesse **Gerenciamento de depósito** \> **Configuração** \> **Ondas** \> **Métodos do processo de onda**.
2. Verifique se **buildLoads** está na lista. Se não estiver, selecione **Regenerar métodos** no Painel de Ação para adicioná-lo.

### <a name="set-up-wave-templates"></a>Configurar modelos de onda

Para aproveitar as vantagens da criação avançada de carga de onda, você deve incluir o método **buildLoads** em cada [modelo de onda](tasks/configure-wave-processing.md) relevante.

1. Acesse **Gerenciamento de depósito** \> **Configuração** \> **Ondas** \> **Modelos de onda**.
1. Selecione um modelo de onda.

    Se você estiver trabalhando com os dados de demonstração da **USMF**, selecione o modelo **Padrão de Remessa 62**.

1. No Painel de Ação, selecione **Editar** para colocar a página no modo de edição.
1. Na FastTab **Métodos**, na grade **Métodos restantes**, selecione o método **buildLoads**.
1. Selecione o botão de seta para a direita para mover o método **buildLoads** para a grade **Métodos selecionados**.
1. Para atribuir um valor **Código da etapa da onda** para o método **buildLoads**, primeiro você deve criar um código na página **Códigos de etapa de onda**. Você pode usar qualquer valor que desejar, mas não se esqueça de anotá-lo porque precisará dele mais tarde. Siga estas etapas para criar o código **WSC2112**:

    1. Na linha do método **buildLoads**, clique com o botão direito do mouse na seta para baixo do campo **Código da etapa da onda** e selecione **Exibir detalhes**.
    1. Na página **Códigos de etapa de onda**, no Painel de Ação, selecione **Novo**.
    1. No campo **Código da etapa da onda**, digite *WSC2112*.
    1. No campo **Descrição da etapa da onda**, digite *WSC2112*.
    1. No campo **Tipo de etapa de onda**, selecione *Criação de Carga*.

1. Selecione **Salvar** e feche a página.
1. Na linha do método **buildLoads**, no campo **Código da etapa da onda**, selecione o código que você acabou de criar (**WSC2112**).
1. No Painel de ações, selecione **Salvar**.

> [!NOTE]
> Os códigos da etapa da onda são códigos que os usuários podem configurar e usar para vincular instâncias específicas de métodos de onda a modelos correspondentes. Os modelos incluem modelos para reabastecimento, transporte em contêineres, impressão de etiquetas, criação de carga e classificação.
>
> Quando os códigos da etapa da onda não forem usados, os usuários deverão inserir texto livre para fazer referência a um modelo específico da instância de método da onda. O texto livre é propenso a erros, pois os usuários devem verificar se o texto da etapa da onda adicionado para um método específico da etapa da onda em um modelo da onda corresponde exatamente ao texto da etapa da onda no modelo de destino.
>
> Os códigos da etapa da onda para um tipo específico da etapa da onda são configurados em uma página separada. Para cada instância de um método da etapa da onda em um modelo da onda que requer um código da etapa da onda, o código da etapa da onda deve ser selecionado na lista suspensa. A seleção na lista suspensa substitui a entrada de texto livre e ajuda a reduzir o risco e o impacto de erros humanos. Códigos de configuração são usados para vincular um método da etapa da onda a um modelo de destino da onda para o método.

### <a name="set-up-load-mix-groups"></a>Configurar grupos mistos de carga

Os grupos mistos de carga estabelecem regras para os tipos de itens que podem ser combinados em uma única carga. É possível configurar quantos grupos mistos de carga forem necessários. No entanto, para usar a criação avançada de carga de onda, você deve ter pelo menos um. Siga estas etapas para criar um grupo misto de cargas.

1. Acesse **Gerenciamento de depósito** \> **Configuração** \> **Carga** \> **Grupos mistos de carga**.
1. No Painel de Ação, selecione **Novo** para criar um grupo de carga.
1. No campo **ID de grupos mistos de carga**, insira um nome para o novo grupo.

    Se você estiver trabalhando com os dados de demonstração da **USMF**, defina os seguintes valores:

    - **ID de grupos mistos de carga:** *TV*
    - **Descrição:** *TV*

1. No Painel de Ação, selecione **Salvar** para tornar a FastTab **Critérios de grupos mistos de carga** disponível.
1. Na FastTab **Critérios de grupos mistos de carga**, selecione **Novo** para adicionar uma linha à grade.
1. Na nova linha, defina os valores desejados em cada campo. Esses valores determinam os grupos de itens que são considerados para a combinação de cargas.

    Se você estiver trabalhando com os dados de demonstração da **USMF**, selecione *TV e Vídeo* no campo **Grupo de itens**.

1. No Painel de Ação, selecione **Salvar** para tornar a FastTab **Restrições de grupos mistos de carga** disponível.
1. Na FastTab **Restrições de grupos mistos de carga**, selecione **Novo** para adicionar uma linha à grade.
1. Na nova linha, defina os valores desejados em cada campo.

    Se você estiver trabalhando com os dados de demonstração da **USMF**, defina os seguintes valores:

    - **Grupo de itens:** *CarAudio*
    - **Ação de criação de carga:** *Restringir* (Este valor impedirá que itens pertencentes ao grupo de itens **CarAudio** estejam na mesma carga que os itens pertencentes ao grupo de itens **TV e Vídeo**.)

1. Continue a trabalhar com as regras até adicionar todos os critérios e restrições necessários para o grupo misto de cargas.

Se estiver trabalhando com os dados de demonstração da **USMF**, agora você concluiu essa configuração.

### <a name="set-up-load-build-templates"></a>Configurar modelos de criação de carga

É possível configurar quantos modelos de criação de carga forem necessários. No entanto, para usar a criação avançada de carga de onda, você deve ter pelo menos um. Siga estas etapas para criar um modelo de criação de carga.

1. Acesse **Gerenciamento de depósito** \> **Configuração** \> **Carga** \> **Modelos de criação de carga de onda**.
1. No Painel de Ação, selecione **Novo** para adicionar uma linha à grade.
1. Na nova linha, defina os valores a seguir.

    | Campo | descrição | Valor nos dados de demonstração da USMF |
    |---|---|---|
    | Número de sequência | A ordem em que o modelo será avaliado. | *1* |
    | Nome do modelo de criação de carga | Insira o identificador exclusivo do modelo de criação de carga. Você deve inserir o nome do modelo que criou ou atualizou anteriormente nesta configuração. | *Padrão de Remessa 62* |
    | Código da etapa da onda | Insira o código da etapa da onda a ser usado para vincular o modelo a um método de onda. Você deve inserir o código que selecionou para o método **buildLoads** ao configurar o modelo de onda anteriormente nessa configuração. | *WSC2112* |
    | ID do modelo de carga | Selecione o modelo de carga a ser usado quando novas cargas forem criadas e fazer a correspondência ao atribuir a cargas existentes. O modelo de carga define o peso e o volume máximos permitidos para a carga inteira. | *Modelo de Carga Padrão* |
    | Equipamento | Os equipamentos para fazer a correspondência ao atribuir a cargas existentes e para inserir em novas cargas que são criadas. | Deixe esse campo em branco. |
    | ID de grupos mistos de carga | Selecione o grupo misto de cargas a ser usado se o item for permitido na carga. O grupo misto estabelece regras para os tipos de itens que podem ser combinados em uma única carga. Você deve selecionar um dos grupos mistos que criou anteriormente nesta configuração. | *TV* |
    | Usar cargas abertas | Selecione se as cargas abertas existentes devem ser adicionadas. As opções a seguir estão disponíveis:<ul><li>**Nenhuma** – Não adicione cargas abertas a nenhuma carga existente.</li><li>**Qualquer uma** — Adiciona cargas abertas a quaisquer cargas existentes válidas para a linha.</li><li>**Atribuída** – Adicione cargas abertas à carga que está atribuída à onda.</li></ul> | *Qualquer* |
    | Criar cargas | Especifique se novas cargas devem ser criadas caso nenhuma carga existente corresponda aos critérios. | Selecionado (= *Sim*) |
    | Permitir divisão de linha de remessa | Especifique se uma única linha de carga pode ser dividida entre várias cargas caso a linha inteira exceda a capacidade máxima do modelo de carga. | Desmarcado (= *Não*) |
    | Validar volumetria | Especifique se a criação de carga deve verificar o peso e o volume conforme cada linha de carga for adicionada para garantir que os limites volumétricos do modelo de carga sejam respeitados. | Desmarcado (= *Não*) |

1. No Painel de Ação, selecione **Salvar** para tornar a opção **Editar consulta** disponível.
1. No Painel de Ação, selecione **Editar consulta** para abrir uma caixa de diálogo para editar a consulta.
1. Na caixa de diálogo, na guia **Classificação**, selecione **Adicionar** para adicionar uma linha à grade.
1. Na nova linha, defina as regras de classificação que você deseja usar. Por exemplo, defina os seguintes valores para classificar os resultados da pesquisa em ordem crescente por número de ordem:

    - **Tabela:** *Detalhes da carga*
    - **Tabela derivada:** *Detalhes da carga*
    - **Campo:** *Número da ordem*
    - **Direção da pesquisa:** *Crescente*

1. Selecione **OK** para salvar as alterações e fechar a caixa de diálogo.
1. Na FastTab **Dividir por**, defina regras para controlar como as cargas são divididas. Normalmente, você pode dividir em campos personalizados que foram estendidos para a linha de carga, como **Roteiro**, **Tour** ou **Execução**. Por exemplo, para criar uma carga por número de ordem, marque a caixa de seleção **Dividir por** para a linha que tem os seguintes valores:

    - **Nome da tabela de referência:** *Detalhes da carga*
    - **Nome do campo de referência:** *Número da ordem*

## <a name="scenario"></a>Cenário

Este cenário mostra como as configurações descritas anteriormente neste artigo afetam as operações de depósito durante o processamento de uma ordem de venda. Este cenário usa os dados de demonstração da **USMF** junto com outros valores de demonstração fornecidos nessas instruções de configuração.

### <a name="create-sales-orders"></a>Criar ordens de venda

1. Acesse **Vendas e marketing** \> **Ordens de venda** \> **Todas as ordens de venda**.
1. No Painel de Ação, selecione **Novo** para abrir a caixa de diálogo **Criar ordem de venda**.
1. Na caixa de diálogo , defina os seguintes valores:

    - Na FastTab **Cliente**, defina o campo **Conta do cliente** como *US-007*.
    - Na FastTab **Geral**, defina o campo **Depósito**, como *62*.

1. Selecione **OK** para criar a ordem de venda e fechar a caixa de diálogo.
1. A nova ordem de venda é aberta. Ele deve incluir uma nova linha vazia na grade da FastTab **Linhas de ordem de venda**. Nessa nova linha, defina o campo **Número do item** como *A0001* e o campo **Quantidade** como *1*.
1. No menu **Estoque** acima da grade, selecione **Reserva**.
1. Na página **Reserva**, no Painel de Ação, selecione **Reservar lote**.
1. Selecione o botão **Fechar** (**X**) no canto superior direito da página para retornar à ordem de venda.
1. No Painel de Ação, na guia **Depósito**, no grupo **Ações**, selecione **Liberar para o depósito**. O sistema cria uma remessa e a adiciona a uma nova carga, porque nenhuma carga existente contém linhas de carga com esse número de ordem.

    Você recebe mensagens informativas que indicam o trabalho, a onda e a remessa que foram criados para a ordem.

1. Para confirmar os detalhes da carga, da remessa e do trabalho na linha de venda, selecione a linha e, no menu **Depósito** acima da grade, selecione **Detalhes da carga**, **Detalhes da remessa** ou **Detalhes do trabalho**.
1. Na ordem de venda recém-criada, na FastTab **Linhas de ordem de venda**, selecione **Adicionar linha** para adicionar outra linha.
1. Na nova linha, defina o campo **Número do item** como *A0002* e o campo **Quantidade** como *1*.
1. Repita as linhas de 6 a 9 para reservar a linha e liberá-la para o depósito. O sistema cria uma **nova** remessa para a linha que você adicionou. No entanto, como você está usando a criação avançada de carga de onda, o sistema adiciona essa remessa e a linha de carga à onda existente. Se você não estivesse usando a criação avançada de carga de onda, o sistema criaria uma nova carga para a remessa.
1. Na ordem de venda recém-criada, na FastTab **Linhas de ordem de venda**, selecione **Adicionar linha** para adicionar outra linha.
1. Na nova linha, defina o campo **Número do item** como *M9200* e o campo **Quantidade** como *1*.
1. Repita as linhas de 6 a 9 para reservar a linha e liberá-la para o depósito. Como anteriormente, o sistema cria uma **nova** remessa para a linha que você adicionou. Porém, como o item é proveniente do grupo de itens **CarAudio**, ele **não passa as restrições configuradas para o grupo misto de cargas**. Por esse motivo, ele é **adicionado a uma nova carga**. Se você não tivesse especificado um grupo misto de cargas no modelo de criação de carga, essa remessa teria sido adicionada à primeira carga.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]