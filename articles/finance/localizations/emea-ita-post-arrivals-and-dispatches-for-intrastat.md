---
title: Lançar entradas e expedições para o Intrastat
description: Este tópico fornece um exemplo que mostra como lançar entradas e expedições para o Intrastat.
author: andosip
ms.date: 8/23/2021
ms.topic: article
audience: Application User
ms.reviewer: kfender
ms.search.region: Global
ms.author: v-aosipov
ms.search.validFrom: ''
ms.openlocfilehash: f7bd1811fd0e580a6b6655244c689268915d320e
ms.sourcegitcommit: 72a82e9aeabbdecf57e1aee72975c63eba75143a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/24/2021
ms.locfileid: "7414778"
---
# <a name="post-arrivals-and-dispatches-for-intrastat"></a>Lançar entradas e expedições para o Intrastat

[!include [banner](../includes/banner.md)]

Este tópico fornece um exemplo que mostra como lançar entradas e expedições para o Intrastat. O exemplo usa a entidade legal **ITCO**.

## <a name="setup"></a>Configurar

1. Importe a versão mais recente das seguintes configurações de relatório eletrônico (ER):

    - Módulo intrastat
    - Relatório intrastat
    - Intrastat (IT)

    Obtenha mais detalhes em [Baixar configurações ER do repositório global de serviço de configuração](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

2. No Microsoft Dynamics 365 Finance, defina as sequências numéricas a seguir como contínuas: **Gene\_397**, **Acco\_16403**, **Gene\_407** e **PUR\_EU**.

    1. Vá para **Administração da organização** > **Sequências numéricas** > **Sequências numéricas**.
    2. Na grade, selecione um dos códigos de sequência numérica.
    3. No Painel de Ações, selecione **Editar**.
    4. Na FastTab **Geral**, na seção **Configuração**, defina a opção **Contínua** como **Sim**.
    5. No Painel de ações, selecione **Salvar**.

3. Defina um endereço de depósito.

    1. Acesse **Gerenciamento de depósito** &gt; **Configuração** &gt; **Depósito** &gt; **Depósitos**.
    2. Na lista, selecione depósito **11**.
    3. Na FastTab **Endereço**, selecione **Adicionar**.
    4. Na caixa de diálogo **Novo** **endereço**, no campo **Nome** **ou** **descrição**, digite **Principal**.
    5. No campo **País/região**, selecione **ITA (Itália)**.
    6. No campo **Cidade**, selecione **Aprilia**.
    7. Selecione **OK**.

4. Configurar códigos da transação.

    1. Acesse **Imposto** > **Configuração** > **Comércio exterior** > **Códigos de transação**.
    2. Selecione **Novo** e configure um código de transação para as transferências de propriedade.

        - No campo **Código de transação**, insira **1**.
        - No campo **Nome**, informe **Transferência de propriedade**.

    3. Selecione **Novo** e configure um código de transação para devoluções.

        - No campo **Código** **de transação**, insira **2**.
        - No campo **Nome**, insira **Devolução de bens**.

5.  Configure os parâmetros de comércio exterior.

    1. Acesse **Imposto** > **Configuração** > **Comércio exterior** > **Parâmetros de comércio exterior**.
    2. Na guia **Intrastat**, na FastTab **Geral**, no campo **Código** **de transação**, selecione **1**.
    3. No campo **Nota de crédito**, selecione **2**.
    4. No campo **Período do relatório de vendas**, selecione **Mês**.
    5. No campo **Período do relatório de compras**, selecione **Mês**.
    6. Na FastTab **Relatório eletrônico**, no campo **Mapeamento de formato de arquivo**, selecione **Intrastat (IT)**.
    7. No campo **Mapeamento de formato de relatório**, selecione **Relatório Intrastat**.
    8. Na FastTab **Hierarquia de código de mercadoria**, no campo **Hierarquia de categoria**, selecione **Intrastat**.
    9. Na FastTab **Valor estatístico**, defina a opção **Imprimir e exportar dados estatísticos** como **Sim**, se necessário.
    10. Na guia **Propriedades de país/região**, verifique se as linhas a seguir existem.

        | **Participante/país/região** | **Código Intrastat** | **Moeda** | **Tipo de país/região** |
        |--------------------------|--------------------|--------------|-------------------------|
        | ITA                      | IT                 | EUR          | Doméstico                |
        | SMR                      | SM                 | EUR          | Doméstico especial        |

    11. Na barra de ferramentas, selecione **Novo** para criar a seguinte linha.

        | **Participante/país/região** | **Código Intrastat** | **Moeda** | **Tipo de país/região** |
        |--------------------------|--------------------|--------------|-------------------------|
        | DNK                      | DK                 | DKK          | UE                      |

6. Configurar números de isenção de impostos.

    1. Vá para **Imposto** > **Configuração** > **Imposto** > **Números de isenção de imposto**.
    2. No Painel de Ações, selecione **Novo** para criar as seguintes linhas.

        | **País/região** | **Número de isenção de imposto** | **Nome da empresa** |
        |--------------------|-----------------------|------------------|
        | DEU                | DE3456789012          | FORNECEDOR DA UE        |
        | DNK                | DK0987654321          | ER do Cliente      |

7. Define o endereço do fornecedor.

    1. Acesse **Contas a pagar** &gt; **Fornecedores** &gt; **Todos os fornecedores**.
    2. Na grade, selecione **Fornecedor UE**.
    3. Na FastTab **Endereço**, selecione **Adicionar**.
    4. Na caixa de diálogo **Novo endereço**, no campo **Nome ou descrição**, insira **Alemanha**.
    5. No campo **País/região**, selecione **DEU**.
    6. Selecione **OK** para criar o novo endereço.
    7. Na FastTab **Fatura e entrega**, na seção **Imposto**, no campo **Número de isenção de imposto**, selecione **Tudo** e depois **DE1234567890**.
    8. No Painel de ações, selecione **Salvar**.

8. Definir endereços de clientes.

    1. Vá para **Contas a receber** > **Clientes** > **Todos os clientes**.
    2. Na grade, selecione **ITCO-000001**.
    3. Na FastTab **Endereços**, selecione **Editar**.
    4. Na caixa de diálogo **Novo endereço**, no campo **Nome ou descrição**, insira **San Marino**.
    5. No campo **País/região**, selecione **SMR**.
    6. Selecione **OK** para criar o novo endereço.
    7. Na FastTab **Fatura e entrega**, na seção **Fatura**, no campo **Conta da fatura**, selecione **ITCO-000001**.
    8. No campo **Grupo de sequências numéricas**, selecione **IT\_VENDOM**.
    9. No Painel de ações, selecione **Salvar**, e feche a página.
    10. Na página **Todos os clientes**, na grade, selecione **ITCO-000002**.
    11. Na FastTab **Endereços**, selecione **Adicionar**.
    12. Na caixa de diálogo **Novo endereço**, no campo **Nome ou descrição**, insira **Dinamarca**.
    13. No campo **País/região**, selecione **DNK**.
    14. Selecione **OK** para criar o novo endereço.
    15. Na FastTab **Dados demográficos de vendas**, no campo **Moeda**, selecione **DKK**.
    16. Na FastTab **Fatura e entrega**, na seção **Imposto**, no campo **Grupo de impostos**, selecione **IT\_PUREU**.
    17. No campo **Número de isenção de imposto**, selecione **Tudo** e selecione **DK0987654321**.
    18. No Painel de ações, selecione **Salvar**.

9. Configurar a hierarquia de categoria.

    1. Vá para **Gerenciamento de informações sobre o produto** > **Configuração** > **Categorias e atributos** > **Hierarquias da categoria**.
    2. Na grade, selecione **Intrastat**.
    3. No Painel de Ações, selecione **Novo nó de categoria**.
    4. No campo **Nome**, digite **Serviço**.
    5. No campo **Código**, insira **123456**.
    6. No Painel de ações, selecione **Salvar**.

10. Configure produtos.

    1. Vá para **Gerenciamento de informações sobre o produto** > **Produtos** > **Produtos liberados**.
    2. Na grade, selecione **ITEM**.
    3. Na FastTab **Compras**, na seção **Administração**, no campo **Fornecedor**, selecione **ITCO-000001**.
    4. Na FastTab **Comércio exterior**, na seção **Intrastat**, no campo **Mercadoria**, selecione **\[100 200 30\] Palestrante**.
    5. Na seção **Origem**, no campo **País/região**, selecione **DEU**.
    6. No campo **Estado/província**, selecione **BE**.
    7. Na FastTab **Gerenciar estoque**, na seção **Medidas líquidas**, no campo **Peso líquido**, digite **5**.
    8. No Painel de ações, selecione **Salvar**.
    9. Na página **Produtos liberados**, na grade, selecione **Item de Serviço**.
    10. Na FastTab **Comércio exterior**, na seção **Intrastat**, no campo **Mercadoria**, selecione **\[123456\] Serviço**.
    11. No Painel de ações, selecione **Salvar**.

11. Configurar métodos de transporte.

    1. Vá para **Imposto** > **Configuração** > **Comércio exterior** > **Método de transporte**.
    2. No Painel de Ações, selecione **Novo** para criar os seguintes métodos de transporte.

        | **Transporte** | **Descrição** |
        |---------------|-----------------|
        | 1             | Rodoviário            |
        | 2             | Via aérea             |

12. Configurar um modo de entrega.

    1. Acesse **Compras e fornecimento** > **Configuração** > **Distribuição** > **Modos de entrega**.
    2. No Painel de Ações, selecione **Novo**.
    3. No campo **Modo de entrega**, digite **1**.
    4. No campo **Descrição**, insira **Caminhão**.
    5. Na FastTab **Comércio exterior**, no campo **Transporte**, selecione **Rodoviário 1**.
    6. No Painel de ações, selecione **Salvar**.

13. Configurar condições de entrega.

    1. Vá para **Contas a pagar** > **Configurar** > **Condições de entrega**.
    2. Na lista, selecione **CFR**.
    3. Na FastTab **Geral**, no campo **Código Intrastat**, digite **1**.

## <a name="post-arrivals-for-intrastat"></a>Lançar entradas para Intrastat

### <a name="purchase-goods-by-using-a-purchase-order"></a>Comprar mercadorias usando uma ordem de compra

Esta parte do exemplo mostra como usar uma ordem de compra para comprar mercadorias (itens) dos países da União Europeia (UE).

1. Vá para **Contas a pagar** > **Ordens de compra** > **Todas as ordens de compra**.
2.  No Painel de Ações, selecione **Novo**.
3.  Na caixa de diálogo **Criar ordem de compra**, no campo **Conta do fornecedor**, selecione **Fornecedor UE**.
4.  Na FastTab **Administração**, no campo **Idioma**, selecione **it**.
5.  Selecione **OK**.
6.  Na exibição **Cabeçalho**, na FastTab **Comércio** **exterior**, verifique se o campo **Código da transação** está definido como **1**.
7.  Verifique se o campo **Região de origem/destino** está definido como **RM**.
8.  Na FastTab **Entrega**, na seção **Entrega**, no campo **Modo de entrega**, selecione **1**.
9.  No campo **Condições de entrega**, selecione **CFR**.
10. Na exibição **Linhas**, na FastTab **Linhas da ordem de compra**, no campo **Número do item**, selecione **Item**.
11. No campo **Local**, selecione **1**.
12. No campo **Depósito**, selecione **11**.
13. No campo **Quantidade**, insira **10**.
14. No campo **Preço unitário**, insira **100**.
15. Na guia **Configuração**, na seção **Imposto**, no campo **Grupo de impostos do item**, selecione **22%EU**.
16. No Painel de Ação, na guia **Compra**, no grupo **Ações**, selecione **Confirmar**.
17. No Painel de Ação, na guia **Fatura**, no grupo **Gerar**, selecione **Fatura**.
18. No Painel de Ações, selecione **Padrão de**.
19. No campo **Quantidade padrão de linhas**, selecione **Quantidade solicitada** e selecione **OK**.
20. Na FastTab **Cabeçalho da fatura de fornecedor**, na seção **Identificação da fatura**, no campo **Número**, digite **0001**.
21. Na seção **Datas da fatura**, no campo **Data da fatura**, selecione **7/9/2021**.
22. No Painel de Ações, selecione **Lançar** para lançar a fatura.

### <a name="purchase-services-by-using-a-vendor-invoice"></a>Comprar serviços usando uma fatura de fornecedor

Esta parte do exemplo mostra como usar uma fatura de fornecedor para comprar serviços dos países da UE.

1. Vá para **Contas a pagar** > **Faturas** > **Diário de fatura**.
2. No Painel de Ações, selecione **Novo**.
3. No campo **Nome**, selecione **VEND\_EUINV**.
4. No Painel de Ações, selecione **Linhas**.
5. No campo **Data**, insira **7/9/2021**.
6. No campo **Tipo de conta**, selecione **Fornecedor**.
7. No campo **Conta**, selecione **Fornecedor da UE**.
8. No campo **Data da fatura**, selecione **9/7/2021**.
9. No campo **Fatura**, digite **ITA-0004**.
10. No campo **Crédito**, digite **120000**.
11. No campo **Tipo de** **contrapartida**, selecione **Razão**.
12. No campo **Contrapartida**, selecione **110130**.
13. No campo **Grupo de impostos**, selecione **IT\_PUREU**.
14. No campo **Grupo de impostos do item**, selecione **22%EU**.
15. Na guia **Comércio exterior**, siga estas etapas:

    1. No campo **Código de transação**, selecione **1**.
    2. No campo **Transporte**, selecione **Aéreo 2**.
    3. No campo **Mercadoria**, selecione **\[123456\] Serviço**.
    4. No campo **País/região**, selecione **ITA**.
    5. No campo **Estado/província**, selecione **LAZ**.
    6. No campo **Região de origem/destino**, selecione **LT**.


16. No Painel de Ação, selecione **Lançar**.
17. Criar uma declaração Intrastat para entradas.

    1. Acesse **Imposto** > **Declarações** > **Comércio exterior** > **Intrastat**.
    2. No Painel de Ação, selecione **Transferir**.
    3. Na caixa de diálogo **Intrastat (Transferência)**, defina a opção **Fatura do fornecedor** como **Sim**.
    4. Selecione **OK** para transferir as transações e depois revise o diário Intrastat.

   ![Página diário Intrastat, guia Visão geral.](media/ita_intrastat_journal_vendor_invoice.png)

18. Revise a guia **Geral** da ordem de compra.

    ![Detalhes da linha do diário Intrastat para ordem de compra](media/ita_intrastat_journal_purchase_order_line_details.png)

19. Revise a guia **Geral** da fatura de fornecedor.

    ![Detalhes da linha do diário Intrastat para fatura de fornecedor](media/ita_intrastat_journal_vendor_invoice_line_details.png)

20. Gera o relatório Intrastat para entradas.

    1. No Painel de Ações, selecione **Saída** > **Relatório**.
    2. Na caixa de diálogo **Relatório Intrastat**, na seção **Data**, no campo **Data inicial**, selecione **1/7/2021**.
    3. No campo **Data final**, selecione **31/7/2021**.
    4. Na seção **Opções de exportação**, defina as opções **Gerar arquivo** e **Gerar relatório** como **Sim**.
    5. No campo **Nome de arquivo**, digite **Arquivo de Entrada**.
    6. No campo **Nome do arquivo de relatório**, digite **Relatório de Entrada**.
    7. No campo **Direção**, selecione **Entradas**.
    8. No campo **Número de referência**, insira **123456**.
    9. Selecione **OK** para gerar o relatório Intrastat e o arquivo Intrastat e examine-os.

    A ilustração a seguir mostra um exemplo de um relatório Intrastat.

    ![Relatório de entradas do Intrastat.](media/ita_intrastat_arrivals_report.png)

    A ilustração a seguir mostra um exemplo de um arquivo Intrastat..

    ![Arquivo de entradas do Intrastat.](media/ita_intrastat_arrivals_file.png)

## <a name="post-dispatches-for-intrastat"></a>Lançar expedições para Intrastat

### <a name="sell-goods-by-using-a-sales-order"></a>Vender mercadorias usando uma ordem de venda

Esta parte do exemplo mostra como usar uma ordem de venda para vender mercadorias (itens) dos países da União Europeia (UE).

1. Acesse **Contas a receber** > **Ordens** > **Todas as ordens de venda**.
2. No Painel de Ações, selecione **Novo**.
3. Na caixa de diálogo **Criar ordem de venda**, no campo **Conta do cliente**, selecione **ITCO-000002**.
4. Selecione **OK**.
5. Na exibição **Cabeçalho**, na FastTab **Entrega**, na seção **Informações de entrega diversas**, no campo **Modo de entrega** selecione **Caminhão 1**.
6. No campo **Condições de entrega**, selecione **CFR**.
7. Na exibição **Linhas**, na FastTab **Linhas da ordem de venda**, no campo **Número do item**, selecione **ITEM**.
8. No campo **Quantidade**, insira **50**.
9. No campo **Local**, selecione **1**.
10. No campo **Depósito**, selecione **11**.
11. No campo **Preço unitário**, insira **250**.
12. Na FastTab **Detalhes da linha**, na guia **Configuração**, na seção **Imposto**, no campo **Grupo de impostos do item**, selecione **22%EU**.
13. No Painel de ações, selecione **Salvar**.
14. No Painel de Ações, na guia **Fatura**, no grupo **Gerar**, selecione **Fatura** para criar a fatura da ordem.
15. Na caixa de diálogo **Lançando fatura**, na FastTab **Parâmetros**, na seção **Parâmetro**, no campo **Quantidade**, selecione **Tudo**.
16. Na FastTab **Configurar**, no campo **Data da** **fatura**, selecione **9/7/2021**.
17. Selecione **OK**.
18. Revise as linhas do diário do Intrastat.

    1. Acesse **Imposto** > **Declarações** > **Comércio exterior** > **Intrastat**.
    2. No Painel de Ação, selecione **Transferir**.
    3. Na caixa de diálogo **Intrastat (Transferência)**, defina a opção **Fatura do cliente** como **Sim**.
    4. Selecione **OK** para transferir as transações e revise o diário Intrastat. A transação da nota de crédito é marcada como uma correção e tem um valor negativo da fatura.

        ![Página do diário do Intrastat](media/ita_intrastat_journal_sales_order.png)

        ![Detalhes da linha do diário Intrastat para ordem de venda](media/ita_intrastat_journal_sales_order_line_details.png)

### <a name="return-goods-by-using-a-credit-note"></a>Devolver mercadorias usando uma nota de crédito

Esta parte do exemplo mostra como usar uma nota de crédito para devolver mercadorias (itens) dos países da União Europeia (UE).

1. Acesse **Contas a receber** > **Ordens** > **Todas as ordens de venda**.
2. No Painel de Ações, selecione **Novo**.
3. Na caixa de diálogo **Criar ordem de venda**, no campo **Conta do cliente**, selecione **ITCO-000002**.
4. Selecione **OK**.
5. Na exibição **Cabeçalho**, na FastTab **Entrega**, na seção **Informações de entrega diversas**, no campo **Modo de entrega** selecione **Caminhão 1**.
6. No campo **Condições de entrega**, selecione **CFR**.
7. Na FastTab **Comércio exterior**, no campo **Código da transação**, selecione **2**.
8. Na guia **Linhas**, na FastTab **Linhas de ordem de venda**, no campo **Número do item**, selecione **ITEM**.
9. No campo **Quantidade**, digite **-10**.
10. No campo **Local**, selecione **1**.
11. No campo **Depósito**, selecione **11**.
12. No campo **Preço unitário**, insira **250**.
13. Na FastTab **Detalhes da linha**, na guia **Configuração**, na seção **Imposto**, no campo **Grupo de impostos do item**, selecione **22%EU**.
14. Na seção **Ordem devolvida**, no campo **Devolver ID de Lote**, selecione o lote que você criou anteriormente.
15. No Painel de ações, selecione **Salvar**.
16. No Painel de Ações, na guia **Fatura**, no grupo **Gerar**, selecione **Fatura** para criar a fatura da ordem.
17. Na FastTab **Parâmetros**, na seção **Parâmetro**, no campo **Quantidade**, selecione **Tudo**.
18. Na caixa de diálogo **Lançando fatura**, na FastTab **Configuração**, no campo **Data da** **Fatura**, selecione **9/7/2021**.
19. Selecione **OK** para lançar a fatura.
20. Revise as linhas do diário do Intrastat.

    1. Acesse **Imposto** > **Declarações** > **Comércio exterior** > **Intrastat**.
    2. No Painel de Ação, selecione **Transferir**.
    3. Na caixa de diálogo **Intrastat (Transferência)**, defina a opção **Fatura do cliente** como **Sim**.
    4. Selecione **OK** para transferir as transações e revise o diário Intrastat. A transação da nota de crédito é marcada como uma correção e tem um valor negativo da fatura.

    ![Nota de crédito do diário Intrastat](media/ita_intrastat_journal_credit_note.png)

    ![Detalhes da linha do diário Intrastat para nota de crédito](media/ita_intrastat_journal_credit_note_line_details.png)

### <a name="sell-goods-to-san-marino-by-using-a-sales-order"></a>Vender mercadorias para San Marino usando uma ordem de venda

Esta parte do exemplo mostra como usar uma ordem de venda para comprar mercadorias (itens) para San Marino.

1. Acesse **Contas a receber** > **Ordens** > **Todas as ordens de venda**.
2. No Painel de Ações, selecione **Novo**.
3. Na caixa de diálogo **Criar ordem de venda**, no campo **Conta do cliente**, selecione **ITCO-000001**.
4. Selecione **OK**.
5. Na exibição **Cabeçalho**, na FastTab **Entrega**, na seção **Informações de entrega diversas**, no campo **Modo de entrega** selecione **1**.
6. No campo **Condições de entrega**, selecione **CFR**.
7. Na guia **Linhas**, na FastTab **Linhas de ordem de venda**, no campo **Número do item**, selecione **ITEM**.
8. No campo **Quantidade**, insira **30**.
9. No campo **Local**, selecione **1**.
10. No campo **Depósito**, selecione **11**.
11. No campo **Preço unitário**, insira **200**.
12. No Painel de ações, selecione **Salvar**.
13. No Painel de Ações, na guia **Fatura**, no grupo **Gerar**, selecione **Fatura** para criar a fatura da ordem.
14. Na FastTab **Parâmetros**, na seção **Parâmetro**, no campo **Quantidade**, selecione **Tudo**.
15. Na caixa de diálogo **Lançando fatura**, na FastTab **Configuração**, no campo **Data da** **Fatura**, selecione **9/7/2021**.
16. Selecione **OK** para lançar a fatura.
17. Revise as linhas do diário do Intrastat.

    1. Acesse **Imposto** > **Declarações** > **Comércio exterior** > **Intrastat**.
    2. No Painel de Ação, selecione **Transferir**.
    3. Na caixa de diálogo **Intrastat (Transferência)**, defina a opção **Fatura do cliente** como **Sim**.
    4. Selecione **OK** para transferir as transações e revise o diário Intrastat.

   ![Diário Intrastat para San Marino](media/ita_intrastat_journal_sales_order_san_marino.png)

   ![Detalhes da linha do diário Intrastat para San Marino](media/ita_intrastat_journal_sales_order_san_marino_line_details.png)

18. Criar uma declaração Intrastat para expedições.

    1. Acesse **Imposto** &gt; **Declarações** &gt; **Comércio exterior** &gt; **Intrastat**.
    2. No Painel de Ações, selecione **Exportar** &gt; **Relatório**.
    3. Na caixa de diálogo **Relatório Intrastat**, na seção **Data**, no campo **Data inicial**, selecione **1/7/2021**.
    4. No campo **Data final**, selecione **31/7/2021**.
    5. Na seção **Opções de exportação**, defina as opções **Gerar arquivo** e **Gerar relatório** como **Sim**.
    6. No campo **Nome de arquivo**, digite **Arquivo de Expedições**.
    7. No campo **Nome do arquivo de relatório**, digite **Relatório de Expedições**.
    8. No campo **Direção**, selecione **Expedições**.
    9. No campo **Número de referência**, insira **98754**.
    10. Selecione **OK** para gerar o relatório Intrastat e o arquivo Intrastat.

        A ilustração a seguir mostra um exemplo de um relatório Intrastat impresso.

        ![Relatório intrastat](media/ita_intrastat_report_for_dispatches.png)

        A ilustração a seguir mostra um exemplo de um arquivo Intrastat impresso.

        ![Arquivo Intrastat para expedições](media/ita_intrastat_file_for_dispatches.png)
