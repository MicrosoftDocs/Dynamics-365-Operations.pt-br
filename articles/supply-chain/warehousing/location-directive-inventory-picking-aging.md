---
title: Classificação por vencimento de separação de estoque de diretiva de localização
description: Este artigo explica como usar as estratégias de diretiva de localização primeiro a entrar, primeiro a sair (FIFO) e último a entrar, primeiro a sair (LIFO) durante a separação.
author: Mirzaab
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationProfile,WHSWorkTable,WHSWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 34ce119ca70596f0e40797c4b44a8fba4d5b7e0e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885686"
---
# <a name="location-directive-inventory-picking-aging"></a>Classificação por vencimento de separação de estoque de diretiva de localização

[!include [banner](../includes/banner.md)]

Este artigo explica como usar as estratégias de diretiva de localização primeiro a entrar, primeiro a sair (FIFO) e último a entrar, primeiro a sair (LIFO) durante a separação. Essas estratégias trabalham em conjunto com as datas de classificação por vencimento registradas para os locais a serem rastreados quando o estoque entra pela primeira vez no depósito. O recurso *Classificação por vencimento de separação de estoque de diretiva de localização* usa a data na localização para determinar a classificação por vencimento. O recurso *Status da localização do depósito* atualiza a data na localização com base na data da placa de licença.

Você pode usar as estratégias FIFO e LIFO para enviar itens rastreados por lote e itens não rastreados por lote, com base na data em que o estoque deu entrada no depósito. Esse recurso pode ser especialmente útil para estoque não rastreado por lote, no qual uma data de vencimento não está disponível para ser usada para classificação.

Quando o estoque é recebido ou criado no depósito pela primeira vez, o sistema atualiza a placa de licença relevante para que a data atual seja mostrada como a data de classificação por vencimento. Essa data é usada pelas estratégias de diretiva de localização para identificar o estoque mais antigo ou mais novo no depósito. Se o estoque for movido para um local que não é rastreado por placa de licença, o local em si será atualizado com as informações de classificação por vencimento, e essas informações serão usadas pelas estratégias.

## <a name="turn-on-the-feature"></a>Ativar o recurso

Para disponibilizar este recurso, ative os seguintes recursos no [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), nesta ordem:

1. Status da localização do depósito
1. Classificação por vencimento de separação de estoque de diretiva de localização

## <a name="feature-requirements"></a>Requisitos do recurso

Para usar este recurso, você deve definir a opção **Habilitar o status do local** como *Sim* para cada [perfil de localização](tasks/create-location-profile.md) usado para o estoque de loja. Para definir esta opção para um perfil de localização, Acesse **Gerenciamento de depósito \> Configuração \> Depósito \> Perfis de localização** e selecione o perfil de localização. Você pode encontrar a opção na FastTab **Geral**.

## <a name="feature-scenarios"></a>Cenários de recursos

Esta seção contém exemplos que mostram como configurar e usar as estratégias FIFO e LIFO.

> [!TIP]
> Esta seção apresenta dois cenários, um para FIFO e outro para LIFO. Os procedimentos apresentados presumem que você fará os dois cenários, na ordem. Recomendamos que você faça os dois cenários para perceber as diferenças entre as duas estratégias.

### <a name="make-sample-data-available"></a>Disponibilizar dados de exemplo

Para analisar esses cenários usando os registros e valores de exemplo especificados aqui, você deve usar um sistema em que os [dados de demonstração](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) padrão estejam instalados. Além disso, você deve selecionar a entidade legal **USMF** antes de começar.

Você também pode usar esses cenários como orientação para usar o recurso em um sistema de produção. No entanto, nesse caso, você deve substituir seus valores por cada configuração descrita aqui.

### <a name="set-up-the-scenarios"></a><a name="demo-set-up"></a>Configurar os cenários

