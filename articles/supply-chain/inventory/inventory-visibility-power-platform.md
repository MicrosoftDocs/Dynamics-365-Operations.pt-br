---
title: Aplicativo Visibilidade de Estoque
description: Este artigo descreve como usar o aplicativo Visibilidade de Estoque.
author: yufeihuang
ms.date: 09/15/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 9886ddbf0b072283cffd73d4bfdc20835ccb3b7c
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762691"
---
# <a name="use-the-inventory-visibility-app"></a>Usar o aplicativo Inventory Visibility

[!include [banner](../includes/banner.md)]

Este artigo descreve como usar o aplicativo Visibilidade de Estoque.

A Visibilidade de Estoque fornece um aplicativo baseado em modelo para visualização. O aplicativo contém três páginas: **Configuração**, **Visibilidade operacional** e **Resumo de estoque**. Ele tem os seguintes recursos:

- Ele fornece uma IU (interface do usuário) para configuração disponível e configuração de reserva flexível.
- Ele oferece suporte a consultas de estoque disponível em tempo real em várias combinações de dimensões.
- Ele fornece uma interface do usuário para o lançamento de solicitações de reserva.
- Ele fornece uma exibição do estoque disponível para os produtos juntamente com todas as dimensões.
- Ele fornece a exibição de uma lista de estoque disponível para produtos juntamente com as dimensões predefinidas. A exibição de lista disponível pode ser um resumo completo ou um resultado pré-carregado de uma consulta disponível.

## <a name="prerequisites"></a>Pré-requisitos

Antes de começar, instale e configure o Suplemento Visibilidade de Estoque conforme descrito em [Instalar e configurar Visibilidade do Estoque](inventory-visibility-setup.md).

## <a name="open-and-authenticate-the-inventory-visibility-app"></a><a name="open-authenticate"></a>Abrir e autenticar o aplicativo Visibilidade de estoque

Para abrir e autenticar o aplicativo Visibilidade de estoque, siga estas etapas.

1. Entre em seu ambiente do Power Apps.
1. Abrir o aplicativo **Visibilidade de Estoque**.
1. Abra a página **Visibilidade operacional** no painel esquerdo.
1. Selecione o botão **Configurações** (símbolo de engrenagem) próximo à parte superior da página.
1. Na caixa de diálogo **Configurações**, insira os valores **Id do cliente**, **Id do locatário** e **Segredo do cliente** que você anotou quando [instalou e configurou o Visibilidade de estoque](inventory-visibility-setup.md).
1. Selecione o botão **Atualizar** ao lado desse campo **Token de portador**. O sistema gera um novo token de portador, com base nas informações que você inseriu.

    ![Configurações de consulta de disponíveis.](media/inventory-visibility-query-settings.png "Configurações de consulta de disponíveis")

1. Ao receber um token de portador válido, feche a caixa de diálogo. O token do portador expirará após algum tempo. Portanto, você deve atualizá-lo ocasionalmente quando precisar atualizar a configuração, postar dados ou consultar dados.

## <a name="configure-the-inventory-visibility-app"></a><a name="configuration"></a>Configurar o aplicativo Visibilidade de Estoque

A página **Configuração** do aplicativo Visibilidade de estoque ajuda você a definir a configuração geral de gerenciamento de dados e a configuração de recursos. Após a instalação do suplemento, a configuração padrão incluirá uma configuração padrão para o Microsoft Dynamics 365 Supply Chain Management (a fonte de dados `fno`). Você pode analisar a configuração padrão. Depois, com base nos requisitos comerciais e nos requisitos de lançamento de estoque do sistema externo, você poderá modificar a configuração para padronizar a forma como as alterações de estoque podem ser lançadas, organizadas e consultadas em vários sistemas.

Para obter detalhes completos sobre como configurar a solução, consulte [Configurar Visibilidade de Estoque](inventory-visibility-configuration.md).

## <a name="operational-visibility"></a>Visibilidade operacional

A página **Visibilidade Operacional** fornece os resultados de uma consulta de estoque disponível em tempo real, lançamento de reserva e alocação com base em várias combinações de dimensão. Quando o recurso *OnHandReservation* estiver [ativado](inventory-visibility-configuration.md), você também poderá lançar solicitações de reserva na página **Visibilidade Operacional**.

