---
title: Habilitar previsões de pagamento do cliente
description: Este tópico explica como habilitar e configurar o recurso de previsões de pagamento de cliente no Finance Insights.
author: ShivamPandey-msft
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: b83d1230c94462ca722ad7ceb7b2185afd636aae
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2022
ms.locfileid: "8109595"
---
# <a name="enable-customer-payment-predictions"></a>Habilitar previsões de pagamento do cliente

[!include [banner](../includes/banner.md)]

Este tópico explica como habilitar e configurar o recurso de previsões de pagamento de cliente no Finance Insights. Você ativa o recurso no espaço de trabalho **Gerenciamento de recursos** e insere definições de configuração na página **Configuração do Finance Insights**. Este tópico também inclui informações que podem ajudar você a usar o recurso com eficiência.

> [!NOTE]
> Antes de concluir as etapas a seguir, certifique-se de concluir as etapas de pré-requisito no tópico [Configuração do Finance Insights](configure-for-fin-insites.md).

1. Ative o recurso Previsões de pagamento do cliente:

    1. Abra o espaço de trabalho **Gerenciamento de recursos**.
    2. Selecione **Verificar se há atualizações**.
    3. Na guia **Tudo**, procure **Previsões de pagamento do cliente**. Se você não encontrar esse recurso, procure **(Versão preliminar) Previsões de pagamento do cliente**. 
    4. Ative o recurso.

    O recurso Previsões de pagamento do cliente agora está ativado e pronto para ser configurado.

2. Configure o recurso de informações de pagamento do cliente:

    1. Acesse **Crédito e cobranças \> Configuração \> Finance Insights \> Previsões de pagamento do cliente**.
    2. Na página **Configuração do Finance Insights**, na guia **Previsões de pagamento do cliente**, selecione **Exibir os campos de dados usados no modelo de previsão** para abrir a página **Campos de dados para o modelo de previsão**. Nela, você pode exibir a lista padrão de campos usados para criar o modelo de previsão de inteligência artificial (AI) para previsões de pagamento do cliente.

        Para usar a lista de campos padrão para criar o modelo de previsão, feche a página **Campos de dados para o modelo de previsão** e, na página **Configuração do Finance Insights**, defina a opção **Habilitar recurso** como **Sim**.
        
   > [!NOTE]
   > O recurso **Previsões de pagamento de cliente** requer mais de 100 transações nos seis a nove meses anteriores. As transações podem incluir faturas de texto livre, ordens de venda e pagamentos de cliente. Esses dados devem ser distribuídos nas configurações **No prazo**, **Atrasado** e **Muito atrasado**.    
     

    3. Especifique o período da transação "Muito atrasado" para definir o que o bucket de previsão **Muito atrasado** significa para seus negócios.

        Para cada fatura aberta, o sistema prevê a probabilidade de pagamento em três buckets: **Dentro do prazo**, **Atrasado** e **Muito atrasado**.

        - **Dentro do prazo** – Esse bucket inclui pagamentos que são previstos na data de vencimento da transação ou antes dela.
        - **Atrasado** – Esse bucket inclui pagamentos que estão previstos para serem pagos após a data de vencimento da transação, mas antes do início do período "Muito atrasado" de transação.
        - **Muito atrasado** – Esse bucket inclui pagamentos que estão previstos para serem pagos após o início do período "Muito atrasado" de transação.

        > [!NOTE]
        > Se você alterar o período da transação "Atrasado" e selecionar **Alterar limite de atraso** depois que o modelo de previsão de IA para pagamentos do cliente for criado, o modelo de previsão existente será excluído e um novo modelo será criado. O novo modelo de previsão moverá as transações para o período "Muito atrasado", com base nas configurações que foram inseridas para defini-lo.

    4. Depois de concluir a definição do período da transação "Muito atrasado", selecione **Criar modelo de previsão** para criar o modelo de previsão. A seção **Modelo de previsão** na página **Configuração do Finance Insights** mostra o status do modelo de previsão.

        > [!NOTE]
        > A qualquer momento enquanto o modelo de previsão estiver sendo criado, você pode selecionar **Redefinir criação do modelo** para reiniciar o processo.

    O recurso foi configurado e agora está pronto para ser usado.

Depois que o recurso for ativado e configurado e o modelo de previsão for criado e estiver funcionando, a seção **Modelo de previsão** da página **Parâmetros do Finance Insights** mostrará a precisão do modelo.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
