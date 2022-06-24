---
title: Configurar um experimento
description: Este artigo descreve como configurar um experimento em um serviço de terceiros.
author: sushma-rao
ms.date: 06/08/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.openlocfilehash: 1073cdc509622279ce7388b8b406079a4e6e9e09
ms.sourcegitcommit: 427fe14824a9d937661ae21b9e9574be2bc9360b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2022
ms.locfileid: "8946157"
---
# <a name="set-up-an-experiment"></a>Configurar um experimento

Depois de [definir uma hipótese e determinar quais métricas de sucesso você deseja usar](experimentation-identify.md), você precisará configurar seu experimento no serviço de terceiros. O diagrama a seguir mostra todas as etapas envolvidas na configuração e execução de um experimento em um site de comércio eletrônico no Dynamics 365 Commerce. Etapas adicionais são abordadas em artigos separados.

[ ![Usuário de teste de experimentação - Configuração.](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)


## <a name="set-up-your-experiment-in-the-third-party-service"></a>Configurar seu experimento no serviço de terceiros
Você já deve ter escolhido o serviço de terceiros para ser executado e monitorar seu experimento e configurar o conector de experimentação. Esses pré-requisitos estão listados em [Experimentação no Dynamics 365 Commerce](experimentation-overview.md).

Siga as etapas necessárias para criar seu experimento no serviço de terceiros. Se o conector estiver configurado corretamente, a lista completa de experimentos configurados no serviço de terceiros aparecerá no construtor de sites do Commerce em cerca de 5 minutos.

## <a name="set-up-your-success-metrics"></a>Configurar métricas de sucesso
Cada experimento precisa de métricas para medir o impacto das variações e para validar a hipótese. Siga as etapas abaixo para habilitar o cálculo de métricas no serviço de terceiros usando eventos de telemetria ativos do Dynamics 365 Commerce.

Para configurar as métricas de sucesso para os módulos prontos para uso, siga estas etapas.

1. No construtor de sites do Commerce, selecione **Páginas** no painel de navegação esquerdo e, em seguida, selecione a página na qual deseja retirar métricas. 
1. Acesse a seção **IDs de evento para rastrear** no painel de propriedades à direita da página ou do módulo que você deseja rastrear.
1. Selecione **Exibir**. Uma lista de todas as IDs de evento de clique é exibida. Copie o evento que você deseja rastrear e cole a chave de evento no local designado no serviço de terceiros. Se você precisar de mais de um evento, copie as chaves uma de cada vez. 
1. Para exibições de página, use o valor de hash SHA-256 do nome da página no construtor de sites com o prefixo `.PageView`. Por exemplo, a ID do evento para `Homepage.PageView` seria `e217eb66c7808ecc43b0f5c517c6a83b39d72b91412fbd54a485da9d8e186a9`.
1. Execute outras etapas para controlar as métricas necessárias no serviço de terceiros.

Para cliques de módulo personalizados, siga estas etapas para instrumentar os eventos de clique:

1. Prepare um objeto **TelemetryContent** para o módulo usando a função abaixo. Essa função usa o nome da página, o nome do módulo e o objeto de telemetria padrão fornecido pelo SDK como entradas.

    ```TypeScript
    getTelemetryObject(pageName: string, moduleName: string, telemetry: ITelemetry): ITelemetryContent
    ```
    
    Veja a seguir um exemplo: 
    
    ```TypeScript
    private readonly telemetryContent: ITelemetryContent = getTelemetryObject(this.props.context.request.telemetryPageName!, this.props.friendlyName, this.props.telemetry);
    ```
    
1. Crie os dados de conteúdo que contêm informações sobre o que precisa ser capturado. Para botões e outros controles estáticos, você pode incluir **etext** como "Compre agora" ou "Pesquisar". E para componentes com cliques, como clicar em um cartão de produto, você pode enviar a **recid**, que é a ID do registro do produto ou da ID do produto.

    ```TypeScript
    getPayloadObject(eventType: string, telemetryContent: ITelemetryContent, etext: string, recid?: string): IPayLoad
    ```
    Como um exemplo de controles estáticos, passe a cadeia de caracteres de texto do botão, conforme mostrado a seguir:

    ```TypeScript
    const payLoad = getPayloadObject('click', this.props.telemetryContent, 'Shop Now', '');
    ```
    Como um exemplo de cliques de produto, passe o recordId do produto como mostrado a seguir:

    ```TypeScript
    const payLoad = getPayloadObject('click', telemetryContent!, '', product.RecordId.toString());
    ```
    
1. Chame a função **OnClick** para registrar o evento.

    ```TypeScript
    onTelemetryClick = (telemetryContent: ITelemetryContent, payLoad: IPayLoad, linkText: string) => () =>
    ```

    Veja a seguir um exemplo:

    ```TypeScript
    onClick: onTelemetryClick(this.props.telemetryContent, payLoad, linkText)
    ```

## <a name="previous-step"></a>Etapa anterior
[Identificar uma hipótese e determinar as métricas para um experimento](experimentation-identify.md) 


## <a name="next-step"></a>Próxima etapa
[Conectar e editar um experimento](experimentation-connect-edit.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
