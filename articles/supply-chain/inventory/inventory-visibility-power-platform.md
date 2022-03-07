---
title: Aplicativo Visibilidade de Estoque
description: Este tópico descreve como usar o aplicativo Visibilidade de Estoque.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a60fc00642a77d3dc595a6222727637f0d7cd588
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475051"
---
# <a name="use-the-inventory-visibility-app"></a>Usar o aplicativo Visibilidade de Estoque

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Este tópico descreve como usar o aplicativo Visibilidade de Estoque.

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

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Use a guia **Lançamento de reserva** para lançar uma solicitação de reserva. Para poder lançar uma solicitação de reserva, você deverá ativar o recurso *OnHandReservation*. Para obter mais informações sobre esse recurso, consulte [Reservas de Visibilidade de Estoque](inventory-visibility-reservations.md).

Para lançar uma solicitação de reserva, você deverá inserir um valor no corpo da solicitação. Use o padrão descrito em [Criar um evento de reserva](inventory-visibility-api.md#create-one-reservation-event). Em seguida, selecione **Lançar**. Para exibir os detalhes da resposta da solicitação, selecione **Mostrar detalhes**. Você também pode obter o valor `reservationId` dos detalhes da resposta.

## <a name="inventory-summary"></a><a name="inventory-summary"></a>Resumo de estoque

**Resumo de estoque** é uma exibição personalizada da entidade *Soma de Estoque Disponível*. Ela fornece um resumo de estoque para produtos juntamente com todas as dimensões. Os dados do resumo de estoque serão sincronizados periodicamente de Visibilidade de Estoque. Para que possa ver dados na guia **Resumo de estoque**, você deve ativar o recurso *OnHandMostSpecificBackgroundService* na guia **Gerenciamento de Recursos**.

Usando o **Filtro avançado** fornecido pelo Dataverse, será possível criar uma exibição pessoal que mostre as linhas importantes para você. As opções de filtro avançado permitem criar uma ampla variedade de exibições, das simples às complexas. Elas também permitem adicionar condições agrupadas e aninhadas aos filtros. Para saber mais sobre como usar o **Filtro avançado**, consulte [Editar ou criar exibições pessoais usando filtros de grade avançados](/powerapps/user/grid-filters-advanced).

A parte superior da exibição personalizada fornece três campos: **Dimensão padrão**, **Dimensão personalizada** e **Medida**. Você pode usar esses campos para controlar quais colunas são visíveis.

Você pode selecionar o cabeçalho da coluna para filtrar ou classificar o resultado atual.

A parte inferior da exibição personalizada mostra informações como "50 registros (29 selecionados)" ou "50 registros". Essas informações se referem aos registros carregados no momento do resultado de **Filtro avançado**. O texto "29 selecionados" se refere ao número de registros selecionados usando o filtro de cabeçalho de coluna para os registros carregados.

Na parte inferior da exibição, há um botão **Carregar mais** que pode ser usado para carregar mais registros do Dataverse. O número padrão de registros carregados é 50. Quando você selecionar **Carregar mais**, os próximos 1.000 registros disponíveis serão carregados na exibição. O número no botão **Carregar mais** indica os registros carregados no momento e o número total de registros para o resultado de **Filtro Avançado**.

![Resumo de Estoque](media/inventory-visibility-onhand-list.png "Resumo de Estoque")
