---
title: Adicionar um código QR ou código de barras a emails transacionais e de recebimento
description: Este artigo explica como inserir códigos QR e códigos de barras que representam IDs de ordens em emails transacionais e de recebimento no Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 03/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-02-16
ms.dyn365.ops.version: Release 10.0.18
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 2832d1df3893e124759e4719a64341494cea2204
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272035"
---
# <a name="add-a-qr-code-or-bar-code-to-transactional-and-receipt-emails"></a>Adicionar um código QR ou código de barras a emails transacionais e de recebimento

[!include [banner](includes/banner.md)]

Este artigo explica como inserir códigos QR e códigos de barras que representam IDs de ordens em emails transacionais e de recebimento no Microsoft Dynamics 365 Commerce.

Você pode incluir facilmente os códigos QR e os códigos de barras em emails transacionais para ajudar a acelerar o processo de pesquisa de ordens em um ambiente de varejo. Para inserir códigos QR e códigos de barras em emails, você usa uma marca HTML **\<img\>** que solicita um código QR ou uma imagem de código de barras de um serviço de geração e renderização. A Microsoft não fornece esse serviço. No entanto, há muitos serviços gratuitos ou baratos que podem servir códigos QR ou códigos de barras gerados dinamicamente com base em um valor que é passado em uma cadeia de caracteres de consulta.

## <a name="add-a-qr-code-or-bar-code-to-a-transactional-email"></a>Adicionar um código QR ou código de barras a um email transacional

Para inserir um código QR ou código de barras em um email transacional enviado como parte de uma compra de comércio eletrônico, siga estas etapas.

1. Abra o código HTML de origem para o modelo de email transacional e adicione uma marca HTML **\<img\>** que aponte para o código QR ou o serviço de código de barras. Veja aqui um exemplo.

    ```HTML
    <img src="https://YOUR_QR_CODE_BAR_CODE_SERVICE?data=%salesid%&param1=value1&param2=value2" alt="%salesid%" />
    ```

    Veja aqui uma explicação do exemplo anterior:

    - **SEU\_SERVIÇO DE\_CÓDIGO\_QR DE\_CÓDIGO DE\_BARRAS** representa o domínio do seu código QR ou serviço de código de barras.
    - **dados** representa o parâmetro que o código QR ou o serviço de código de barras usa para receber o conteúdo que deve ser processado como um código QR ou um código de barras.

        O valor **%salesid%** deve ser atribuído a esse parâmetro. Neste exemplo, observe que o valor também é usado como texto alternativo para a imagem.

    - **param1** e **param2** representam parâmetros opcionais adicionais.

1. Acesse **Varejo e Comércio \> Configuração do headquarters \> Parâmetros \> Modelos de email da organização** e carregue o HTML atualizado no modelo de email transacional apropriado.

> [!NOTE]
> Os parâmetros podem ser diferentes entre o código QR e os provedores de serviço de código de barras. Portanto, lembre-se de contatar o provedor de serviços para confirmar os parâmetros aos quais você deve atribuir valores.

## <a name="add-a-qr-code-or-bar-code-to-a-receipt-email"></a>Adicionar um código QR ou código de barras a um email de recebimento 

Para inserir um código QR ou código de barras em um email de recebimento que pode ser enviado depois que uma compra é feita no ponto de venda (PDV), siga estas etapas.

1. Abra o código HTML de origem para o modelo de email de recebimento e adicione uma marca HTML **\<img\>** que aponte para o código QR ou o serviço de código de barras. Veja um exemplo abaixo.

    ```HTML
    <img src="https://YOUR_QR_CODE_BAR_CODE_SERVICE?data=%receiptid%&param1=value1&param2=value2" alt="%receiptid%" />
    ```

    Veja aqui uma explicação do exemplo anterior:

    - **SEU\_SERVIÇO DE\_CÓDIGO\_QR DE\_CÓDIGO DE\_BARRAS** representa o domínio do seu código QR ou serviço de código de barras.
    - **dados** representa o parâmetro que o código QR ou o serviço de código de barras usa para receber o conteúdo que deve ser processado como um código QR ou um código de barras.

        O valor **%receiptid%** deve ser atribuído a esse parâmetro. Neste exemplo, observe que o valor também é usado como texto alternativo para a imagem.

    - **param1** e **param2** representam parâmetros opcionais adicionais.

1. Acesse **Varejo e Comércio \> Configuração do headquarters \> Parâmetros \> Modelos de email da organização** e carregue o HTML atualizado no modelo de email com o **emailrecpt** da ID do email.

> [!NOTE]
> Os parâmetros podem ser diferentes entre o código QR e os provedores de serviço de código de barras. Portanto, lembre-se de contatar o provedor de serviços para confirmar os parâmetros aos quais você deve atribuir valores.

## <a name="additional-resources"></a>Recursos adicionais

[Enviar recibos por email do Modern POS (MPOS)](email-receipts.md)

[Criar modelos de email para eventos transacionais](email-templates-transactions.md)
