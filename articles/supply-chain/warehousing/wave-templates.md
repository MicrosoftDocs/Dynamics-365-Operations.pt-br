---
title: Modelos de ciclo
description: Este artigo descreve como configurar os critérios que determinam se os ciclos são processados de forma manual ou automática e se o trabalho será gerado para um depósito quando um ciclo for processado.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: e4a74b61ea32df432da118ac8af550a4ca4b0089
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851188"
---
# <a name="wave-templates"></a>Modelos de ciclo

[!include [banner](../includes/banner.md)]

Este artigo descreve como configurar os critérios que determinam se os ciclos são processados de forma manual ou automática e se o trabalho será gerado para um depósito quando um ciclo for processado. Você especifica os critérios configurando modelos e consultas do ciclo que correspondam a um ciclo com linhas liberadas em ordens de venda, ordens de produção e kanbans.

## <a name="settings-for-wave-templates"></a>Configurações para modelos do ciclo

Quando você configura um modelo do ciclo, especifica o seguinte:

- O **Local** e o **Depósito** para o qual o modelo criará trabalhos.
- A ordem em que os modelos serão avaliados. A sequência na qual os modelos serão correspondidos com linhas liberadas em ordens de venda, ordens de produção e kanbans. Quando uma linha é liberada, o sistema aplica o primeiro modelo do ciclo para o qual a linha atende os critérios. Quanto mais amplos forem os critérios, maior a probabilidade de que a linha atenda aos critérios e, portanto, você deve colocar os modelos com os critérios mais específicos na parte superior da lista. Use os botões **Mover para cima** e **Mover para baixo** no Painel de Ações para organizar os modelos na lista.
- As ações executadas por cada modelo. Os **Métodos** do ciclo executam as ações criadas pelo modelo, como a criação ou a distribuição de trabalho de cada tipo de modelo do ciclo.
- Os atributos do ciclo (filtros) que devem ser aplicados ao modelo do ciclo a ser usado.

> [!NOTE]
> Se necessário, um desenvolvedor poderá criar métodos adicionais. Você pode exibir a lista completa de métodos na página **Métodos de processo do ciclo**.

Algumas configurações representam decisões estratégicas para o processo do ciclo, da seguinte maneira:

- Se o modelo for usado para a remessa de itens para ordens de venda e ordens de transferência, ou usado para mover itens para produção para ordens de produção ou kanbans.
- Se um ciclo for processado de forma manual ou automática, da seguinte maneira:

  - **Processamento manual** – a linha é adicionada a um ciclo e o estoque é reservado, mas você deve selecionar **Processo** na lista **Todos os ciclos** para criar o trabalho de separação para a ordem.
  - **Processamento automático** – você pode automatizar o processamento do ciclo de forma total ou parcial. Se você automatizar o processamento do ciclo de forma total, será criado um ciclo com a linha da ordem de venda, ordem de produção ou kanban quando uma ordem de venda, ordem de produção ou kanban for criada. Os itens serão deduzidos do estoque disponível e o trabalho de separação será criado. Se automatizar o processamento do ciclo de forma parcial, você poderá especificar valores que dispararão o processamento do ciclo. Por exemplo, você pode especificar um peso máximo para remessas que dispararão o processamento do ciclo quando o peso total das linhas do ciclo atingir o valor.

- Se você atribuir remessas feitas a um ciclo aberto. Por exemplo, se você prometer aos clientes que uma ordem feita ao meio-dia será remetida em 24 horas, poderá configurar o modelo do ciclo para atribuir automaticamente linhas de ordem para um ciclo aberto até o meio-dia. Nessa hora, o ciclo será automaticamente processado.

Quando um ciclo é processada, o trabalho de separação criado se baseia no modelo de trabalho e na diretiva de localização especificada para o depósito. O modelo de trabalho especifica como o trabalho de separação é criado, e a diretiva de localização especifica as localizações de separação e de colocação.

## <a name="create-a-wave-template"></a>Criar um modelo do ciclo

Para configurar um modelo do ciclo, siga estas etapas:

1. Acesse **Gerenciamento de depósito** \> **Configuração** \> **Ondas** \> **Modelos de onda**.
1. Selecione **Novo** para criar um novo modelo do ciclo.
1. No campo **Tipo de modelo do ciclo**, selecione uma das seguintes opções:

    - *Remessa* – use o modelo do ciclo para itens de remessa para ordens de venda e ordens de transferência.
    - *Ordens de produção* – use o modelo do ciclo para mover itens para ordens de produção.
    - *Kanban* – use o modelo do ciclo para mover itens para ordens kanban.

1. Nos campos **Nome do modelo do ciclo** e **Descrição do modelo do ciclo**, insira um nome e uma descrição para o modelo do ciclo.

    > [!NOTE]
    > Se mais de um modelo for criado para um depósito, o número no campo **Sequência de modelo do ciclo** indicará a posição do modelo na sequência na qual os modelos serão aplicados quando os critérios do modelo forem atendidos. Você pode selecionar **Mover para cima** ou **Mover para baixo** para reorganizar a sequência de modelos.

