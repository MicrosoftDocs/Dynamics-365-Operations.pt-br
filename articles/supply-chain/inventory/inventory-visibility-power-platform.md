---
title: Aplicativo Visibilidade de Estoque
description: Este artigo descreve como usar o aplicativo Visibilidade de Estoque.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a360b8beaad2bf6916c22765131e37f90e40282b
ms.sourcegitcommit: f2175fe5e900d39f34167d671aab5074b09cc1b8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/17/2022
ms.locfileid: "9306163"
---
# <a name="use-the-inventory-visibility-app"></a>Usar o aplicativo Inventory Visibility

[!include [banner](../includes/banner.md)]


Este artigo descreve como usar o aplicativo Visibilidade de Estoque.

A Visibilidade de Estoque fornece um aplicativo baseado em modelo para visualização. O aplicativo contém três páginas: **Configuração**, **Visibilidade operacional** e **Resumo de estoque**. Ele tem os seguintes recursos:

- Ele fornece uma IU (interface do usuário) para configuração disponível e configuração de reserva flexível.
- Ele oferece suporte a consultas de estoque disponível em tempo real em várias combinações de dimensões.
- Ele fornece uma interface do usuário para o lançamento de solicitações de reserva.
- Ele fornece uma exibição personalizada do estoque disponível para produtos juntamente com todas as dimensões.

## <a name="prerequisites"></a>Pré-requisitos

Antes de começar, instale e configure o Suplemento Visibilidade de Estoque conforme descrito em [Instalar e configurar Visibilidade do Estoque](inventory-visibility-setup.md).

## <a name="open-the-inventory-visibility-app"></a>Abrir o aplicativo Visibilidade de Estoque

Para abrir o aplicativo Visibilidade de Estoque, entre no seu ambiente do Power Apps e abra **Visibilidade de Estoque**.

## <a name="configuration"></a><a name="configuration"></a>Configuração

A página **Configuração** do aplicativo Visibilidade de Estoque ajuda você a definir a configuração disponível e a configuração de reserva flexível. Após a instalação do suplemento, a configuração padrão incluirá uma configuração padrão para o Microsoft Dynamics 365 Supply Chain Management (a fonte de dados `fno`). Você pode analisar a configuração padrão. Assim, com base nos requisitos comerciais e nos requisitos de lançamento de estoque do sistema externo, você poderá modificar a configuração para padronizar a forma como as alterações de estoque podem ser lançadas, organizadas e consultadas em vários sistemas.

Para obter detalhes completos sobre como configurar a solução, consulte [Configurar Visibilidade de Estoque](inventory-visibility-configuration.md).

## <a name="operational-visibility"></a>Visibilidade operacional

A página **Visibilidade Operacional** fornece os resultados de uma consulta de estoque disponível em tempo real, com base em várias combinações de dimensão. Quando o recurso *OnHandReservation* estiver ativado, você também poderá lançar solicitações de reserva na página **Visibilidade Operacional**.

### <a name="on-hand-query"></a>Consulta de disponíveis

A guia **Consulta de Disponíveis** mostra os resultados de uma consulta de estoque disponível em tempo real.

Quando você seleciona a guia **Consulta de Disponíveis**, o sistema solicita suas credenciais para obter o token de portador necessário para consultar o serviço Visibilidade de Estoque. Você pode simplesmente colar o token de portador no campo **BearerToken** e fechar a caixa de diálogo. Em seguida, você pode lançar uma solicitação de consulta de disponíveis.

Se o token de portador não for válido ou se tiver expirado, você deverá colar um novo no campo **BearerToken**. Insira os valores corretos de **ID do Cliente**, **ID do Locatário**, **Segredo do Cliente** e selecione **Atualizar**. O sistema receberá automaticamente um novo token de portador válido.

