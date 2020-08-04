---
title: Status da localização do depósito
description: Este tópico fornece uma visão geral do recurso Status do local do depósito.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 128083b22bb14d9b445863a0ba1217f723727ee4
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597497"
---
# <a name="warehouse-location-status"></a>Status da localização do depósito

[!include [banner](../includes/banner.md)]

O Microsoft Dynamics 365 Supply Chain Management inclui vários campos de localização que trazem flexibilidade quando você trabalha com locais e os mantêm. Você pode incluir status de localização na consulta de diretiva de localização para oferecer melhor controle do fluxo de depósito.

Os quatro campos a seguir na página **Locais** rastreiam informações sobre o status atual de um local. Esses campos permitem que os gerentes de depósito tenham uma visão geral do status dos locais de depósito. Eles também permitem relatórios e filtragem avançados.

- **Número do item** — o item que está no local no momento. Se o local contiver vários itens, este campo ficará em branco.
- **Data e hora da última atividade** — o carimbo de data/hora da última transação de depósito executada no local.
- **Data de classificação por vencimento** — a data em que o estoque no local foi trazido para o depósito. Esse valor é calculado com base na data de vencimento da placa de licença. Ele é preciso em locais que são rastreados na placa de licença, mas pode não ser preciso em locais que não sejam rastreados na placa de licença.
- **Status do local** – o status do local. Há quatro valores possíveis:

    - **Indeterminado** – o perfil de local não pode rastrear o status. Portanto, o status atual é desconhecido.
    - **Vazio** – no momento, não há estoque no local.
    - **Separação** – as transações de saída foram executadas no local desde o último esvaziamento.
    - **Armazenamento** – apenas as transações de entrada foram executadas no local desde o último esvaziamento do local.

## <a name="turn-on-the-warehouse-location-status-feature"></a>Ativar o recurso Status da localização do depósito

Para que você possa usar o recurso *Status da localização do depósito*, ele deve estar ativado no sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo se necessário. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *Status da localização do depósito*

## <a name="set-up-warehouse-location-status"></a>Configurar o status da localização do depósito

### <a name="prepare-the-sample-data-that-is-required-for-the-example-scenario"></a>Preparar os dados de exemplo necessários para o cenário de exemplo

Antes de começar a trabalhar no cenário, você deve ativar os dados de exemplo e configurar o recurso conforme descrito nesta seção. Para concluir o cenário de exemplo, você deve usar o aplicativo de depósito ou o emulador baseado em navegador. As etapas fornecidas aqui usam o aplicativo de depósito. As etapas para o emulador baseado em navegador são semelhantes.

#### <a name="use-the-usmf-legal-entity"></a>Usar a entidade legal USMF

Para trabalhar com o cenário de exemplo usando os registros e valores de exemplo especificados aqui, você deve usar um sistema em que os [dados de demonstração](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) padrão estejam instalados. Além disso, você deve selecionar a entidade legal **USMF** antes de começar.

#### <a name="set-up-location-profiles"></a>Configurar perfis de localização

O cenário de exemplo requer que você prepare dois perfis de local.

1. Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Perfis de localização**.
1. Selecione **Editar** para colocar a página no modo de edição.
1. Selecione o perfil **MASSA-06**.
1. Na FastTab **Geral**, defina os seguintes valores:

    - **Habilitar o item no local:** defina esta opção como _Sim_.
    - **Habilitar data e hora da atividade de localização:** defina esta opção como _Sim_.
    - **Habilitar o status do local:** defina esta opção como _Sim_.

    Essas opções controlam se os campos de referência no local estão ativos.

1. Repita as etapas 3 a 4 para o perfil **SEPARAÇÃO-06**.

### <a name="scenario"></a>Cenário

1. Acesse **Compras \> Ordens de compra \> Todas ordens de compra**.
1. Selecione **Novo**.
1. Na caixa de diálogo **Criar ordem de compra**, na FastTab **Fornecedor** , no campo **Conta de fornecedor**, selecione *104*.
1. Na Guia Rápida **Geral**, no campo **Depósito**, selecione *61*.
1. Selecione **OK**.
1. A nova ordem de compra (OC) é aberta. Ela inclui uma linha vazia na grade **Linhas da ordem de compra**. Nessa linha, defina os seguintes valores:

    - **Número de item:** _A0002_
    - **Quantidade:** _5_

1. No Painel de Ações, na guia **Compra**, no grupo **Ações**, selecione **Confirmar** para confirmar a ordem de compra.
1. No dispositivo móvel, vá para **Entrada \> Recebimento de compra**.
1. Selecione o campo **PONUM**, insira o número da OC e confirme.
1. Selecione o campo **ITEM**, insira *A0002* como o número de item e confirme.
1. Na página **QTD**, digite *5* como a quantidade e confirme.

    Há duas maneiras de inserir a quantidade:

    - Selecione o botão de sinal de adição (**+**) ou de subtração (**–**) para adicionar ou subtrair um valor numérico.
    - Selecione o campo em branco entre os botões de sinal de adição (**+**) e sinal de subtração (**–**) para abrir o teclado numérico.