1. Nos campos **Local** e **Depósito**, selecione o local e o depósito para os quais o modelo do ciclo criará ciclos do modelo e trabalho de separação.
1. Se quiser automatizar o processamento de ciclos, faça as seguintes configurações conforme necessário:

    - **Automatizar criação do ciclo** – defina como *Sim* para criar automaticamente um ciclo quando uma ordem de venda, uma ordem de produção ou um kanban forem liberados para o depósito.
    - **Atribuir a ciclos abertos** – defina como *Sim* para atribuir automaticamente linhas a um ciclo aberto quando as linhas forem liberadas. As linhas são atribuídas a ondas com base no filtro da consulta para o modelo de onda.
    - **Processar ciclo na liberação para depósito** – defina como *Sim* para processar automaticamente o ciclo e criar trabalho quando uma linha for liberada para o depósito.
    - **Processar ciclo automaticamente no limite** – defina como *Sim* para processar automaticamente o ciclo quando seus valores atingirem os limites de peso, de remessa e de linhas especificados no grupo de campos **Limites de ciclo**. Essa configuração só estará ativa se *Remessa* estiver selecionada no campo **Tipo de modelo de ciclo**.
    - **Automatizar liberação de ciclo** – defina como *Sim* para liberar automaticamente o ciclo. O trabalho de separação é criado e disponibilizado em dispositivos móveis.
    - **Automatizar liberação de trabalho de reabastecimento** – defina como *Sim* para criar o trabalho de reabastecimento baseado em demanda e liberá-lo automaticamente. Você deve adicionar o método de ciclo de reabastecimento ao modelo de ciclo e criar um modelo de reabastecimento do tipo *Demanda do ciclo*. Configure um modelo de reabastecimento na página **Modelos de reabastecimento**. Isso requer que você adicione o método reabastecer ao modelo de onda.
    - **Continuar processamento do ciclo quando a criação do trabalho falhar** – quando definido como *Sim*, o sistema usará um local em branco se não puder reservar estoque no local proposto pela diretiva de localização (por exemplo, porque o estoque não está mais disponível). Quando definido como *Não*, haverá falha no ciclo se o sistema não puder reservar o estoque.

1. Defina o grupo de campos **Limites de ciclo** conforme necessário:
    - **Limite de peso do ciclo** – insira o peso máximo que um ciclo pode conter.
    - **Limite de remessa** – insira o número máximo de remessas que podem ser incluídas em um ciclo.
    - **Limite de linha** – insira o número máximo de linhas que podem ser incluídas em um ciclo.

1. No grupo de campos **Valores padrão**, selecione os atributos de ciclo a serem usados como critérios adicionais para o modelo de ciclo. Os atributos de ciclo são úteis para a atribuição de critérios adicionais, como o nome de um cliente específico, a um modelo de ciclo. Você cria esses atributos na página **Atributos de ciclo**. 

1. Defina a **Política de notificação de ciclo** para a política que você deseja usar para gerar notificações relacionadas a ciclos que usam esse modelo. Para obter um exemplo de uma política de notificação de ciclos, consulte [Notificações de execução de ciclos](wave-execution-notifications.md).

1. Na Guia Rápida **Métodos**, o painel **Métodos selecionados** lista os métodos para o tipo de modelo de ciclo selecionado. Os métodos do ciclo executam as ações criadas pelo modelo, como a criação ou a distribuição de trabalho de cada tipo de modelo de ciclo. Essas ações também são conhecidas como etapas de ciclo. Os métodos de ciclo são predefinidos para cada tipo de modelo de ciclo. Não é possível remover os métodos de ciclo predefinidos, mas você pode reorganizar a ordem dos métodos e adicionar outros métodos. Por exemplo, se você estiver criando um modelo de ciclo para remessa, poderá adicionar métodos para reabastecimento e transporte em contêineres. O transporte em contêineres de ciclo pode ser adicionado a uma sequência de métodos de ciclo para definir o transporte em contêineres das linhas processadas em um modelo de ciclo. Para adicionar outro método, faça o seguinte:

    - Selecione um método no painel **Métodos restantes** e, em seguida, selecione a seta **Para a esquerda** para adicioná-lo ao painel **Métodos selecionados**.
    - Para alterar a sequência, selecione um método e selecione **Para cima** ou **Para baixo**.

    > [!NOTE]
    > Quando você adicionar um método, ele será automaticamente listado na localização apropriada na sequência de etapas.

1. Para configurar a consulta que fará a correspondência entre as linhas liberadas e um ciclo apropriado, selecione **Editar consulta** no Painel de Ações.
1. Para verificar se as configurações do modelo de ciclo são válidas, selecione **Validar modelo**.
