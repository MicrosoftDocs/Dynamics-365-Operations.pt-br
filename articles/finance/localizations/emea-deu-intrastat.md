---
title: Intrastat alemã
description: Este artigo contém informações sobre a declaração Intrastat na Alemanha.
author: anasyash
ms.date: 09/09/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: ''
ms.openlocfilehash: 9516a4516488282820659da141fe3ad33fbe3a9d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848450"
---
# <a name="german-intrastat"></a>Intrastat alemã

[!include [banner](../includes/banner.md)]

A página **Intrastat** serve para gerar e relatar informações sobre o comércio entre os países da União Europeia (UE). A declaração Intrastat alemã contém informações sobre o comércio de mercadorias para relatórios. O relatório é formatado de acordo com as diretrizes das autoridades alemãs apresentadas nas [Declarações do arquivo 6.2 no formato do INSTAT/XML](https://www-idev.destatis.de/idev/doc/intra_en/hilfe6_2.html).

A tabela abaixo mostra os campos que são incluídos na Declaração Intrastat alemã.

| Campos | Expedições | Entradas |
|-------------------------|-------------------------|-------------------------|
| Período de referência | X | X |
| Código de direção | X | X |
| Moeda da declaração Intrastat</br>**Observação:** esta moeda está na <em>moeda contábil</em>. | X | X |
| Código da mercadoria | X | X |
| Nome da mercadoria | X | X |
| Código de unidade suplementar | X | X |
| Estado do membro de consignação/destino | X | X |
| Massa líquida | X | X |
| Quantidade em unidades suplementares | X | X |
| País de origem |  | X |
| Valor da fatura | X |  |
| Valor estatístico | X | X |
| Natureza das transações | X | X |
| Modo de transporte | X | X |
| Código da região</br>**Nota:**</br><ul></br><li>Se o país ou a região de origem for a Alemanha e a fatura for para expedições, será exibido um código Intrastat para o estado de origem.</li></br><li>Se o país ou a região de origem não for a Alemanha e a fatura for para expedições, o código **99** será mostrado.</li></br><li>Se a fatura for para entradas, será exibido um código Intrastat para o estado.</li></br></ul> | X | X |
| Código de porto/aeroporto/porta de entrada | X | X |
| Condições de entrega | X | X |


## <a name="set-up-intrastat"></a>Configurar Intrastat

1. Configurar os códigos da empresa.

    1. Acesse **Administração da organização** > **Organizações** > **Entidades legais**.
    2. Na FatsTab **Comércio exterior e Logística**, na seção **Identificação**, no campo **DVR**, insira a ID do Contrato de intercâmbio. A ID será incluída no relatório.
    3. No campo **Exportação do número de isenção de IVA**, insira o número de imposto sobre valor agregado (IVA) da sua empresa para exportação.
    4. No campo **Importação do número de isenção de IVA**, insira o número de IVA da sua empresa para importação.
    5. No campo **Código Intrastat**, insira o código Intrastat atribuído à entidade legal.
    6. Na Guia Rápida **Registro de imposto**, no campo **Número de registro de imposto**, insira o número de registro de imposto da sua empresa.

    > [!NOTE]
    > Se você gerar um relatório Intrastat para afiliados, no campo **Número de registro de imposto**, insira o número de registro de imposto da sua empresa pai.

2. No [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index), na biblioteca de ativos compartilhados, baixe as versões mais recentes das seguintes configurações de Relatório Eletrônico (ER) para a declaração Intrastat.

    - Módulo intrastat
    - Relatório intrastat
    - INSTAT XML
    - INSTAT XML (DE)

3. Configure os parâmetros de comércio exterior:

    1. No Dynamics 365 Finance, vá para **Imposto** > **Configuração** > **Parâmetros de comércio exterior**.
    2. Na guia **Intrastat**, na Guia Rápida **Relatório Eletrônico**, no campo **Mapeamento de formato de arquivo**, selecione **Intrastat XML (DE)**.
    3. No campo **Mapeamento de formato de relatório**, selecione **Relatório Intrastat**.
    4. Na Guia Rápida **Hierarquia de código de mercadoria**, no campo **Hierarquia de categoria**, selecione **Intrastat**.
    5. No campo **Código da transação**, selecione o código da transação para transferências de propriedades. Você usa esse código para transações que produzem transferências reais ou planejadas da propriedade sobre compensação (financeira ou outra). Ele também é usado para correções.
    6. No campo **Nota de crédito**, selecione o código de transação para a devolução de bens.
    7. No campo **Trabalhador**, selecione a pessoa de contato para o relatório Intrastat. Alternativamente, na guia **Contato** insira ou selecione valores nos campos **Nome**, **Telefone**, **Fax**, **E-mail** e **Endereço da Internet**. Esses campos são incluídos no relatório.
    8. No campo **Autoridade**, selecione a autoridade Intrastat.
    9. Acesse **Imposto** > **Impostos indiretos** > **Imposto de venda** > **Autoridades de impostos de venda** e insira as seguintes informações para a autoridade Intrastat selecionada na etapa anterior:

       - Identificação de autoridade
       - Endereço
       - Informações do contato

    10. Na guia **Propriedades de país/região**, no campo **País/região**, indique todos os países ou regiões com os quais sua empresa faz negócios. Para cada país ou região, no campo **Tipo de país/região**, selecione **UE**, para que o país ou a região apareça no relatório Intrastat.

4. Configure os códigos de região.

    1. Acesse **Administração da organização** > **Catálogo de endereços global** > **Endereços** > **Catálogos de endereços**.
    2. Na guia **Estado/província**, no campo **País/região**, selecione **DEU** e, em seguida, **Aplicar filtro**.
    3. Na grade, selecione o estado. Em seguida, no campo **Código Intrastat**, insira o código Intrastat exclusivo.

5. Configure o endereço de origem de um produto.

    1. Acesse **Gerenciamento de informações do produto** > **Produtos** > **Produtos liberados**.
    2. Na grade, selecione o produto.
    3. Na Guia Rápida **Comércio exterior**, na seção **Intrastat**, no campo **País de origem**, selecione **DEU**.

6. Acesse **Imposto** > **Configuração** > **Comércio exterior** > **Compactação do Intrastat** e selecione os campos que podem ser comparados quando a informação do Intrastat é resumida. Para a Intrastat alemã, selecione os valores para os seguintes campos:

    - Mercadoria
    - País/região
    - Correção
    - Direção
    - Condições de entrega
    - Fatura
    - País/região de origem
    - Porto
    - País/região do remetente
    - Estado do remetente
    - Procedimento estatístico
    - Código de transação
    - Transporte
    - Número de isenção de imposto

### <a name="intrastat-transfer"></a>Transferência Intrastat

Na página **Intrastat**, no Painel de Ações, selecione **Transferir** para transferir automaticamente as informações sobre o comércio intracomunidade de ordens de venda, faturas de texto livre, ordens de compra, faturas de fornecedor, recebimentos de produtos do fornecedor **,** faturas de projeto e ordens de transferência. Somente os documentos que tiverem um país da UE como o país ou a região de destino (para envios) ou consignação (para recebimentos) serão transferidos.

Como alternativa, você pode inserir transações manualmente selecionando **Novo** no Painel de Ação.

### <a name="generate-an-intrastat-report"></a>Gerar um relatório do Intrastat

1. Acesse **Imposto** > **Declarações** > **Comércio exterior** > **Intrastat**.
2. No Painel de Ações, selecione **Saída** > **Relatório**.
3. Na caixa de diálogo **Relatório do Intrastat**, defina estes campos.

    | Campo | descrição |
    |-------------------------|-------------------------|
    | Data Inicial | Selecione a data de início do relatório. |
    | Data final | Selecione a data de término do relatório. |
    | Gerar arquivo | Defina esta opção como **Sim** para gerar um arquivo .xml. |
    | Nome do arquivo | Deixe esse campo em branco. O nome do arquivo é gerado automaticamente e consiste no valor da tag XML **&lt;envelopeId&gt;**, mais a extensão de nome de arquivo **.xml**.</br>O valor **&lt;envelopeId&gt;** é uma concatenação dos seguintes elementos, nesta ordem:</br><ol type="1"></br><li>O valor da tag **&lt;interchangeAgreementId&gt;**</li></br><li>Um hífen (-)</li></br><li>O valor da tag **&lt;referencePeriod em AAAAMM&gt;**</li></br><li>Um hífen (-)</li></br><li>O valor da tag **&lt;Envelope/DateTime/date em AAAADD&gt;**</li></br><li>Um hífen (-)</li></br><li>O valor da tag **&lt;Envelope/DateTime/time em hhmm&gt;**</li></br></ol> |
    | Direção | <ul></br><li>Selecione **Entradas** para relatar entradas de intracomunidade.</li></br><li>Selecione **Expedições** para relatar expedições de intracomunidade.</li></br><li>Selecione **Ambos** para relatar entradas e expedições.</li></br></ul> |
    | Número de inscrição de imposto | Insira o número de registro a ser usado para gerar o código de identificação do remetente, caso o número seja diferente do número de registro de imposto da entidade legal. |


## <a name="example"></a>Exemplo

Este exemplo mostra como lançar entradas e expedições para o Intrastat. Ele usa a entidade legal **DEMF**.

1. No [LCS](https://lcs.dynamics.com/Logon/Index), na biblioteca de ativos compartilhados, baixe as versões mais recentes das seguintes configurações de ER para o formato de declaração Intrastat:

    - Módulo intrastat
    - Relatório intrastat
    - Intrastat XML
    - Intrastat XML (DE)

2. Crie códigos de transação.

    1. Acesse **Imposto** > **Configuração** > **Comércio exterior** > **Códigos de transação**.
    2. No Painel de Ações, selecione **Novo**.
    3. No campo **Código** **de transação**, insira **21**.
    4. No campo **Nome**, insira **Devolução de bens**.
    5. No Painel de ações, selecione **Salvar**.

3. Configure o número de identificação da autoridade.

    1. Acesse **Imposto** > **Impostos indiretos** > **Imposto de venda** > **Autoridades do imposto de venda**.
    2. Na lista, selecione **TA**.
    3. No campo **Identificação da autoridade**, insira **123**.

4. Configure os códigos de região.

    1. Acesse **Administração da organização** > **Catálogo de endereços global** > **Endereços** > **Catálogos de endereços**.
    2. Na guia **Estado/província**, no campo **País/região**, selecione **DEU** e, em seguida, **Aplicar filtro**.
    3. Na grade, selecione **BE** e, no campo **Código do Intrastat**, insira **11**.
    4. No Painel de ações, selecione **Salvar**.

5. Configure os parâmetros de comércio exterior.

    1. Acesse **Imposto** > **Configuração** > **Comércio exterior** > **Parâmetros de comércio exterior**.
    2. Na guia **Intrastat**, na Guia Rápida **Geral**, no campo **Código** **de transação**, selecione **11**.
    3. No campo **Nota de crédito**, selecione **21**.
    4. No campo **Autoridade**, selecione **TA**.
    5. Na Guia Rápida **Relatório Eletrônico**, no campo **Mapeamento de formato de arquivo**, selecione **INSTAT XML (DE)**.
    6. No campo **Mapeamento de formato de relatório**, selecione **Relatório Intrastat**.
    7. Na Guia Rápida **Hierarquia de código de mercadoria**, no campo **Hierarquia de categoria**, certifique-se de que **Intrastat** esteja selecionado.
    8. Na guia **Propriedades de país/região**, selecione **Novo**.
    9. No campo **País/região do participante**, selecione **FRA**.
    10. No campo **Tipo de país/região**, selecione **EU**.

6. Atribua um código de mercadoria a um produto e defina a origem dele. Os campos **Código da mercadoria**, **País/região de origem** e **Estado de origem** serão automaticamente definidos em ordens de venda e ordens de compra quando você selecionar o produto.

    1. Acesse **Gerenciamento de informações do produto** > **Produtos** > **Produtos liberados**.
    2. Na grade, selecione **D0001**.
    3. Na Guia Rápida **Comércio exterior**, na seção **Intrastat**, no campo **Mercadoria**, selecione **920 20 34**.
    4. Na seção **Origem**, no campo **País/região**, selecione **DEU**.
    5. Na Guia Rápida **Gerenciar estoque**, na seção **Medidas de peso**, no campo **Peso líquido**, digite **12**.
    6. No Painel de ações, selecione **Salvar**.

7. Atribua o transporte a um modo de entrega. O código de transporte será, então, automaticamente definido em ordens quando você selecionar o modo de entrega.

    1. Acesse **Compras e fornecimento** > **Configuração** > **Distribuição** > **Modos de entrega**.
    2. Na lista, selecione **10**.
    3. Na Guia Rápida **Comércio exterior**, no campo **Transporte**, selecione **01**.

8. Crie uma ordem de venda com um cliente da UE.

    1. Acesse **Contas a receber** > **Ordens** > **Todas as ordens de venda**.
    2. No Painel de Ações, selecione **Novo**.
    3. Na caixa de diálogo **Criar ordem de venda**, na Guia Rápida **Cliente**, na seção **Cliente**, no campo **Conta do cliente**, selecione **DE-012**.
    4. Na Guia Rápida **Geral**, na seção **Dimensões de armazenamento**, no campo **Site**, selecione **1**.
    5. No campo **Depósito**, selecione **11**.
    6. Selecione **OK**.
    7. Na guia **Cabeçalho**, na Guia Rápida **Comércio exterior**, no campo **Porta**, selecione **53**.
    8. No campo **Procedimento estatístico**, selecione **31710**.
    9.  Na guia **Linhas**, na Guia Rápida **Linhas** **da ordem de venda**, no campo **Número do item**, selecione **D0001**. Depois, no campo **Quantidade**, insira **10**.
    10. Na Guia Rápida **Detalhes da linha**, na guia **Comércio exterior**, verifique se os campos **Código de transação**, **Transporte**, **Mercadoria** e **País/região de origem** estão definidos automaticamente.
    11. No Painel de ações, selecione **Salvar**.
    12. No Painel de Ação, na guia **Fatura**, na seção **Gerar**, selecione **Fatura**.
    13. Na caixa de diálogo **Lançando fatura**, na Guia Rápida **Parâmetros**, na seção **Parâmetro**, no campo **Quantidade**, selecione **Tudo**.
    14. Selecione **OK** para lançar a fatura.

9.  Transfira a transação para o diário Intrastat e revise o resultado.

    1. Acesse **Imposto** > **Declarações** > **Comércio exterior** > **Intrastat**.
    2. No Painel de Ação, selecione **Transferir**.
    3. Na caixa de diálogo **Intrastat (Transferência)**, na seção **Parâmetros**, defina a opção **Fatura de cliente** como **Sim**.
    4. Selecione **Filtro**.
    5. Na caixa de diálogo **Filtro Intrastat**, na guia **Intervalo**, selecione a primeira linha e verifique se o campo **Campo** está definido como **Data**.
    6. No campo **Critérios**, selecione a data atual.
    7. Selecione **OK** para fechar a caixa de diálogo **Filtro Intrastat**.
    8. Selecione **OK** para fechar a caixa de diálogo **Intrastat (Transferência)** e revisar o resultado. A linha representa a ordem de venda que você criou anteriormente.

        ![Linha que representa a ordem de venda na página Intrastat](media/intrastat_deu_1.png)

10. Selecione a linha de transação e, em seguida, a guia **Geral** para exibir mais detalhes.

    ![Detalhes da ordem de venda na guia Geral da página Intrastat](media/intrastat_deu_2.png)

11. Crie uma nota de crédito usando uma ordem de venda.

    1. Acesse **Contas a receber** > **Ordens** > **Todas as ordens de venda**.
    2. No Painel de Ações, selecione **Novo**.
    3. Na caixa de diálogo **Criar ordem de venda**, na Guia Rápida **Cliente**, na seção **Cliente**, no campo **Conta do cliente**, selecione **DE-012**.
    4. Na Guia Rápida **Geral**, na seção **Dimensões de armazenamento**, no campo **Site**, selecione **1**.
    5. No campo **Depósito**, selecione **11**.
    6. Na guia **Cabeçalho**, na Guia Rápida **Comércio exterior**, no campo **Porta**, selecione **53**.
    7. No campo **Procedimento estatístico**, selecione **31710**.
    8. Na guia **Linhas**, na Guia Rápida **Linhas** **da ordem de venda**, no campo **Número do item**, selecione **D0001**. Depois, no campo **Quantidade**, insira **-2**.
    9. Na Guia Rápida **Detalhes da linha**, na guia **Comércio exterior**, no campo **Código de transação**, selecione **21**.
    10. Verifique se os campos **Transporte**, **Mercadoria** e **País/região de origem** estão definidos automaticamente.
    11. No Painel de ações, selecione **Salvar**.
    12. No Painel de Ação, na guia **Fatura**, na seção **Gerar**, selecione **Fatura**.
    13. Na caixa de diálogo **Lançando fatura**, na Guia Rápida **Parâmetros**, na seção **Parâmetro**, no campo **Quantidade**, selecione **Tudo**.
    14. Selecione **OK** para lançar a fatura.

12. Transfira a transação para o diário Intrastat e revise o resultado.

    1. Acesse **Imposto** > **Declarações** > **Comércio exterior** > **Intrastat**.
    2. No Painel de Ação, selecione **Transferir**.
    3. Na caixa de diálogo **Intrastat (Transferência)**, na seção **Parâmetros**, defina a opção **Fatura de cliente** como **Sim**.
    4. Selecione **OK** para fechar a caixa de diálogo **Intrastat (Transferência)** e revisar o resultado. Foi adicionada uma nova linha na qual o campo **Direção** está definido como **Entradas**.            
        Essa linha representa a devolução física de bens.

        ![Linha para a devolução física de bens na página Intrastat](media/intrastat_deu_3.png)

13. Selecione a linha de transação e, em seguida, a guia **Geral** para exibir mais detalhes.

    ![Detalhes da devolução física de bens na guia Geral da página Intrastat](media/intrastat_deu_4.png)

14. Crie uma correção usando uma ordem de venda:

    1. Acesse **Contas a receber** > **Ordens** > **Todas as ordens de venda**.
    2. No Painel de Ações, selecione **Novo**.
    3. Na caixa de diálogo **Criar ordem de venda**, na Guia Rápida **Cliente**, na seção **Cliente**, no campo **Conta do cliente**, selecione **DE-012**.
    4. Na Guia Rápida **Geral**, na seção **Dimensões de armazenamento**, no campo **Site**, selecione **1**.
    5. No campo **Depósito**, selecione **11**.
    6. Na guia **Cabeçalho**, na Guia Rápida **Comércio exterior**, no campo **Porta**, selecione **53**.
    7. No campo **Procedimento estatístico**, selecione **31710**.
    8. Na guia **Linhas**, na Guia Rápida **Linhas** **da ordem de venda**, no campo **Número do item**, selecione **D0001**. Depois, no campo **Quantidade**, insira **-3**.
    9. Na Guia Rápida **Detalhes da linha**, na guia **Comércio exterior**, no campo **Código de transação**, selecione **11**.
    10. Verifique se os campos **Transporte**, **Mercadoria** e **País/região de origem** estão definidos automaticamente.
    11. No Painel de ações, selecione **Salvar**.
    12. Verifique se o campo **Código da transação** está definido como 11.
    13. No Painel de Ação, na guia **Fatura**, na seção **Gerar**, selecione **Fatura**.
    14. Na caixa de diálogo **Lançando fatura**, na Guia Rápida **Parâmetros**, na seção **Parâmetro**, no campo **Quantidade**, selecione **Tudo**.
    15. Selecione **OK** para lançar a fatura.

15. Transfira a transação para o diário Intrastat e revise o resultado:

    1. Acesse **Imposto** > **Declarações** > **Comércio exterior** > **Intrastat**.
    2. No Painel de Ação, selecione **Transferir**.
    3. Na caixa de diálogo **Intrastat (Transferência)**, na seção **Parâmetros**, defina a opção **Fatura de cliente** como **Sim**.
    4. Selecione **OK** para fechar a caixa de diálogo **Intrastat (Transferência)** e revisar o resultado. Foi adicionada uma nova linha na qual uma marca de seleção aparece na coluna **Correção**.

        ![Linha para a correção na página Intrastat](media/intrastat_deu_5.png)

16. Selecione a linha de transação e, em seguida, a guia **Geral** para exibir mais detalhes.

    ![Detalhes da correção na guia Geral da página Intrastat](media/intrastat_deu_6.png)

17. No Painel de Ações, selecione **Saída** > **Relatório**.
18. Na caixa de diálogo **Relatório Intrastat**, na Guia Rápida **Parâmetros**, na seção **Data**, selecione o mês da ordem de venda que você criou.
19. Na seção **Opções** **de exportação**, defina a opção **Gerar arquivo** como **Sim**.
20. No campo **Nome do arquivo**, insira o nome necessário.
21. Selecione **OK** e revise o relatório gerado. A tabela a seguir mostra os valores no relatório de exemplo.

    | **Organização**                  | **Fatura de venda**  |   **Correção**   | **Nota de Crédito** |
    |---------------------------|--------------------|--------------------|-----------------|
    | declarationId             | 2021-07-D          | 2021-07-A          |                 |
    | referencePeriod           | 2021-07            | 2021-07            |                 |
    | PSIId                     | 11203/118/12345000 | 11203/118/12345000 |                 |
    | functionCode              | O                  | O                  |                 |
    | flowCode                  | B                  | A                  |                 |
    | CurrencyCode              | EUR                | EUR                |                 |
    | itemNumber                | 0000362            | 0000362            | 0000361         |
    | CN8Code                   | 9202034            | 9202034            | 9202034         |
    | goodsDescription          | Palestrante            | Palestrante            | Palestrante         |
    | MSConsDestCode            | FR                 | FR                 | FR              |
    | countryOfOriginCode       | \-                 | \-                 | DE              |
    | netMass                   | 120                | -36                | 24              |
    | invoicedAmount            | 3290               | -987               | \-              |
    | StatisticalValue          | 3290               | -987               | 658             |
    | natureOfTransactionACode  | 1                  | 1                  | 2               |
    | natureOfTransactionBCode  | 1                  | 1                  | 1               |
    | modeOfTransportCode       | 01                 | 01                 | 01              |
    | regionCode                | 11                 | 11                 | 11              |
    | portAirportInlandportCode | 53                 | 53                 | 53              |

