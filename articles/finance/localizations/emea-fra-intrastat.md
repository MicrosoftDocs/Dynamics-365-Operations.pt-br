---
title: Intrastat francês
description: Este tópico contém informações sobre a declaração Intrastat na França.
author: andosip
ms.date: 07/9/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: v-aosipov
ms.search.validFrom: ''
ms.openlocfilehash: a0f418aa18db99088db0b75df41f950e67160e3f
ms.sourcegitcommit: 8fb79920bea14746a71551a4456236a6386bfcea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "6538869"
---
# <a name="french-intrastat"></a>Intrastat francês

[!include[banner](../includes/banner.md)]

As empresas na França que são registradas para IVA (imposto sobre valor agregado) e que comercializam com outros países da União Europeia (UE) devem declarar a troca de bens e serviços para e da França. O DEB (declaração de comércio sobre mercadorias) é uma combinação de relatórios de lista de vendas da UE e do relatório Intrastat. Você deve enviar este relatório mensalmente para todas as vendas de mercadorias intracomunidade.

Você pode gerar o relatório DEB em um dos dois formatos de arquivo de texto eletrônico: SAISUNIC 330 ou INTRACOM.

A tabela a seguir mostra os campos incluídos na declaração Intrastat francesa no formato SAISUNIC 330.

| **Campo**                   | **Nível de relatório**   |              |
|-----------------------------|--------------------|--------------|
|                             | **4 (simplificado)** | **1 (completo)** |
| Período de referência         | X                  | X            |
| Número da declaração       | X                  | X            |
| Número da Linha                 | X                  | X            |
| Código ISO do País (FR)       | X                  | X            |
| Código complementar          | X                  | X            |
| Número de Siren                | X                  | X            |
| Código IVA de cliente        | X                  | X            |
| Código de direção              | X                  | X            |
| Tipo de Transação            | X                  | X            |
| Nível de obrigação            | X                  | X            |
| Código da mercadoria              |                    | X            |
| NGP nacional                |                    | X            |
| Município (Departamento)         |                    | X            |
| Natureza da transação       |                    | X            |
| País de origem      |                    | X            |
| País de origem - Importações |                    | X            |
| Destino final - Exportações |                    | X            |
| Valor da fatura               | X                  | X            |
| Valor estatístico           |                    | X            |
| Peso líquido                  |                    | X            |
| Unidades adicionais            |                    | X            |
| Código de transporte              |                    | X            |

A tabela a seguir mostra os campos incluídos na declaração Intrastat francesa no formato INTRACOM.

| **Campo**                   | **Nível de relatório**   |              |
|-----------------------------|--------------------|--------------|
|                             | **4 (simplificado)** | **1 (completo)** |
| Código                        | X                  | X            |
| Número da declaração       | X                  | X            |
| Número da linha              | X                  | X            |
| Siren                       | X                  | X            |
| Município (Departamento)         |                    | X            |
| Código de transporte              |                    | X            |
| País de origem           |                    | X            |
| Natureza da transação       |                    | X            |
| Valor da fatura               | X                  | X            |
| Modos de entrega           |                    | X            |
| Tipo de Transação            | X                  | X            |
| Nível de obrigação            | X                  | X            |
| Código da mercadoria              |                    | X            |
| NGP nacional                |                    | X            |
| Peso líquido                  |                    | X            |
| Valor estatístico           |                    | X            |
| Unidades adicionais            |                    | X            |
| País de origem - Importações |                    | X            |
| Destino final - Exportações |                    | X            |
| Código IVA de cliente        | X                  | X            |
| Código complementar          | X                  | X            |
| Período de referência         | X                  | X            |

### <a name="set-up-intrastat"></a>Configurar Intrastat

1.  No [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index), na biblioteca de ativos compartilhados, baixe as versões mais recentes das seguintes configurações de Relatório Eletrônico (ER) para a declaração Intrastat:

-   Módulo intrastat

-   Relatório intrastat

-   INTRACOM Intrastat (FR)

-   SAISUNIC Intrastat (FR)