Os dados de demonstração exigem ajustes na configuração e no estoque para dar suporte aos cenários. Siga estas etapas para criar os dados de estoque necessários para trabalhar nos cenários de FIFO e LIFO.

1. Entre em um sistema no qual os dados de demonstração estejam instalados e selecione a entidade legal **USMF**.
1. Acesse **Gerenciamento de depósito \> Configuração \> Depósito \> Perfis de localização**.
1. No Painel de Ações, selecione **Editar**.
1. Na lista de perfis de localização, selecione **FLOOR-05**.
1. Na FastTab **Geral**, defina a opção **Habilitar o status do local** como *Sim*.
1. Selecione **Salvar**.
1. Acesse **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.
1. Na lista de diretivas de localização, selecione **Transporte em contêineres de separação 63**.
1. Selecione **Editar** para colocar a página no modo de edição.
1. Na FastTab **Ações de diretiva de localização**, encontre a linha onde o campo **Número de sequência** está definido como *1* e siga uma destas etapas:

    - Se estiver configurando um cenário de FIFO, altere o valor do campo **Estratégia** para *Classificação por vencimento local FIFO*.
    - Se estiver configurando um cenário de LIFO, altere o valor do campo **Estratégia** para *Classificação por vencimento local LIFO*.

1. Na FastTab **Ações de diretiva de localização**, selecione **Editar consulta**.
1. Na caixa de diálogo de consulta, na guia **Intervalo**, selecione **Adicionar** para adicionar uma linha e defina os seguintes valores:

    - **Tabela:** *Localizações*
    - **Tabela derivada:** *Locais*
    - **Campo:** *ID da zona*
    - **Critérios:** *Chão*

1. Selecione **OK** para aplicar suas configurações e fechar a caixa de diálogo de consulta.
1. Selecione **Salvar** para salvar as alterações na diretiva de localização.
1. Em um dispositivo móvel ou no aplicativo *Dynamics 365 for Finance and Operations - Warehousing* no PC, siga estas etapas para remover o estoque existente da localização de depósito para dar suporte aos cenários:

    1. Entre no depósito *63* usando a ID de usuário e a senha apropriadas.
    1. No menu principal, selecione **Qualidade**.
    1. No menu **Gerenciamento de qualidade**, selecione **Sucata**.
    1. Na página **Sucata**, selecione o campo **LOC/LP** e insira *63\_1*.
    1. Selecione **Enter** ou **OK**.
    1. Confirme os detalhes de **Sucata** para **Ajuste de saída** selecionando **Enter** ou **OK**.

    Quando o estoque de placa de licença passar pelo ajuste de saída, você receberá uma mensagem "Trabalho Concluído".

    Essas etapas deixam estoque em dois locais nos dados de demonstração. Cada local tem uma data de classificação por vencimento diferente. O local *FL-001* tem uma data de classificação por vencimento de 15 de abril de 2017, e o local *FL-002* de 29 de janeiro de 2017. Os dois locais contêm o item *A0001*.

    Para ver esses dados, Acesse **Gerenciamento de estoque \> Consultas e relatórios \> Lista disponível** e filtre pelo depósito *63* e o item *A0001*. Nas linhas em que o campo **Local** está definido como *FL-001* ou *FL-002*, selecione uma linha com valor **Estoque físico** positivo e, no Painel de Ação, selecione **Transações**. O campo **Data física** mostrará uma data que corresponde a uma das datas de classificação por vencimento mencionadas anteriormente.

### <a name="scenario-1-set-up-and-use-fifo-location-aging"></a><a name="fifo-demo"></a>Cenário 1: configurar e usar a classificação por vencimento local FIFO

A estratégia FIFO encontra o local que contém a data de classificação por vencimento mais antiga e aloca a separação com base nessa data.

