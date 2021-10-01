---
title: Intrastat francês
description: Este tópico contém informações sobre a declaração Intrastat na França.
author: anasyash
ms.date: 07/9/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: ''
ms.openlocfilehash: 4d38576e1c6b40242d5c6313fb06f08e170b4466
ms.sourcegitcommit: 7a2001e4d01b252f5231d94b50945fd31562b2bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2021
ms.locfileid: "7487891"
---
# <a name="french-intrastat"></a>Intrastat francês

[!include[banner](../includes/banner.md)]

As empresas na França que são registradas para IVA (imposto sobre valor agregado) e que comercializam com outros países da União Europeia (UE) devem declarar a troca de bens e serviços para e da França. O DEB (declaração de comércio sobre mercadorias) é uma combinação de relatórios de lista de vendas da UE e do relatório Intrastat. Você deve enviar este relatório mensalmente para todas as vendas de mercadorias intracomunidade.

Você pode gerar o relatório DEB em um dos dois formatos de arquivo de texto eletrônico: SAISUNIC 330 ou INTRACOM.

A tabela a seguir mostra os campos incluídos na declaração Intrastat francesa no formato SAISUNIC 330. A tabela também indica o nível de relatório do campo. O campo pode ser **4** (simplificado), **1** (completo) ou ambos.

| **Campo**                   | **Nível de relatório** |
|-----------------------------|------------------|
| Período de referência         | 4, 1              | 
| Número da declaração       | 4, 1              |
| Número da Linha                 | 4, 1              |
| Código ISO do País (FR)       | 4, 1              | 
| Código complementar          | 4, 1              | 
| Número de Siren                | 4, 1              | 
| Código IVA de cliente        | 4, 1              | 
| Código de direção              | 4, 1              |
| Tipo de Transação            | 4, 1              | 
| Nível de obrigação            | 4, 1              |
| Código da mercadoria              | 1                | 
| NGP nacional                | 1                | 
| Município (Departamento)         | 1                |
| Natureza da transação       | 1                | 
| País de origem      | 1                | 
| País de origem - Importações | 1                | 
| Destino final - Exportações | 1                | 
| Valor da fatura               | 4, 1              | 
| Valor estatístico           | 1                |
| Peso líquido                  | 1                | 
| Unidades adicionais            | 1                |
| Código de transporte              | 1                | 

A tabela a seguir mostra os campos incluídos na declaração Intrastat francesa no formato INTRACOM.
A tabela também indica o nível de relatório do campo. O campo pode ser **4** (simplificado), **1** (completo) ou ambos.

| **Campo**                   | **Nível de relatório**   | 
|-----------------------------|--------------------|
| Código                        | 4, 1               | 
| Número da declaração       | 4, 1               |
| Número da linha              | 4, 1               | 
| Siren                       | 4, 1               |
| Município (Departamento)         | 1                  |          
| Código de transporte              | 1                  |          
| País de origem           | 1                  |            
| Natureza da transação       | 1                  |             
| Valor da fatura               | 4, 1               |             
| Modos de entrega           | 1                  |           
| Tipo de Transação            | 4, 1               |            
| Nível de obrigação            | 4, 1               |           
| Código da mercadoria              | 1                  |            
| NGP nacional                | 1                  |            
| Peso líquido                  | 1                  |            
| Valor estatístico           | 1                  |            
| Unidades adicionais            | 1                  |            
| País de origem - Importações | 1                  |            
| Destino final - Exportações | 1                  |            
| Código IVA de cliente        | 4, 1               |            
| Código complementar          | 4, 1               |           
| Período de referência         | 4, 1               |         

### <a name="set-up-intrastat"></a>Configurar Intrastat

