---
title: Ancoragem
description: Este tópico explica como habilitar e usar a ancoragem.
author: GalynaFedorova
ms.date: 07/29/2021
ms.topic: article
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2021-07-29
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 26a7bf60912ff1e8a23305e9331d520fe8d65727
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8676485"
---
# <a name="anchoring"></a>Ancoragem

[!include [banner](../includes/banner.md)]

Este tópico fornece detalhes sobre o processo de ancoragem. Ele descreve a configuração necessária e a lógica executada quando um trabalhador de depósito altera o local de preparo ou o local de carregamento.

O recurso de ancoragem permite substituir o local de preparo ou de carregamento. Todas as colocações abertas serão direcionadas para o novo local de preparo ou de carregamento que você especificar.

Esse recurso pode ajudar os trabalhadores a serem mais eficientes enquanto enviam mercadorias. Veja alguns exemplos:

- Um trabalhador que deve colocar itens para a ordem 1 em um local de preparo na doca 1 não pode concluir esta operação porque um carregamento anterior não liberou o local. Em vez de aguardar que o local de preparo da doca 1 fique disponível, o trabalhador decide usar o local de preparo da doca 2. Nesse caso, o trabalhador substitui o local de preparo sugerido. O local de armazenamento de todos os itens restantes do trabalho é, em seguida, atualizado para o local de preparo da doca 2.
- Um trabalhador que deve realizar várias seleções para a mesma entrega pode ter certeza de que todos os itens colocados foram montados no mesmo lugar. Portanto, é necessário menos tempo para carregar os itens no caminhão.

Você configura a ancoragem para itens de menu de dispositivo móvel usando a opção **Ancorar**. Se você definir esta opção como *Sim*, você pode usar o campo **Ancorar por** para especificar se deseja ancorar por remessa ou carga. Se você definir o campo **Ancorar por** para *Remessa*, as aberturas subsequentes serão alteradas para o novo local dessa remessa. Se você defini-lo como *Carga*, as aberturas subsequentes serão alteradas para o novo local dessa carga.

> [!IMPORTANT]
> O local para aberturas subsequentes serão alteradas somente nas linhas de trabalho geradas a partir da mesma linha de modelo de trabalho. Em outras palavras, o sistema irá ancorar as linhas de colocação originadas na mesma linha de modelo de trabalho.

Este tópico fornece um cenário que mostra como a ancoragem funciona. Durante o cenário, você criará um conjunto de ordens de venda e as liberará para o depósito. Em seguida, você substituirá o local de preparo sugerido e verificará se todo o trabalho de armazenamento restante foi direcionado para o novo local.

## <a name="scenario-prerequisite-make-demo-data-available"></a>Pré-requisitos do cenário: disponibilizar dados de demonstração

O cenário neste tópico faz referência a valores e registros incluídos nos dados de demonstração padrão que são fornecidos para o Microsoft Dynamics 365 Supply Chain Management. Se você deseja usar os valores fornecidos aqui ao fazer os exercícios, procure trabalhar em um ambiente no qual os dados de demonstração estejam instalados e defina a entidade legal como *USMF* antes de começar.

## <a name="scenario-setup"></a>Configuração de cenário

Antes de trabalhar no cenário de exemplo, você deve habilitar a ancoragem para o item de menu do dispositivo móvel relevante.

### <a name="set-up-a-mobile-device-menu-item-to-enable-anchoring"></a>Configurar um item de menu do dispositivo móvel para habilitar a ancoragem

Siga estas etapas para habilitar a ancoragem para um item de menu de dispositivo móvel.

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
1. No painel da lista, selecione o registro chamado *Separação de vendas*. Se nenhum registro existente tiver esse nome, crie-o. Confirme ou defina os seguintes valores para o registro:

    - **Nome do item de menu:** *separação de vendas*
    - **Título:** *separação de vendas*
    - **Modo:** *Trabalho*
    - **Usar trabalho existente:** *Sim*
    - **Direcionado por:** *direcionado pelo usuário*
    - **Ancoragem:** *Sim*

        Esta configuração faz com que o sistema ancore várias linhas de ordem de trabalho juntas durante a separação de vendas.

    - **Âncora por:** *Carga*

        Esta configuração faz com que o sistema ancore por carga.

    - **Substituir placa de licença de destino:** *Sim*
    - **Substituir placa de licença durante put:** *Sim*
    - **Manter trabalho bloqueado pelo usuário:** *Sim*
    - **Permitir separação em excesso:** *Sim*

### <a name="set-up-a-work-template-to-enable-staging"></a>Configurar um modelo de trabalho para habilitar o preparo

