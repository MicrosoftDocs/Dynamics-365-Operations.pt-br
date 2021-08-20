---
title: Criar ordens de transferência do aplicativo de depósito
description: Este tópico descreve como criar e processar ordens de transferência do aplicativo móvel do Gerenciamento de Depósito
author: perlynne
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileDeviceQueueEvent
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 986abfaef81474571de7db179253c4d76f65d4bec180fa9f355f3218ddbb96ba
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746810"
---
# <a name="create-transfer-orders-from-the-warehouse-app"></a>Criar ordens de transferência do aplicativo de depósito

[!include [banner](../includes/banner.md)]

Esse recurso permite que os trabalhadores do depósito criem e processem ordens de transferência diretamente do aplicativo móvel do Gerenciamento de Depósito. O trabalhador começa selecionando o depósito de destino e, em seguida, verifica uma ou mais placas de licença usando o aplicativo para adicionar placas de licença à ordem de transferência. Quando o trabalho de depósito selecionar **Ordem completa**, um trabalho em lotes criará a ordem de transferência e as linhas de ordem necessárias com base no estoque disponível registrado para essas placas de licença.

## <a name="enable-the-create-transfer-orders-from-the-warehouse-app-feature"></a><a name="enable-create-transfer-order-from-warehouse-app"></a>Permitir a criação de ordens de transferência do recurso do aplicativo de depósito

