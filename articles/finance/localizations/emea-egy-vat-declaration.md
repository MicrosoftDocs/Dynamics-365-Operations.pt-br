---
title: Declaração de IVA para o Egito
description: Este artigo explica como configurar e gerar o formulário de devolução de IVA para o Egito.
author: AdamTrukawka
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: 2017-06-20
ms.dyn365.ops.version: 10.0.17
ms.search.scope: ''
ms.openlocfilehash: c035c52d7d577a01f5903461548c0cb33f05045f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287811"
---
#  <a name="vat-declaration-for-egypt-eg-00002"></a>Declaração de IVA para o Egito (EG-00002)

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/banner.md)]

Este artigo explica como configurar e gerar o formulário de devolução de IVA e os livros de vendas e de compras para entidades legais no Egito.

O formulário de devolução de IVA para Egito é o documento oficial que resume o valor total de imposto IVA de saída devido, o valor de imposto IVA de entrada total recuperável e a obrigação do valor de imposto IVA relacionado. O formulário é usado para todos os tipos de contribuintes e deve ser preenchido manualmente por meio do portal da autoridade de imposto. O formulário de devolução de IVA normalmente é mencionado como o perfil de devolução de IVA.

O formulário de devolução de IVA no Dynamics 365 Finance inclui os seguintes relatórios:

- Formulário de devolução de IVA número 10, que fornece uma divisão de valores, ajustes e valor de IVA por item de linha no formulário de devolução de IVA, conforme descrito na legislação.
- Registro de transações de vendas
- Registro de transações de compra

## <a name="prerequisites"></a>Pré-requisitos
O público-alvo principal da entidade legal deve estar no Egito.
No espaço de trabalho **Gerenciamento de recursos**, habilite este recurso:

   - (Egito) Hierarquia de categorias para o Sales e relatório de impostos.