1. Confirme a seleção do número de item *A0002* e uma quantidade de *5*. Uma mensagem "trabalho concluído" aparece na parte inferior da página.
1. Selecione o botão de menu (às vezes referido como hamburger ou o botão de hamburger) no canto superior direito e selecione **Cancelar** para sair de **Recebimento de compra** e retornar ao menu **Entrada**.
1. Na página de ordem de compra, selecione **Detalhes do trabalho** acima da grade **Linhas da ordem de compra**.
1. Na guia **Geral**, observe a **ID de trabalho** e os valores de ID da **ID da placa de licença de destino** que foram criados.
1. Na seção **Linhas**, observe os valores de **Localização** para os tipos de trabalho *Separar* e *Colocar*.
1. No dispositivo móvel, vá para **Entrada \> Armazenamento de compra**.
1. Selecione o campo **ID**, insira a ID de trabalho e confirme.
1. Confirme mais uma vez para concluir a entrada *Separação*.
1. Selecione o botão de menu no canto superior direito e, depois, selecione **Concluído** para concluir o trabalho de *Separação*.
1. Anote a localização de Armazenamento e confirme. Uma mensagem "trabalho concluído" aparece na parte inferior da página.
1. Selecione o botão de menu no canto superior direito e selecione **Cancelar** para sair de **Armazenamento de compra** e retornar ao menu **Entrada**.
1. Selecione **Voltar** para retornar ao menu principal.
1. No Dynamics 365 Supply Chain Management, vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Localizações**.
1. Filtre em **Local** e insira o local de armazenamento do trabalho da ordem de compra. Você verá os seguintes resultados:

    - A coluna **Status do local** mostra um valor de *Armazenamento* porque a última transação neste local foi colocada.
    - O **Número do item** mostra um valor de *A0002* porque esse item foi recebido e colocado no local.
    - A coluna **Data e hora da última atividade** mostra o carimbo de data/hora em que o trabalho foi concluído no local.

1. No dispositivo móvel, vá para **Qualidade \> Movimento**.
1. Selecione o campo **LOC/LP** e insira o local em que você fez a anotação nas etapas anteriores.
1. Confirme as informações mostradas. Anote o número da placa de licença que é gerado.
1. Na tela **Para informações**, selecione o campo **LOC/LP** e insira *06A07R2S1B* como o local para onde o item será movido.
1. Na tela **Para informações**, confirme o valor **LP** (a ID da placa de licença de destino), que é automaticamente gerado. Uma mensagem "trabalho concluído" aparece na parte inferior da página.
1. Selecione o botão de menu no canto superior direito e selecione **Cancelar** para sair de **Movimento** e retornar ao menu **Gerenciamento de Qualidade**.
1. Selecione **Voltar** para retornar ao menu principal.
1. No Dynamics 365 Supply Chain Management, vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Localizações**.
1. Atualize a página **Locais** e reexiba o local de armazenamento original. Observe que agora o campo **Status do local** está definido como *Vazio* e a coluna **Número do item** está em branco.
1. Exiba o registro do local *06A07R2S1B* e note que o valor de **Status** foi alterado para *Armazenamento* e os campos **Número do item** e **Data e hora da última atividade** foram atualizados.
1. Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. Selecione **Novo**.
1. Na caixa de diálogo **Criar ordem de venda**, no campo **Conta do cliente**, selecione *US-002*.
1. No campo **Depósito**, selecione *61*.
1. Selecione **OK**.
1. A nova ordem de venda é aberta. Ela inclui uma linha vazia na grade **Linhas da ordem de venda**. Nessa linha, defina os seguintes valores:

    - **Número de item:** _A0002_
    - **Quantidade:** _1_

1. Na FastTab **Linhas da ordem de venda**, no menu **Estoque**, selecione **Reserva**.
1. Na página **Reserva**, selecione **Reservar lote** para reservar a linha da ordem. Selecione o botão **Fechar** (**X**) no canto superior direito para fechar a página.
1. No Painel de Ação, na guia **Depósito**, no grupo **Ações**, selecione **Liberar para o depósito**.
1. Na seção **Linhas de ordem de venda**, no menu **Depósito**, selecione **Detalhes do trabalho**.
1. Copie o valor **ID de trabalho** que foi criado.
1. No dispositivo móvel, vá para **Saída \> Separação de venda**.
1. Selecione o campo **ID**, insira a ID de trabalho que você copiou antes e confirme.
1. Na página **Ordens de venda: separar**, o campo **LOC** sugere o local de separação como o local de armazenamento criado anteriormente. Anote o local.
1. Selecione o campo **LOC**, insira o local e confirme.
1. Selecione o campo **LP**, insira o número da placa de licença que anotou durante a atividade de movimento e confirme.
1. Selecione o campo **Item**, insira *A0002* como o número de item e confirme.
1. Na página **QTD**, digite *1* como a quantidade e confirme.

    Há duas maneiras de inserir a quantidade:

    - Selecione o botão de sinal de adição (**+**) ou de subtração (**–**) para adicionar ou subtrair um valor numérico.
    - Selecione o campo em branco entre os botões de sinal de adição (**+**) e sinal de subtração (**–**) para abrir o teclado numérico.

1. Selecione o campo **LP DE DESTINO**, insira uma ID da placa de licença de destino definida pelo usuário e confirme.
1. Confirme mais uma vez para concluir o trabalho de separação. Uma mensagem "trabalho concluído" aparece na parte inferior da página.
1. Selecione o botão de menu no canto superior direito e selecione **Cancelar** para concluir a atividade de separação e retornar ao menu **Saída**.
1. No Dynamics 365 Supply Chain Management, vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Localizações**.
1. Filtre em **Local** e insira o local de separação do trabalho da ordem de venda.
1. Observe que o campo **Status do local** para o local de onde o trabalho de ordem de venda foi coletado está definido como *Separação* e o campo **Data e hora da última atividade** foi atualizado.

> [!NOTE]
> Os campos de localização são atualizados somente por transações de depósito. Se você mover o estoque usando um diário ou outros processos não-WHS, os campos não serão atualizados.
