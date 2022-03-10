---
title: Interface de equipamento de manuseio de materiais (MHAX)
description: Este tópico descreve como configurar a interface de equipamento de manuseio de materiais (MHAX) para que você possa se conectar a sistemas de manuseio de materiais (MH) físicos externos.
author: Mirzaab
ms.date: 03/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMHEParameters, WMHESubscription, WMHEQueueManagerWorkspace, WMHEInboundQueue, WMHEOutboundQueue
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-04
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 7e71ca2877effe671723be53e844e8401714038a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7565199"
---
# <a name="material-handling-equipment-interface-mhax"></a>Interface de equipamento de manuseio de materiais (MHAX)

[!include [banner](../../includes/banner.md)]

Você pode usar a *interface de equipamento de manuseio de materiais* (MHAX) para conectar sistemas de manuseio de materiais (MH) físicos externos para um depósito gerenciado por um gerenciamento de depósito avançado (WMS) no Microsoft Dynamics 365 Supply Chain Management. A interface entre o WMS e os sistemas de MH consiste em duas filas: uma para eventos de saída (WMS para MH) e outra para eventos de entrada (MH para WMS). O sistema do WMS gera eventos de saída com base em linhas de trabalho criadas durante vários processos de criação e execução de trabalho. O sistema de MH regularmente verifica o sistema do WMS em busca de novos eventos e processa as respostas. Depois que o sistema de MH termina de tratar os eventos de acordo com as instruções do trabalho, ele envia eventos de entrada, como conclusão da linha de trabalho e separação insuficiente.

A ilustração a seguir mostra os vários elementos e a ordem em que os processos ocorrem ao usar a integração de MHAX.

![Componentes e interações do MHAX.](media/mhax-components.png "Componentes e interações do MHAX")

Veja uma explicação das interações mostradas na ilustração anterior:

1. Durante a criação ou execução do trabalho, os eventos de saída são criados na fila de saída.
2. O equipamento de MH se conecta ao serviço do equipamento de MH, pesquisa novos eventos relevantes e os processa.
3. Quando o equipamento de MH estiver pronto para reportar, ele se conectará ao serviço novamente e enviará os eventos de entrada. Esses eventos são processados imediatamente pelo processador de fila.
4. Com base nos dados de evento de entrada, o processador de fila pode executar o trabalho existente, modificá-lo ou criar outro.

## <a name="turn-on-the-mhax-feature"></a>Ativar o recurso MHAX

Antes de usar o recurso de MHAX, é necessário ativar o recurso e a chave de configuração.