Para obter mais informações sobre como habilitar recursos, consulte [Visão geral do gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

No espaço de trabalho **Relatório eletrônico**, importe o seguinte formato de Relatório eletrônicos do repositório:

- Declaração de IVA Excel (EG)

> [!NOTE]
> O formato acima se baseia no **modelo Declaração de impostos** e usa o **mapeamento de modelos Declaração de imposto**. As configurações adicionais serão automaticamente importadas.

Para obter mais informações sobre como importar configurações de Relatório eletrônico, consulte [Baixar configurações de Relatório eletrônico do Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

## <a name="download-electronic-reporting-configurations"></a>Baixar configurações de Relatório eletrônico

A implementação do formulário de devolução de IVA para o Egito baseia-se em configurações de Relatório eletrônico (ER). Para obter mais informações sobre os recursos e conceitos de relatórios configuráveis, consulte [Relatórios eletrônicos](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

Para ambientes de produção e de teste de aceitação de usuários (UAT), consulta [Baixar configurações de Relatório eletrônico do Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

Para gerar o formulário de devolução de IVA e os relatórios relacionados em uma entidade legal do Egito, carregue as seguintes configurações:

- Declaração de imposto modelo.versão.70.xml ou versão posterior
- Modelo de declaração de imposto mapeamento.versão.70.120.xml ou uma versão posterior
- Declaração de IVA Excel (EG).versão.70.32 ou uma versão posterior

Depois de baixar as configurações de ER do Lifecycle Services (LCS) ou do repositório global, execute as etapas a seguir.

1. Acesse o espaço de trabalho **Relatório eletrônico** e selecione o bloco **Configurações de relatórios**.
1. Na página **Configurações**, no Painel de Ações, selecione **Troca** > **Carregar de arquivo XML**.
1. Carregue os arquivos na ordem em que foram listados acima. Depois que todas as configurações são carregadas, a árvore de configuração deve estar presente no Finance.

## <a name="set-up-application-specific-parameters"></a>Configurar parâmetros específicos do aplicativo

Os parâmetros específicos do aplicativo permitem estabelecer os critérios de como as transações de impostos serão classificadas e calculadas em cada linha quando o relatório é gerado. A determinação se baseia na configuração do grupo de impostos sobre vendas do item, do grupo de impostos sobre vendas, do código do imposto e de outros critérios estabelecidos na definição de pesquisa.

Os relatórios de registros de vendas e de compras para o Egito incluem um conjunto de colunas que correspondem a classificações de transação específicas como tipos de operações, produtos e documentos específicos para o Egito. Em vez de incluir essas novas classificações como novos dados de entrada quando as transações são lançadas, as classificações serão determinadas com base nas diferentes pesquisas introduzidas em **Configurações** > **Configurar parâmetros específicos do aplicativo** > **Configuração** para atender aos requisitos de relatórios de IVA para o Egito. 

![Página de parâmetros específicos do aplicativo.](media/egypt-vat-declaration-setup1.png)

Essas configurações de pesquisa a seguir são usadas para classificar as transações nos relatórios de registros de IVA de compra e de venda:

- **PurchaseItemTypeLookup** > Coluna O: Tipo de item
- **VATRateTypeLookup** > Coluna B: Tipo de imposto
- **VATRateTypeLookup** > Coluna C: Tipo de item de tabela
- **PurchaseOperationTypeLookup** > Coluna A: Tipo de documento
- **CustomerTypeLookup** > Coluna A: tipo de documento
- **SalesOperationTypeLookup** > Coluna N: Tipo de operação
- **SalesItemTypeLookup** > Coluna O: Tipo de item

Conclua as etapas a seguir para configurar as diferentes pesquisas usadas para gerar a declaração de IVA e os livros fiscais relacionados. 

1. No espaço de trabalho **Relatório eletrônico**, selecione **Configurações** > **Configuração** para identificar a transação de imposto na caixa relacionada do formulário de devolução de IVA.
2. Selecione a versão atual e, na Guia Rápida **Pesquisas**, selecione o nome da pesquisa. Por exemplo, **SalesItemTypeLookup**. Essa pesquisa identifica a lista de classificações no registro de IVA de vendas exigido pela autoridade fiscal.
3. Na Guia Rápida **Condições**, selecione **Adicionar** e, na nova linha na coluna **Resultado da pesquisa**, selecione a linha relacionada que representa a classificação na **Coluna O**.
4. Na coluna **Grupo de itens de imposto**, selecione o grupo de impostos usado para identificar a classificação. Por exemplo, **Fatura de venda doméstica**. Você também pode usar o grupo de impostos sobre vendas do item, o código de imposto ou a combinação de atributos de árvore se a configuração for definida de outra maneira. 
5. Na coluna **Nome**, selecione a classificação de transação de imposto.
6. Repita as etapas 3 a 5 para todas as pesquisas disponíveis.
7. Selecione **Adicionar** para incluir a linha de registro final e, na coluna **Resultado da pesquisa**, selecione **Não aplicável**. 
8. Nas colunas restantes, selecione **Não vazio**. 
9. No campo **Estado**, selecione **Concluído**.
10. Selecione **Salvar** e feche a página **Parâmetros específicos do aplicativo**.

> [!NOTE]
> Ao adicionar o último registro, **Não aplicável**, você define a seguinte regra: quando o grupo de impostos sobre vendas, o grupo de impostos sobre vendas do item, o código de imposto e o nome que é passado como um argumento não satisfazem nenhuma das regras anteriores, as transações não são incluídas no registro de IVA de saída. Embora essa regra não seja usada ao gerar o relatório, a regra ajuda a evitar erros na geração de relatórios quando há uma configuração de regra ausente.

As tabelas a seguir representam um exemplo de configuração sugerida para as configurações de pesquisa descritas. 

**SalesItemTypeLookup**

| Resultado da pesquisa         | Linha | Grupo de impostos sobre vendas    | Grupo de impostos do item    | Código de imposto (Código) | Organização                  |
|-----------------------|------|--------------------|-------------------------|-----------------|-----------------------|
| Doméstico              | 1    | VAT_LOCAL          | *Não vazio*             | *Não vazio*     | Vendas                 |
| Doméstico              | 2    | VAT_LOCAL          | *Não vazio*             | *Não vazio*     | SalesCreditNote       |
| Doméstico              | 3    | VAT_FINALC         | *Não vazio*             | *Não vazio*     | Vendas                 |
| Doméstico              | 4    | VAT_FINALC         | *Não vazio*             | *Não vazio*     | SalesCreditNote       |
| Doméstico              | 5    | VAT_PUBLIO         | *Não vazio*             | *Não vazio*     | Vendas                 |
| Doméstico              | 6    | VAT_PUBLIO         | *Não vazio*             | *Não vazio*     | SalesCreditNote       |
| Exportar                | 7    | VAT_EXPORT         | *Não vazio*             | *Não vazio*     | Vendas                 |
| Exportar                | 8    | VAT_EXPORT         | *Não vazio*             | *Não vazio*     | SalesCreditNote       |
| Máquina e equipamento | 9    | *Não vazio*        | VAT_M&E                 | *Não vazio*     | Vendas                 |
| Máquina e equipamento | 10   | *Não vazio*        | VAT_M&E                 | *Não vazio*     | SalesCreditNote       |
| Máquinas de peças        | 11   | *Não vazio*        | VAT_PARTS               | *Não vazio*     | Vendas                 |
| Máquinas de peças        | 12   | *Não vazio*        | VAT_PARTS               | *Não vazio*     | SalesCreditNote       |
| Isenções            | 13   | VAT_EXE            | *Não vazio*           | *Não vazio*     | SaleExempt            |
| Isenções            | 14   | VAT_EXE            | *Não vazio*           | *Não vazio*     | SalesExemptCreditNote |
| Não Aplicável        | 15   | *Em Branco*            | *Em Branco*                 | VAT_ADJ         | *Não vazio*           |
| Não Aplicável        | 16   | *Não vazio*        | *Não vazio*             | *Não vazio*     | *Não vazio*           |

 **SalesOperationTypeLookup**

| Resultado da pesquisa  | Linha | Grupo de impostos do item    | Código do imposto    | Organização                  |
|----------------|------|-------------------------|-------------|-----------------------|
| Mercadorias          | 1    | VAT_GOODS               | *Não vazio* | Vendas                 |
| Mercadorias          | 2    | VAT_GOODS               | *Não vazio* | SalesCreditNote       |
| Mercadorias          | 3    | VAT_GOODS               | *Não vazio* | SaleExempt            |
| Mercadorias          | 4    | VAT_GOODS               | *Não vazio* | SalesExemptCreditNote |
| Prestador de serviços       | 5    | VAT_SERV                | *Não vazio* | Vendas                 |
| Prestador de serviços       | 6    | VAT_SERV                | *Não vazio* | SalesCreditNote       |
| Prestador de serviços       | 7    | VAT_SERV                | *Não vazio* | SaleExempt            |
| Prestador de serviços       | 8    | VAT_SERV                | *Não vazio* | SalesExemptCreditNote |
| Ajustes    | 9    | *Em Branco*                 | VAT_ADJ     | Vendas                 |
| Ajustes    | 10   | *Em Branco*                 | VAT_ADJ     | SalesCreditNote       |
| Não Aplicável | 11   | *Não vazio*             | *Não vazio* | *Não vazio*           |

**PurchaseItemTypeLookup**

| Resultado da pesquisa          | Linha | Grupo de impostos do item    | Código do imposto    | Organização                     |
|------------------------|------|-------------------------|-------------|--------------------------|
| Mercadorias                  | 1    | VAT_GOODS               | *Não vazio* | Compra                 |
| Mercadorias                  | 2    | VAT_GOODS               | *Não vazio* | PurchaseCreditNote       |
| Prestador de serviços               | 3    | VAT_SERV                | *Não vazio* | Compra                 |
| Prestador de serviços               | 4    | VAT_SERV                | *Não vazio* | PurchaseCreditNote       |
| Máquina e equipamento  | 5    | VAT_M&E                 | *Não vazio* | Compra                 |
| Máquina e equipamento  | 6    | VAT_M&E                 | *Não vazio* | PurchaseCreditNote       |
| Máquinas de peças         | 7    | VAT_PARTS               | *Não vazio* | Compra                 |
| Máquinas de peças         | 8    | VAT_PARTS               | *Não vazio* | PurchaseCreditNote       |
| Isenções             | 9    | VAT_EXE                 | *Não vazio*  | PurchaseExempt           |
| Isenções             | 10   | VAT_EXE                 | *Não vazio* | PurchaseExemptCreditNote |
| Não Aplicável         | 11   | *Não vazio*             | *Não vazio* | *Não vazio*              |

**PurchaseOperationTypeLookup**

| Resultado da pesquisa  | Linha | Grupo de impostos sobre vendas  | Código do imposto    | Organização                     |
|----------------|------|------------------|-------------|--------------------------|
| Doméstico       | 1    | VAT_LOCAL        | *Não vazio* | Compra                 |
| Doméstico       | 2    | VAT_LOCAL        | *Não vazio* | PurchaseCreditNote       |
| Doméstico       | 3    | VAT_LOCAL        | *Não vazio* | PurchaseExempt           |
| Doméstico       | 4    | VAT_LOCAL        | *Não vazio* | PurchaseExemptCreditNote |
| Importado       | 5    | VAT_IMPORT       | *Não vazio* | Compra                 |
| Importado       | 6    | VAT_IMPORT       | *Não vazio* | PurchaseCreditNote       |
| Importado       | 7    | VAT_IMPORT       | *Não vazio* | PurchaseExempt           |
| Importado       | 8    | VAT_IMPORT       | *Não vazio* | PurchaseExemptCreditNote |
| Ajustes    | 9    | *Em Branco*          | VAT_ADJ     | PurchaseCreditNote       |
| Ajustes    | 10   | *Em Branco*          | VAT_ADJ     | Compra                 |
| Não Aplicável | 11   | *Não vazio*      | *Não vazio* | *Não vazio*              |

**CustomerTypeLookup**

|    Resultado da pesquisa    | Linha | Grupo de impostos sobre vendas |
|---------------------|------|-----------------|
| Organização        |  1   | VAT_LOCAL       |
| Organização        |  2   | VAT_EXPORT      |
| Organização        |  3   | VAT_EXE         |
| Consumidor final      |  4   | VAT_FINALC      |
| Organização pública |  5   | VAT_PUBLIO      |
| Não Aplicável      |  6   | *Não vazio*     |

**VATRateTypeLookup**

| Resultado da pesquisa  | Linha | Código de imposto (Código) |
|----------------|------|-----------------|
| GeneralGoods   | 1    | VAT_ST          |
| GeneralGoods   | 2    | VAT_RD          |
| FirstTable     | 3    | *Não vazio*     |
| SecondTable    | 4    | *Não vazio*     |
| Não Aplicável | 5    | *Não vazio*     |


## <a name="set-up-general-ledger-parameters"></a>Configurar parâmetros de Contabilidade

Para gerar o relatório do formulário de devolução de IVA no formato do Microsoft Excel, defina um formato ER na página **Parâmetros da Contabilidade**.

1. Acesse **Imposto** > **Configuração** > **Parâmetros de Contabilidade**.
2. Na guia **Imposto**, na seção **Opções de imposto**, no campo **Mapeamento de formatos do demonstrativo de IVA**, selecione **Declaração de IVA Excel (EG)**. Se você deixar o campo em branco, o relatório de imposto padrão será gerado no formato SSRS.
3. Selecione a **Hierarquia de categoria**. Esta categoria habilita o código de mercadoria nas transações da guia comércio exterior para permitir que os usuários selecionem e classifiquem bens e serviços. A descrição dessa classificação é detalhada nos relatórios de transações de venda e de compra. Essa configuração é opcional.

![Formulário de declaração.](media/egypt-vat-declaration-setup2.png)


## <a name="generate-a-vat-return-report"></a>Gerar um relatório de devolução de IVA
O processo para preparar e enviar um relatório de devolução de IVA para um período baseia-se em transações de pagamento de impostos sobre vendas que foram lançadas durante a liquidação e lançar o trabalho de imposto. Para obter mais informações sobre a liquidação e relatório de imposto, consulte [Visão geral de imposto](../general-ledger/indirect-taxes-overview.md).

Conclua as etapas a seguir para gerar o relatório de declaração de impostos.

1. Acesse **Imposto** > **Declarações** > **Imposto** > **Relatar imposto para o período de liquidação** ou **Liquidar e lançar imposto**.
2. Selecione o **Período de liquidação**.
3. Selecione a data inicial e selecione a versão de pagamento do imposto.
5. Selecione **OK**. 
6. Insira o valor do crédito do período anterior, se aplicável, ou deixe o valor como zero.
7. No campo **Detalhes de relatórios**, selecione uma das seguintes opções disponíveis. 
   - **Registro de IVA de entrada**: gere o relatório de detalhes de transações de imposto.
   - **Registro de IVA de saída**: gere o relatório de detalhes de transações de imposto.
   - **Declaração de IVA**: gere somente o formulário de devolução da declaração de IVA.
8. Insira o nome da pessoa que está registrada para atribuir o formulário.
9. Selecione o idioma. Todos os relatórios são traduzidos em **en-us** e **ar-eg**.
  
[!INCLUDE[footer-include](../../includes/footer-banner.md)]


