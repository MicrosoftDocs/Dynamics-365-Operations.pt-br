---
title: Intrastat francês
description: Este artigo contém informações sobre a declaração Intrastat na França.
author: anasyash
ms.date: 11/30/2022
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: ''
ms.openlocfilehash: 2076649c7fff9f47b9c1fda62a103168b19bb973
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831796"
---
# <a name="french-intrastat"></a>Intrastat francês

[!include[banner](../includes/banner.md)]

As empresas na França que são registradas para IVA (imposto sobre valor agregado) e que comercializam com outros países da União Europeia (UE) devem declarar a troca de bens e serviços para e da França. O DEB (declaração de comércio sobre mercadorias) é uma combinação de relatórios de lista de vendas da UE e do relatório Intrastat. Você deve enviar este relatório mensalmente para todas as vendas de mercadorias intracomunidade.

Você pode gerar o relatório DEB em um dos dois formatos de arquivo de texto eletrônico: SAISUNIC 330 ou INTRACOM.

A tabela a seguir mostra os campos incluídos na declaração Intrastat francesa no formato SAISUNIC 330. A tabela também indica os níveis de relatório de cada campo. Um campo pode ter os seguintes níveis de relatório:

- **4** – Declaração de imposto.
- **1** – Resposta estatística.
- **5** – Resposta estatística à remessa e à declaração de imposto e preenchimento em conjunto.

| Campo                       | Níveis de relatório |
|-----------------------------|---------------|
| Período de referência         | 4, 1, 5       |
| Número da declaração       | 4, 1, 5       |
| Número da Linha                 | 4, 1, 5       |
| Código ISO do País (FR)       | 4, 1, 5       |
| Código complementar          | 4, 1, 5       |
| Número de Siren                | 4, 1, 5       |
| Código IVA de cliente        | 4, 1, 5       |
| Código de direção              | 4, 1, 5       |
| Tipo de Transação            | 4, 1, 5       |
| Nível de obrigação            | 4, 1, 5       |
| Código da mercadoria              | 1, 5          |
| NGP nacional                | 1, 5          |
| Município (Departamento)         | 1, 5          |
| Natureza da transação       | 1, 5          |
| País de origem      | 1, 5          |
| País de origem - Importações | 1, 5          |
| Destino final - Exportações | 1, 5          |
| Valor da fatura               | 4, 1, 5       |
| Valor estatístico           | 1, 5          |
| Peso líquido                  | 1, 5          |
| Unidades adicionais            | 1, 5          |
| Código de transporte              | 1, 5          |

A tabela a seguir mostra os campos incluídos na declaração Intrastat francesa no formato INTRACOM. A tabela também indica os níveis de relatório de cada campo. Um campo pode ter os seguintes níveis de relatório:

- **4** – Declaração de imposto.
- **1** – Resposta estatística.
- **5** – Resposta estatística à remessa e à declaração de imposto e preenchimento em conjunto.

| Campo                       | Níveis de relatório |
|-----------------------------|---------------|
| Código de direção              | 4, 1, 5       |
| Número da declaração       | 4, 1, 5       |
| Número da linha              | 4, 1, 5       |
| Siren                       | 4, 1, 5       |
| Município (Departamento)         | 1, 5          |
| Código de transporte              | 1, 5          |
| País de origem           | 1, 5          |
| Natureza da transação       | 1, 5          |
| Valor da fatura               | 4, 1, 5       |
| Modos de entrega           | 1, 5          |
| Tipo de Transação            | 4, 1, 5       |
| Nível de obrigação            | 4, 1, 5       |
| Código da mercadoria              | 1, 5          |
| NGP nacional                | 1, 5          |
| Peso líquido                  | 1, 5          |
| Valor estatístico           | 1, 5          |
| Unidades adicionais            | 1, 5          |
| País de origem - Importações | 1, 5          |
| Destino final - Exportações | 1, 5          |
| Código IVA de cliente        | 4, 1, 5       |
| Código complementar          | 4, 1, 5       |
| Período de referência         | 4, 1, 5       |

