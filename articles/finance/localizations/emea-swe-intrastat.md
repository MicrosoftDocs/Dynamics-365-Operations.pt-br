---
title: Intrastat sueco
description: Este artigo contém informações sobre o relatório Intrastat na Suécia.
author: AdamTrukawka
ms.date: 08/24/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: ''
ms.openlocfilehash: e13076a6b8f18374c012a5b56f13e752010256b8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279221"
---
# <a name="swedish-intrastat"></a>Intrastat Sueco

[!include[banner](../includes/banner.md)]

A página **Intrastat** serve para gerar e relatar informações sobre o comércio entre os países da União Europeia (UE). A declaração Intrastat sueca contém informações sobre o comércio de mercadorias para relatórios.

Os seguintes campos estão incluídos na Declaração INTRASTAT Sueca:

   - Código ISO do país do parceiro
   - Código de transação
   - Código da mercadoria
   - Unidade adicional
   - Peso
   - Valor da fatura

## <a name="set-up-intrastat"></a>Configurar Intrastat

Importe a versão mais recente das seguintes configurações de relatório eletrônico (ER):

   - Módulo intrastat
   - Relatório intrastat
   - Intrastat (SE)

Para obter mais informações, consulte [Baixar configurações ER do repositório global de serviço de configuração](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

## <a name="set-up-foreign-trade-parameters"></a>Configurar parâmetros de comércio exterior

1. No Microsoft Dynamics 365 Finance, vá para **Imposto** > **Configuração** > **Parâmetros de comércio exterior**.
2. Na guia **Intrastat**, na Guia Rápida **Relatório eletrônico**, no campo **Mapeamento de formato de arquivo**, selecione **Intrastat (SE)**.
3. No campo **Mapeamento de formato de relatório**, selecione **Relatório Intrastat**.
4. Na Guia Rápida **Hierarquia de código de mercadoria**, no campo **Hierarquia de categoria**, selecione **Intrastat**.
5. No campo **Código da transação**, selecione o código da transação para transferências de propriedades. Você usa esse código para transações que produzem transferências reais ou planejadas da propriedade sobre compensação (financeira ou outra). Ele também é usado para correções. As empresas na Suécia usam códigos de transação de um dígito.
6. No campo **Nota de crédito**, selecione o código de transação para a devolução de bens.
7. Na guia **Propriedades de país/região**, no campo **País/região**, indique todos os países ou regiões com os quais sua empresa faz negócios. Para cada país que faz parte da UE, no campo **Tipo de país/região**, selecione **UE**, para que o país ou a região apareça no relatório Intrastat.

## <a name="set-up-the-product-parameters-for-the-intrastat-declaration"></a>Configurar os parâmetros de produto para a declaração Intrastat

1. Acesse **Gerenciamento de informações do produto** > **Produtos** > **Produtos liberados**.
2. Na grade, selecione um produto.
3. Na Guia Rápida **Comércio exterior**, na seção **Intrastat**, no campo **Mercadoria**, selecione o código da mercadoria.
4. Na Guia Rápida **Gerenciar estoque**, no campo **Peso líquido**, informe o peso do produto em quilogramas.
5. Acesse **Imposto** > **Configuração** > **Comércio exterior** > **Compactação do Intrastat** e selecione os campos que podem ser comparados quando a informação do Intrastat é resumida. Para a Intrastat sueco, selecione os valores para os seguintes campos:

    - Mercadoria
    - Código de transação
    - Direção
    - País/região
    - Correção
    - Fatura

## <a name="intrastat-transfer"></a>Transferência Intrastat

Na página **Intrastat**, no Painel de Ações, você pode selecionar **Transferir** para transferir automaticamente as informações sobre o comércio intracomunidade de ordens de venda, faturas de texto livre, ordens de compra, faturas de fornecedor, recebimentos de produtos do fornecedor, faturas de projeto e ordens de transferência. Somente os documentos que tiverem um país da UE como o país ou a região de destino (para envios) ou consignação (para recebimentos) serão transferidos.

Como alternativa, você pode inserir transações manualmente selecionando **Novo** no Painel de Ação.

### <a name="generate-an-intrastat-report"></a>Gerar um relatório do Intrastat

1. Acesse **Imposto** > **Declarações** > **Comércio exterior** > **Intrastat**.
2. No Painel de Ações, selecione **Saída** > **Relatório**.
3. Na caixa de diálogo **Relatório do Intrastat**, defina estes campos.

    | Campo            | descrição                                                                                                                         |
    |------------------|-------------------------------------------------------------------------------------------------------------------------------------|
    | Data Inicial        | Selecione a data de início do relatório.                                                                                               |
    | Data final          | Selecione a data de término do relatório.                                                                                                 |
    | Gerar arquivo    | Defina esta opção como **Sim** para gerar um arquivo .txt para seu relatório Intrastat.                                                       |
    | Nome do arquivo        | Insira o nome do arquivo .txt.                                                                                                    |
    | Gerar relatório  | Defina esta opção como **Sim** para gerar um arquivo .xlsx para seu relatório Intrastat.                                                     |
    | Nome do arquivo de relatório | Insira o nome do arquivo .xlsx.                                                                                                   |
    | Direção        | Selecione **Entradas** para um relatório sobre as entradas de intracomunidade. Selecione **Expedições** para um relatório sobre expedições de intracomunidade. |

4. Selecione **OK** e revise os relatórios gerados.

## <a name="example"></a>Exemplo

Este exemplo mostra como lançar entradas e expedições para o Intrastat. Ele usa a entidade legal **DEMF**.

### <a name="preliminary-setup"></a>Configuração preliminar

1. Vá para **Administração da organização** > **Organização** > **Entidades legal** e selecione a entidade legal **DEMF**.
2. Na Guia Rápida **Endereços**, selecione **Editar** e, no campo **País/região**, selecione **SUE (Suécia)**.
3. Importe a versão mais recente das seguintes configurações de relatório eletrônico (ER):

    - Módulo intrastat
    - Relatório intrastat
    - Intrastat (SE)

### <a name="create-transaction-codes"></a>Crie códigos de transação

1. Acesse **Imposto** > **Configuração** > **Comércio exterior** > **Códigos de transação**.
2. No Painel de Ações, selecione **Novo**.
3. No campo **Código** **de transação**, insira **1**.
4. No campo **Nome**, digite **Transações normais**
5. No Painel de ações, selecione **Salvar**.

### <a name="set-up-foreign-trade-parameters"></a>Configurar parâmetros de comércio exterior

1. Acesse **Imposto** > **Configuração** > **Comércio exterior** > **Parâmetros de comércio exterior**.
2. Na guia **Intrastat**, na Guia Rápida **Geral**, no campo **Código** **de transação**, selecione **1**.
3. Na Guia Rápida **Relatório eletrônico**, no campo **Mapeamento de formato de arquivo**, selecione **Intrastat (SE)**.
4. No campo **Mapeamento de formato de relatório**, selecione **Relatório Intrastat**.
5. Na Guia Rápida **Hierarquia de código de mercadoria**, no campo **Hierarquia de categoria**, certifique-se de que **Intrastat** esteja selecionado.
6. Na guia **Propriedades de país/região**, selecione **Novo**.
7. No campo **País/região do participante**, selecione **SWE**.
8. No campo **Tipo de país/região**, selecione **Doméstico**.
9. No campo **País/região do participante**, selecione **DEU** e, em seguida, no campo **Tipo de país/região**, selecione **EU**.

### <a name="set-up-product-information"></a>Configurar informações do produto

1. Vá para **Gerenciamento de informações do produto** > **Produtos** > **Produtos liberados**.
2. Na grade, selecione **D0001**.
3. Na Guia Rápida **Comércio exterior**, na seção **Intrastat**, no campo **Mercadoria**, selecione **100 200 30**.
4. Na Guia Rápida **Gerenciar estoque**, na seção **Medidas de peso**, no campo **Peso líquido**, digite **5**.
5. No Painel de ações, selecione **Salvar**.

### <a name="change-the-site-address"></a>Altere o endereço do site

1. Vá para **Gerenciamento de depósito** > **Configuração** > **Configuração** > **Locais**.
2. Na grade, selecione **1**.
3. Na Guia Rápida **Endereços**, selecione **Editar**.
4. Na caixa de diálogo **Editar endereço**, no campo **País/região**, selecione **SWE**.
5. Selecione **OK**.

### <a name="create-a-sales-order-with-an-eu-customer"></a>Crie uma ordem de venda com um cliente da UE

1. Acesse **Contas a receber** > **Ordens** > **Todas as ordens de venda**.
2. No Painel de Ações, selecione **Novo**.
3. Na caixa de diálogo **Criar ordem de venda**, na Guia Rápida **Cliente**, na seção **Cliente**, no campo **Conta do cliente**, selecione **DE-015**.
4. Na Guia Rápida **Geral**, na seção **Dimensões de armazenamento**, no campo **Site**, selecione **1**.
5. No campo **Depósito**, selecione **11**.
6. Selecione **OK**.
7. Na guia **Linhas**, na Guia Rápida **Linhas de ordem de venda**, no campo **Número do item**, selecione **D0001**. Depois, no campo **Quantidade**, insira **10**.
8. Na Guia Rápida **Detalhes da linha**, na guia **Comércio exterior**, certifique-se de que os campos **Código da transação** e **Mercadoria** são definidos automaticamente.
9. No Painel de ações, selecione **Salvar**.
10. No Painel de Ação, na guia **Fatura**, na seção **Gerar**, selecione **Fatura**.
11. Na caixa de diálogo **Lançando fatura**, na Guia Rápida **Parâmetros**, na seção **Parâmetro**, no campo **Quantidade**, selecione **Tudo**.
12. Selecione **OK** para lançar a fatura.

### <a name="transfer-the-transaction-to-the-intrastat-journal-and-review-the-result"></a>Transfira a transação para o diário Intrastat e revise o resultado

1. Acesse **Imposto** > **Declarações** > **Comércio exterior** > **Intrastat**.
2. No Painel de Ação, selecione **Transferir**.
3. Na caixa de diálogo **Intrastat (Transferência)**, na seção **Parâmetros**, defina a opção **Fatura de cliente** como **Sim**.
4. Selecione **Filtro**.
5. Na caixa de diálogo **Filtro Intrastat**, na guia **Intervalo**, selecione a primeira linha e verifique se o campo **Campo** está definido como **Data**.
6. No campo **Critérios**, selecione a data atual.
7. Selecione **OK** para fechar a caixa de diálogo **Filtro Intrastat**.
8. Selecione **OK** para fechar a caixa de diálogo **Intrastat (Transferência)** e revisar o resultado. A linha representa a ordem de venda que você criou anteriormente.

    ![Linhas do diário Intrastat para ordem de venda](media/swe_intrastat_journal_sales_order.png)

9. Selecione a linha de transação e, em seguida, a guia **Geral** para exibir mais detalhes.

    ![Detalhes da linha do diário Intrastat para ordem de venda](media/swe_intrastat_journal_sales_order_line_details.png)

10. No Painel de Ações, selecione **Saída** > **Relatório**.
11. Na caixa de diálogo **Relatório Intrastat**, na Guia Rápida **Parâmetros**, na seção **Data**, selecione o mês da ordem de venda que você criou.
12. Na seção **Opções** **de exportação**, defina a opção **Gerar arquivo** como **Sim**. Em seguida, no campo **Nome do arquivo**, insira o nome necessário.
13. Defina a opção **Gerar relatório** como **Sim**. Em seguida, no campo **Nome do arquivo do relatório**, insira o nome necessário.
14. No campo **Direção**, selecione **Expedições**.
15. Selecione **OK** e revise o relatório no formato .txt que foi gerado. A tabela a seguir mostra os valores no relatório de exemplo.

    | Código ISO do país do parceiro | Código de transação | Código da mercadoria | Unidade adicional | Peso | Valor da fatura |
    |--------------------------|------------------|----------------|-----------------|--------|----------------|
    | IT                       | 1                | 10020030       | 0               | 50     | 3290           |

16. Revise o relatório no formato do Excel que foi gerado.

    ![Relatório intrastat](media/swe_intrastat_report_for_dispatches.png)

### <a name="create-a-purchase-order"></a>Criar uma ordem de compra

1. Vá para **Contas a pagar** > **Ordens de compra** > **Todas as ordens de compra**.
2. No Painel de Ações, selecione **Novo**.
3. Na caixa de diálogo **Criar ordem de venda**, no campo **Conta do fornecedor**, selecione **DE-001**.
4. Selecione **OK**.
5. Na guia **Cabeçalho**, na FastTAb **Comércio** **exterior**, verifique se o campo **Código da transação** está definido como **1**.
6. Na guia **Linhas**, na Guia Rápida **Linhas de ordem de compra**, no campo **Número do item**, selecione **D0001**. Depois, no campo **Quantidade**, insira **6**.
7. No Painel de Ação, na guia **Compra**, no grupo **Ações**, selecione **Confirmar**.
8. No Painel de Ação, na guia **Fatura**, no grupo **Gerar**, selecione **Fatura**.
9. No Painel de Ações, selecione **Padrão de**. No campo **Quantidade padrão para linhas**, selecione **Quantidade encomendada**. Em seguida, selecione **OK**.
10. Na Guia Rápida **Cabeçalho da fatura de fornecedor**, na seção **Identificação da fatura**, no campo **Número**, digite **0001**.
11. No Painel de Ações, selecione **Lançar** para lançar a fatura.

### <a name="create-an-intrastat-declaration-for-arrivals"></a>Criar uma declaração Intrastat para entradas

1. Acesse **Imposto** > **Declarações** > **Comércio exterior** > **Intrastat**.
2. No Painel de Ação, selecione **Transferir**.
3. Na caixa de diálogo **Intrastat (Transferência)**, defina a opção **Fatura do fornecedor** como **Sim**.
4. Selecione **OK** para transferir as transações e revise o diário Intrastat.

    ![Diário Intrastat para ordem de compra](media/swe_intrastat_journal_purchase_order.png)

5. Revise a guia **Geral** da ordem de compra.

    ![Detalhes da linha do diário Intrastat para ordem de compra](media/swe_intrastat_journal_purchase_order_line_details.png)

6. No Painel de Ações, selecione **Saída** > **Relatório**.
7. Na caixa de diálogo **Relatório Intrastat**, na Guia Rápida **Parâmetros**, na seção **Data**, selecione o mês da ordem de venda que você criou.
8. Na seção **Opções** **de exportação**, defina a opção **Gerar arquivo** como **Sim**. Em seguida, no campo **Nome do arquivo**, insira o nome necessário.
9. Defina a opção **Gerar relatório** como **Sim**. Em seguida, no campo **Nome do arquivo do relatório**, insira o nome necessário.
10. No campo **Direção**, selecione **Entradas**.
11. Selecione **OK** e revise o relatório no formato .txt que foi gerado. A tabela a seguir mostra os valores no relatório de exemplo.

    | Código ISO do país do parceiro | Código de transação | Código da mercadoria | Unidade adicional | Peso | Valor da fatura |
    |--------------------------|------------------|----------------|-----------------|--------|----------------|
    | IT                       | 1                | 10020030       | 0               | 30     | 1714           |

12. Revise o relatório no formato do Excel que foi gerado.

    ![Relatório de entradas do Intrastat](media/swe_intrastat_arrivals_report.png)
