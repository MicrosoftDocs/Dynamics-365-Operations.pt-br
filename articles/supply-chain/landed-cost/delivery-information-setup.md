---
title: Configuração de informações de entrega
description: Este tópico descreve como configurar informações de entrega para o módulo de Custo de entrega.
author: sherry-zheng
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMPortTable, ITMLeadTimeTable, ITMLegTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 4cb1207916c40a18cf5b295baa913ae2d7198a05
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841881"
---
# <a name="delivery-information-setup"></a>Configuração de informações de entrega

[!include [banner](../../includes/banner.md)]

Este tópico descreve como configurar informações de entrega para o módulo de **Custo de entrega**.

## <a name="shipping-ports"></a>Portas de remessa

As portas de remessa identificam a origem e o destino de mercadorias. Para cada viagem, são definidas uma porta "para" e outra "de", com base na jornada selecionada para a embarcação de viagem. As portas de remessa são usadas para criar os trechos de uma jornada e também as atividades da viagem. Normalmente, elas são definidas usando o nome da cidade e o país ou a região em que a porta de remessa física está localizada.

Para trabalhar com portas de remessa, acesse **Custo de entrega \> Configuração de informações de entrega \> Portas de remessa**. Lá você pode exibir, adicionar e remover registros das portas de remessa. A tabela a seguir descreve os campos disponíveis para cada registro.

| Campo | Descrição |
|---|---|
| Porta de remessa | Insira um nome/número de identificação exclusivo para a porta de remessa. |
| descrição | Insira uma descrição da porta de remessa. |

## <a name="tracking-control-center"></a><a name="tracking-control-center"></a>Centro de controle de acompanhamento

Use o centro de controle de acompanhamento para configurar os prazos de entrega, as atualizações de status e o fluxo das informações associadas a uma viagem, já que os contêineres de remessa são movidos de um trecho para o seguinte. Quando você cria um registro de controle de acompanhamento, ele é associado a um trecho específico de uma jornada para uma viagem. Quando uma viagem atualizar um trecho, o registro associado será atualizado e preenchido conforme definido. Você pode atualizar as informações de acompanhamento de viagens individuais na página **Todas as viagens**.

Para abrir o centro de controle de acompanhamento, acesse **Custo de entrega \> Configuração de informações de entrega \> Centro de controle de acompanhamento**.

O centro de controle de acompanhamento mostra uma das três exibições de página, dependendo do valor selecionado no campo **Tipo de criação** no painel de lista: *Em branco*, *Prazo de entrega* ou *Atualização de status*. Cada tipo de criação atualiza um conjunto de informações diferente associado ao progresso de uma viagem do ponto de origem ao destino final.

### <a name="common-rule-settings"></a>Configurações de regra comuns

A tabela a seguir mostra os campos disponíveis para todos os três tipos de criação no centro de controle de acompanhamento.

| Campo | Descrição |
|---|---|
| Tabela de origem, campo de origem | Esses campos identificam uma tabela e um campo de origem no banco de dados. A regra carregará o valor no campo e, depois, o usará da forma definida por outras configurações da regra. |
| Tabela de destino, campo de destino | Esses campos identificam uma tabela e um campo de destino no banco de dados. A regra carregará o valor no campo e, depois, o usará (ou substituirá) da forma definida por outras configurações da regra. |
| Atividade | Este campo identifica o tipo de atividade que deve ser aplicada a um contêiner de remessa correspondido por uma regra. |
| Critérios de correspondência | Este campo determina como o sistema identifica uma correspondência para uma regra. Em cada instância, o sistema revisa os dados nas tabelas de origem e de destino para determinar se um campo deve ser atualizado na tabela de destino.<p>Por exemplo, a tabela de origem é *Viagens* e a tabela de destino é *Cabeçalho de compra* ou *Linhas de compra*. A tabela *Viagens* tem um valor **Porta de origem** de *Hong Kong* e a tabela *Cabeçalho de compra* tem um valor **Porta de origem** de *Shanghai*. Uma regra é criada com *Hong Kong* como a porta "de". Nesse caso, os valores do campo **Critérios de correspondência** funcionarão da seguinte maneira:</p><ul><li>**Ambos** – o campo de destino não será atualizado, pois uma das duas portas não corresponde.</li><li>**Origem** – o campo de destino será atualizado, pois a porta "de" da tabela de origem é *Hong Kong*.</li><li>**Destino** – o campo de destino não será atualizado porque a porta "de" da tabela de destino está em *Xangai* (e não *Hong Kong*).</li></ul> |
| Copiar ação | Os valores disponíveis são *Copiar* e *Padrão*. Selecione *Copiar* para copiar o valor do campo de origem no campo de destino. Selecione *Padrão* para definir um valor estático para o campo de destino. |
| Padrão | Quando o campo **Copiar ação** está definido como *Padrão*; o campo **Padrão** define o valor padrão do campo de destino. Por exemplo, se a ação estiver relacionada a uma atualização de porta e o campo **Copiar ação** estiver definido como *Padrão*, o campo **Padrão** identificará uma porta. |
| Itinerário | Este campo identifica o trecho da jornada para o qual a ação especificada ocorre, como carregamento ou alfândega. |
| Provedor de serviços | Se um provedor de serviços específico for usado para a atualização do status atual/trecho da jornada, este campo identificará o provedor de serviços. Os provedores de serviço são definidos na conta do fornecedor. |