Siga estas etapas para configurar um modelo de trabalho para habilitar o preparo. Essa configuração oferece suporte ao cenário no qual um trabalhador insere itens para uma ordem em um local de preparo.

1. Acesse **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelo de trabalho**.
1. No campo **Tipo de ordem de trabalho**, selecione *Ordens de compra*.
1. Na grade, selecione o modelo de trabalho **61 Preparação de OV**.
1. Na seção **Detalhes do Modelo de Trabalho**, verifique se as seguintes linhas existem e se estão configuradas como mostrado aqui:

    - Linha 1:

        - **Tipo de trabalho:** *Separar*
        - **Obrigatório:** selecionado (= *Sim*)
        - **ID da classe de trabalho:** *Separação de OV*

    - Linha 2:

        - **Tipo de trabalho:** *Colocar*
        - **Obrigatório:** selecionado (= *Sim*)
        - **Código de diretiva:** *Estágio*
        - **ID da classe de trabalho:** *Separação de OV*

    - Linha 3:

        - **Tipo de trabalho:** *Separar*
        - **Obrigatório:** selecionado (= *Sim*)
        - **Parar trabalho:** *Sim*
        - **ID da classe de trabalho:** *Carga de OV*

    - Linha 4:

        - **Tipo de trabalho:** *Colocar*
        - **Obrigatório:** selecionado (= *Sim*)
        - **Código de diretiva:** *Porta da baía*
        - **ID da classe de trabalho:** *Carga de OV*

1. No Painel de Ações, selecione **Editar consulta** para abrir o editor de consultas.
1. Na guia **Intervalo**, verifique se a seguinte linha está presente:

    - **Tabela:** *Transações de trabalho temporário*
    - **Tabela Derivada:** *Transações de trabalho temporário*
    - **Campo:** *Depósito*
    - **Critérios:** *61*

1. Na guia **Classificação**, verifique se a seguinte linha está presente:

    - **Tabela:** *Transações de trabalho temporário*
    - **Tabela Derivada:** *Transações de trabalho temporário*
    - **Campo:** *ID da Remessa*
    - **Direção da pesquisa:** *Crescente*

1. Selecione **OK** para aplicar as configurações e fechar o editor de consultas. Aceite as alterações, se for solicitado.
1. No Painel de Ação, selecione **Quebras de cabeçalho de trabalho**.
1. Na linha em que o campo **Nome do campo** está definido como *ID da Remessa*, certifique-se de que a caixa de seleção **Agrupar por este campo** está selecionada.

### <a name="set-up-license-plates-locations-and-inventory"></a>Configurar placas de licença, locais e estoque

Antes de criar ordens de venda e remessas, você deve garantir que os locais necessários, as chapas de licença e o estoque existem.

1. Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Placas de licença** e crie duas placas de licença:

    - MyLP1
    - MyLP2

1. Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Locais** e crie os seguintes locais, se ele não estiverem presentes.

    | Depósito | Localização   | ID do perfil de localização | ID da zona   |
    |-----------|------------|---------------------|-----------|
    | 61        | 06A01R2S1B | PICK-06             | FLOOR     |
    | 61        | 06A01R3S1B | PICK-06             | FLOOR     |
    | 61        | STAGE01    | STAGE               | *(Em branco)* |
    | 61        | STAGE02    | STAGE               | *(Em branco)* |
    | 61        | STAGE03    | STAGE               | *(Em branco)* |
    | 61        | STAGE04    | STAGE               | *(Em branco)* |

1. Verifique se o seguinte estoque está disponível. Se precisar ajustar o estoque, você poderá criar movimentações manuais, usar o reabastecimento ou utilizar qualquer outro fluxo.

    | Nº de itens | Quantidade | Depósito | Localização   | Placa de licença |
    |-------------|----------|-----------|------------|---------------|
    | A0001       | 100      | 61        | 06A01R2S1B | MyLP1         |
    | A0002       | 100      | 61        | 06A01R3S1B | MyLP2         |

### <a name="create-demand"></a>Criar demanda

Antes de tentar a funcionalidade de ancoragem, você deve criar alguma demanda. Neste cenário, você criará três ordens de venda para o mesmo cliente.

1. Acesse **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. Selecione **Novo** para criar a primeira ordem de venda.
1. Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:

    - **Conta de cliente:** *US-001*
    - **Depósito:** *61*

1. Selecione **OK**.
1. A nova ordem de venda é aberta. Ela inclui uma linha em branco na Guia Rápida **Linhas da ordem de venda**. Defina os seguintes valores para essa linha:

    - **Número de item:** *A0001*
    - **Quantidade:** *1*