1. Se você ainda não fez isso, [prepare os dados de exemplo](#demo-set-up) necessários para este cenário.
1. Acesse **Vendas e marketing \> Ordem de venda \> Todas as ordens de venda**.
1. Selecione **Novo**.
1. Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:

    - Na FastTab **Cliente**, defina o campo **Conta do cliente** como *US-001*.
    - Na FastTab **Geral**, defina o campo **Depósito**, como *63*.

1. Selecione **OK** para criar a ordem de venda e fechar a caixa de diálogo.
1. A nova ordem de venda é aberta. Ele inclui uma nova linha vazia na grade da FastTab **Linhas de ordem de venda**. Para essa linha de ordem, defina o campo **Número do item** como *A0001* e o campo **Quantidade** como *1*.
1. No menu **Estoque** acima da grade, selecione **Reserva**.
1. Na página **Reserva**, selecione **Reservar lote** para reservar a quantidade encomendada desse item do estoque no depósito escolhido.
1. Feche a página **Reserva**.
1. Na página **Ordem de venda**, no Painel de Ação, na guia **Depósito**, no grupo **Ações**, selecione **Liberar para o depósito**. Você receberá mensagens informativas. O sistema criará uma remessa, a adicionará a uma nova carga e criará o trabalho necessário.
1. Na FastTab **Linhas da ordem de venda**, no menu **Depósito**, selecione **Detalhes do trabalho** para abrir o trabalho criado para essa ordem de venda. Observe que a linha na qual o valor **Tipo de trabalho** é *Separar* mostra um valor **Local** de *FL-002*. Esse local contém a placa de licença que tem a data de classificação por vencimento mais antiga (FIFO).
1. Selecione **Depósito \> Detalhes da remessa**.
1. Na FastTab **Geral**, anote a ID do ciclo para usá-la no cenário 2.

### <a name="scenario-2-set-up-and-use-lifo-location-aging"></a>Cenário 2: configurar e usar a classificação por vencimento local LIFO

A estratégia LIFO encontra o local que contém a data de classificação por vencimento mais novo e aloca a separação com base nessa data. No cenário 2, você editará a configuração do cenário 1 (FIFO) e reutilizará a ordem de venda e a onda que foram criadas durante esse cenário.

1. Antes de iniciar esse cenário, configure e conclua todo o cenário de FIFO, conforme descrito na [seção anterior](#fifo-demo). Neste cenário, você reutilizará a onda e a maior parte da configuração que foram criadas para esse cenário.
1. Edite a diretiva de localização **Transporte em contêineres de separação 63** para que ela use a estratégia *Classificação por vencimento local LIFO*, conforme descrito na primeira parte do procedimento [Configurar os cenários](#demo-set-up).

    Em seguida, você modificará a onda que foi criada para a ordem de venda no cenário 1 para que ela use a estratégia *Classificação por vencimento local LIFO*.

1. Acesse **Gerenciamento de depósito \> Ondas de saída \> Ondas de remessa \> Todas as ondas**.
1. Selecione e abra a onda que contém a ordem criada para o cenário de FIFO.
1. No Painel de Ação, na guia **Trabalho**, selecione **Cancelar** para cancelar o trabalho criado para o cenário de FIFO.
1. No Painel de Ação, na guia **Onda**, no grupo **Onda**, selecione **Processar**.
1. Quando o processamento for concluído, no Painel de Ação, na guia **Onda**, no grupo **Informações relacionadas**, selecione **Trabalho** para abrir o trabalho que foi criado para esta onda.
1. Na página **Trabalho**, na guia **Visão geral**, deve ter duas linhas. Selecione a linha na qual o campo **Status do trabalho** está definido como *Aberto*.
1. Observe que a linha na qual o valor **Tipo de trabalho** é *Separar* mostra um valor **Local** de *FL-001*. Esse local contém a placa de licença que tem a data de classificação por vencimento mais nova (LIFO).

Nesses cenários, você viu como a estratégia de classificação por vencimento local direciona o trabalho para a localização de estoque que tem o estoque mais antigo ou o mais recente, dependendo da estratégia selecionada.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]