### <a name="lead-time-rules"></a>Regras de prazo de entrega

O prazo de entrega é o tempo previsto que uma viagem exigirá para concluir um trecho definido de uma jornada para uma viagem. O prazo de entrega de cada trecho de uma jornada é usado para calcular a data de entrega estimada da viagem. Essa data é, então, inserida no campo **Data de entrega confirmada** em cada linha de compra da viagem.

As regras de prazo de entrega são usadas para gerenciar atualizações de datas. As atividades são geradas automaticamente quando um modelo de jornada é usado para uma viagem.

Para adicionar uma regra de prazo de entrega ao centro de controle de acompanhamento, siga estas etapas.

1. Siga uma destas etapas:

    - Acesse **Custo de entrega \> Configuração de percurso de vários trechos \> Trechos**. Selecione o trecho para o qual você deseja configurar prazos de entrega e, no Painel de Ações, selecione **Centro de controle de acompanhamento**. O centro de controle de acompanhamento é pré-carregado com informações sobre o trecho selecionado.
    - Acesse **Custo de entrega \> Configuração de informações de entrega \> Centro de controle de acompanhamento**. Você deve selecionar manualmente um trecho na etapa 4 deste procedimento.

1. No painel de lista, defina o campo **Tipo de criação** como *Prazo de entrega*.
1. No Painel de Ações, selecione **Novo**.
1. Se você iniciou a partir do centro de controle de acompanhamento na etapa 1, defina o campo **Trecho** como o trecho para o qual deseja criar uma regra de prazo de entrega. Se você iniciou na página **Trechos**, o campo **Trecho** será predefinido com o trecho selecionado antes da abertura do centro de controle de acompanhamento.

    Com base no valor do campo **Trecho**, vários campos são definidos automaticamente, conforme mostrado aqui:

    - **Tabela de origem:** *Atividades de contêiner*
    - **Campo de origem:** *Data de início*
    - **Tabela de destino:** *Atividades de contêiner*
    - **Campo de destino:** *Data de término prevista*

1. No campo **Atividade**, selecione a atividade à qual a regra atual deve ser aplicada.
1. No campo **Prazo de entrega**, insira o prazo de entrega (em dias) que deve ser aplicado quando a regra atual é disparada.

### <a name="status-update-rules"></a>Regras de atualização do status

Os registros em que o campo **Tipo de criação** está definido como *Atualização do status* atualizarão o status de linhas da ordem de compra, ou o status em nível de viagem, contêiner de remessa ou portfólio. Os status podem ser definidos independentemente. Use-os para informar o usuário ou o departamento sobre o estágio de uma viagem (como documentos recebidos ou mercadorias em trânsito).