1. Na barra de ferramentas, selecione **Adicionar linha** para adicionar uma segunda linha da ordem de compra e defina os seguintes valores a ela:

    - **Número de item:** *A0002*
    - **Quantidade:** *1*

1. Siga estas etapas para cada linha de venda na ordem a fim de reservar estoque para ela:

    1. Na Guia Rápida **Linhas de ordem de venda**, selecione uma linha da ordem de venda.
    1. Na barra de ferramentas, selecione **Estoque \> Reserva**.
    1. Na página **Reserva**, selecione **Reservar lote** e feche a página.
    1. No Painel de ações, selecione **Salvar**.

1. Repita as etapas 2 a 6 para criar uma segunda ordem de venda. Defina os seguintes valores para ele:

    - Na caixa de diálogo **Criar ordem de venda**:

        - **Conta de cliente:** *US-001*
        - **Depósito:** *61*

    - Na linha 1 da ordem de venda:

        - **Número de item:** *A0001*
        - **Quantidade:** *2*

    - Na linha 2 da ordem de venda:

        - **Número de item:** *A0002*
        - **Quantidade:** *2*

1. Repita a etapa 7 para reservar cada linha na ordem de venda 2.
1. Repita as etapas 2 a 6 para criar uma terceira ordem de venda. Defina os seguintes valores para ele:

    - Na caixa de diálogo **Criar ordem de venda**:

        - **Conta de cliente:** *US-001*
        - **Depósito:** *61*

    - Na linha 1 da ordem de venda:

        - **Número de item:** *A0001*
        - **Quantidade:** *3*

    - Na linha 2 da ordem de venda:

        - **Número de item:** *A0002*
        - **Quantidade:** *3*

1. Repita a etapa 7 para reservar cada linha na ordem de venda 3.

### <a name="use-the-load-planning-workbench-to-create-a-load-and-release-it-to-the-warehouse"></a>Use a bancada de planejamento de carga para criar uma carga e liberá-la para o depósito

Siga estas etapas para criar uma carga para cada as ordens que você criou para esse cenário e, em seguida, liberá-la para o depósito.

1. Acesse **Gerenciamento de depósito \> Cargas \> Bancada de planejamento de carga**.
1. Na guia **Linhas de venda**, localize e selecione todas as linhas da ordem de venda para a ordem de venda 1 e a ordem de venda 2.
1. No Painel de Ação, na guia **Oferta e demanda** , no grupo **Adicionar** , selecione **Para nova carga**.
1. Na caixa de diálogo **Atribuição de modelo de carga**, no campo **ID do modelo de carga**, selecione um modelo de carga, como *Modelo de Carga Padrão*.
1. Selecione **OK** para fechar a caixa de diálogo.
1. Na seção **Cargas**, localize e selecione a carga que você criou.
1. Na barra de ferramentas, selecione **Liberar \> Liberar para o depósito**.
1. Na caixa de diálogo **Liberar carga para depósito**, selecione **OK** para liberar a carga selecionada para o depósito.
1. Acesse **Gerenciamento de depósito \> Trabalho \> Todos os trabalhos** para exibir o trabalho criado. Você deve encontrar duas novas IDs de trabalho, uma para cada remessa. Cada ID de trabalho tem linhas de separação e armazenamento que trazem o estoque dos locais de retirada para o local de preparo e do local de preparo para a porta da baía. Anote o valor da **ID do Trabalho** para a primeira remessa porque você precisará usá-lo no próximo procedimento.

### <a name="sales-order-picking-to-the-staging-location-for-the-first-shipment"></a>Separação da ordem de venda para o local de preparo da primeira remessa

1. Entre no aplicativo móvel do Warehouse Management como um trabalhador no depósito *61*. (Nos dados de demonstração padrão, você pode entrar usando _61_ como o ID do usuário e _1_ como senha.)
1. No menu principal, selecione **Saída**.
1. No menu **Saída**, selecione **Separação de Venda**.
1. Selecione o campo **ID** e insira a ID de trabalho para a primeira remessa.
1. Confirme a entrada.
1. No campo **LP**, insira um número de placa de licença para o primeiro item (*MyLP1*).
1. Confirme a entrada.
1. No campo **LP de Destino**, insira qualquer número (a placa de licença de destino ainda não deve existir).

    Você separará todas as linhas criadas da onda processada para a mesma placa de licença de destino.

1. Confirme a entrada.
1. No campo **LP**, insira um número de placa de licença para o segundo item (*MyLP2*).
1. Confirme a entrada.

    Imagine que o trabalhador coletou a ordem, mas quando chegarem ao local de preparo especificado no trabalho, descobrirão que o espaço já está ocupado. No entanto, o trabalhador pode ver que outro local próximo (*STAGE03*) está disponível. Portanto, eles solicitarão alterar o local de preparo. Como o recurso de ancoragem está habilitado, o sistema atualizará automaticamente o local de preparo deste e de todo o trabalho relacionado.

