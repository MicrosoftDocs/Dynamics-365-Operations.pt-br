---
title: Declaração de imposto retido na fonte para o Egito
description: Este tópico explica como configurar e gerar as declarações de imposto retido na fonte para o Egito.
author: sndray
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: ''
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2017-06-20
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 8c9aaa3868167806ce3189d724621991ec7e53eb
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022802"
---
#  <a name="withholding-tax-declaration-for-egypt-eg-00005"></a>Declaração de imposto retido na fonte para o Egito (EG-00005)

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

## <a name="overview"></a>Visão Geral
Este tópico explica como configurar e gerar a declaração de imposto retido na fonte e os formulários de declaração de imposto retido na fonte 41 e 11 para entidades legais no Egito 

Todas as entidades egípcias devem preparar o formulário 41, que resume todos os impostos que são retidos de fornecedores locais e provedores de serviço. Além do formulário 41, o formulário 11 deve ser gerado para detalhar todos os impostos retidos de fornecedores estrangeiros. 

O relatório **Declaração de imposto retido na fonte** no Dynamics 365 Finance inclui os seguintes relatórios:

- Nº do formulário de declaração 41
- Nº do formulário de declaração 11
    
    
## <a name="prerequisites"></a>Pré-requisitos
O público-alvo principal da entidade legal deve estar no Egito.
No espaço de trabalho **Gerenciamento de recursos**, o recurso a seguir deve estar habilitado:

   - **Imposto retido na fonte global**

Para obter mais informações sobre como habilitar recursos, consulte [Visão geral do gerenciamento de recursos.](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)

1. Acesse **Imposto** > **Configuração** > **Parâmetros** > **Parâmetros de Contabilidade** e, na guia **Imposto retido na fonte**, defina **Habilitar imposto retido na fonte global** como **Sim**.
2. No espaço de trabalho **Relatório eletrônico**, importe os seguintes formatos de Relatório eletrônicos do repositório:

    - Declaração WHT Excel (EG)

    > [!NOTE]
    > O formato acima se baseia no **modelo Declaração de impostos** e usa o **mapeamento de modelos Declaração de imposto**. Essa configuração adicional é importada automaticamente.