Quando o campo **Tipo de criação** é definido como *Atualização de status*, o centro de controle de acompanhamento inclui uma FastTab **Linhas**, em que você pode definir uma área de custo e o status atualizado da viagem. Por exemplo, você tem uma linha em que o campo **Área de custo** está definido como *Contêiner* e o campo **Status da viagem** é definido como *Mercadorias em trânsito*. Nesse caso, quando uma ordem concluir o trecho especificado, o campo **Status da viagem** do contêiner de remessa será atualizado para *Mercadorias em trânsito*.

As atualizações de status fornecem o status de uma viagem durante as linhas de viagem e linhas de ordem de compra associadas a essa viagem. No percurso da viagem desde o porto, navegação e alfândega rumo ao depósito de destino, o campo **Status da viagem** do registro da viagem fornece uma exibição rápida da fase em que os itens estão.

Para adicionar uma regra de atualização de status ao centro de controle de acompanhamento, siga estas etapas.

1. Siga uma destas etapas:

    - Acesse **Custo de entrega \> Configuração de percurso de vários trechos \> Trechos**. Selecione o trecho para o qual você deseja configurar uma atualização de status e, no Painel de Ações, selecione **Centro de controle de acompanhamento**. O centro de controle de acompanhamento é pré-carregado com informações sobre o trecho selecionado.
    - Acesse **Custo de entrega \> Configuração de informações de entrega \> Centro de controle de acompanhamento**. Você deve selecionar manualmente um trecho na etapa 4 deste procedimento.

1. No painel de lista, defina o campo **Tipo de criação** como *Atualização de status*.
1. No Painel de Ações, selecione **Novo**.
1. Se você iniciou a partir do centro de controle de acompanhamento na etapa 1, defina o campo **Trecho** como o trecho para o qual deseja criar uma regra de atualização de status. Se você iniciou na página **Trechos**, o campo **Trecho** será predefinido com o trecho selecionado antes da abertura do centro de controle de acompanhamento.

    Com base no valor do campo **Trecho**, vários campos são definidos automaticamente, conforme mostrado aqui:

    - **Tabela de origem:** *Atividades de contêiner*
    - **Campo de origem:** *Data de término real*
    - **Tabela de destino:** este campo é deixado em branco.
    - **Campo de destino:** este campo é deixado em branco.

1. No campo **Atividade**, selecione a atividade à qual a regra deve ser aplicada.
1. Na FastTab **Linhas**, insira as atualizações de status para cada área de custo.

### <a name="blank-type-rules"></a>Regras de tipo em branco

Você usa registros com um valor **Tipo de criação** de *Em branco* para substituir ou inserir um valor de campo, com base nos dados de outro campo. Um campo do Custo de entrega substituirá dados em outras áreas do Microsoft Dynamics 365 Supply Chain Management, com base em regras configuradas no centro de controle de acompanhamento.

1. Acesse **Custo de entrega \> Configuração de informações de entrega \> Centro de controle de acompanhamento**.
1. No painel de lista, defina o campo **Tipo de criação** como *Em branco*.
1. No Painel de Ações, selecione **Novo**.
1. Defina os valores de origem e de destino, critérios de correspondência, ação de cópia e outros parâmetros relevantes, conforme necessário para a regra.

### <a name="required-tracking-control-setup"></a>Configuração do controle de acompanhamento necessário

Para cada modelo de percurso, dois registros devem ser configurados no centro de controle de acompanhamento. Esses registros têm um valor **Tipo de criação** de *Em branco* e são usados em todas as implementações de Custo de entrega. Elas ajudam a garantir que a data de compra confirmada e as datas esperadas de mercadorias em trânsito sejam atualizadas para viagens e linhas de ordem de compra relacionadas na forma esperada.

O primeiro registro é necessário para atualizar linhas de compra. Ele deve ter as seguintes configurações:

- **Tabela de origem:** *Atividades de contêiner*
- **Campo de origem:** *Data de término prevista*
- **Tabela de destino:** *Linhas de compra*
- **Campo de destino:** *Data de entrega ou confirmada*

O segundo registro é necessário para atualizar mercadorias em transações em trânsito. Ele deve ter as seguintes configurações:

- **Tabela de origem:** *Atividades de contêiner*
- **Campo de origem:** *Data de término prevista*
- **Tabela de destino:** *Ordem de mercadorias em trânsito*
- **Campo de destino:** *Data esperada*
