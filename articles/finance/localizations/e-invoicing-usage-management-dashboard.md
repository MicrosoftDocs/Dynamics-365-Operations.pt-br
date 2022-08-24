---
title: Painel Gerenciamento de uso
description: Este artigo explica como usar o Painel Gerenciamento de uso para monitorar o uso do serviço de Faturamento Eletrônico e permanecer em conformidade.
author: gionoder
ms.date: 06/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.custom: 97423
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 74f3d88faf192474c177da971a9f7bb0e58e1279
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272199"
---
# <a name="usage-management-dashboard"></a>Painel de gerenciamento de uso

[!include [banner](../includes/banner.md)]

O painel **Gerenciamento de uso** ajuda você monitorar o uso do serviço de Faturamento Eletrônico e, portanto, ajuda sua organização a permanecer em conformidade em termos de uso mensal. A conformidade é determinada calculando o volume de submissão e comparando-o com o volume de submissões para identificar qualquer desvio entre o volume adquirido e o volume usado.

O painel inclui os seguintes indicadores:

- Um indicador de custo que você pode usar para monitorar o consumo para fins de conformidade de licença:

    - Uso por mês (exportação)

- Os três indicadores operacionais que você pode usar para rastrear o uso do serviço de Faturamento Eletrônico para fins de gerenciamento:

    - Uso por recurso
    - Uso por ambiente
    - Uso por mês (importação)

## <a name="measurement-scope"></a>Escopo de medição

- Unidade de medida: 

    O painel **Gerenciamento de uso** conta o envio de documentos de negócios e faturas eletrônicas importadas.

- Organização: 

    A conta é resumida pelo ID de locatário da sua organização, não importa o número de instâncias do Microsoft Dynamics 365 Finance ou Dynamics 365 Supply Chain Management, nem o número de entidades legais em que o serviço de Faturamento Eletrônico está ativado.


## <a name="indicator-usage-per-month-export"></a>Indicador: uso por mês (exportação)

Este indicador fornece detalhes sobre os faturamentos eletrônicos que a sua organização emite durante um período definido.

### <a name="scope"></a>Escopo
- O número de documentos de negócios que são enviados do Finance and Supply Chain Management para o o serviço de Faturamento de Eletrônico, não importa o número de linhas que esses documentos de negócios contenham.
- O número de documentos de negócios enviados que são processados com sucesso pelo serviço de Faturamento Eletrônico. Um documento é considerado processado com sucesso quando o fluxo de ações que são definidas na configuração do recurso é concluído.

> [!NOTE]
> Quando uma fatura eletrônica é enviada para um serviço Web externo, a contagem é independente dos resultados do processamento do serviço Web (aceito, rejeitado ou erro de validação do esquema). Se serviço Web tiver recebido e respondido à solicitação do serviço de Faturamento Eletrônico, o envio será considerado uma contagem válida.

- **Exceção:** os documentos de negócios não serão contados se eles forem reenviados do Finance e Supply Chain Management para o serviço de Faturamento Eletrônico, como nos cenários em que um reenvio do mesmo documento de negócio for necessário para alterar o status do faturamento eletrônico. Por exemplo, a emissão de uma fatura eletrônica brasileira (documento fiscal) é contada como válida, mas a solicitação de cancelamento para ela não.


### <a name="calculation"></a>Cálculo

O cálculo do saldo é feito da seguinte forma:

Saldo = Gratuito + Comprado - Usado

Onde:

- Gratuito:
  
    Um volume gratuito dos documentos de negócio que o cliente pode enviar por mês. Ele inclui um pacote de 100 documentos negócios enviados que podem ser enviados para o serviço de Faturamento Eletrônico. O volume gratuito não é cumulativo e qualquer saldo restante não é passado para o próximo período.
  
- Adquiridas:
  
    Um pacote de 1.000 documentos negócios enviados que podem ser enviados para o serviço de Faturamento Eletrônico. Este pacote deve ser adquirido para sua organização mensalmente. O volume comprado não é cumulativo e qualquer saldo restante não é passado para o próximo período.
  
- Usado: 

    A contagem dos envios de documento de negócio para o serviço Faturamento Eletrônico de acordo com os critérios definidos.
   
> [!IMPORTANT]
> Se a sua organização planeja exceder o volume mensal de 100 envios gratuitos, compre o volume máximo para garantir a conformidade com a política de licenciamento da Microsoft para o serviço Faturamento Eletrônico.
>
> Atualmente, o volume comprado deve ser inserido manualmente, de acordo com a data de aquisição, como vários pacotes de 1.000 envios.

## <a name="indicator-usage-by-feature"></a>Indicador: uso por recurso

Este indicador mostra o uso de recursos de faturamento eletrônico para emissão de faturas eletrônicas durante um período definido.

- Cálculo:
  
    Usado =-A contagem de quantas vezes cada recurso de faturamento eletrônico foi usado durante o envio dos documentos de negócio para o serviço Faturamento Eletrônico.

## <a name="indicator-usage-by-environment"></a>Indicador: uso por ambiente

Este indicador mostra o uso de ambientes do serviço de faturamento eletrônico durante um período definido.

- Cálculo:
    
    Usado =-A contagem de quantas vezes cada ambiente do serviço de faturamento eletrônico foi usado durante o envio dos documentos de negócio para o serviço Faturamento Eletrônico.

## <a name="indicator-usage-per-month-import"></a>Indicador: uso por mês (importação)

Este indicador mostra o volume de importação de faturas eletrônicas pelo serviço Faturamento Eletrônico no Finance e Supply Chain Management durante um período definido.

- Escopo:

    As faturas eletrônicos que são importados no Finance and Supply Chain Management para o o serviço de Faturamento de Eletrônico, não importa o número de linhas que esses documentos de negócios contenham.

- Cálculo:

    Recebido = A contagem de faturas eletrônicas importadas no Finance e Supply Chain Management.

## <a name="functions"></a>Funções
### <a name="purchase"></a>Compra

Na guia **Uso por mês (export)**, selecione **Comprar** para registrar manualmente a quantidade de envios adquiridos.

Para uma data específica, selecione **Novo** e digite o número de **Pacotes** adquiridos nessa data.

A **Quantidade** é calculada como:

Quantidade = Pacotes * 1.000

A **Quantidade** calculada reflete no campo **Comprado** no indicador **Uso por mês (exportar)**.

### <a name="update"></a>Atualização

No Painel de ações, selecione **Atualizar** para atualizar o cálculo e atualizar os dados mostrados na página e no gráfico.

### <a name="reset-history-data"></a>Redefinir dados do histórico

No Painel de ações, selecione **Redefinir dados históricos** para atualizar as bases de dados de onde os indicadores são calculados.




> [!NOTE]
> O painel **Gerenciamento de uso** não mostra as quantidades monetárias. Em vez disso, ele mostra somente o volume dos envios contados e documentos e importados.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
