---
title: Solucionar problemas de configuração do Finance Insights
description: Este tópico lista problemas que podem ocorrer ao usar os recursos da Finance insights. Ele também explica como corrigir esses problemas.
author: panolte
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-20
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: f3cac30a66ff3a74a7f67c11dd9fa14af79d10af
ms.sourcegitcommit: 03fa7556840aa59f825697f6f9edeb58ea673fca
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "7752608"
---
# <a name="troubleshoot-finance-insights-setup-issues"></a>Solucionar problemas de configuração do Finance Insights

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tópico lista problemas que podem ocorrer ao usar os recursos da Finance insights. Ele também explica como corrigir esses problemas.

## <a name="symptom-why-cant-i-map-the-customer-payment-insights-data-integration-template-destination-column"></a>Sintoma: por que não consigo mapear a coluna destino do modelo de integração de dados de insights de pagamento do cliente?

### <a name="resolution"></a>Resolução

Você pode estar usando um modelo para uma versão anterior. Antes do lançamento da versão 10.0.17, visualize os clientes configurados no modelo de DI (Integração de Dados) **Resultados de insights de pagamento de cliente (CDS para Fin and Ops)** usando a entidade **Resultado de previsão de pagamento (versão preliminar)**. Depois de uma atualização para o 10.0.17 e posterior, você deverá usar o modelo de DI **Resultados de insights de pagamento de cliente (CDs para Fin and Ops 10.0.17 e posterior)** para concluir o mapeamento. Talvez você não consiga mapear a coluna de destino do modelo de DI até que a lista da entidade de gerenciamento de dados seja atualizada e a entidade **Resultado da previsão de pagamento** aparecer nela. Para atualizar a lista de entidades e mostrar o resultado da previsão de pagamento, conclua as etapas no Microsoft Dynamics 365 Finance e no Dataverse (anteriormente conhecido como portal do administrador do Common Data Service \[CDs\]).

### <a name="in-finance"></a>No Finance

Siga estas etapas no Finance após a atualização.

1. Acesse **Administração de sistema \> Locais de trabalho \> Gerenciamento de dados**.
2. No espaço de trabalho **Gerenciamento de dados**, selecione o bloco **Parâmetros de estrutura**.
3. Na página **Parâmetros de importação/exportação de dados**, selecione **Configurações da entidade** e, em seguida, selecione **Atualizar lista de entidades**.
4. Feche a página **Parâmetros de importação/exportação de dados**.
5. No espaço de trabalho **Gerenciamento de dados**, selecione o bloco **Entidades de dados**.
6. Procure "Resultado da previsão de pagamento". Verifique se a entidade **Resultado da previsão de pagamento** não é a versão preliminar. O nome da versão preliminar termina em "(versão preliminar)." Se você vir somente a versão preliminar da entidade, contate o suporte da Microsoft.

### <a name="in-dataverse"></a>No Dataverse

Siga estas etapas no [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com/environments) para atualizar seus projetos de integração de dados.

1. Se você estiver usando uma versão preliminar do Finance Insights, remova o projeto de DI associado ao modelo de **Resultados de insights de pagamento do cliente (CDS para Fin and Ops)**.
2. Siga as etapas em [Criar um projeto de integrador de dados](create-data-integrate-project.md). Use o modelo **Resultados de insights de pagamento do cliente (CDS para Fin and Ops 10.0.17 e posteriores)**.

## <a name="symptom-when-i-try-to-open-ai-builder-by-using-the-links-on-the-customer-payment-predictions-setup-page-why-do-i-receive-the-following-error-message-sorry-theres-been-a-disconnect"></a>Sintoma: quando tento abrir o AI Builder usando os links na página Configuração de previsões de pagamento do cliente, por que recebo a seguinte mensagem de erro: "Houve uma desconexão"?

### <a name="resolution"></a>Resolução

Os usuários do Dynamics 365 Finance devem ter uma conta de usuário do Microsoft Power Apps para o ambiente e essa conta de usuário deve ter a função de personalizador de sistema. O administrador do sistema do Microsoft Power Apps pode criar a conta de usuário e atribuir a função. Você pode acessar <https://make.preview.powerapps.com/>, entrar usando essa conta de usuário e tentar os links novamente.

## <a name="symptom-why-doesnt-the-cash-forecast-tab-in-the-cash-flow-forecast-workspace-show-any-data"></a>Sintoma: por que a guia Previsão de caixa na área de trabalho Previsão de fluxo de caixa mostra dados?

### <a name="resolution"></a>Resolução

A função de previsão de fluxo de caixa em Gerenciamento de caixa e de banco e o recurso de previsões de fluxo de caixa no Finance Insights deve ser configurada para mostrar corretamente os dados no espaço de trabalho **Previsão de fluxo de caixa**.

Primeiro, configure e habilite as contas de previsão de fluxo de caixa e de liquidez. Para obter mais informações, consulte [Previsão de fluxo de caixa](../cash-bank-management/cash-flow-forecasting.md). Se essa configuração tiver sido concluída, mas você não vir os resultados esperados, consulte [Solucionar problemas da configuração de previsão de fluxo de caixa](../cash-bank-management/cash-flow-forecasting-tsg.md) para obter mais informações.

Em seguida, confirme se o recurso Previsões de fluxo de caixa do Finance Insights (**Gerenciamento de caixa e banco \> Configuração \> Finance Insights \> Previsões de fluxo de caixa**) foi habilitado e se o treinamento do modelo de IA foi concluído. Se o treinamento não tiver sido concluído, selecione **Previsão agora** para iniciar o processo de treinamento do modelo.
