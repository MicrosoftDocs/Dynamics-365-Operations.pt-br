---
title: Habilitar previsões de pagamento do cliente (versão prévia)
description: Este tópico explica como habilitar e configurar o recurso de previsões de pagamento de cliente no Finance Insights.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 584c1af5f9252a4b8c88a8866a64184bd0595b2e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009409"
---
# <a name="enable-customer-payment-predictions-preview"></a>Habilitar previsões de pagamento do cliente (versão prévia)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tópico explica como habilitar e configurar o recurso de previsões de pagamento de cliente no Finance Insights. Para ativar o recurso no espaço de trabalho **Gerenciamento de recursos** e inserir definições de configuração, acesse a página **Parâmetros do Financial insights**. Este tópico também inclui informações que podem ajudar você a usar o recurso com eficiência.

> [!NOTE]
> Antes de concluir as etapas a seguir, certifique-se de concluir as etapas de pré-requisito no tópico [Configuração do Finance Insights](configure-for-fin-insites.md).

1. Use as informações da página de ambiente no Microsoft Dynamics Lifecycle Services (LCs) para se conectar à instância principal do Azure SQL para esse ambiente. Execute o comando Transact-SQL (T-SQL) a seguir para ativar as versões piloto no ambiente de área restrita. (Talvez seja necessário ativar o acesso ao seu endereço IP no LCS antes de se conectar remotamente ao servidor de objetos de aplicativo \[AOS\].)

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED, PARTITION) VALUES ('PayPredEnableFeature', 1, 5637144576)`

    > [!NOTE]
    > Se a sua implantação do Microsoft Dynamics 365 Finance for uma implantação do Service Fabric, você pode ignorar essa etapa. A equipe do Finance Insights já deve ter ativado a versão piloto para você. Se você não vir o recurso no espaço de trabalho **Gerenciamento de recursos** ou se tiver problemas ao tentar ligá-lo, contate <fiap@microsoft.com>.

2. Habilite o recurso de informações de pagamento do cliente:

    1. Vá para **Administrador do sistema \> Espaços de trabalho \> Gerenciamento de recursos**.
    2. Localize o recurso que é chamado de **Informações de pagamento do cliente (versão prévia)**.
    3. Selecione **Habilitar agora**.

    O recurso de insights de pagamento do cliente agora está ativado e pronto para ser configurado.

3. Configure o recurso de informações de pagamento do cliente:

    1. Acesse **Crédito e cobranças \> Configuração \> Finance Insights \> Parâmetros do Finance Insights**.

        [![Parâmetros de informações financeiras antes do recurso ser configurado](./media/finance-insights-parameters.png)](./media/finance-insights-parameters.png)

    2. Na página **Parâmetros de informações financeiras**, na guia **Informações de pagamento do cliente**, selecione **Exibir os campos de dados usados no link do modelo de previsão** para abrir a página **Campos de dados para o modelo de previsão**. Nela, você pode exibir a lista padrão de campos usados para criar o modelo de previsão de inteligência artificial (AI) para previsões de pagamento do cliente.

        Para usar a lista de campos padrão para criar o modelo de previsão, feche a página **Campos de dados para o modelo de previsão** e, na página **Parâmetros de informações financeiras**, defina a opção **Habilitar recurso** como **Sim**.

    3. Especifique o período da transação "Muito atrasado" para definir o que o bucket de previsão **Muito atrasado** significa para seus negócios.

        Para cada fatura aberta, o sistema prevê a probabilidade de pagamento em três buckets: **Dentro do prazo**, **Atrasado** e **Muito atrasado**.

        - **Dentro do prazo** – Esse bucket inclui pagamentos que são previstos na data de vencimento da transação ou antes dela.
        - **Atrasado** – Esse bucket inclui pagamentos que estão previstos para serem pagos após a data de vencimento da transação, mas antes do início do período "Muito atrasado" de transação.
        - **Muito atrasado** – Esse bucket inclui pagamentos que estão previstos para serem pagos após o início do período "Muito atrasado" de transação.

        > [!NOTE]
        > Se você alterar o período da transação "Atrasado" e selecionar **Alterar limite de atraso** depois que o modelo de previsão de IA para pagamentos do cliente for criado, o modelo de previsão existente será excluído e um novo modelo será criado. O novo modelo de previsão moverá as transações para o período "Muito atrasado", com base nas configurações que foram inseridas para defini-lo.

    4. Depois de concluir a definição do período da transação "Muito atrasado", selecione **Criar modelo de previsão** para criar o modelo de previsão. A seção **Modelo de previsão** na página **Parâmetros de informações financeiras** mostra o status do modelo de previsão.

        > [!NOTE]
        > A qualquer momento enquanto o modelo de previsão estiver sendo criado, você pode selecionar **Redefinir criação do modelo** para reiniciar o processo.

    O recurso foi configurado e agora está pronto para ser usado.

Depois que o recurso for ativado e configurado e o modelo de previsão tiver sido criado e estiver funcionando, a seção **Modelo de previsão** da página **Parâmetros de informações financeiras** mostrará a precisão do modelo, conforme mostrado na ilustração a seguir.

[![Precisão do modelo de previsão na página Parâmetros de informações financeiras](./media/finance-insights-parameters-accuracy.png)](./media/finance-insights-parameters-accuracy.png)

## <a name="release-details"></a>Detalhes da liberação

A versão prévia pública do Finance Insights está disponível para implantações de avaliação nos Estados Unidos da América, Europa e Reino Unido. A Microsoft está adicionando suporte para mais regiões de forma incremental.

Os recursos de versão preliminar pública só devem ser ativados em ambientes de área restrita de Camada 2. A Configuração e os Modelos de IA criados em um ambiente de área restrita não podem ser migrados para o ambiente de produção. Para obter mais informações, consulte [Termos de uso suplementares para versões preliminares do Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/public-preview-terms).

## <a name="privacy-notice"></a>Aviso de privacidade

As versões prévias (1) podem utilizar menos medidas de privacidade e segurança que o serviço do Dynamics 365 Finance and Operations, (2) não estão incluídas no contrato de nível de serviço (SLA) desse serviço, (3) não devem ser usadas para processar dados pessoais ou outros dados sujeitos a requisitos de conformidade legais ou regulatórios e (4) têm suporte limitado.