Para obter mais informações sobre como importar configurações de Relatório eletrônico, consulte [Baixar configurações de Relatório eletrônico do Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

## <a name="download-electronic-reporting-configurations"></a>Baixar configurações de Relatório eletrônico

A implementação dos formulários de declaração WHT para o Egito baseia-se em configurações de Relatório eletrônico (ER). Para obter mais informações sobre os recursos e conceitos de relatórios configuráveis, consulte [Relatórios eletrônicos](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

Para ambientes de produção e de teste de aceitação de usuários (UAT), siga as instruções no tópico [Baixar configurações de Relatório eletrônico do Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

Para gerar as Declarações de retenção em uma entidade legal egípcia, é necessário carregar as seguintes configurações:

- Declaração de imposto modelo.versão.82.xml ou versão posterior
- Modelo de declaração de imposto mapeamento.versão.82.133.xml ou uma versão posterior
- Declaração WHT Excel (EG).versão.82.21 ou uma versão posterior

Depois de terminar de baixar as configurações de ER do Lifecycle Services (LCS) ou do repositório global, execute as etapas a seguir.

1. Acesse o espaço de trabalho **Relatório eletrônico** e selecione o bloco **Configurações de relatórios**.
1. Na página **Configurações**, no Painel de Ações, selecione **Troca > Carregar de arquivo XML**.
1. Carregue todos os arquivos na ordem em que estão listados nos marcadores anteriores. Depois que todas as configurações são carregadas, a árvore de configuração deve estar presente no Finance.

## <a name="set-up-application-specific-parameters"></a>Configurar parâmetros específicos do aplicativo

A opção de parâmetros específicos do aplicativo permite que os usuários estabeleçam os critérios de como as transações de imposto serão classificadas e calculadas em cada linha de um relatório gerado, dependendo da configuração do **grupo de itens de imposto retido na fonte** ou de outros critérios estabelecidos na definição de pesquisa.

O formulário 41 de imposto retido na fonte inclui uma coluna específica na qual a transação de imposto retido na fonte deve ser classificada de acordo com a classificação de autoridade de imposto chamada **Tipo de código de desconto**. Em vez de incluir essas novas classificações como novos dados de entrada quando as transações são lançadas, as classificações serão determinadas com base nas diferentes pesquisas introduzidas em **Configurações** > **Configurar parâmetros específicos do aplicativo** > **Configuração** para atender aos requisitos de relatórios de retenção para o Egito. 

A configuração a seguir é usada para classificar as transações no formulário 41 Declaração de retenção.

- **DiscountTaxTypeLookup**-> Coluna Nº 18 

Conclua as etapas a seguir para configurar as diferentes pesquisas usadas para gerar a declaração WHT e os livros fiscais relacionados. 

1. No espaço de trabalho **Relatório eletrônico**, selecione **Configurações** > **Configuração** para configurar as regras para identificar como as transações são classificadas no relatório de declaração WHT. 
2. Selecione a versão atual e, na Guia Rápida **Pesquisas**, selecione o nome da pesquisa. Por exemplo, **DiscountTaxTypeLookup**. Essa pesquisa identifica a lista de tipos de desconto exigidos pela autoridade fiscal.
3. Na Guia Rápida **Condições**, selecione **Adicionar** e, na nova linha na coluna **Resultado da pesquisa**, selecione a linha relacionada que representa a classificação na **Coluna 18**.
4. Na coluna **Grupo de itens de imposto retido na fonte**, selecione o código relacionado que é usado para identificar a classificação. Por exemplo, **Desconto permitido**.  
5. Repita as etapas 3 e 4 para todas as pesquisas disponíveis.
6. Selecione **Adicionar** novamente para incluir a linha de registro final e, na coluna **Resultado da pesquisa**, selecione **Não aplicável**. 
7. Nas colunas restantes, selecione **Não vazio**. 

> [!NOTE]

## <a name="set-up-general-ledger-parameters"></a>Configurar parâmetros de Contabilidade

Para gerar os relatórios do formulário de declaração WHT no Microsoft Excel, defina um formato ER na página **Parâmetros da Contabilidade**.

1. Acesse **Imposto** > **Configuração** > **Parâmetros de Contabilidade**.
2. Na guia **Imposto retido na fonte**, no campo **Mapeamento de formato de declaração WHT**, selecione **Declaração WHT Excel (EG)**. Se você deixar o campo em branco, o relatório de imposto padrão será gerado no formato SSRS.


![Formulário de declaração](media/egypt-wht-declaration-setup1.png)

## <a name="generate-the-withholding-declaration-forms"></a>Gerar os formulários Declaração de retenção
O processo de preparação e de envio de um formulário Declaração de retenção para um período específico é baseado nas transações de retenção de imposto lançadas durante a liquidação e lançar o trabalho de imposto de pagamento. Para obter mais informações sobre imposto retido na fonte global, consulte [Imposto retido na fonte global](../general-ledger/global-withholding-tax-overview.md).

Conclua as etapas a seguir para gerar o relatório de declaração de impostos.

1. Acesse **Imposto** > **Declarações** > **Imposto retido na fonte** > **Pagamento de imposto retido na fonte*.
2. Selecione o período de liquidação e selecione a data inicial do relatório. 
3. Insira a data de transação e selecione **OK**.
4. Na caixa de diálogo que é aberta, selecione um ou mais dos tipos de formulário **Formulário Nº 41**, **Formulário Nº 11** ou **Nenhum**. Se você selecionar **Nenhum**, o relatório padrão será gerado. 
5. Selecione o idioma. Todos os relatórios são traduzidos em **en-us** e **ar-eg**.
6. Insira o branch e o nome do banco em que o pagamento de imposto será pago.
7. Selecione o tipo comercial e insira os números de cheque e documento. 
8. Insira o tipo da entidade. 
9. Insira o nome da pessoa registrada para atribuir o formulário e selecione **OK** para confirmar a geração do relatório. 

 
[!INCLUDE[footer-include](../../includes/footer-banner.md)]