1. Selecione **Substituir local** para substituir o local de preparo sugerido.
1. No campo **Exceções de trabalho**, especifique *Raia de preparo alterada*.
1. No campo **Local**, insira um novo local de preparo (*STAGE03*).
1. Confirme a entrada. Você receberá uma mensagem "Trabalho concluído".
1. Acesse **Gerenciamento de depósito \> Trabalho \> Todos os trabalhos**.
1. Abra a ID de trabalho para a primeira remessa. Verifique se o local de preparo foi atualizado para o novo local (*STAGE03*) definido com o dispositivo móvel.
1. Abra a ID de trabalho para a segunda remessa. Verifique se o local de preparo foi atualizado para o novo local de preparo (*STAGE03*) por causa da configuração de ancoragem.

> [!NOTE]
> O local de todas as linhas de trabalho abertas restantes que têm o mesmo local de preparo e que foram geradas a partir da mesma linha de modelo de trabalho serão atualizadas para o novo local.

### <a name="use-the-load-planning-workbench-to-add-the-new-sales-order-to-the-existing-load"></a>Use a bancada de planejamento de carga para adicionar a nova ordem de venda à carga existente

Siga estas etapas para adicionar uma ordem à carga e depois liberá-la para o depósito.

1. Acesse **Gerenciamento de depósito \> Cargas \> Bancada de planejamento de carga**.
1. Na guia **Linhas de venda**, localize e selecione todas as linhas da ordem de venda da ordem de venda 3.
1. No Painel de Ações, na guia **Oferta e demanda**, no grupo **Adicionar**, selecione **Para carga existente** para adicionar as linhas de ordem selecionadas para uma carga existente.
1. Selecione **OK** para fechar a caixa de diálogo.
1. Na seção **Cargas**, localize e selecione a carga das etapas anteriores.
1. Selecione **Liberação \> Liberação para depósito**.
1. Na caixa de diálogo **Liberar carga para depósito**, selecione **OK** para liberar a carga selecionada para o depósito.
1. Acesse **Gerenciamento de depósito \> Trabalho \> Todos os trabalhos** para exibir o trabalho criado. Anote o valor da **ID do Trabalho**, pois precisará usá-lo no próximo procedimento.

### <a name="sales-order-picking-to-the-staging-location-for-the-third-shipment"></a>Separação da ordem de venda para o local de preparo da terceira remessa

1. Entre no aplicativo móvel como um trabalhador do depósito *61*.
1. No menu principal, selecione **Saída**.
1. No menu **Saída**, selecione **Separação de Venda**.
1. Selecione o campo **ID** e insira a ID de trabalho para a terceira remessa.
1. Confirme a entrada.
1. No campo **LP**, insira um número de placa de licença para o primeiro item (*MyLP1*).
1. Confirme a entrada.
1. No campo **LP de Destino**, insira qualquer número (a placa de licença de destino ainda não deve existir).
1. Confirme a entrada.
1. No campo **LP**, insira um número de placa de licença para o segundo item (*MyLP2*).
1. Confirme a entrada.

    Como para a primeira carga, imagine que o trabalhador descobre que o local de preparo especificado não está disponível. Portanto, eles desejam usar um local de preparo diferente (*STAGE04*).

1. Selecione **Substituir local** para substituir o local de preparo sugerido.
1. No campo **Exceções de trabalho**, especifique *Raia de preparo alterada*.
1. No campo **Local**, insira um novo local de preparo (*STAGE04*).
1. Confirme a entrada. Você receberá uma mensagem "Trabalho concluído".
1. Acesse **Gerenciamento de depósito \> Trabalho \> Todos os trabalhos**.
1. Abra a ID de trabalho para a primeira remessa. Verifique se o local de preparo não foi atualizado para o novo local de preparo (*STAGE04*), pois a linha de trabalho aberta restante não corresponde à linha de modelo de serviço da linha de armazenamento concluída.
1. Abra a ID de trabalho para a segunda remessa. Verifique se o local de preparo não foi atualizado para o novo local de preparo (*STAGE04*), pois o local de armazenamento não corresponde à linha de preparo da linha de armazenamento concluída. Em outras palavras, a linha de trabalho de armazenamento preenchida e a linha de trabalho aberta restante têm diferentes locais de armazenamento e, nesse caso, somente as linhas que têm os mesmos locais de preparo são atualizadas.
1. Abra a ID de trabalho para a terceira remessa. Verifique se o local de preparo foi atualizado para o novo local de preparo (*STAGE04*).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
