---
title: Sincronizar classificações de produto no Dynamics 365 Commerce
description: Este tópico descreve como sincronizar classificações do produto no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f2112c87912a1d130017c5804c4193b62c1e5a476be79bfd485640ec98b42f77
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730890"
---
# <a name="sync-product-ratings-in-dynamics-365-commerce"></a>Sincronizar classificações de produto no Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Este tópico descreve como sincronizar classificações do produto no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

Para consumir classificações de produtos em omnicanais, como no ponto de venda (PDV) e em call centers, as classificações de produtos do serviço de classificações e opiniões devem ser importadas para o banco de dados do canal do Commerce. Quando as classificações de produtos são disponibilizadas nos omnicanais, elas podem ajudar os clientes indiretamente durante suas interações com os representantes de vendas.

Este tópico descreve as seguintes tarefas:

1. Configurar **Tarefa de sincronização de classificações de produtos** como um trabalho em lotes para sincronizar classificações de produtos do **Serviço de classificações e opiniões**.
1. Verifique se o trabalho em lotes para sincronização da classificação do produto foi bem-sucedido.
1. Disponibilizar classificações do produto no PDV.

## <a name="configure-a-batch-job-to-synchronize-product-ratings"></a>Configure um trabalho em lotes para sincronizar classificações de produtos

> [!IMPORTANT]
> Antes de começar, verifique se a versão 10.0.6 ou posterior do Dynamics 365 Commerce está instalada.

### <a name="initialize-the-commerce-scheduler"></a>Inicializar o agendador do Commerce

Para inicializar o agendador do Commerce, siga estas etapas.

1. Acesse **Retail e Commerce \> Configuração do Headquarters \> Agendador do Commerce \> Inicializar agendador do Commerce** Como alternativa, procure "Inicializar agendador do Commerce".
1. Na caixa de diálogo **Inicializar agendador do Commerce**, certifique-se de que a opção **Excluir configuração existente** esteja definida como **Não** e, em seguida, selecione **OK**.

### <a name="verify-the-retailproductrating-subjob"></a>Verifique o subtrabalho RetailProductRating

Para verificar se o subtrabalho **RetailProductRating** existe, siga estas etapas.

1. Acesse **Retail e Commerce \> Configuração do Headquarters \> Agendador do Commerce \> Subtrabalhos do agendador**. Como alternativa, procure por "Subtrabalhos do agendador".
1. Na lista de subtrabalhos, localize ou procure o subtrabalho **RetailProductRating** .

A ilustração a seguir mostra um exemplo dos detalhes do subtrabalho no Commerce.

![Detalhes do subtrabalho RetailProductRating.](media/rnr-hq-ratings-sub-job.png)

> [!NOTE]
> Se você não encontrar o subtrabalho **RetailProductRating**, talvez você já tenha executado o trabalho **Sincronizar classificações de produto** e o trabalho **1040 CDX** antes de inicializar o agendador do Commerce. Neste caso, siga estas etapas para executar o trabalho **Sincronização de dados completa**.

> 1. Acesse **Retail e Commerce \> Configuração do Headquarters \> Agendador do Commerce \> Banco de dados do canal**. Como alternativa, procure por "Banco de dados do canal".
> 1. Selecione o base de dados do canal para sincronizar.
> 1. No painel de ações, selecione **Sincronização de dados completa**.
> 1. Na caixa de diálogo suspensa **Selecionar uma agenda de distribuição** , selecione **1040 - produtos**, e **OK**.
> 1. Repita as etapas do procedimento anterior para verificar se o subtrabalho **RetailProductRating** foi criado.

### <a name="import-product-ratings"></a>Importar classificações de produtos

Para importar classificações de produto no Commerce do serviço de classificações e opiniões, siga estas etapas.