### <a name="on-hand-query"></a>Consulta de disponíveis

A guia **Consulta disponível** da página **Visibilidade operacional** permite consultar o inventário disponível em tempo real. Siga estas etapas para configurar e executar uma consulta.

1. Abrir o aplicativo **Visibilidade de Estoque**.
1. Abra a página **Visibilidade operacional** no painel esquerdo.
1. Na guia **Consulta disponível**, insira os valores de **ID da organização**, **ID do site** e **ID do local** que deseja consultar.
1. No campo **ID do produto**, insira um ou mais IDs de produto para obter uma correspondência exata para sua consulta. Se você deixar o campo **ID do produto** em branco, os resultados incluirão todos os produtos no site e local especificados.
1. Para obter um resultado mais granular (por exemplo, uma visualização por valores de dimensão, como cor e tamanho), selecione dimensões Agrupadas Por no campo **Agrupar resultado por**.
1. Para encontrar itens que tenham um valor de dimensão específico (como cor = vermelho), selecione a dimensão no campo **Dimensões do filtro** e insira um valor de dimensão.
1. Selecione **Consulta**. Você receberá uma mensagem de sucesso (verde) ou uma mensagem de falha (vermelha). Se a consulta falhar, verifique seus critérios de consulta e certifique-se de que seu [portador de token](#open-authenticate) não tenha expirado.

Outra maneira de fazer uma consulta sobre disponibilidade é fazer solicitações de API diretas. Você pode usar `/api/environment/{environmentId}/onhand/indexquery` ou `/api/environment/{environmentId}/onhand`. Para obter mais informações, consulte [APIs públicas de Visibilidade de Estoque](inventory-visibility-api.md).

### <a name="reservation-posting"></a>Lançamento de reserva

Use a guia **Lançamento de reserva** da página **Visibilidade Operacional** para lançar uma solicitação de reserva. Para poder lançar uma solicitação de reserva, você deverá ativar o recurso *OnHandReservation*. Para obter mais informações sobre esse recurso e como ativá-lo, consulte [Reservas de Visibilidade de Estoque](inventory-visibility-reservations.md).

> [!NOTE]
> A capacidade de fazer uma reserva flexível por meio da interface do usuário destina-se a permitir que você teste o recurso. Cada solicitação de reserva flexível deve ser associada a uma alteração de linha de ordem de transação (criação, modificação, exclusão e assim por diante). Portanto, recomendamos que você faça apenas reservas flexíveis vinculadas a um pedido de back-end. Para obter mais informações, consulte [Reservas de Visibilidade de Estoque](inventory-visibility-reservations.md).

Siga estas etapas para postar uma solicitação de reserva flexível usando a interface do usuário.

1. Abrir o aplicativo **Visibilidade de Estoque**.
1. Abra a página **Visibilidade operacional** no painel esquerdo.
1. Na guia **Lançamento de Reserva**, no campo **Quantidade**, especifique a quantidade da reserva flexível.
1. Desmarque a caixa de seleção **Habilitar estoque negativo para oferecer suporte a vendas excessivas** para evitar que o estoque seja vendido ou reservado em excesso.
1. No campo **Operator**, selecione a fonte de dados e a medida física que se aplicam à quantidade de reserva flexível.
1. Insira os valores de **ID da organização**, **ID do site**, **ID do local** e **ID do produto** que deseja consultar.
1. Para obter um resultado mais granular, selecione uma fonte de dados, dimensões e valores de dimensão.

Outra maneira de publicar uma reserva flexível é fazer solicitações de API diretas. Use o padrão descrito em [Criar um evento de reserva](inventory-visibility-api.md#create-one-reservation-event). Em seguida, selecione **Lançar**. Para exibir os detalhes da resposta da solicitação, selecione **Mostrar detalhes**. Você também pode obter o valor `reservationId` dos detalhes da resposta.

### <a name="allocation"></a>Alocação

Para obter informações sobre como gerenciar alocações da interface do usuário e APIs, consulte [Alocação de estoque do Visibilidade do estoque](inventory-visibility-allocation.md).

## <a name="inventory-summary"></a><a name="inventory-summary"></a>Resumo de estoque

A página **Resumo de estoque** fornece um resumo de estoque para produtos junto com todas as dimensões. Esta é uma exibição personalizada da entidade *Soma de Estoque Disponível*. Os dados do resumo de estoque são sincronizados periodicamente de Visibilidade de Estoque.

Para habilitar a página **Resumo de estoque** e definir a frequência de sincronização, siga estas etapas:

1. Abra a página **Configuração**.
1. Abra a guia **Configurações e Gerenciamento de Recursos**.
1. Defina a chave de alternância para o recurso **OnHandMostSpecificBackgroundService** como *Sim*.
1. Quando o recurso for habilitado, a seção **Configuração do Serviço** será disponibilizada e incluirá uma linha para configurar o recurso **OnHandMostSpecificBackgroundService**. Essa configuração permite que você escolha a frequência em que dados de resumo de estoque são sincronizados. Use os botões **Para cima** e **Para baixo** na coluna **Valor** para alterar o tempo entre sincronizações (que pode ser de no mínimo 5 minutos). Selecione **Salvar**.

    ![A Configuração de OnHandMostSpecificBackgroundService](media/inventory-visibility-ohms-freq.png "A Configuração de OnHandMostSpecificBackgroundService")

1. Selecione **Atualizar configuração** para salvar todas as alterações.

> [!NOTE]
> O recurso *OnHandMostSpecificBackgroundService* rastreia somente as alterações do estoque disponível que ocorreram depois que você ativou o recurso. Os dados de produtos que não foram alterados desde que você ativou o recurso não serão sincronizados do cache do serviço de estoque para o ambiente do Dataverse. Se a sua página **Resumo de estoque** não mostrar todas as informações disponíveis que você espera, abra o Supply Chain Management, acesse **Gerenciamento de Estoque > Tarefas periódicas > Integração da Visibilidade de Estoque**, desabilite o trabalho em lote e habilite-o novamente. Isso fará o push inicial e todos os dados serão sincronizados com a entidade *Soma Disponível de Estoque* nos próximos 15 minutos. Se você quiser usar o recurso *OnHandMostSpecificBackgroundService*, recomendamos que você o ative antes de criar qualquer alteração disponível e ative o habilite o trabalho em lotes **Integração da Visibilidade de Estoque**.

## <a name="preload-a-streamlined-on-hand-query"></a><a name="preload-streamlined-onhand-query"></a>Pré-carregar uma consulta de disponibilidade simplificada

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: Preview until further notice -->

O Supply Chain Management armazena um grande volume de informações sobre o estoque disponível atual e as disponibiliza para uma ampla variedade de finalidades. No entanto, muitas operações diárias e integrações de terceiros requerem apenas um pequeno subconjunto desses detalhes e consultar o sistema para todos eles pode resultar em grandes conjuntos de dados que demoram para montar e a transferir. Portanto, o serviço de Visibilidade de Estoque pode buscar e armazenar periodicamente um conjunto simplificado de dados de estoque disponível para tornar as informações otimizadas disponíveis continuamente. Os detalhes de estoque disponível armazenados são filtrados com base nos critérios comerciais configuráveis para garantir que somente as informações mais relevantes sejam incluídas. Como as listas de estoque disponível filtradas são armazenadas localmente no serviço de Visibilidade de Estoque e são atualizadas regularmente, elas oferecem suporte ao acesso rápido, exportações de dados sob demanda e integração simplificada com sistemas externos.

A página **Pré-carregar Resumo da Visibilidade de Estoque** fornece uma exibição da entidade *Resultados Pré-carregados da Consulta de Índice Disponível*. Diferentemente da entidade *Resumo de estoque*, a entidade *Resultados Pré-carregados da Consulta de Índice Disponível* oferece uma lista de estoque disponível para os produtos juntamente com as dimensões selecionadas. A Visibilidade de Estoque sincroniza os dados de resumo pré-carregados a cada 15 minutos.

Para exibir dados na guia **Pré-carregar o Resumo da Visibilidade de Estoque**, você deve ativar o recurso *OnHandIndexQueryPreloadBackgroundService* na guia **Gerenciamento de Recursos** da página **Configuração** e, em seguida, selecionar **Atualizar configuração** (consulte também [Configurar a Visibilidade de Estoque](inventory-visibility-configuration.md)).

> [!NOTE]
> Como no recurso *OnhandMostSpecificBackgroudService*, o recurso *OnHandIndexQueryPreloadBackgroundService* rastreia somente as alterações de estoque disponível que ocorreram após a ativação do recurso. Os dados de produtos que não foram alterados desde que você ativou o recurso não serão sincronizados do cache do serviço de estoque para o ambiente do Dataverse. Se sua página **Resumo de estoque** não mostrar todas as informações disponíveis que você espera, vá para **Gerenciamento de Estoque > Tarefas periódicas > Integração da Visibilidade de Estoque**, desative o trabalho em lote e reative-o. Isso fará o push inicial e todos os dados serão sincronizados com a entidade *Resultados Pré-carregados da Consulta de Índice Disponível* nos próximos 15 minutos. Se você quiser usar esse recurso, recomendamos que você o ative antes de criar qualquer alteração disponível e ative o trabalho em lote **Integração da Visibilidade de Estoque**.

## <a name="filter-and-browse-the-inventory-summaries"></a><a name="additional-tip-for-viewing-data"></a>Filtrar e procurar os resumos de estoque

Usando o **Filtro avançado** fornecido pelo Dataverse, será possível criar uma exibição pessoal que mostre as linhas importantes para você. As opções de filtro avançado permitem criar uma ampla variedade de exibições, das simples às complexas. Elas também permitem adicionar condições agrupadas e aninhadas aos filtros. Para saber mais sobre como usar o filtro avançado, consulte [Editar ou criar exibições pessoais usando filtros de grade avançados](/powerapps/user/grid-filters-advanced).

A página **Resumo de estoque** fornece três campos acima da grade (**Dimensão padrão**, **Dimensão personalizada** e **Medida**) que podem ser usados para controlar quais colunas ficam visíveis. Você também pode selecionar qualquer cabeçalho de coluna para filtrar ou classificar o resultado atual por essa coluna. A captura de tela a seguir destaca os campos de dimensão, filtragem, contagem de resultados e "carregar mais" disponíveis na página **Resumo de estoque**.

![A página Resumo de estoque.](media/inventory-visibility-onhand-list.png "A página Resumo de estoque")

Como você terá predefinido as dimensões usadas para carregar os dados do resumo, a página **Pré-carregar Resumo do Visibilidade de Estoque** exibirá as colunas relacionadas à dimensão. *As dimensões não são personalizáveis &mdash; o sistema oferece suporte somente às dimensões de site e de local para listas disponíveis pré-carregadas.* A página **Pré-carregar o Resumo da Visibilidade do Estoque** fornece filtros semelhantes aos da página **Resumo de estoque**, com a exceção de que as dimensões já estão selecionadas. A captura de tela a seguir destaca os campos de filtragem disponíveis na página **Pré-carregar Resumo da Visibilidade de Estoque**.

![A página de resumo Pré-carregar Visibilidade de Estoque.](media/inventory-visibility-preload-onhand-list.png "A página de resumo Pré-carregar Visibilidade de Estoque")

Na parte inferior das páginas **Pré-carregar Resumo da Visibilidade de Estoque** e **Resumo de estoque**, você encontrará informações como "50 registros (29 selecionados)" ou "50 registros". Essas informações se referem aos registros carregados no momento do resultado de **Filtro avançado**. O texto "29 selecionados" se refere ao número de registros selecionados usando o filtro de cabeçalho de coluna para os registros carregados. Há também um botão **Carregar mais** que pode ser usado para carregar mais registros do Dataverse. O número padrão de registros carregados é 50. Ao selecionar **Carregar mais**, os próximos 1.000 registros disponíveis serão carregados na exibição. O número no botão **Carregar mais** indica os registros carregados no momento e o número total de registros para o resultado de **Filtro Avançado**.
