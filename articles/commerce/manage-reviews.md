---
title: Gerenciar classificações e opiniões
description: Este tópico explica como gerenciar classificações e opiniões no construtor de site do Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3fc88bc5a5868dce7c0539bf3f0ddc5b751e7b75
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4410211"
---
# <a name="manage-ratings-and-reviews"></a>Gerenciar classificações e opiniões

[!include [banner](includes/banner.md)]

Este tópico explica como gerenciar classificações e opiniões no construtor de site do Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

O Dynamics 365 Commerce usa o Serviço Cognitivo do Microsoft Azure para moderar automaticamente o texto da opinião, redigindo palavras profanas. Além disso, os moderadores podem usar o construtor de site do Dynamics 365 Commerce para implementar as seguintes tarefas manuais:

- Moderar as opiniões, respondendo-as ou removendo-as.
- Excluir opiniões de um cliente na solicitação do cliente.
- Importar em massa dados de classificações e opiniões de todos os produtos para um modelo do Power BI , para que as tendências para classificações e opiniões possam ser analisadas.

## <a name="read-a-review"></a>Ler uma opinião 

Para ler uma opinião no construtor de site do Commerce, siga estas etapas.

1. Vá para **Início \> Opiniões \> Moderação**.
1. Use o campo de pesquisa no canto superior direito da página para filtrar as opiniões mostradas por ID do produto, nome do produto ou texto da opinião.

Os filtros adicionais permitem delimitar as opiniões por período, classificação, canal, status de interesse (obtidas, respondidas ou reportadas).

![Home page de moderação](media/rnr-moderation-home.png) 

## <a name="respond-to-a-review"></a>Responder a uma opinião 

Às vezes, os clientes que compraram um produto expressam sua satisfação ou insatisfação ou não sabem como usá-lo. Como moderador, você pode publicar uma resposta a uma opinião. Esta resposta aparece junto com a opinião no site. 

Para responder uma opinião no construtor de site do Commerce, siga estas etapas.

1. Vá para **Início \> Opiniões \> Moderação**.
1. Encontre e selecione a opinião que requer uma resposta.
1. No painel de propriedades à direita, selecione **Adicionar uma resposta**.
1. Insira o texto de resposta e o nome que devem ser mostrado para o respondente. O nome do respondente padrão é **Moderador**.
1. Quando terminar, selecione **Postar resposta**.

![Respondendo uma opinião](media/rnr-moderation-response.png) 

## <a name="take-down-a-review"></a>Desativar uma opinião 

Às vezes, há uma justificativa comercial para que os moderadores desativem as opiniões dos clientes. 

Para desativar uma opinião no construtor de site do Commerce, siga estas etapas.

1. Vá para **Início \> Opiniões \> Moderação**.
1. Localize e selecione a opinião que deve ser desativada.
1. No painel de propriedades à direita, selecione o motivo da desativação em **Desativação da Opinião** e depois selecione **Desativar**.
    
## <a name="delete-a-customers-reviews-at-the-customers-request"></a>Excluir opiniões de um cliente na solicitação do cliente 

Às vezes, os clientes querem que seus dados de classificações e opiniões sejam excluídos permanentemente de um site de comércio eletrônico. Um moderador que recebe uma solicitação de remoção de um cliente pode remover os dados do cliente usando o recurso de exclusão da opinião. Para localizar e excluir os dados de um cliente, o moderador exige o endereço de email que o cliente usou para entrar e dar as opiniões. 

Para localizar e excluir dados do cliente no construtor de site do Commerce, siga estas etapas.

1. Vá para **Início \> Opiniões \> Excluir**.
1. Na caixa **Procurar usuários por endereço de email** , insira o endereço de email do cliente e selecione **Pesquisar**.
1. Se o cliente tiver alguma atividade de opinião (por exemplo, envios de opiniões, votos sobre a utilidade das opiniões de outro cliente ou comentários sobre a opinião de outro cliente), os resultados serão mostrados. Para cada item, há um botão **Excluir** .
1. Para cada item a ser excluído, selecione **Excluir**. Quando for solicitado a confirmação, selecione **Sim**. 
    
![Excluindo dados do cliente](media/rnr-moderation-delete-reviews.png) 

> [!NOTE]
> - Pode levar até sete dias para que os dados sejam completamente removidos do sistema. Os moderadores devem notificar aos clientes sobre esse atraso.
> - Se os clientes alteraram o nome nas configurações da conta, vários itens podem aparecer nos resultados da pesquisa. Nesse caso, para excluir completamente os dados do cliente, o moderador deve selecionar **Excluir** para cada item. 

## <a name="download-ratings-and-reviews-data"></a>Fazendo download de dados de classificações e opiniões

O construtor de site do Commerce permite que os moderadores importem dados de classificações e opiniões em massa, para que possam analisar tendências. Um modelo do Power BI que inclui métricas básicas estará disponível. Os moderadores podem usar esse modelo para conectar dados importados em massa e visualizar um painel. Eles não precisam criar um painel personalizado. Os moderadores também podem personalizar o modelo do Power BI para atender às suas necessidades específicas. 

Para baixar dados de classificações e opiniões no construtor de site do Commerce, siga estas etapas.

1. Vá para **Início \> Opiniões \> Relatórios**.
1. Selecione **Baixar dados de opiniões** para baixar dados em massa de classificações e opiniões no formato de valores separados por vírgulas (CSV).

## <a name="view-ratings-and-reviews-trends"></a>Visualizar tendência de classificações e opiniões

Os moderadores podem fazer download do modelo do Power BI, de forma que possam exibir as tendências em um painel.

Para exibir tendências de classificações e opiniões no construtor de site do Commerce, siga estas etapas.

1. Vá para **Início \> Opiniões \> Relatórios**.
1. Selecione **Modelo do PowerBI** para baixar o modelo.

    ![Baixe o modelo do Power BI](media/rnr-moderation-reports.png) 

1. Abra o modelo baixado usando o aplicativo Power BI. Feche a caixa de diálogo **Acessar o conteúdo da Web** que é exibida e feche a mensagem de erro "Atualizar" que é exibida.
1. Vá para **Início**, selecione **Editar consultas** e selecione **Configurações da fonte de dados**.
1. Na caixa de diálogo **Configurações da fonte de dados**, selecione **Alterar Origem**.
1. No campo **URL** , insira o caminho de dados das opiniões baixado no procedimento anterior (por exemplo, **c:\\opiniões\\ReviewsData.csv**).

    ![Campo da URL na caixa de diálogo Valores Separados por Vírgulas](media/rnr-powerbi-datasource-settings.png) 

1. Selecione **OK** e, em seguida, selecione **Aplicar alterações**. Levará um a dois minutos para aplicar suas alterações na fonte de dados.
1. Selecione **Planilha de tendências** para exibir as tendências de classificações e opiniões.

    ![Tendência de classificações e opiniões](media/rnr-powerbi-dashboard-template.png) 
    
## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de classificações e opiniões](ratings-reviews-overview.md)

[Aceitar usar classificações e opiniões](opt-in-ratings-reviews.md)

[Configurar classificações e opiniões](configure-ratings-reviews.md)

[Sincronizar classificações de produto no Dynamics 365 Retail](sync-product-ratings.md)