Para obter mais informações, consulte [Baixar configurações do Relatório eletrônico no Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

2.  No Dynamics 365 Finance, acesse **Imposto** &gt; **Configuração** &gt; **Comércio exterior** &gt; **Parâmetros de comércio exterior** e siga estas etapas:

    1.  Na guia **Intrastat**, na Guia Rápida **Relatório eletrônico**, no campo **Mapeamento de formato de arquivo**, selecione **INTRACOM Intrastat (FR)** ou **SAISUNIC Intrastat (FR)**.

    2.  No campo **Mapeamento de formato de relatório**, selecione **Relatório Intrastat**.

    3.  Na Guia Rápida **Hierarquia de código de mercadoria**, no campo **Hierarquia de categoria**, selecione **Intrastat**.

    4.  Na Guia Rápida **Geral**, no campo **Código de transação**, selecione o código usado para as transferências de mercadorias.

    5.  No campo **Nota de crédito**, selecione o código usado para devoluções de mercadorias.

    6.  No campo **Nível de obrigação para exportação**, insira o nível de detalhe do relatório de exportação. O nível selecionado afeta as linhas mostradas no relatório. Para obter mais informações, consulte as tabelas o início deste tópico.

3.  Acesse **Administração da organização** &gt; **Organizações** &gt; **Entidades legais**, selecione sua empresa e siga estas etapas:

    1.  Na Guia Rápida **Números de registro**, no campo **Código NAF**, insira o código NAF. Para obter mais informações, consulte [FR-00003 Códigos NAF e números de Siret](tasks/fr-00003-naf-codes-siret-numbers.md).

    2.  Na Guia Rápida **Comércio exterior e logística**, na seção **Intrastat**, defina os campos **Exportação de número de isenção de IVA** e **Importação de número de isenção de IVA**.

    3.  Na Guia Rápida **Registro de imposto**, no campo **Número de registro de imposto**, insira o número de registro de imposto da sua empresa.

4.  Para especificar códigos NAF e números de isenção de imposto para clientes, acesse **Contas a receber** &gt; **Clientes** &gt; **Todos os clientes** e siga estas etapas:

    1.  Selecione um cliente.

    2.  Na Guia Rápida **Fatura e entrega**, na seção **Imposto**, no campo **Número de isenção de imposto**, insira o número de isenção de imposto do cliente.

    3.  Na Guia Rápida **Dados demográficos de vendas**, no campo **Siret francês**, insira o número de Siret da empresa.

    4.  No campo **Código NAF**, insira o código NAF da empresa.

    5.  Repita essas etapas para outros clientes.

5.  Para especificar códigos NAF e números de isenção de imposto para fornecedores, acesse **Contas a pagar** &gt; **Fornecedores** &gt; **Todos os fornecedores** e siga estas etapas:

    1.  Selecione um fornecedor.

    2.  Na Guia Rápida **Fatura e entrega**, na seção **Imposto**, no campo **Número de isenção de imposto**, insira o número de isenção de imposto do fornecedor.

    3.  Na Guia Rápida **Dados demográficos de compras**, no campo **Siret francês**, insira o número de Siret da empresa.

    4.  No campo **Código NAF**, insira o código NAF da empresa.

    5.  Repita essas etapas para outros fornecedores.

6.  Acesse **Imposto** &gt; **Configuração** &gt; **Comércio exterior** &gt; **Compactação do Intrastat** e selecione os campos que podem ser comparados quando a informação do Intrastat é resumida. Para Intrastat francês, selecione **Procedimento de estatística**, **Estado de origem**, **País/região de origem**, **Condições de entrega**, **Transporte**, **Correção**, **País/região**, **País de origem/destino**, **Direção**, **País/região do remetente**, **Estado do remetente**, **Estado**, **Código de transação** e **Mercadoria**.

7.  Acesse **Gerenciamento de depósitos** &gt; **Configuração** &gt; **Depósito** &gt; **Depósitos**, selecione um depósito e siga estas etapas:

    1.  Na Guia Rápida **Endereços**, selecione **Adicionar** ou **Editar**.

    2.  Na caixa de diálogo, no campo **Cidade**, selecione a cidade do depósito. O estado da cidade será usado como uma região do seu relatório DEB.

### <a name="ngp-codes"></a>Códigos NGP

No relatório DEB, a codificação de produtos consiste nos seguintes elementos:

1.  O código CN8 de oito dígitos que representa a tarifa e a nomenclatura estatística da UE.

2.  Se aplicável, o código de item nacional Nomenclature Générale des Produits (NGP) de um dígito.

Em 2021, o NGP aplica-se somente a três tipos de produtos:

-   Alguns produtos de vacas, ovelhas e cabras

-   Equipamento militar

-   Vinhos franceses

Você deve configurar os códigos NGP e atribuí-los a produtos relacionados. O campo **NGP** é automaticamente definido na página **Diário do Intrastat**.

#### <a name="set-up-an-ngp-code"></a>Configurar um código NGP

1.  Acesse **Imposto** &gt; **Configuração** &gt; **Comércio exterior** &gt; **Códigos NGP**.

2.  No Painel de Ações, selecione **Novo** para criar um código NGP.

3.  No campo **NGP**, insira um código de um único dígito.

4.  No campo **Descrição**, insira uma descrição para o código.

#### <a name="assign-an-ngp-code-to-a-product"></a>Atribuir um código NGP a um produto

1.  Vá para **Gerenciamento de informações do produto** &gt; **Produtos** &gt; **Produtos liberados**.

2.  Na grade, selecione um produto.

3.  Na Guia Rápida **Comércio exterior**, na seção **Intrastat**, no campo **NGP**, selecione o código NGP apropriado.

## <a name="intrastat-journal"></a>Diário do Intrastat

Acesse **Imposto** &gt; **Declarações** &gt; **Comércio** **exterior** &gt; **Intrastat** para gerenciar suas transações aplicáveis ao comércio exterior com países da UE. Para obter mais informações, consulte [Visão geral do Intrastat](emea-intrastat.md).

A coluna **NGP** é específica da França. Ela mostra o código NGP do produto. Se o NGP não for aplicável a um produto, **0** (zero) será exibido. Você pode ajustar o código NGP. Selecione a transação. Depois, na guia **Geral**, na seção **Códigos**, no campo **NGP**, selecione o código NGP necessário.

### <a name="intrastat-transfer"></a>Transferência Intrastat

Na página **Intrastat**, no Painel de Ações, você pode selecionar **Transferir** para transferir automaticamente as informações sobre o comércio intracomunidade de ordens de venda, faturas de texto livre, ordens de compra, faturas de fornecedor, recebimentos de produtos do fornecedor, faturas de projeto e ordens de transferência. Somente os documentos que tiverem um país da UE como o país ou a região de destino (para envios) ou consignação (para recebimentos) serão transferidos.

Como o relatório DEB é uma combinação da lista de vendas da UE e do relatório Intrastat, ele também inclui transações *triangulares*, em que uma entrega direta é realizada de um país da UE (participante A) para outro país da UE (participante C), e uma entidade legal francesa (participante B) está no meio do acordo triangular.

### <a name="generate-a-deb-intrastat-report"></a>Gerar um relatório DEB (Intrastat)

1.  Acesse **Imposto** &gt; **Declarações** &gt; **Comércio exterior** &gt; **Intrastat**.

2.  No Painel de Ações, selecione **Exportar** &gt; **Relatório**.

3.  Na caixa de diálogo **Relatório do Intrastat**, defina estes campos.

| Campo            | descrição                                                                                                                         |
|------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Data Inicial        | Selecione a data de início do relatório.                                                                                               |
| Data final          | Selecione a data de término do relatório.                                                                                                 |
| Gerar arquivo    | Defina esta opção como **Sim** para gerar um arquivo .txt.                                                                                 |
| Nome do arquivo        | Insira o nome do arquivo. txt do relatório do Intrastat.                                                                          |
| Gerar relatório  | Defina esta opção como **Sim** para gerar um arquivo .xml.                                                                                |
| Nome do arquivo de relatório | Insira o nome necessário.                                                                                                            |
| Somente correções | Defina essa opção como **Sim** para relatar apenas correções. Defina como **Não** para relatar transações normais e correções.         |
| Direção        | Selecione **Entradas** para um relatório sobre as entradas de intracomunidade. Selecione **Expedições** para um relatório sobre expedições de intracomunidade. |

## <a name="example"></a>Exemplo

O exemplo a seguir mostra como configurar e trabalhar com códigos NGP. Ele usa a entidade legal **DEMF**.

1.  No [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index), na biblioteca de ativos compartilhados, baixe as versões mais recentes das seguintes configurações de ER para o formato de declaração Intrastat:

-   Módulo intrastat

-   Relatório intrastat

-   INTRACOM Intrastat (FR)

2.  Em Finanças, configure um código de transação:

    1.  Acesse **Imposto** &gt; **Configuração** &gt; **Comércio exterior** &gt; **Códigos de transação**.

    2.  No Painel de Ações, selecione **Novo**.

    3.  No campo **Código de transação**, insira **11**.

    4.  No campo **Nome**, digite **Compra ou Venda**.

    5.  No Painel de ações, selecione **Salvar**.

3.  Configure uma hierarquia de produtos:

    1.  Acesse **Gerenciamento de informações sobre produtos** &gt; **Configuração** &gt; **Categorias e atributos** &gt; **Hierarquias de categoria**.

    2.  Na grade, selecione **Intrastat**. No Painel de Ações, na guia **Hierarquia de categoria**, no grupo **Manter**, selecione **Editar**.

    3.  No Painel de Ações, selecione **Novo nó de categoria**.

    4.  No campo **Nome**, digite **Autres Libournais**.

    5.  No campo **Código**, insira **2204 21 42**.

    6.  No Painel de ações, selecione **Salvar**.

4.  Acesse **Imposto** &gt; **Configuração** &gt; **Comércio exterior** &gt; **Parâmetros de comércio exterior** e siga estas etapas:

    1.  Na guia **Intrastat**, na Guia Rápida **Geral**, no campo **Código de transação**, selecione **11**.

    2.  Na Guia Rápida **Relatório eletrônico**, no campo **Mapeamento de formato de arquivo**, selecione **INTRACOM Intrastat (FR)**.

    3.  No campo **Mapeamento de formato de relatório**, selecione **Relatório Intrastat**.

    4.  Na Guia Rápida **Hierarquia de código de mercadoria**, no campo **Hierarquia de categoria**, selecione **Intrastat**.

5.  Configure um código NGP:

    1.  Acesse **Imposto** &gt; **Configuração** &gt; **Comércio exterior** &gt; **Códigos NGP**.

    2.  No Painel de Ações, selecione **Novo**.

    3.  No campo **NGP**, insira **8**.

    4.  No campo **Nome da descrição**, insira **NGP 8**.

    5.  No Painel de ações, selecione **Salvar**.

6.  Atribua o código NGP a um produto:

    1.  Vá para **Gerenciamento de informações do produto** &gt; **Produtos** &gt; **Produtos liberados**.

    2.  Na grade, selecione **0001**.

    3.  Na Guia Rápida **Comércio exterior**, no campo **NGP**, selecione **8**.

    4.  No campo **Mercadoria**, selecione **2204 21 42**.

    5.  No Painel de ações, selecione **Salvar**.

7.  Crie uma ordem de venda que inclua o novo produto:

    1.  Acesse **Contas a receber** &gt; **Ordens** &gt; **Todas as ordens de vendas**.

    2.  No Painel de Ações, selecione **Novo**.

    3.  Na caixa de diálogo **Criar** **ordem** **de venda**, na seção **Cliente**, no campo **Conta** **do cliente**, selecione **100001**.

    4.  Na seção **Endereço**, no campo **Endereço de entrega**, selecione o sinal de adição (**+**) para criar um endereço.

    5.  Na caixa de diálogo **Novo endereço**, no campo **Nome da descrição**, insira **Alemanha**.

    6.  No campo **País/região**, selecione **DEU**.

    7.  Selecione **OK**.

    8.  Na caixa de diálogo **Criar ordem de venda**, selecione **OK**.

    9.  Na Guia Rápida **Linhas** **da ordem de venda**, no campo **Número do item**, selecione **0001**.

    10. No Painel de ações, selecione **Salvar**.

    11. No Painel de Ação, na guia **Fatura**, no grupo **Gerar**, selecione **Fatura**.

    12. Na caixa de diálogo **Lançando fatura**, na Guia Rápida **Parâmetros**, na seção **Parâmetro**, no campo **Quantidade**, selecione **Tudo**. Selecione **OK** para lançar a fatura.

8.  Crie o relatório DEB:

    1.  Acesse **Imposto** &gt; **Declarações** &gt; **Comércio exterior** &gt; **Intrastat**:

    2.  No Painel de Ações, selecione **Transferir**.

    3.  Na caixa de diálogo **Intrastat (Transferência)**, na seção **Parâmetros**, defina a opção **Fatura de cliente** como **Sim**. Em seguida, selecione **OK**.

    4.  Classifique transações pelo campo **Data**. A transação superior é a transação de resultado. O campo **NGP** é definido automaticamente.

    5.  No Painel de Ações, selecione **Exportar** &gt; **Relatório**.

    6.  Na caixa de diálogo **Relatório Intrastat**, na Guia Rápida **Parâmetros**, na seção **Data**, selecione o mês da ordem de venda que você criou.

    7.  Na seção **Opções de exportação**, defina a opção **Gerar arquivo** como **Sim**.

    8.  No campo **Nome do arquivo**, insira o nome necessário.

    9.  Selecione **OK** e analise o relatório.