1. Acesse **Retail e Commerce \> Configuração do Headquarters \> Agendador do Commerce \> Sincronizar trabalho de classificações de produto**. Como alternativa, procure por "Sincronizar trabalho de classificações do produto".
1. Na caixa de diálogo **Obter classificações do produto**, na Guia Rápida **Executar em segundo plano**, selecione **Recorrência**.
1. Na caixa de diálogo **Definir recorrência** , configure um padrão de recorrência. (O valor sugerido é duas horas.) Não agende uma recorrência inferior a de uma hora.
1. Selecione **OK**.
1. Defina a opção **Processo em lote** como **Sim**. Essa configuração ajuda a garantir que você poderá auditar os logs e verificar o status de execuções do trabalho em lotes.
1. Selecione **OK** para programar o trabalho em lotes.

A ilustração a seguir mostra um exemplo da configuração do trabalho em lotes no Commerce.

![Configuração do trabalho em lotes Sincronizar classificações do produto.](media/rnr-hq-batchjob-recurrence.png)

## <a name="verify-that-the-batch-job-for-product-rating-synchronization-was-successful"></a>Verifique se o trabalho em lotes para sincronização da classificação do produto foi bem-sucedido

Para verificar se o trabalho em lotes **Sincronizar classificações de produto** foi bem-sucedido, siga estas etapas.

1. Acesse **Retail e Commerce \> Administrador do sistema \> Consultas \> Trabalho em lotes** ou, se você estiver usando a uma unidade de manutenção de estoque (SKU) do Commerce, **Retail e Commerce \> Consultas e relatórios \> Trabalho em lotes** . Como alternativa, procure "Trabalho em lotes".
1. Para exibir os detalhes do trabalho em lotes, na lista de trabalho em lotes na coluna **Descrição do trabalho**, procure uma descrição que contenha "Obter classificações do produto."
1. Selecione a ID do trabalho para visualizar os detalhes do trabalho em lotes, como a data/hora de início agendada e o texto da recorrência.

A ilustração a seguir mostra um exemplo detalhes do trabalho em lotes no Commerce quando o trabalho em lote for programado para ser executado em intervalos de duas horas.

![Detalhes do trabalho em lotes Sincronizar classificação do produto.](media/rnr-hq-batchjob-status-checking.png)

## <a name="make-product-ratings-available-at-the-pos"></a>Disponibilizar classificações do produto no PDV.

A solução de classificações e opiniões no Dynamics 365 Commerce é uma solução do omnicanal. Porém, as classificações de produtos não são mostradas no PDV, por padrão. Para ajudar os clientes nas lojas a verem classificações e opiniões quando estiverem sendo ajudados por vendedores, é necessário ativar as classificações de produtos no PDV.

Para ativar as classificações do produto no PDV, siga estas etapas.

1. Acesse **Retail e Commerce \> Configuração do Headquarters \> Parâmetros \> Parâmetros do Commerce**. Como alternativa, procure "Parâmetros do Commerce".
1. Na guia **Configurar parâmetros** , selecione **Novo**.
1. Insira um nome como **RatingsAndReviews.EnableProductRatingsForRetailStores** e defina o valor para **verdadeiro**.
1. Selecione **Salvar**.
1. Acesse **Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição**. Alternativamente, procure por "Agenda de distribuição".
1. Na lista de trabalho, selecione **1110** (**Configuração global**) e **Executar agora**.
1. Depois que o trabalho for executado com sucesso, verifique se as classificações dos produtos agora são mostradas no PDV.

A ilustração a seguir mostra um exemplo da configuração dos parâmetros do Commerce para ativar as classificações do produto no PDV.

![Configuração de parâmetros do Commerce para classificações de produtos no PDV.](media/rnr-hq-enable-ratings-in-pos.png)

A ilustração a seguir mostra um exemplo de classificações do produto no PDV.

![Classificações do produto no PDV.](media/rnr-pos-catalog-ratings.png)

A ilustração a seguir mostra um exemplo de classificações do produto em canais do call center.

![Classificações de produtos em um canal de call center.](media/rnr-call-center-ratings.png)

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de classificações e opiniões](ratings-reviews-overview.md)

[Aceitar o uso das classificações e opiniões](opt-in-ratings-reviews.md)

[Gerenciar classificações e opiniões](manage-reviews.md)

[Configurar classificações e opiniões](configure-ratings-reviews.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]