## <a name="set-up-intrastat"></a>Configurar Intrastat

- No [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/Logon/Index), na biblioteca de ativos compartilhados, baixe as versões mais recentes das seguintes configurações de Relatório Eletrônico (ER) para a declaração Intrastat:

    - Módulo intrastat
    - Relatório intrastat
    - INTRACOM Intrastat (FR)
    - SAISUNIC Intrastat (FR)

    Para obter mais informações, consulte [Baixar configurações do Relatório eletrônico no Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

### <a name="set-up-vat-ids"></a>Configurar IDs do IVA

#### <a name="set-up-vat-codes-for-your-company"></a>Configurar códigos de IVA para sua empresa

1. Acesse **Imposto** \> **Configuração** \> **Imposto** \> **Números de isenção de imposto**.
2. No Painel de Ações, selecione **Novo**.
3. No campo **País/região**, selecione **FRA**.
4. No campo **Número de isenção de imposto**, insira a chave de número de IVA da sua empresa.
5. Acesse **Administração da organização** \> **Organizações** \> **Entidades legais** e selecione sua empresa.
6. Na Guia Rápida **Comércio exterior e logística**, na seção **Intrastat**, defina os campos **Exportação de número de isenção de IVA** e **Importação de número de isenção de IVA** para o código criado na etapa 4.
7. Na Guia Rápida **Registro de imposto**, no campo **Número de registro de imposto**, insira o número de registro de imposto da sua empresa.

#### <a name="set-up-the-vat-ids-for-trading-partners"></a>Configurar as IDs do IVA para parceiros comerciais

##### <a name="create-a-registration-type-for-the-company-code"></a>Criar um tipo de registro para o código da empresa

Você deve criar tipos de registro de ID do IVA para todos os países ou regiões com os quais sua empresa faz negócios.

1. Acesse **Administração da organização** \> **Catálogo de endereços global** \> **Tipos de registro** \> **Tipos de registro**.
2. No Painel de Ações, selecione **Novo** para criar um tipo de registro para o ID do IVA.
3. Na caixa de diálogo **Inserir detalhes do tipo de registro**, no campo **Nome**, insira um nome para o novo tipo de registro. Por exemplo, insira **ID do IVA**.
4. No campo **País/região**, selecione o país ou a região do parceiro comercial.
5. Selecione **Criar**.

##### <a name="match-the-registration-type-with-a-registration-category"></a>Faça a correspondência do tipo de registro com a categoria de registro

1. Acesse **Administração da organização** \> **Catálogo de endereços global** \> **Tipos de registro** \> **Categorias de registro**.
2. No Painel de Ações, selecione **Novo** para criar um link entre um tipo de registro e uma categoria de registro.
3. Para o tipo de registro para a ID do IVA, selecione a categoria de registro **ID do IVA**.
4. Repita as etapas 2 e 3 para os outros tipos de registro criados para os países ou regiões com os quais sua empresa faz negócios.

##### <a name="set-up-the-vat-number-of-a-trading-partner"></a>Configurar o número do IVA de um parceiro comercial

1. Acesse **Contas a receber** \> **Clientes** \> **Todos os clientes**.
2. Na grade, selecione um cliente.
3. No Painel de Ações, na guia **Cliente**, no grupo **Registro**, selecione **IDs do Registro**.
4. Na Guia Rápida **ID do Registro**, selecione **Adicionar** para criar uma ID do registro.
5. No campo **Tipo de registro**, selecione o tipo de registro criado para o código da empresa.
6. No campo **Número de registro**, insira o número do IVA da empresa.
7. No Painel de Ações, selecione **Salvar** e feche a página.

Para mais informações, consulte [IDs do Registro](emea-registration-ids.md).

### <a name="set-up-foreign-trade-parameters"></a>Configurar parâmetros de comércio exterior

1. Vá para **Imposto** \> **Configuração** \> **Comércio exterior** \> **Parâmetros de comércio exterior**.
2. Na guia **Intrastat**, na Guia Rápida **Relatório eletrônico**, no campo **Mapeamento de formato de arquivo**, selecione **INTRACOM Intrastat (FR)** ou **SAISUNIC Intrastat (FR)**.
3. No campo **Mapeamento de formato de relatório**, selecione **Relatório Intrastat**.
4. Na Guia Rápida **Hierarquia de código de mercadoria**, no campo **Hierarquia de categoria**, selecione **Intrastat**.
5. Na Guia Rápida **Geral**, no campo **Código de transação**, selecione o código usado para as transferências de mercadorias.
6. No campo **Nota de crédito**, selecione o código usado para devoluções de mercadorias.
7. No campo **Trabalhador**, selecione o nome da pessoa de contato.
8. Na guia **Contato**, adicione informações sobre a pessoa de contato:

    - No campo **Telefone**, insira o número de telefone da pessoa de contato.
    - No campo **Fax**, insira o número de fax da pessoa de contato.

9. Na guia **Propriedades de país/região**, no campo **País/região**, indique todos os países ou regiões com os quais sua empresa faz negócios. Para cada país que faz parte da UE, selecione **UE** no campo **Tipo de país/região**, para que o país apareça no seu relatório Intrastat. Para França, selecione **Doméstico** no campo **Tipo de país/região**.

### <a name="set-up-compression-of-intrastat"></a>Configurar compactação do Intrastat

- Acesse **Imposto** \> **Configuração** \> **Comércio exterior** \> **Compactação do Intrastat** e selecione os campos que podem ser comparados quando a informação do Intrastat é resumida. Para a Intrastat francesa, selecione os valores para os seguintes campos:
 
    - Procedimento estatístico
    - País/região de origem
    - Transporte
    - Correção
    - País/região
    - Região de origem/destino
    - Direção
    - País/região do remetente
    - Código de transação
    - Mercadoria

### <a name="set-up-product-parameters-for-the-intrastat-declaration"></a>Configurar os parâmetros de produto para a declaração Intrastat

1. Acesse **Gerenciamento de informações do produto** \> **Produtos** \> **Produtos liberados**.
2. Na grade, selecione um produto.
3. Na Guia Rápida **Comércio exterior**, na seção **Intrastat**, no campo **Mercadoria**, selecione o código da mercadoria. O nome da mercadoria será impresso no campo **Descrição de mercadorias** no relatório Intrastat.
4. Na seção **Origem**, no campo **País/região**, selecione o país ou a região de origem do produto.
5. Na Guia Rápida **Gerenciar estoque**, no campo **Peso líquido**, informe o peso do produto em quilogramas.

### <a name="ngp-codes"></a>Códigos NGP

No relatório DEB, a codificação de produtos consiste nos seguintes elementos:

- O código CN8 de oito dígitos que representa a tarifa e a nomenclatura estatística da UE.
- Se aplicável, o código de item nacional Nomenclature Générale des Produits (NGP) de um dígito.

Em 2022, o NGP aplica-se somente a três tipos de produtos:

- Alguns produtos de vacas, ovelhas e cabras
- Equipamento militar
- Vinhos franceses

Você deve configurar os códigos NGP e atribuí-los a produtos relacionados. O campo **NGP** é automaticamente definido na página **Diário do Intrastat**.

#### <a name="set-up-an-ngp-code"></a>Configurar um código NGP

1. Acesse **Imposto** \> **Configuração** \> **Comércio exterior** \> **Códigos NGP**.
2. No Painel de Ações, selecione **Novo**.
3. No campo **NGP**, insira um código de um único dígito.
4. No campo **Descrição**, insira uma descrição para o código.

#### <a name="assign-an-ngp-code-to-a-product"></a>Atribuir um código NGP a um produto

1. Acesse **Gerenciamento de informações do produto** \> **Produtos** \> **Produtos liberados**.
2. Na grade, selecione um produto.
3. Na Guia Rápida **Comércio exterior**, na seção **Intrastat**, no campo **NGP**, selecione o código NGP apropriado.

### <a name="set-up-warehouse-parameters-for-the-intrastat-declaration"></a>Configurar os parâmetros de depósito para a declaração Intrastat

1. Acesse **Gerenciamento de depósito** \> **Configuração** \> **Depósito** \> **Depósitos**.
2. Selecione um depósito e, na Guia Rápida **Endereços**, selecione **Adicionar** ou **Editar**.
3. Na caixa de diálogo, no campo **Cidade**, selecione a cidade do depósito. O estado ou província da cidade será usado como uma região do seu relatório DEB.

### <a name="set-up-the-transport-method"></a>Configurar o método de transporte

1. Vá para **Imposto** \> **Configuração** \> **Comércio exterior** \> **Método de transporte**.
2. No Painel de Ações, selecione **Novo**.
3. No campo **Transporte**, informe um código exclusivo. As empresas na França usam códigos de transporte de um dígito.

### <a name="intrastat-journal"></a>Diário do Intrastat

Acesse **Imposto** \> **Declarações** \> **Comércio exterior** \> **Intrastat** para gerenciar suas transações aplicáveis ao comércio exterior com países da UE. Para obter mais informações, consulte [Visão geral do Intrastat](emea-intrastat.md).

A coluna **NGP** é específica da França e mostra o código NGP do produto. Se o NGP não for aplicável a um produto, **0** (zero) será exibido. Para ajustar o código NGP, selecione a transação. Depois, na guia **Geral**, na seção **Códigos**, no campo **NGP**, selecione o código NGP necessário.

#### <a name="intrastat-transfer"></a>Transferência Intrastat

Na página **Intrastat**, no Painel de Ações, você pode selecionar **Transferir** para transferir automaticamente as informações sobre o comércio intracomunidade de ordens de venda, faturas de texto livre, ordens de compra, faturas de fornecedor, recebimentos de produtos do fornecedor, faturas de projeto e ordens de transferência. Somente os documentos que tiverem um país da UE como o país ou a região de destino (para envios) ou consignação (para recebimentos) serão transferidos.

Como o relatório DEB é uma combinação da lista de vendas da UE e do relatório Intrastat, ele também inclui transações *triangulares*, em que uma entrega direta é realizada de um país da UE (participante A) para outro país da UE (participante C), e uma entidade legal francesa (participante B) está no meio do acordo triangular.

#### <a name="generate-a-deb-intrastat-report"></a>Gerar um relatório DEB (Intrastat)

1. Acesse **Imposto** \> **Declarações** \> **Comércio exterior** \> **Intrastat**.
2. No Painel de Ações, selecione **Exportar** \> **Relatório**.
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

4. Selecione **OK** para fechar a caixa de diálogo **Relatório Intrastat**.
5. Na caixa de diálogo **Parâmetros do relatório eletrônico**, na Guia Rápida **Parâmetros**, no campo **Nível do relatório**, selecione o nível do relatório. O nível do relatório pode ser **1 - resposta estatística**, **4 - declaração de imposto** ou **5 - resposta estatística a remessa e declaração de imposto**.

## <a name="example"></a>exemplo

O exemplo a seguir mostra como configurar o Intrastat francês e criar o relatório DEB. Ele usa a entidade legal **DEMF**.

### <a name="preliminary-setup"></a>Configuração preliminar

1. No [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/Logon/Index), na biblioteca Ativos compartilhados, baixe as versões mais recentes das seguintes configurações de ER para o formato de declaração Intrastat:

    - Módulo intrastat
    - Relatório intrastat
    - INTRACOM Intrastat (FR)

2. Configure uma hierarquia de produtos:

    1. Acesse **Gerenciamento de informações sobre produtos** \> **Configuração** \> **Categorias e atributos** \> **Hierarquias de categoria**.
    2. Na grade, selecione **Intrastat**.
    3. No Painel de Ações, na guia **Hierarquia de categoria**, no grupo **Manter**, selecione **Editar**.
    4. No Painel de Ações, selecione **Novo nó de categoria**.
    5. No campo **Nome**, digite **Autres Libournais**.
    6. No campo **Código**, insira **2204 21 42**.
    7. No Painel de ações, selecione **Salvar**.

### <a name="set-up-vat-ids"></a>Configurar IDs do IVA

#### <a name="set-up-vat-codes-for-your-company"></a>Configurar códigos de IVA para sua empresa

1. Acesse **Imposto** \> **Configuração** \> **Imposto** \> **Números de isenção de imposto**.
2. No Painel de Ações, selecione **Novo**.
3. No campo **País/região**, selecione **FRA**.
4. No campo **Número de isenção de imposto**, insira **MS123456**.
5. Acesse **Administração da organização** \> **Organizações** \> **Entidades legais** e selecione **DEMF**.
6. Na Guia Rápida **Comércio exterior e logística**, na seção **Intrastat**, defina os campos **Exportação de número de isenção de IVA** e **Importação de número de isenção de IVA** para o código criado na etapa 4.
7. Na Guia Rápida **Registro de imposto**, no campo **Número de registro de imposto**, insira **123456789**.

#### <a name="set-up-the-vat-ids-for-trading-partners"></a>Configurar as IDs do IVA para parceiros comerciais

##### <a name="create-a-registration-type-for-the-company-code"></a>Criar um tipo de registro para o código da empresa

1. Acesse **Administração da organização** \> **Catálogo de endereços global** \> **Tipos de registro** \> **Tipos de registro**.
2. No Painel de Ações, selecione **Novo** para criar um tipo de registro para o ID do IVA.
3. Na caixa de diálogo **Inserir detalhes do tipo de registro**, no campo **Nome**, digite **ID do IVA**.
4. No campo **País/região**, selecione **DEU**.
5. Selecione **Criar**.

##### <a name="match-the-registration-type-with-a-registration-category"></a>Faça a correspondência do tipo de registro com a categoria de registro

1. Acesse **Administração da organização** \> **Catálogo de endereços global** \> **Tipos de registro** \> **Categorias de registro**.
2. No Painel de Ações, selecione **Novo** para criar um link entre o tipo de registro e a categoria de registro.
3. Para o tipo de registro **ID do IVA** do país **DEU**, selecione a categoria de registro **ID do IVA**.

##### <a name="set-up-the-customers-vat-registration-number"></a>Configurar o número de registro do IVA do cliente

1. Acesse **Contas a receber** \> **Clientes** \> **Todos os clientes**.
2. Na grade, selecione **DE-016**.
3. No Painel de Ações, na guia **Cliente**, no grupo **Registro**, selecione **IDs do Registro**.
4. Na Guia Rápida **ID do Registro**, selecione **Adicionar** para criar uma ID do registro.
5. No campo **Tipo de registro**, selecione **ID do IVA**.
6. No campo **Número de registro**, insira **DE9012**.
7. No Painel de Ações, selecione **Salvar** e feche a página.
8. Na Guia Rápida **Fatura e entrega**, na seção **Imposto**, no campo **Número de isenção de impostos**, selecione **DE9012**.

### <a name="set-up-foreign-trade-parameters"></a>Configurar parâmetros de comércio exterior

1. Vá para **Imposto** \> **Configuração** \> **Comércio exterior** \> **Parâmetros de comércio exterior**.
2. Na guia **Intrastat**, na Guia Rápida **Geral**, no campo **Código de transação**, selecione **11**.
3. Na Guia Rápida **Relatório eletrônico**, no campo **Mapeamento de formato de arquivo**, selecione **INTRACOM Intrastat (FR)**.
4. No campo **Mapeamento de formato de relatório**, selecione **Relatório Intrastat**.
5. Na Guia Rápida **Hierarquia de código de mercadoria**, no campo **Hierarquia de categoria**, selecione **Intrastat**.
6. No campo **Trabalhador**, selecione um registro.
7. Na guia **Contato**, no campo **Telefone**, insira o número de telefone do contato
8. No campo **Fax**, insira o número de fax do contato.

### <a name="create-ngp-code"></a>Criar código NGP

1. Acesse **Imposto** \> **Configuração** \> **Comércio exterior** \> **Códigos NGP**.
2. No Painel de Ações, selecione **Novo**.
3. No campo **NGP**, insira **8**.
4. No campo **Nome da descrição**, insira **NGP 8**.
5. No Painel de ações, selecione **Salvar**.

### <a name="set-up-product-information"></a>Configurar informações do produto

1. Acesse **Gerenciamento de informações do produto** \> **Produtos** \> **Produtos liberados**.
2. Na grade, selecione **D0001**.
3. Na Guia Rápida **Comércio exterior**, na seção **Intrastat**, no campo **NGP**, selecione **8**.
4. No campo **Mercadoria**, selecione **2204 21 42**.
5. Na seção **Origem**, no campo **País/região**, selecione **FRA**.
6. Na Guia Rápida **Gerenciar estoque**, na seção **Medidas de peso**, no campo **Peso líquido**, digite **2**.
7. No Painel de Ações, selecione **Salvar** e feche a página.
8. Na grade, selecione **D0003**.
9. Na Guia Rápida **Comércio exterior**, na seção **Intrastat**, no campo **Mercadoria**, selecione **100 200 30**.
10. Na seção **Origem**, no campo **País/região**, selecione **DEU**.
11. Na Guia Rápida **Gerenciar estoque**, na seção **Medidas de peso**, no campo **Peso líquido**, digite **5**.
12. No Painel de ações, selecione **Salvar**.

### <a name="set-up-regime-codes"></a>Configurar Códigos de regime

1. Acesse **Imposto** \> **Configuração** \> **Comércio exterior** \> **Procedimento estatístico**.
2. No Painel de Ações, selecione **Novo**.
3. No campo **Procedimento estatístico**, insira **21**.
4. No campo **Texto 1**, insira **Código de regime 21**.

### <a name="change-the-site-address"></a>Altere o endereço do site

1. Acesse **Gerenciamento do depósito** \> **Configuração** \> **Depósito** \> **Locais**.
2. Na grade, selecione **1**.
3. Na Guia Rápida **Endereços**, selecione **Editar**.
4. Na caixa de diálogo **Editar endereço**, no campo **País/região**, selecione **FRA**.
5. Selecione **OK**.
6. Acesse **Gerenciamento de depósitos** \> **Configuração** \> **Depósito** \> **Depósitos** e selecione um depósito.
7. Na FastTab **Endereço**, selecione **Adicionar**.
8. Na caixa de diálogo **Novo endereço**, no campo **País/região**, selecione **FRA**.
9. No campo **Cidade**, selecione **Bordeaux**.
10. Selecione **OK** para fechar a caixa de diálogo.

### <a name="set-up-a-transport-method"></a>Configurar um método de transporte

1. Vá para **Imposto** \> **Configuração** \> **Comércio exterior** \> **Método de transporte**.
2. No Painel de Ações, selecione **Novo**.
3. No campo **Transporte**, digite **3**.
4. No campo **Descrição**, insira **Transporte rodoviário**.

### <a name="assign-a-transport-mode-to-a-mode-of-delivery"></a>Atribuir um modo de transporte a um modo de entrega

1. Acesse **Compras e fornecimento** \> **Configuração** \> **Distribuição** \> **Modos de entrega**.
2. Na grade, selecione **50**.
3. Na Guia Rápida **Comércio exterior**, no campo **Transporte**, selecione **3**.

### <a name="create-a-sales-order-with-an-eu-customer-that-includes-the-new-product"></a>Criar uma ordem de venda com um cliente da UE que inclua o novo produto

1. Acesse **Contas a receber** \> **Ordens** \> **Todas as ordens de vendas**.
2. No Painel de Ações, selecione **Novo**.
3. Na caixa de diálogo **Criar ordem de venda**, na seção **Cliente**, no campo **Conta do cliente**, selecione **DE-016**.
4. Na seção **Endereço**, no campo **Endereço de entrega**, selecione o sinal de adição (**+**) para criar um endereço.
5. Na caixa de diálogo **Novo endereço**, no campo **Nome da descrição**, insira **Alemanha**.
6. No campo **País/região**, selecione **DEU**.
7. Selecione **OK**.
8. Na caixa de diálogo **Criar ordem de venda**, selecione **OK**.
9. Na Guia Rápida **Linhas da ordem de venda**, no campo **Número do item**, selecione **0001**.
10. Na Guia Rápida **Detalhes das linhas**, na guia **Comércio exterior**, no campo **Procedimento estatístico**, selecione **21**.
11. No campo **Estado de origem**, selecione **AL**.
12. No Painel de ações, selecione **Salvar**.
13. Na guia **Cabeçalho**, na Guia Rápida **Entrega**, no campo **Modo de entrega**, verifique se **50** está selecionado.
14. No Painel de Ação, na guia **Fatura**, no grupo **Gerar**, selecione **Fatura**.
15. Na caixa de diálogo **Lançando fatura**, na Guia Rápida **Parâmetros**, na seção **Parâmetro**, no campo **Quantidade**, selecione **Tudo**. Selecione **OK** para lançar a fatura.

### <a name="transfer-the-transaction-to-the-intrastat-journal-and-review-the-result"></a>Transfira a transação para o diário Intrastat e revise o resultado

1. Acesse **Imposto** \> **Declarações** \> **Comércio exterior** \> **Intrastat**.
2. No Painel de Ação, selecione **Transferir**.
3. Na caixa de diálogo **Intrastat (Transferência)**, na seção **Parâmetros**, defina a opção **Fatura de cliente** como **Sim**. Em seguida, selecione **OK**.
4. Classifique transações pelo campo **Data**. A transação superior é a transação de resultado.

    ![Linha que representa a ordem de venda na página Intrastat.](media/intrastat_fr_1.png)

5. Selecione a linha de transação e, em seguida, a guia **Geral** para exibir mais detalhes.

    ![Detalhes da ordem de venda na guia Geral da página Intrastat.](media/intrastat_fr_2.png)

6. No Painel de Ações, selecione **Exportar** \> **Relatório**.
7. Na caixa de diálogo **Relatório Intrastat**, na Guia Rápida **Parâmetros**, na seção **Data**, selecione o mês da ordem de venda que você criou.
8. Na seção **Opções de exportação**, defina a opção **Gerar arquivo** como **Sim**.
9. No campo **Nome do arquivo**, insira o nome necessário.
10. Selecione **OK** para fechar a caixa de diálogo **Relatório Intrastat**.
11. Na caixa de diálogo **Parâmetros do relatório eletrônico**, na Guia Rápida **Parâmetros**, no campo **Nível de relatório**, selecione **5 - resposta estatística para remessa e declaração de imposto** e revise o relatório.

    ![Relatório intrastat Intracom sobre expedições.](media/intrastat_fr_3.png)

12. Revise o relatório do Excel gerado.

    ![Relatório intrastat sobre expedições.](media/intrastat_fr_4.png)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