Antes de poder usar esse recurso, ele e seus pré-requisitos deverão estar habilitados no seu sistema. Os administradores podem usar a página [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário.

1. Primeiro, habilite o recurso [Processar eventos do aplicativo de depósito](warehouse-app-events.md), listado no [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) como:
    - **Módulo** - gerenciamento de Depósito
    - **Nome do recurso** - Processar eventos de aplicativo de depósito
1. Em seguida, habilite o recurso *Criar ordens de transferência do aplicativo de depósito*, que está listado como:
    - **Módulo** - gerenciamento de Depósito
    - **Nome do recurso** - crie e processe ordens de transferência do aplicativo de depósito
1. Para automatizar o processamento das remessas de saída, você também deve habilitar o recurso [Confirmar remessas de saída do trabalho em lotes](confirm-outbound-shipments-from-batch-jobs.md). Esse recurso está listado como:
    - **Módulo** - gerenciamento de Depósito
    - **Nome do recurso** - confirme remessas de saída de trabalhos em lote

## <a name="set-up-a-mobile-device-menu-item-to-create-transfer-orders"></a><a name="setup-warehouse-app-menu"></a>Configurar um item de menu do dispositivo móvel para criar ordens de transferência

Aqui estão diretrizes gerais para configurar um item de menu de dispositivo móvel para criar uma ordem de transferência. Dependendo das necessidades comerciais do nível de automação a ser definido quando os usuários criarem ordens de transferência desde o início, as configurações diferentes serão habilitadas. O cenário neste documento descreverá uma dessas configurações.

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
1. Selecione **Novo** para adicionar um novo item de menu. Em seguida, faça as seguintes configurações para começar:

    - **Nome do item de menu** - atribua um nome como deve aparecer no Supply Chain Management.
    - **Título** - atribua um nome de menu como deve ser apresentado a trabalhadores no aplicativo móvel do Gerenciamento de Depósito.
    - **Modo** - defina como *Indireto* (este item de menu não criará trabalho).
    - **Código de atividade** - defina para *Criar uma ordem de transferência de placas de licença* para habilitar os trabalhadores do depósito a criar uma ordem de transferência com base em uma ou mais placas de licença digitalizadas.

1. Use a configuração **Política de criação de linha de ordem de transferência** para controlar como as linhas da ordem de transferência serão criadas por esse item de menu. As linhas serão criadas/atualizadas com base no estoque disponível registrado para as placas de licença verificadas. Escolha um dos seguintes valores:

    - **Nenhuma reserva** - as linhas da ordem de transferência não serão reservadas.
    - **Placa de licença guiada com reserva de linha** – as linhas da ordem de transferência serão reservadas e use a opção Estratégia guiada da placa de licença, que armazena as IDs de placa da licença relevante associadas às linhas da ordem. Os valores de ID da placa de licença localizada podem, portanto, ser usados como parte do processo de criação do trabalho para as linhas da ordem de transferência.

1. Use a configuração **Política de remessa de saída** para adicionar mais automação ao processo de remessa da ordem de transferência de saída, conforme necessário. Quando um trabalhador seleciona o botão **Ordem completa**, o aplicativo cria o evento do aplicativo de depósito *Ordem completa*, que salvará o valor escolhido aqui no campo **Política de remessa de saída** para cada linha na ordem de transferência atual. Posteriormente, quando a fila de eventos for processada por um trabalho em lotes para criar a ordem de transferência, o valor armazenado neste campo poderá ser lido pelo trabalho em lotes e, portanto, poderá controlar a forma como o trabalho processa cada linha. Selecione uma das seguintes opções:

    - **Nenhum** - nenhum processamento automatizado é concluído.
    - **Liberar para depósito** - automatiza o processo de liberação para depósito.
    - **Confirmação de remessa** - automatiza o processo de confirmação de remessa.
    - **Confirmar liberação e remessa** - automatiza os processos de liberação para depósito e remessa.

## <a name="add-the-mobile-device-menu-item-to-a-menu"></a>Adicionar o item de menu de dispositivo móvel a um menu

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Menu do dispositivo móvel**
1. Selecione **Editar**.
1. Selecione um menu existente após a seleção do novo item de menu , em **Menus disponíveis e itens de menu**. Adicione o item de menu selecionando o botão de seta para a direita.

## <a name="create-a-transfer-order-based-on-license-plates"></a>Criar uma ordem de transferência com base em placas de licença

O aplicativo móvel do Gerenciamento de Depósito tem um processo simples para criar ordens de transferência com base em placas de licença. Para isso, o trabalhador faz o seguinte usando o aplicativo móvel do Gerenciamento de Depósito:

1. Cria a ordem de transferência e identifica o depósito de destino.
1. Identifica cada placa de licença a ser remetida.
1. Seleciona **Concluir ordem**.

>[!NOTE]
> É possível que vários trabalhadores atribuam placas de licença destinadas à mesma ordem de transferência usando o botão **Selecionar ordem de transferência** para selecionar um número de ordem de transferência existente e não processado da fila de eventos do aplicativo de depósito. Para obter informações sobre como localizar os valores numéricos da ordem de transferência, veja [Consultar os eventos do aplicativo de depósito](#inquire-the-warehouse-app-events).

## <a name="example-scenario"></a>Cenário de exemplo

Este cenário fornece uma visão geral do processo para obter ordens de transferência criadas e processadas automaticamente com base no estoque disponível registrado nas placas de licença selecionadas.

Para trabalhar neste cenário usando os valores sugeridos, você deverá trabalhar em um sistema com dados de demonstração instalados e selecionar a entidade legal *USMF* antes de começar.

Este cenário presume que você já tenha habilitado [Criar e processar ordens de transferência do recurso de aplicativo de depósito](#enable-create-transfer-order-from-warehouse-app)e o recurso de [processamento de eventos de aplicativo de depósito](warehouse-app-events.md).

Além de configurar a ordem de transferência de criação nos itens de menu do dispositivo móvel, modelos adicionais, diretivas de local e trabalhos em lotes também deverão ser configurados e habilitados.

### <a name="example-scenario-blueprint"></a>Blueprint de cenário de exemplo

Você é um varejista e tem várias placas de licença, cada uma contendo uma mistura de itens colocados em um local específico em um de seus depósitos (*Depósito 51*). Você gostaria de habilitar o processo que permite que os funcionários criem uma ordem de transferência para outro depósito (*Depósito 61*) para um conjunto de placas de licença digitalizadas. Você remeterá e atualizará automaticamente a ordem de transferência, assim que a última placa de licença da ordem for identificada.

![Exemplo de processo de ordem de transferência automatizada.](media/create-transfer-order-from-app-example.png "Exemplo de processo de ordem de transferência automatizada")

### <a name="create-a-mobile-device-menu-item-for-creating-transfer-orders"></a>Criar um item de menu do dispositivo móvel para a criação de ordens de transferência

Esta seção explica como criar um novo item de menu de dispositivo móvel para criar ordens de transferência. Defina o **Modo** como *Indireto* e o **Código de atividade** como *Criar ordem de transferência das placas de licença*.

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
1. Selecione **Novo**.
1. No campo **Nome do item de menu**, insira o nome *Criar PARA*.
1. No campo **Título**, insira a descrição *Criar PARA*.
1. No campo **Modo**, selecione *Indireto*.
1. No **Código de atividade**, selecione *Criar ordem de transferência de placas de licença*
1. Na **Política de criação de linha da ordem**, selecione *Placa de licença guiada com reserva de linha*.
1. Na **Política de remessa de saída**, selecione *Confirmação de liberação e remessa*.
1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Menu do dispositivo móvel**.
1. Selecione **Editar**.
1. Selecione o menu **Estoque** existente e então selecione o novo item de menu em **Menus e itens de menu disponíveis**. Adicione o item de menu no menu **Estoque** selecionando o botão de seta para a direita.

### <a name="set-up-work-templates-to-auto-process-and-break-work-by-located-license-plate"></a>Configurar modelos de trabalho para processar automaticamente e dividir o trabalho por placa de licença localizada

Esta seção explica como habilitar um modelo de trabalho para processar automaticamente o trabalho criado pelo modelo quando um ciclo é liberado.

1. Acesse **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelo de trabalho**.
1. No campo **Tipo de ordem de serviço**, selecione *Problema de transferência*.
1. Selecione **Novo** para criar um novo modelo de trabalho.
1. No campo **Modelo de trabalho**, digite *51 Processar PL automaticamente*.
1. No campo **Descrição do modelo de trabalho**, insira *51 Processar PL automaticamente*.
1. Marque a caixa de seleção **Processar automaticamente**. Isso deve ser selecionado para que as etapas de automação sejam processadas.
1. Nos dados de demonstração, já existe um modelo de trabalho *51 Transferência*, edite o campo **Número de sequência** para que o novo modelo de trabalho tenha um número de sequência inferior ao da transferência do modelo de trabalho existente *51 Transferência*.
1. Selecione **Salvar** na barra de ferramentas para habilitar a Guia Rápida **Detalhes do Modelo de Trabalho**.
1. Na Guia Rápida **Detalhes do Modelo de Trabalho**, selecione **Novo** na barra de ferramentas. Você adicionará duas linhas.
1. No campo **Tipo de trabalho**, selecione *Separar*.
1. No campo **ID da classe de trabalho**, selecione *TransfOut*.
1. Selecione **Novo** na barra de ferramentas **Detalhes do Modelo de Trabalho**.
1. No campo **Tipo de trabalho**, selecione *Colocar*.
1. No campo **ID da classe de trabalho**, selecione *TransfOut*.
1. Selecione **Salvar** para habilitar o campo **Código de diretiva**.
1. Na *Put* do **Tipo de trabalho** , selecione o **Código de diretiva** *Baydoor*. Certifique-se de que esse novo modelo de trabalho obtenha o **Número de sequência** mais baixo.
1. Na varra de ferramentas, selecione **Editar consulta** para abrir o editor de consultas.
1. Na guia **Intervalo**, selecione **Adicionar**.
1. Na linha adicionada, em **Campo**, selecione *Depósito*.
1. No campo **Critérios**, selecione *51*.
1. Selecione a guia **Classificação**.
1. Selecione **Adicionar** e defina **Campo** como *ID da placa de licença localizada*. A seleção desse campo habilitará as **Quebras de cabeçalho de trabalho** do botão da barra de ferramentas.
1. Selecione **OK** seguido por **Sim** para redefinir o agrupamento e retornar à página **Modelos de trabalho**.
1. Selecione **Quebras de cabeçalho de trabalho** e habilite **Agrupar por este campo** para a **ID da placa de licença localizada** e feche.

> [!NOTE]
> Nem toda a configuração pode ser processada automaticamente, por exemplo, itens de peso variável e o uso de dimensões de rastreamento misto.

### <a name="set-up-location-directives-for-the-license-plate-guided-strategy"></a>Configurar diretivas de localização para a estratégia de placa de licença guiada

Esta seção explica como configurar um processo de escolha de diretiva de localização para usar a estratégia **Placa de licença guiada**.

1. Acesse **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.
1. Selecione **Editar**.
1. No cabeçalho da lista de navegação, selecione o **Tipo de ordem de trabalho** *Problema de transferência*.
1. Na lista de navegação, selecione a diretiva de localização existente **51 A separar**.
1. Na Guia Rápida **Linhas**, marque a caixa de seleção **Permitir divisão**.
1. Na Guia Rápida **Ações de Diretiva de Localização**, selecione **Nova** para adicionar uma nova linha de ação.
1. No campo **Nome**, insira *PL Guiada*.
1. No campo **Estratégia**, selecione *Placa de licença guiada*. Esta ação precisa do número de sequência mais baixo.
1. Selecione **Salvar** na barra de ferramentas.
1. Selecione o ícone de página **Atualizar** na barra de ferramentas.
1. Na Guia Rápida **Ações de Diretiva de Localização**, selecione a linha *TOPick*.
1. Na barra de ferramentas **Ações de Diretiva de Localização**, selecione **Mover para baixo** para alterar o número de sequência para maior do que o número de sequência da ação *PL Guiada* que acabou de ser criada.

> [!NOTE]
> A estratégia dirigida pela placa de licença tentará reservar e criar um trabalho de separação contra os locais que contêm as placas de licença solicitadas que foram associadas às linhas da ordem de transferência. Mas se isso não for possível e você ainda deseja criar um trabalho de separação, faça fallback para a outra estratégia de ação de diretiva de localização e talvez pesquise também o estoque em outra área do depósito, dependendo de suas necessidades de processo comercial.

### <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a>Configurar um trabalho em lotes para processar eventos de aplicativo de depósito

Esta seção explica como configurar um trabalho em lotes agendado para processar eventos de aplicativo de depósito.

1. Acesse **Gerenciamento de depósito \> Tarefas periódicas \> Processar remessas de saída**.
2. Na caixa de diálogo, habilite **Processamento em lotes** na seção **Executar em segundo plano**.
3. Selecione **Recorrência** e configure o trabalho em lotes para processar com base no intervalo necessário para a sua empresa.
4. Selecione **OK** para retornar ao diálogo principal.
5. Selecione **OK** no diálogo principal para adicionar o trabalho à fila de lotes.

### <a name="set-up-a-batch-job-to-release-transfer-orders-automatically"></a>Configurar um trabalho em lotes para liberar ordens de transferência automaticamente

Esta seção explica como configurar um trabalho em lotes agendado para liberar as ordens de transferência que foram marcadas como "prontas para liberação".

1. Acesse **Gerenciamento de depósito \> Liberar para depósito \> Liberação automática de ordens de transferência**.
1. Na caixa de diálogo, expanda a seção **Registros a serem incluídos**.
1. Selecione **Filtrar** na seção **Registros a serem incluídos**.
1. Na página da consulta **WHSTransferAutoRTWQuery**, na guia **Intervalo**, selecione **Adicionar** para adicionar uma nova linha à consulta.
1. No campo **Tabela** da nova linha, selecione o menu suspenso e selecione a tabela **Liberação de linha de transferência para depósito**.
1. No menu suspenso **Campo**, selecione **Política de remessa de saída**.
1. No campo **Critérios**, selecione **Confirmação de liberação e remessa**.
1. Na linha onde **Campo** está definido como *Do depósito*, no campo **Critérios**, selecione *51*.
1. Selecione **OK** para retornar à caixa de diálogo principal.
1. Expanda a seção **Executar em segundo plano** para configurar o processamento em lotes.
1. Habilite **Processamento em lotes** na seção **Executar em segundo plano**.
1. Selecione **Recorrência** e configure o trabalho em lotes para processar com base no intervalo necessário para a sua empresa.
1. Selecione **OK** para retornar ao diálogo principal.
1. Selecione **OK** no diálogo principal para adicionar o trabalho em lotes à fila de lotes.

### <a name="set-up-the-process-outbound-shipment-batch-job"></a>Configurar o trabalho em lotes "Processar remessa de saída"

Esta seção explica como configurar um trabalho em lotes agendado para executar a confirmação de remessa de saída para cargas prontas para remessa relacionadas a linhas de ordem de transferência que estão "prontas para serem remetidas".

1. Acesse **Gerenciamento de depósito \> Tarefas periódicas \> Processar remessas de saída**.
1. Expanda a seção **Registros a serem incluídos**.
1. Selecione **Filtro**.
1. Na consulta **WHSLoadShipConfirm**, selecione a guia **Junções**.
1. Expanda a hierarquia da tabela para que **Cargas** e **Detalhes da carga** sejam expandidos.
1. Selecione a tabela **Detalhes da carga**.
1. Selecione o botão **Adicionar junção de tabela**.
1. Na lista de relações de tabela, filtre ou pesquise na coluna **Relação** para *Linhas de ordem de transferência (Referência)*.
1. Focalize a relação de tabela na lista e pressione o botão **Selecionar**.
1. Selecione a tabela **Linhas da ordem de transferência**.
1. Selecione o botão **Adicionar junção de tabela**.
1. Na lista de relações de tabela, filtre ou pesquise na coluna **Relação** para *Campos Adicionais da Transferência de Estoque (Record-ID)*.
1. Focalize a relação de tabela na lista e pressione o botão **Selecionar**.
1. Selecione a guia **Intervalo**.
1. Nas tabelas de consulta de **Intervalo** , você configurará três intervalos de critérios de consulta. Selecione o botão **Adicionar** para adicionar uma linha.
1. Adicione um intervalo à tabela **Cargas**. Defina **Campo** como *Status da carga* e defina **Critérios** como *Carregado*.
1. Adicione outro intervalo para a tabela **Campos Adicionais de Transferência de Estoque**. Defina **Campo** como *Política de remessa de saída* e defina **Critérios** como *Confirmação de liberação e remessa*.
1. Adicione outro intervalo para a tabela **Detalhes da carga**. Defina **Campo** como *Referência* e defina **Critérios** como *Remessa de ordem de transferência*.
1. Selecione **OK** para retornar à caixa de diálogo principal.
1. Expanda a seção **Executar em segundo plano**.
1. Habilite **Processamento em lotes**.
1. Selecione **Recorrência** e configure o trabalho em lotes para processar com base no intervalo necessário para a sua empresa.
1. Selecione **OK** para retornar ao diálogo principal.
1. Selecione **OK** no diálogo principal para adicionar o trabalho em lotes à fila de lotes.

> [!NOTE]
> Para obter mais informações, consulte [Confirmar remessas de saída de trabalhos em lotes](confirm-outbound-shipments-from-batch-jobs.md).

## <a name="processing-the-example-for-create-transfer-order-from-the-warehouse-app"></a>Processamento do exemplo para "Criar ordem de transferência do aplicativo de depósito"

### <a name="add-on-hand-on-a-license-plate"></a>Adicionar disponível a uma placa de licença

Como ponto de partida para este cenário, você precisará ter uma placa de licença que contenha estoque físico disponível.

| Item  | Depósito | Status do estoque | Localização | Placa de licença | Quantidade |
| --- | --- | --- | --- | --- | --- |
| A0001 | 51 | Disponível | LP-010 | LP10 | 1 |
| A0002 | 51 | Disponível | LP-010 | LP10 | 2 |

Adicione as quantidades de estoque físico disponível usando os valores a seguir:

> [!NOTE]
> Será necessário criar a placa de licença e locais de uso que permitam que você carregue itens mistos, como LP-010.

### <a name="create-and-process-transfer-orders-from-the-warehouse-app"></a>Criar e processar ordens de transferência do aplicativo de depósito

1. Abra o aplicativo e entre como o usuário *51*. O depósito atual do usuário será o 51.
1. Selecione o item de menu **Criar PARA** da localização do menu ao qual você o adicionou durante a configuração.
1. Inicie a criação de uma ordem de transferência inserindo o depósito de destino (Depósito final); no campo **Depósito**, digite *61*. A nova ordem de transferência passará do depósito 51 atual (Depósito inicial) para o depósito de destino, *61*.
1. Selecione **OK**.
1. Verifique a ID da placa de licença no campo **Placa de licença**. Insira a placa de licença do estoque adicionado em uma etapa anterior, *LP10*.
1. Selecione **OK**.
1. Selecione o botão de menu e selecione **Concluir ordem** para finalizar a criação da ordem de transferência do aplicativo de depósito.

Para o exemplo mencionado, são usados dois **Eventos de aplicativo de depósito** (*Criar ordem de transferência* e *Concluir ordem de transferência*).

### <a name="inquire-the-warehouse-app-events"></a><a name="#inquire-the-warehouse-app-events"></a>Consultar os eventos do aplicativo de depósito

Você pode exibir a fila de eventos e as mensagens de eventos geradas pelo aplicativo móvel Gerenciamento de Depósito indo para **Gerenciamento de depósito \> Consultas e relatórios \> Logs do dispositivo móvel \> Eventos do aplicativo de depósito**.

As mensagens de evento *Criar ordem de transferência* receberão o status *Aguardando*, o que significa que o trabalho em lotes **Processar eventos do aplicativo de depósito** não coletará e processará as mensagens de evento. Assim que a mensagem de evento for atualizada para o status *Enfileirada*, o trabalho em lotes processará os eventos. Isso ocorrerá ao mesmo tempo que a criação do evento *Concluir ordem de transferência* (quando um trabalhador seleciona o botão **Concluir ordem** no aplicativo móvel do Gerenciamento de Depósito). Quando as mensagens do evento *Criar ordem de transferência* tiverem sido processadas, o status será atualizado para *Concluído* ou *Falha*. Quando o status *Concluir ordem de transferência* é atualizado para *Concluído*, todos os eventos relacionados são excluídos da fila.

Como os **Eventos do aplicativo de depósito** para a criação de dados de ordem de transferência não serão processados pelo trabalho em lotes antes de as mensagens serem atualizadas para o status *Enfileirado*, será necessário procurar os números de ordem de transferência solicitados como parte do campo **Identificador**. O campo **Identificador** está no cabeçalho da página **Eventos do aplicativo de depósito**.

Como parte do processamento de eventos de depósito, a criação da linha da ordem de transferência pode falhar. Nesse caso, o estado da mensagem do evento é atualizado para *Falha* e você pode usar as informações de **Log de lote** para saber o motivo e executar ações para corrigir qualquer problema.

Os problemas típicos podem estar relacionados à configuração ausente do processo, como um depósito de trânsito ausente para o evento *Criar ordem de transferência*. Em um exemplo como este, você adicionaria um depósito de trânsito ao depósito de remessa e usaria a opção **Redefinir** para alterar o status de todas as mensagens de evento de aplicativo de depósito de *Falha* para *Enfileirado*, o que significa que o trabalho em lotes processaria as mensagens de evento novamente após a correção dos dados de configuração.

Em ambientes de produção, as exceções estariam mais relacionadas a processos, como ter uma placa de licença solicitada que, no tempo de processamento do trabalho em lotes, está vazia e, portanto, nenhuma linha de ordem de transferência é criada. Esta mensagem de evento com falha pode ser removida usando a opção **Excluir** ou você pode adicionar o disponível físico necessário na placa de licença e usar a opção **Redefinir** para todas as mensagens de evento relacionadas.

Para obter mais informações, consulte [Processamento de eventos do aplicativo de depósito](warehouse-app-events.md).

### <a name="follow-up-on-the-example-scenario-processing"></a>Acompanhamento no processamento do cenário de exemplo

Durante este cenário, ocorreu o seguinte:

1. Usando o aplicativo móvel do Gerenciamento de Depósito, você selecionou um item de menu que usa o código de atividade **Criar ordem de transferência de placas de licença**.
1. O aplicativo solicitou que você selecionasse o depósito de destino para a ordem de transferência. O depósito de origem é sempre aquele no qual você entrou como um Trabalhador.
1. Na seleção do depósito de destino, o sistema reservou um número de ID para a ordem de transferência futura (com base na sequência numérica da ordem de transferência definida no sistema), mas ainda não criou a ordem de transferência.
1. Quando você digitalizou a placa de licença *LP10* com o estoque disponível que deveria ser movido para o novo depósito, um **Evento de aplicativo de depósito** foi adicionado à fila de eventos para ser processado posteriormente. O evento de depósito continha detalhes da mensagem sobre a verificação, incluindo o número da ordem de transferência pretendida.
1. No aplicativo móvel do Gerenciamento de Depósito, quando o botão **Concluir ordem** é selecionado, um novo evento de aplicativo de depósito, **Concluir ordem de transferência**, é criado e o evento relacionado existente, **Criar ordem de transferência**, altera o status para **Enfileirado**.
1. No back-end, **Processar trabalho em lotes de eventos do aplicativo de depósito** separou o evento **Enfileirado** e coletou o disponível relacionado à placa de licença verificada. Com base na disponibilidade, o registro de ordem de transferência real e as linhas associadas foram criados. O trabalho também preencheu o campo **Política de remessa de saída** para a ordem de transferência com o valor baseado *Confirmação de liberação e remessa* configurada e vinculou a placa de licença às linhas da estratégia **Placa de licença guiada**.
1. Com base no valor do campo **Política de remessa de saída** da linha da ordem de transferência, a consulta do **trabalho em lotes Liberação automática de ordens de transferência** agora resultou na liberação da ordem de transferência para o depósito de remessa. E, devido à configuração para **Modelo de ciclo**, **Modelo de trabalho** e **Diretivas de localização** usados, o trabalho recebeu processos automáticos, resultando na atualização do **Status da carga** para *Carregado*.
1. O **trabalho em lotes Processar remessa de saída** é executado para a carga, resultando na remessa da ordem de transferência e na geração da Notificação de Remessa Antecipada (ASN).
1. O tempo de todos esses eventos depende das configurações de **Recorrência** dos trabalhos em lote criados.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="mobile-device-menu-item-setup"></a>Configuração de item de menu de dispositivo móvel

#### <a name="why-cant-i-see-create-transfer-order-from-license-plate-in-the-menu-item-work-activity-drop-down-list"></a>Por que não consigo ver "Criar ordem de transferência da placa de licença" na lista suspensa de atividade de trabalho do item de menu?

O recurso *Criar e processar ordens de transferência do aplicativo de depósito* deve estar habilitado. Para obter mais informações, consulte [Habilitar a criação de ordens de transferência do aplicativo Depósito](#enable-create-transfer-order-from-warehouse-app).

### <a name="warehouse-management-mobile-app-processes"></a>Processos do aplicativo móvel de Gerenciamento de depósito

#### <a name="why-cant-i-see-the-menu-button-complete-order"></a>Por que não consigo ver o botão de menu "Concluir ordem"?

Você deve ter pelo menos uma placa de licença atribuída à ordem de transferência.

#### <a name="can-several-warehouse-management-mobile-app-users-add-license-plates-to-the-same-transfer-order-at-the-same-time"></a>Vários usuários de aplicativo móvel do Gerenciamento de Depósito podem adicionar placas de licença à mesma ordem de transferência ao mesmo tempo?

Sim, vários trabalhadores de depósito podem digitalizar placas de licença na mesma ordem de transferência.

#### <a name="can-the-same-license-plate-be-added-to-different-transfer-orders"></a>É possível adicionar a mesma placa de licença a diferentes ordens de transferência?

Não, uma placa de licença só pode ser adicionada a uma ordem de transferência no momento.

#### <a name="after-having-selected-the-complete-order-button-can-i-then-add-more-license-plates-for-that-transfer-order"></a>Depois de selecionar o botão "Concluir ordem", posso adicionar mais placas de licença à essa ordem de transferência?

Não, não é possível adicionar mais placas de licença a uma ordem de transferência que tenha um evento de aplicativo de depósito **Concluir ordem de transferência**.

#### <a name="how-can-i-find-existing-transfer-orders-to-be-used-via-the-select-transfer-order-button-in-the-warehouse-management-mobile-app-if-the-order-has-not-yet-been-created-in-the-backend-system"></a>Como encontro as ordens de transferência existentes para serem usadas por meio do botão "Selecionar ordem de transferência" no aplicativo móvel do Gerenciamento de Depósito, caso a ordem ainda não tenha sido criada no sistema de back-end?

No momento, não é possível pesquisar ordens de transferência no aplicativo, mas você pode encontrar os números de ordem de transferência na página **Eventos do aplicativo de depósito**. Para obter mais informações, consulte [Consultar eventos do aplicativo de depósito](#inquire-the-warehouse-app-events).

#### <a name="can-i-manually-select-the-transfer-order-number-to-be-used-from-the-warehouse-management-mobile-app"></a>Posso selecionar manualmente o número da ordem de transferência a ser usado no aplicativo móvel do Gerenciamento de Depósito?

Só há suporte para números de ordens de transferência autogerados por meio de sequências numéricas.

### <a name="background-processing"></a>Processamento em segundo plano

#### <a name="how-should-i-clean-up-records-in-my-warehouse-app-events-queue-message-tables"></a>Como devo limpar registros em minhas tabelas de mensagens de fila de eventos do aplicativo de depósito?

Você pode exibir e manter isso na página **Eventos do aplicativo de depósito**. Para obter mais informações, consulte [Consultar eventos do aplicativo de depósito](#inquire-the-warehouse-app-events).

#### <a name="why-is-the-transfer-order-receipt-date-not-updated-according-to-my-delivery-date-control-setup"></a>Por que a "Data de recebimento" da ordem de transferência não é atualizada de acordo com a minha configuração de "Controle da data de entrega"?

As ordens de transferência são criadas sem o uso dos recursos de **Controle da data de entrega**.

#### <a name="can-i-use-a-license-plate-having-physical-negative-inventory-on-hand"></a>É possível usar uma placa de licença com estoque físico negativo disponível?

O recurso só é compatível com quantidades físicas disponíveis positivas no nível de placa de veículo, mas você pode ter quantidades físicas disponíveis negativas nos níveis de status do armazém e inventário ao atribuir placas de veículo para transferir ordens.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]