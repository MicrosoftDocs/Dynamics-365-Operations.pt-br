---
title: Solucionar problemas de configuração do Finance Insights
description: Este tópico lista problemas que podem ocorrer ao usar os recursos da Finance insights. Ele também explica como corrigir esses problemas.
author: panolte
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2021-08-20
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: 5669b414283013ae1de095de2201df066ab588dd
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8725895"
---
# <a name="troubleshoot-finance-insights-setup-issues"></a>Solucionar problemas de configuração do Finance Insights

[!include [banner](../includes/banner.md)]

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

## <a name="symptom-why-isnt-the-install-a-new-add-in-button-visible-in-microsoft-dynamics-lifecycle-services"></a>Sintoma: por que o botão instalar um novo suplemento está visível nos Microsoft Dynamics Lifecycle Services?

### <a name="resolution"></a>Resolução

Primeiro, verifique se a função **Gerente do Ambiente** ou **Proprietário do Projeto** está atribuída ao usuário conectado no campo **Função de segurança do projeto** no Microsoft Dynamics Lifecycle Services (LCS). A instalação dos novos suplementos requer uma dessas funções de segurança do projeto.

Se a função de segurança correta do projeto estiver atribuída a você, talvez seja necessário atualizar a janela do navegador para ver o botão **Instalar novo suplemento**.

## <a name="symptom-the-finance-insights-add-in-doesnt-seem-to-be-installing-why-is-that"></a>Sintoma: parece que o suplemento do Finance insights não está instalado. Por que?

### <a name="resolution"></a>Resolução

As etapas a seguir devem ter sido concluídas.

- Verifique se você tem acesso de **Administrador do sistema** e de **Personalizador do Sistema** no centro de administração do Power Portal.
- Verifique se uma licença do Dynamics 365 Finance ou equivalente está sendo aplicada ao usuário que está instalando o suplemento.
- Verifique se o seguinte aplicativo do Azure AD está registrado no Azure AD: 

  | Solicitação de Emprego                  | ID do Aplicativo           |
  | ---------------------------- | ---------------- |
  | CDS de Microsserviços de ERP do Microsoft Dynamics | 703e2651-d3fc-48f5-942c-74274233dba8 | 
  
## <a name="symptom-error-we-didnt-find-any-data-for-the-selected-filter-range-please-select-a-different-filter-range-and-try-again"></a>Sintoma: Erro: Não encontramos dados para o intervalo de filtros selecionado. Selecione um intervalo de filtros diferente e tente novamente.  

### <a name="resolution"></a>Resolução

Verificar a configuração do integrador de dados para verificar se ele está funcionando conforme o esperado e a quebra do retorno dos dados de AI Builder ao Finance.  
Para obter mais informações, consultar [Criar um projeto de integração de dados](../finance-insights/create-data-integrate-project.md).

## <a name="symptom-customer-payment-prediction-training-failed-and-the-ai-builder-error-states-prediction-should-have-only-2-distinct-outcome-values-to-train-the-model-map-to-two-outcomes-and-retrain-training-report-issue-isnotminrequireddistinctnonnullvalues"></a>Sintoma: Falha no treinamento de previsão de pagamento de cliente e nos estados de erro de AI Builder, "a previsão deve ter somente dois valores de resultado distintos para treinar o modelo. Mapear para dois resultados e retreinar ","Problema de relatório de treinamento: IsNotMinRequiredDistinctNonNullValues".

### <a name="resolution"></a>Resolução

Esse erro indica que não há transações históricas suficientes no último ano que representa cada categoria descrita nas categorias **No prazo**, **Atrasado**, e **Muito atrasado**. Para resolver esse erro, ajuste o período da transação para **Muito atrasado**. Se o ajuste do período da transação **Muito atrasado** não corrigir o erro, **as previsões de pagamento do cliente** não serão a melhor solução a ser usada, já que precisa de dados em cada categoria para fins de treinamento.

Para obter mais informações sobre como ajustar as categorias **No prazo**, **Atrasado** e **Muito atrasado**, consulte [Habilitar previsões de pagamento de cliente](../finance-insights/enable-cust-paymnt-prediction.md).

## <a name="symptom-model-training-failed"></a>Sintoma: falha no treinamento do modelo

### <a name="resolution"></a>Resolução

O treinamento do modelo **Previsão de fluxo de caixa** requer dados que contêm 100 ou mais transações que se estendem por mais de um ano. É recomendável ter pelo menos dois anos de dados com mais de 1.000 transações.

O recurso **Previsões de pagamento de cliente** requer mais de 100 transações nos seis a nove meses anteriores. As transações podem incluir faturas de texto livre, ordens de venda e pagamentos de cliente. Esses dados devem ser espalhados pelas configurações **No prazo**, **Atrasado** e **Muito atrasado** definidas na página **Configuração**.    

O recurso **Proposta de orçamento** exige um mínimo de três anos de orçamento ou dados reais. Esta solução usa de três a dez anos de dados nas projeções. Mais de três anos apresentarão resultados melhores. Os dados em si funcionam melhor quando há variação nos valores. Se os dados contiverem todos os dados constantes, como uma despesa de arrendamento, o treinamento poderá falhar porque a falta de variação não exige a IA para projetar os valores.

## <a name="symptom-error-message-states-that-the-table-with-name-msdyn_paypredpredictionresultentities-does-not-exist-the-remote-server-returned-an-error-404-not-found"></a>Sintoma: a mensagem de erro informa que a "tabela com o nome, "msdyn_paypredpredictionresultentities" não existe. O servidor remoto retornou um erro: (404) não encontrado..."

### <a name="resolution"></a>Resolução

O ambiente atingiu o limite máximo de tabela de Serviços do Data Lake. Para obter mais informações sobre o limite, consulte a seção **Habilitar alterações de dados quase em tempo real** do tópico [Visão geral da Exportação para o Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/Azure-Data-Lake-GA-version-overview.md).