1. Acesse **Administrador do sistema \> Espaços de trabalho \> Gerenciamento de recursos**.
2. No espaço de trabalho de **[Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)**, ative o recurso chamado de *Interface de equipamento de manuseio de materiais*.
3. Coloque seu sistema em modo de manutenção, conforme descrito em [Modo de manutenção](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
4. Acesse **Administração de sistema \> Configurar \> Configuração de licença**.
5. Expanda **Comércio \> Gerenciamento de Depósito e Transporte** e marque a caixa de seleção **Interface de equipamento de manuseio de materiais**.
6. Desative o modo de manutenção, conforme descrito em [Modo de manutenção](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).

## <a name="set-mhax-parameters"></a>Definir parâmetros de MHAX

É necessário definir alguns parâmetros gerais na página **Parâmetros de interface de equipamento de manuseio de materiais** para configurar o recurso.

1. Acesse **Interface de equipamento de manuseio de materiais \> Configuração \> Parâmetros de interface de equipamento de manuseio de materiais**.
2. Na guia **Geral**, defina os seguintes campos:

    - **ID de usuário** – Selecione um trabalhador. Este trabalhador será usado para executar todas as operações de trabalho (separar e colocar) processados por meio da fila de entrada.
    - **Habilitar ID da mensagem de entrada** – Quando esta opção estiver definida como *Sim*, se uma ID de mensagem de entrada duplicada for recebida, a mensagem será rejeitada e uma mensagem de erro indicará que ela já existe. Quando esta opção estiver definida como *Não*, as IDs de mensagens de entrada duplicadas serão permitidas.

3. Na guia **Sequências numéricas**, selecione as sequências numéricas de todo o sistema que devem ser usadas para gerar IDs exclusivas para os itens da fila de entrada, itens da fila de saída e pares da linha de trabalho.

## <a name="outbound-events"></a>Eventos de saída

Em alguns pontos durante a criação ou execução do trabalho, o sistema determina se deve gerar eventos de saída para enviar ao sistema de MH. Se uma assinatura for configurada para um ponto específico durante o processamento do depósito, o sistema gerará o evento de acordo com a configuração da assinatura.

### <a name="structure-of-outbound-events"></a>Estrutura dos eventos de saída

Cada evento de saída é identificado exclusivamente por uma ID de fila de saída. O tipo de transação de saída determina o tipo do evento. O depósito e a ID da assinatura que gerou o evento também são registrados no evento.

Para transferir dados do sistema de MH, o evento de saída contém 10 campos por dados (**data01** para **data10**). Esses campos de dados têm um mapeamento de um para um (1:1) para campos de bancos de dados existentes. Especificamente, eles são extraídos de campos na linha de trabalho e tabelas de cabeçalho de trabalho. Os campos podem ser livremente selecionados. Eles são configurados ao criar a assinatura.

Além dos 10 campos de dados com mapeamento de 1:1 para campos de dados existentes, o evento pode conter um campo de dados adicional conhecido como *carga*. O conteúdo deste campo é gerado pelo código X++ personalizado conhecido como *gerador de carga*. Qualquer gerador de carga que deve ser usado é configurado na assinatura.

Para garantir que o sistema de MH receba cada ID de fila de saída somente uma vez, um campo de status é usado para especificar se um evento está pronto para ser enviado para o sistema externo ou se ele já foi enviado.

### <a name="outbound-queue-subscriptions"></a>Assinaturas da fila de saída

Antes de qualquer evento ser gerado, uma assinatura deve ser configurada para informar ao recurso MHAX se e como gerar eventos. Os eventos gerados são marcados pelo identificador de assinatura. Portanto, vários sistemas de MH podem se conectar ao mesmo sistema do WMS, mas manter eventos separados. Quando o serviço de MHAX é consultado em busca de novos eventos, uma assinatura é uma das opções disponíveis para recuperar os eventos.

Para criar uma assinatura, acesse **Interface de equipamento de manuseio de materiais \> Configuração \> Assinaturas**. Para cada assinatura, os seguintes parâmetros estão disponíveis:

- **ID da assinatura** – Um nome exclusivo que identifica a assinatura.
- **Descrição** – Uma descrição de texto livre da assinatura.
- **Depósito** – Os depósitos específicos pelos quais os eventos devem ser filtrados.
- **Tipo de transação de saída** – O tipo de evento que a assinatura deve conter.
- **Gerador de carga** – Uma extensão de código opcional que pode inserir informações adicionais no campo **Carga** do evento de saída.

Uma consulta pode ser associada a cada assinatura. Esta consulta filtra as linhas e os cabeçalhos de trabalho para limitar ainda mais o trabalho que usará a assinatura para gerar eventos. Para adicionar uma consulta a uma assinatura, marque a caixa de seleção **Executar consulta** da assinatura relevante na página **Assinaturas** e selecione **Editar consulta** no Painel de Ações. O editor de consulta do Supply Chain Management padrão é exibido.

Além disso, a assinatura inclui um *mapa de assinatura* que mapeia campos do cabeçalho ou da linha do trabalho para alguns ou todos os 10 campos de dados livres do evento de saída, conforme necessário. Para retornar informações para o serviço de MHAX, você normalmente incluirá a ID do registro da linha de trabalho ou a *ID do par de linhas do trabalho*. (A ID do par de linhas de trabalho é uma nova propriedade que permite que o sistema use um único comando de retorno para processar as linhas de separação e colocação.) Os campos restantes dependem do caso de uso. Alguns exemplos são fornecidos posteriormente neste tópico.

Para configurar um mapa de assinatura, selecione a assinatura relevante na página **Assinaturas** e, depois, selecione **Mapa de assinatura** no Painel de Ações. Na caixa de diálogo **Mapa da assinatura** exibida, você pode atribuir uma tabela e um campo para cada campo de dados disponível, conforme necessário.

### <a name="outbound-event-types"></a>Tipos de eventos de saída

Esta seção descreve os vários tipos de eventos que estão disponíveis. (Os tipos de eventos também são conhecidos como *tipos de transação*.) Isso também explica quando cada tipo de evento é criado no sistema do WMS.

#### <a name="work-creation-events"></a>Eventos de criação de trabalho

Os eventos de criação de trabalho são criados após o trabalho ter sido gerado pelo aplicativo. Esse comportamento se aplica à maioria dos tipos de processos de criação de trabalho, principalmente à criação de trabalho de separação e reabastecimento. Em geral, se o trabalho é criado em um estado *Aberto*, o que indica que o trabalho está pronto para ser executado por um trabalhador, um evento de criação de trabalho será gerado. Além disso, os eventos de criação de trabalho serão gerados para trabalho de movimento básico (não movimento por trabalho de modelo), mesmo se esse trabalho não for criado como trabalho aberto.

Uma exceção notável desse comportamento é o trabalho de contagem cíclica, que atualmente não é compatível. As contagens de estoque no sistema de MH estão fora do escopo do MHAX e os resultados das contagens será importado para um diário de contagem de estoque.

Depois que o trabalho tiver sido criado, o serviço do MHAX processa as linhas de trabalho geradas e atribui uma ID do par de linhas de trabalho a todas as linhas de trabalho geradas para cada cabeçalho de trabalho. O objetivo é agrupar todas as linhas de trabalho de separação com as colocações sucessivas em uma ID de par de linhas de trabalho. (Os grupos correspondem a pares de seleção/colocação em modelos de trabalho.) Dessa forma, uma única ID pode ser usada para concluir o trabalho de todas as linhas de separação e colocação relacionadas. O processo de agrupamento começa com a primeira linha e continua com a mesma ID até encontrar um par sucessivo de linhas de trabalho de colocação/separação. A ID de execução é atribuída à linha de colocação desse par. Subsequentemente, uma nova ID será usada para a linha de separação do par. Esse processo continua até que ele tenha processado todas as linhas que pertencem ao cabeçalho do trabalho.

Como recurso especial de eventos de criação de trabalho, se a opção **Ciclo bloqueado** estiver definida como *Sim* no cabeçalho do trabalho, os eventos gerados terão um status *Bloqueado* em vez do status normal *Pronto*, usado para enviá-los para o sistema de MH. O sinalizador **Ciclo bloqueado** no cabeçalho do trabalho indica que o cabeçalho do trabalho ainda não está pronto para ser executado pelos trabalhadores, talvez devido ao trabalho de reabastecimento não concluído. Quando o sinalizador **Ciclo bloqueado** for desmarcado, os eventos que já foram gerados serão desbloqueados e disponibilizados para que o sistema de MH recupere da fila.

#### <a name="work-initiation-events"></a>Eventos de iniciação de trabalho

Os eventos de iniciação de trabalho são acionados quando o status de trabalho mudar de *Aberto* para *Em processo* durante a atualização de trabalho.

#### <a name="work-completion-events"></a>Eventos de conclusão de trabalho

Os eventos de conclusão de trabalho são acionados quando o status de trabalho mudar de *Em processo* para *Fechado* durante a atualização de trabalho.

#### <a name="work-cancellation-events"></a>Cancelamento de eventos de trabalho

Os eventos de cancelamento de trabalho são acionados quando o status de trabalho mudar de qualquer status, além de *Cancelado* para *Cancelado*, durante a atualização de trabalho. Além disso, todos os outros eventos relacionados ao cabeçalho de trabalho são excluídos da fila para todas as assinaturas. Dessa forma, os sistemas externos são impedidos de processar eventos que não são necessários.

#### <a name="pickput-completion-events"></a>Eventos de conclusão de separação/colocação

Os eventos de conclusão de separação/conclusão são acionados quando o status da linha de separação/colocação alterar de *Em processo* para *Fechado* durante a atualização da linha de trabalho.

### <a name="monitor-the-outbound-queue"></a>Monitorar a fila de saída

Para revisar a fila de saída, acesse **Interface de equipamento de manuseio de materiais \> Comum \> Fila de saída**. A página **Fila de saída** lista todos os itens de fila de saída e o status. Selecione o item de fila para exibir os detalhes. Esses detalhes incluem o tipo de transação do item, a assinatura usada e os valores de cada campo de dados (**data01** até **data10**) e a carga.

### <a name="clean-up-the-outbound-queue"></a>Limpar a fila de saída

Subsequentemente, a fila de saída começará a ficar cheia de itens de fila que já foram enviados. Para remover esses itens, acesse **Interface de equipamento de manuseio de materiais \> Tarefas periódicas \> Limpeza \> Limpeza de fila de saída**.

## <a name="inbound-events"></a>Eventos de entrada

Esta seção descreve os vários tipos de eventos de entrada que o sistema de MH pode relatar de volta para o sistema do WMS. Ele também explica que os dados devem ser fornecidos pelo sistema de MH e o que cada evento de entrada faz no sistema do WMS.

### <a name="structure-of-inbound-events"></a>Estrutura dos eventos de entrada

Quando um evento de entrada é enviado, o sistema externo deve fornecer o tipo de transação de entrada com até 10 parâmetros (**data01** até **data10**). A validação opcional pode garantir que o serviço do MHAX não receba o mesmo evento de entrada mais de uma vez. Para habilitar essa validação, cada evento de entrada deve ter uma ID de mensagem exclusiva. Se um ID de mensagem duplicado for recebido e a opção **Habilitar ID de mensagem de entrada** for definido como *Sim* na página **Parâmetros da interface de equipamento de manuseio de materiais**, a mensagem será rejeitada. Uma mensagem de erro informará que a mensagem já existe.

Além dos campos de dados de entrada, o sistema atribui uma ID de fila exclusiva ao evento.

### <a name="inbound-event-types"></a>Tipos de evento de entrada

Esta seção descreve os tipos de evento de entrada (tipos de transação) que são compatíveis e os dados que devem ser fornecidos para processar os eventos.

#### <a name="work-confirm-events"></a>Eventos work-confirm

Eventos work-confirm exigem que os campos de dados de entrada incluam as seguintes informações:

- **data01** – A ID do par de linhas de trabalho.
- **data02** – A ID do registro da linha do trabalho (valor `RecId`).

    > [!NOTE]
    > *Ou* campo **data01** *ou* o campo **data02** deve estar presente.

- **data03** – A ID da placa de licença para escolher.
- **data04** – A ID da placa de licença de destino do cabeçalho do trabalho.

Se a ID do par de linhas de trabalho for fornecida, todas as linhas de trabalho de separação, colocação ou personalizadas marcadas pela ID do par de linhas de trabalho com status *Aberto* ou *Em processo* serão executadas sequencialmente. Se a ID do registro da linha de trabalho (valor `RecId`) for fornecida, a linha de trabalho deve ser uma linha de trabalho de separação, colocação ou personalizada com status *Aberto* ou *Em processo*.

As linhas de separação das localizações controladas por placa de licença exigem que o **data03** especifique a placa de licença da qual escolher, independentemente das linhas estarem marcadas pela ID do registro da linha de trabalho ou ID do par de linhas de trabalho. O campo **data04** deve especificar a placa de licença de destino do cabeçalho do trabalho para a escolha.

As linhas de colocação não aceitam mais informações. Eles são executados com base apenas na localização da linha de trabalho atual e na placa de licença de destino do trabalho. Se a colocação deve ser feita em um local diferente, altere a localização da linha de trabalho conforme descrito na seção [Eventos de substituição](#override-events) posteriormente neste tópico.

As linhas de trabalho personalizadas não exigem, ou oferecem suporte, a informações adicionais no evento de entrada.

#### <a name="short-pick-events"></a>Eventos de separação insuficiente

Eventos de separação insuficiente exigem que os campos de dados de entrada incluam as seguintes informações:

- **data02** – A ID do registro do trabalho (valor `RecId`).
- **data03** – A ID da placa de licença para escolher.
- **data04** – A quantidade a ser separada.
- **data05** – O código de exceção de separação insuficiente.
- **data06** – A ID da placa de licença de destino do cabeçalho do trabalho.

> [!NOTE]
> O campo **data01** não é usado para eventos de separação insuficiente.

Este evento se assemelha ao evento de confirmação de trabalho, mas aplica-se somente às linhas de separação.

#### <a name="override-events"></a><a id="override-events"></a>Eventos de substituição

Eventos de substituição exigem que os campos de dados de entrada incluam as seguintes informações:

- **data01** – A ID do registro do trabalho (valor `RecId`).
- **data02** – A ID da nova localização.

A linha de trabalho deve ter um status *Aberto* ou *Em processo* e a nova localização deve existir.

#### <a name="license-plate-receipt-events"></a>Eventos de recebimento de placa de licença

Eventos de recebimento da placa de licença exigem que os campos de dados de entrada incluam as seguintes informações:

- **data01** – A ID da placa de licença de entrada a ser recebida.

O sistema executa uma operação de recebimento de placa de licença, com base na placa de licença que é transmitida como o valor do campo **data01**.

### <a name="monitor-the-inbound-queue"></a>Monitorar a fila de entrada

Para revisar a fila de entrada, acesse a **Interface de equipamento de manuseio de materiais \> Comum \> Fila de entrada**. A página **Fila de entrada** lista todos os itens da fila de entrada e o status. Selecione o item de fila para exibir os detalhes. Esses detalhes incluem o tipo de transação do item, a ID da mensagem e os valores de cada campo de dados (**data01** até **data10**).

Se um erro ou outro tipo de item de log ocorreu durante o processamento dos eventos de entrada, você pode verificar o log selecionando **Log de erros** no Painel de Ações.

### <a name="inbound-event-processing"></a>Processamento de evento de entrada

Os eventos de entrada são gravados primeiro no banco de dados e executados imediatamente (de forma síncrona). Se um erro ocorrer durante o processamento, o evento ainda será gravado na fila, mas o status será definido como *Com erro*. O serviço do MHAX retorna uma mensagem de erro para o sistema de MH e armazena o log de erros no registro de evento de entrada para investigação futura.

Eventos com status *Com erro* podem ser reprocessados posteriormente se a condição do erro for corrigida. Para reprocessá-los, siga uma das seguintes etapas:

- Acesse a **Interface de equipamento de manuseio de materiais \> Comum \> Fila de entrada**. Selecione a fila de entrada relevante e selecione **Reprocessar** no Painel de Ações.
- Acesse a **Interface de equipamento de manuseio de materiais \> Comum \> Reprocessar fila de entrada com erro**. Uma caixa de diálogo de trabalho em lotes padrão é exibida. Em seguida, você pode configurar um filtro de registros e agendar ou executar um trabalho em lotes para reprocessar a fila.

Todas as operações de trabalho (separações e colocações) são executadas usando o trabalhador selecionado no campo **ID de Usuário** na página **Parâmetros de interface de equipamento de manuseio de materiais**.

### <a name="clean-up-the-inbound-queue"></a>Limpar a fila de entrada

Subsequentemente, a fila de entrada começará a ficar cheia de itens de fila que já foram processados. Para remover esses itens, acesse a **Interface de equipamento de manuseio de materiais \> Tarefas periódicas \> Limpeza \> Limpeza da fila de entrada**.

## <a name="get-a-quick-overview-by-using-the-queue-manager"></a>Obtenha uma visão geral rápida usando o gerenciador de filas

Para obter uma visão geral rápida de toda atividade relacionada às filas de entrada e saída, acesse **Interface de equipamento de manuseio de materiais \> Espaços de trabalho \> Gerenciador de filas**. A página **Gerenciador de filas** fornece um conjunto de guias e blocos que você pode usar para monitorar e explorar suas filas. Também fornece links úteis para a maioria das outras páginas mencionadas neste tópico.

## <a name="connect-to-the-mhax-service"></a>Conectar ao serviço do MHAX

O MHAX é implementado como serviço personalizado. Portanto, é acessível via chamadas SOAP e REST. Veja os endereços dos pontos de extremidade SOAP e REST:

- **SOAP:** `https://base_environment_URL/soap/services/WMHEServices`
- **REST:** `https://base_environment_URL/api/services/WMHEServices/WMHEService`

## <a name="retrieve-messages-from-the-outbound-queue"></a>Recuperar mensagens da fila de saída

Para recuperar mensagens da fila de saída, use um dos seguintes métodos:

- Use `readOutboundSubscriptionQueue` para recuperar os eventos com base na ID da assinatura.
- Use `readOutboundWarehouseQueue` para recuperar os eventos com base no tipo de evento e na ID de depósito em várias assinaturas.