1.  No [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index), na biblioteca de ativos compartilhados, baixe as versões mais recentes das seguintes configurações de Relatório Eletrônico (ER) para a declaração Intrastat:

    - Módulo intrastat
    - Relatório intrastat
    - INTRACOM Intrastat (FR)
    - SAISUNIC Intrastat (FR)

    Para obter mais informações, consulte [Baixar configurações do Relatório eletrônico no Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

2.  No Dynamics 365 Finance, vá para **Imposto** > **Configuração** >  **Comércio exterior** > **Parâmetros de comércio exterior** e siga estas etapas:

    1. Na guia **Intrastat**, na Guia Rápida **Relatório eletrônico**, no campo **Mapeamento de formato de arquivo**, selecione **INTRACOM Intrastat (FR)** ou **SAISUNIC Intrastat (FR)**.
    2. No campo **Mapeamento de formato de relatório**, selecione **Relatório Intrastat**.
    3. Na Guia Rápida **Hierarquia de código de mercadoria**, no campo **Hierarquia de categoria**, selecione **Intrastat**.
    4. Na Guia Rápida **Geral**, no campo **Código de transação**, selecione o código usado para as transferências de mercadorias.
    5. No campo **Nota de crédito**, selecione o código usado para devoluções de mercadorias.
    6. No campo **Nível de obrigação para exportação**, insira o nível de detalhe do relatório de exportação. O nível selecionado afeta as linhas mostradas no relatório. Para obter mais informações, consulte as tabelas o início deste tópico.

3. Vá para **Administração da organização** > **Organizações** > **Entidades legais**, selecione sua empresa e siga estas etapas:

    1. Na Guia Rápida **Números de registro**, no campo **Código NAF**, insira o código NAF. Para obter mais informações, consulte [FR-00003 Códigos NAF e números de Siret](tasks/fr-00003-naf-codes-siret-numbers.md).
    2. Na Guia Rápida **Comércio exterior e logística**, na seção **Intrastat**, defina os campos **Exportação de número de isenção de IVA** e **Importação de número de isenção de IVA**.
    3. Na Guia Rápida **Registro de imposto**, no campo **Número de registro de imposto**, insira o número de registro de imposto da sua empresa.

4. Para especificar códigos NAF e números de isenção de imposto para clientes, vá para **Contas a receber** > **Clientes** > **Todos os clientes** e siga estas etapas:

    1. Selecione um cliente.
    2. Na Guia Rápida **Fatura e entrega**, na seção **Imposto**, no campo **Número de isenção de imposto**, insira o número de isenção de imposto do cliente.
    3. Na Guia Rápida **Dados demográficos de vendas**, no campo **Siret francês**, insira o número de Siret da empresa.
    4. No campo **Código NAF**, insira o código NAF da empresa.
    5. Repita essas etapas para outros clientes.

5. Para especificar códigos NAF e números de isenção de imposto para fornecedores, vá para **Contas a pagar** > **Fornecedores** > **Todos os fornecedores** e siga estas etapas:

    1. Selecione um fornecedor.
    2. Na Guia Rápida **Fatura e entrega**, na seção **Imposto**, no campo **Número de isenção de imposto**, insira o número de isenção de imposto do fornecedor.
    3. Na Guia Rápida **Dados demográficos de compras**, no campo **Siret francês**, insira o número de Siret da empresa.
    4. No campo **Código NAF**, insira o código NAF da empresa.
    5. Repita essas etapas para outros fornecedores.

6. Acesse **Imposto** > **Configuração** > **Comércio exterior** > **Compactação do Intrastat** e selecione os campos que podem ser comparados quando a informação do Intrastat é resumida. Para Intrastat francês, selecione **Procedimento de estatística**, **Estado de origem**, **País/região de origem**, **Condições de entrega**, **Transporte**, **Correção**, **País/região**, **País de origem/destino**, **Direção**, **País/região do remetente**, **Estado do remetente**, **Estado**, **Código de transação** e **Mercadoria**.

7. Vá para **Gerenciamento de depósito** > **Configuração** > **Depósito** > **Depósitos**, selecione um depósito e siga estas etapas:

    1. Na Guia Rápida **Endereços**, selecione **Adicionar** ou **Editar**.
    2. Na caixa de diálogo, no campo **Cidade**, selecione a cidade do depósito. O estado da cidade será usado como uma região do seu relatório DEB.

### <a name="ngp-codes"></a>Códigos NGP

No relatório DEB, a codificação de produtos consiste nos seguintes elementos:

  - O código CN8 de oito dígitos que representa a tarifa e a nomenclatura estatística da UE.
  - Se aplicável, o código de item nacional Nomenclature Générale des Produits (NGP) de um dígito.

Em 2021, o NGP aplica-se somente a três tipos de produtos:

  - Alguns produtos de vacas, ovelhas e cabras
  - Equipamento militar
  - Vinhos franceses

 Você deve configurar os códigos NGP e atribuí-los a produtos relacionados. O campo **NGP** é automaticamente definido na página **Diário do Intrastat**.

#### <a name="set-up-an-ngp-code"></a>Configurar um código NGP

1. Vá para **Imposto** > **Configuração** > **Comércio exterior** > **Códigos NGP**.
2. No Painel de Ações, selecione **Novo** para criar um código NGP.
3. No campo **NGP**, insira um código de um único dígito.
4. No campo **Descrição**, insira uma descrição para o código.

#### <a name="assign-an-ngp-code-to-a-product"></a>Atribuir um código NGP a um produto

1. Acesse **Gerenciamento de informações do produto** > **Produtos** > **Produtos liberados**.
2. Na grade, selecione um produto.
3. Na Guia Rápida **Comércio exterior**, na seção **Intrastat**, no campo **NGP**, selecione o código NGP apropriado.

## <a name="intrastat-journal"></a>Diário do Intrastat

Vá para **Imposto** > **Declarações** > **Comércio** **exterior** > **Intrastat** para gerenciar suas transações que são aplicáveis ao comércio exterior com países da UE. Para obter mais informações, consulte [Visão geral do Intrastat](emea-intrastat.md).

A coluna **NGP** é específica da França. Ela mostra o código NGP do produto. Se o NGP não for aplicável a um produto, **0** (zero) será exibido. Você pode ajustar o código NGP. Selecione a transação. Depois, na guia **Geral**, na seção **Códigos**, no campo **NGP**, selecione o código NGP necessário.

### <a name="intrastat-transfer"></a>Transferência Intrastat

Na página **Intrastat**, no Painel de Ações, você pode selecionar **Transferir** para transferir automaticamente as informações sobre o comércio intracomunidade de ordens de venda, faturas de texto livre, ordens de compra, faturas de fornecedor, recebimentos de produtos do fornecedor, faturas de projeto e ordens de transferência. Somente os documentos que tiverem um país da UE como o país ou a região de destino (para envios) ou consignação (para recebimentos) serão transferidos.

Como o relatório DEB é uma combinação da lista de vendas da UE e do relatório Intrastat, ele também inclui transações *triangulares*, em que uma entrega direta é realizada de um país da UE (participante A) para outro país da UE (participante C), e uma entidade legal francesa (participante B) está no meio do acordo triangular.

### <a name="generate-a-deb-intrastat-report"></a>Gerar um relatório DEB (Intrastat)

1. Acesse **Imposto** > **Declarações** > **Comércio exterior** > **Intrastat**.
2. No Painel de Ações, selecione **Saída** > **Relatório**.
3. Na caixa de diálogo **Relatório do Intrastat**, defina estes campos.

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

O exemplo a seguir mostra como configurar o Intrastat francês e criar o relatório DEB. Ele usa a entidade legal **DEMF**.

1. No [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index), na biblioteca de ativos compartilhados, baixe as versões mais recentes das seguintes configurações de ER para o formato de declaração Intrastat:

    - Módulo intrastat
    - Relatório intrastat
    - INTRACOM Intrastat (FR)

2. Em Finanças, configure um código de transação:

    1. Acesse **Imposto** > **Configuração** > **Comércio exterior** > **Códigos de transação**.
    2. No Painel de Ações, selecione **Novo**.
    3. No campo **Código de transação**, insira **11**.
    4. No campo **Nome**, digite **Compra ou Venda**.
    5. No Painel de ações, selecione **Salvar**.

3.  Configure uma hierarquia de produtos:

    1. Vá para **Gerenciamento de informações sobre o produto** > **Configuração** > **Categorias e atributos** > **Hierarquias da categoria**.
    2. Na grade, selecione **Intrastat**. No Painel de Ações, na guia **Hierarquia de categoria**, no grupo **Manter**, selecione **Editar**.
    3. No Painel de Ações, selecione **Novo nó de categoria**.
    4. No campo **Nome**, digite **Autres Libournais**.
    5. No campo **Código**, insira **2204 21 42**.
    6. No Painel de ações, selecione **Salvar**.

4. Vá para **Imposto** > **Configuração** > **Comércio exterior** > **Parâmetros de comércio exterior** e siga estas etapas:

    1. Na guia **Intrastat**, na Guia Rápida **Geral**, no campo **Código de transação**, selecione **11**.
    2. Na Guia Rápida **Relatório eletrônico**, no campo **Mapeamento de formato de arquivo**, selecione **INTRACOM Intrastat (FR)**.
    3. No campo **Mapeamento de formato de relatório**, selecione **Relatório Intrastat**.
    4. Na Guia Rápida **Hierarquia de código de mercadoria**, no campo **Hierarquia de categoria**, selecione **Intrastat**.

5. Configure um código NGP:

    1. Vá para **Imposto** > **Configuração** > **Comércio exterior** > **Códigos NGP**.
    2. No Painel de Ações, selecione **Novo**.
    3. No campo **NGP**, insira **8**.
    4. No campo **Nome da descrição**, insira **NGP 8**.
    5. No Painel de ações, selecione **Salvar**.

6. Atribua o código NGP a um produto:

    1. Acesse **Gerenciamento de informações do produto** > **Produtos** > **Produtos liberados**.
    2. Na grade, selecione **0001**.
    3. Na Guia Rápida **Comércio exterior**, no campo **NGP**, selecione **8**.
    4. No campo **Mercadoria**, selecione **2204 21 42**.
    5. No Painel de ações, selecione **Salvar**.

7. Crie uma ordem de venda que inclua o novo produto:

    1. Acesse **Contas a receber** > **Ordens** > **Todas as ordens de venda**.
    2. No Painel de Ações, selecione **Novo**.
    3. Na caixa de diálogo **Criar** **ordem** **de venda**, na seção **Cliente**, no campo **Conta** **do cliente**, selecione **100001**.
    4. Na seção **Endereço**, no campo **Endereço de entrega**, selecione o sinal de adição (**+**) para criar um endereço.
    5. Na caixa de diálogo **Novo endereço**, no campo **Nome da descrição**, insira **Alemanha**.
    6. No campo **País/região**, selecione **DEU**.
    7. Selecione **OK**.
    8. Na caixa de diálogo **Criar ordem de venda**, selecione **OK**.
    9. Na Guia Rápida **Linhas** **da ordem de venda**, no campo **Número do item**, selecione **0001**.
    10. No Painel de ações, selecione **Salvar**.
    11. No Painel de Ação, na guia **Fatura**, no grupo **Gerar**, selecione **Fatura**.
    12. Na caixa de diálogo **Lançando fatura**, na Guia Rápida **Parâmetros**, na seção **Parâmetro**, no campo **Quantidade**, selecione **Tudo**. Selecione **OK** para lançar a fatura.

8.  Crie o relatório DEB:

    1. Acesse **Imposto** > **Declarações** > **Comércio exterior** > **Intrastat**:
    2. No Painel de Ações, selecione **Transferir**.
    3. Na caixa de diálogo **Intrastat (Transferência)**, na seção **Parâmetros**, defina a opção **Fatura de cliente** como **Sim**. Em seguida, selecione **OK**.
    4. Classifique transações pelo campo **Data**. A transação superior é a transação de resultado. O campo **NGP** é definido automaticamente.
    5. No Painel de Ações, selecione **Exportar** &gt; **Relatório**.
    6. Na caixa de diálogo **Relatório Intrastat**, na Guia Rápida **Parâmetros**, na seção **Data**, selecione o mês da ordem de venda que você criou.
    7. Na seção **Opções de exportação**, defina a opção **Gerar arquivo** como **Sim**.
    8. No campo **Nome do arquivo**, insira o nome necessário.
    9. Selecione **OK** e analise o relatório.