Para lançar uma consulta disponível, insira a consulta no corpo da solicitação. Use o padrão descrito em [Consultar usando o método post](inventory-visibility-api.md#query-with-post-method).

![Configurações de consulta de disponíveis](media/inventory-visibility-query-settings.png "Configurações de consulta de disponíveis")

### <a name="reservation-posting"></a>Lançamento de reserva

Use a guia **Lançamento de reserva** para lançar uma solicitação de reserva. Para poder lançar uma solicitação de reserva, você deverá ativar o recurso *OnHandReservation*. Para obter mais informações sobre esse recurso, consulte [Reservas de Visibilidade de Estoque](inventory-visibility-reservations.md).

Para lançar uma solicitação de reserva, você deverá inserir um valor no corpo da solicitação. Use o padrão descrito em [Criar um evento de reserva](inventory-visibility-api.md#create-one-reservation-event). Em seguida, selecione **Lançar**. Para exibir os detalhes da resposta da solicitação, selecione **Mostrar detalhes**. Você também pode obter o valor `reservationId` dos detalhes da resposta.

## <a name="inventory-summary"></a><a name="inventory-summary"></a>Resumo de estoque

A página **Resumo de estoque** fornece um resumo de estoque para produtos junto com todas as dimensões. Esta é uma exibição personalizada da entidade *Soma de Estoque Disponível*. Os dados do resumo de estoque são sincronizados periodicamente de Visibilidade de Estoque.

### <a name="enable-the-inventory-summary-and-set-the-synchronization-frequency"></a>Habilitar o resumo de estoque e definir a frequência de sincronização

Para habilitar a página **Resumo de estoque** e definir a frequência de sincronização, siga estas etapas:

1. Abra a página **Configuração**.
1. Abra a guia **Configurações e Gerenciamento de Recursos**.
1. Defina a chave de alternância para o recurso **OnHandMostSpecificBackgroundService** como *Sim*.
1. Quando o recurso for habilitado, a seção **Configuração do Serviço** será disponibilizada e incluirá uma linha para configurar o recurso **OnHandMostSpecificBackgroundService**. Essa configuração permite que você escolha a frequência em que dados de resumo de estoque são sincronizados. Use os botões **Para cima** e **Para baixo** na coluna **Valor** para alterar o tempo entre sincronizações (que pode ser de no mínimo 5 minutos). Selecione **Salvar**.
1. Selecione **Atualizar configuração** para salvar todas as alterações.

![Configuração de OnHandMostSpecificBackgroundService](media/inventory-visibility-ohms-freq.PNG "Configuração de OnHandMostSpecificBackgroundService")

> [!NOTE]
> O recurso *OnHandMostSpecificBackgroundService* rastreia apenas as alterações disponíveis no produto que ocorreram depois que você ativou o recurso. Os dados de produtos que não foram alterados desde que você ativou o recurso não serão sincronizados do cache do serviço de estoque para o ambiente do Dataverse. Se sua página **Resumo de estoque** não mostrar todas as informações disponíveis que você espera, vá para **Gerenciamento de Estoque > Tarefas periódicas > Integração da Visibilidade de Estoque**, desative o trabalho em lote e reative-o. Isso fará o push inicial e todos os dados serão sincronizados com a entidade *Soma Disponível de Estoque* nos próximos 15 minutos. Se você quiser usar esse recurso, recomendamos que você o ative antes de criar qualquer alteração disponível e ative o trabalho em lote **Integração da Visibilidade de Estoque**.

### <a name="work-with-the-inventory-summary"></a>Trabalhar com o resumo de estoque

Usando o **Filtro avançado** fornecido pelo Dataverse, será possível criar uma exibição pessoal que mostre as linhas importantes para você. As opções de filtro avançado permitem criar uma ampla variedade de exibições, das simples às complexas. Elas também permitem adicionar condições agrupadas e aninhadas aos filtros. Para saber mais sobre como usar o **Filtro avançado**, consulte [Editar ou criar exibições pessoais usando filtros de grade avançados](/powerapps/user/grid-filters-advanced).

A parte superior da exibição personalizada fornece três campos: **Dimensão padrão**, **Dimensão personalizada** e **Medida**. Você pode usar esses campos para controlar quais colunas são visíveis.

Você pode selecionar o cabeçalho da coluna para filtrar ou classificar o resultado atual.

A parte inferior da exibição personalizada mostra informações como "50 registros (29 selecionados)" ou "50 registros". Essas informações se referem aos registros carregados no momento do resultado de **Filtro avançado**. O texto "29 selecionados" se refere ao número de registros selecionados usando o filtro de cabeçalho de coluna para os registros carregados.

Na parte inferior da exibição, há um botão **Carregar mais** que pode ser usado para carregar mais registros do Dataverse. O número padrão de registros carregados é 50. Quando você selecionar **Carregar mais**, os próximos 1.000 registros disponíveis serão carregados na exibição. O número no botão **Carregar mais** indica os registros carregados no momento e o número total de registros para o resultado de **Filtro Avançado**.

![Resumo de Estoque](media/inventory-visibility-onhand-list.png "Resumo de Estoque")
