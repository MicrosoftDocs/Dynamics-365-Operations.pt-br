---
title: Introdução ao Cálculo de Imposto
description: Este tópico explica como configurar o Cálculo de Imposto.
author: wangchen
ms.date: 08/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: intro-internal
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1ddbb22d4f7c6108ca93b415276c53794b5450dd
ms.sourcegitcommit: 03f53980a4bc67b73ac2be76a3b3e7331d0db705
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/18/2021
ms.locfileid: "7394500"
---
# <a name="get-started-with-tax-calculation"></a>Introdução ao Cálculo de Imposto

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Este tópico fornece informações sobre como começar a usar o Cálculo de Imposto. Ele orienta você nas etapas de configuração no Microsoft Dynamics Lifecycle Services (LCS), no Regulatory Configuration Service (RCS) e no Dynamics 365 Finance e Dynamics 365 Supply Chain Management. Depois, ele analisa o processo comum para usar recursos de Cálculo de Imposto em transações do Finance e do Supply Chain Management.

A configuração consiste em quatro etapas principais:

1. No LCS, instale o suplemento de Cálculo de Imposto.
2. No RCS, configure o recurso de Cálculo de Imposto. Essa configuração não é específica de uma entidade legal. Ela pode ser configurada entre entidades legais no Finance e no Supply Chain Management.
3. No Finance e no Supply Chain Management, configure os parâmetros de Cálculo de Imposto por entidade legal.
4. No Finance e no Supply Chain Management, crie transações, como ordens de venda, e use o Cálculo de Imposto para determinar e calcular impostos.

## <a name="prerequisites"></a>Pré-requisitos

Antes de concluir os procedimentos deste tópico, os pré-requisitos devem estar em vigor para cada tipo de ambiente.

### <a name="for-a-production-environment"></a>Para um ambiente de produção

Para um ambiente de produção, os seguintes pré-requisitos devem ser atendidos:

- Você deve ter acesso à conta do LCS e deve ter um projeto do LCS implantado com ambiente com Camada 2 ou superior que executa o Dynamics 365 versão 10.0.21 ou posterior.
- Você deve criar um ambiente de RCS para sua organização e deve ter acesso à sua conta. Para obter mais informações sobre como criar um ambiente de RCS, consulte [Visão geral do Regulatory Configuration Service](rcs-overview.md).
- Os recursos a seguir devem ser ativados no espaço de trabalho **Gerenciamento de recursos** de seu ambiente do Finance ou Supply Chain Management com base em suas necessidades de negócios:

    - Cálculo de Imposto
    - Oferecer suporte a vários números de inscrição de IVA
    - Imposto na ordem de transferência
    - Transferência da lista de vendas da UE com base apenas em transações de imposto
    - Relatório intrastat por ID de Imposto Múltiplo
    - Relatórios da lista de Vendas da UE por ID de Imposto Múltiplo
    - Declaração de impostos por ID de Imposto Múltiplo

- Os recursos a seguir devem ser ativados no espaço de trabalho **Gerenciamento de recursos** do seu ambiente RCS implantado.

    - Recursos de globalização

### <a name="for-a-test-environment-public-preview"></a>Para um ambiente de teste (Versão Preliminar Pública)

Para um ambiente de teste, os seguintes pré-requisitos devem ser atendidos:

- Você deve ter acesso à conta do LCS e deve ter um projeto do LCS implantado com ambiente com Camada 2 ou superior que executa o Dynamics 365 versão 10.0.18 com KB4616360 ou uma versão posterior.
- Você deve criar um ambiente de RCS para sua organização e deve ter acesso à sua conta. Para obter mais informações sobre como criar um ambiente de RCS, consulte [Visão geral do Regulatory Configuration Service](rcs-overview.md).
- Você deve entrar em contato com a Microsoft, enviando email para <taxcalc@microsoft.com> para habilitar a liberação de versões no ambiente do Finance ou Supply Chain Management implantado.
- Os recursos a seguir devem ser ativados no espaço de trabalho **Gerenciamento de recursos** de seu ambiente do Finance ou Supply Chain Management com base em suas necessidades de negócios:

    - Cálculo de Imposto
    - Oferecer suporte a vários números de inscrição de IVA
    - Imposto na ordem de transferência
    - Transferência da lista de vendas da UE com base apenas em transações de imposto
    - Relatório intrastat por ID de Imposto Múltiplo
    - Relatórios da lista de Vendas da UE por ID de Imposto Múltiplo
    - Declaração de impostos por ID de Imposto Múltiplo

- Os recursos a seguir devem ser ativados no espaço de trabalho **Gerenciamento de recursos** do seu ambiente RCS implantado.

    - Recursos de globalização

## <a name="set-up-tax-calculation-in-lcs"></a>Configure o Cálculo de Imposto em LCS

1. Entre no [LCS](https://lcs.dynamics.com)
2. Calcule a configuração da integração do Microsoft Power Platform. Para obter mais informações, consulte a [Visão geral dos suplementos](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).
3. Selecione um dos ambientes implantados e depois selecione **Instalar um novo suplemento**.
4. Selecione **Cálculo de Imposto**.
5. Leia e concorde com os termos e as condições e selecione **Instalar**.

## <a name="set-up-tax-calculation-in-rcs"></a>Configure o Cálculo de Imposto em RCS

As etapas nesta seção não estão relacionadas a uma entidade legal específica. É necessário concluir este procedimento somente uma vez, sendo possível concluí-lo em qualquer entidade legal no RCS.

1. Entre no [RCS](https://marketing.configure.global.dynamics.com/).
2. No espaço de trabalho **Relatório eletrônico**, adicione um novo provedor de configuração. Use o nome da empresa como o nome do provedor. Para obter mais informações, consulte [Criar provedores de configuração e marcá-los como ativos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
3. Selecione o provedor de configuração recém-criado e, depois, selecione **Definir como ativo**.
4. Selecione o provedor de configuração **Microsoft** e, depois, selecione **Repositórios**.
5. No campo **Tipo**, selecione **Global**.
6. Selecione **Abrir**.
7. Acesse o **Modelo de Dados do Imposto**, expanda a árvore de arquivos e selecione **Configuração de Imposto**.
8. Selecione a versão de configuração de imposto correta, com base na sua versão do Finance, e selecione **Importar**.

    | Versão de lançamento | Configuração de imposto                       | Mapeamento de modelo                   |
    | --------------- | --------------------------------------- | ------------------------------- |
    | 10.0.18         | Configuração de Imposto - Europa 30.12.82     |                                 |
    | 10.0.19         | Configuração de Cálculo do Imposto 36.38.193 |                                 |
    | 10.0.20         | Configuração de Cálculo do Imposto 40.43.208 |                                 |
    | 10.0.21         | Configuração de Cálculo do Imposto 40.46.212 | Mapeamento de Modelo do Dataverse 40.46.9 |

9. No espaço de trabalho **Recursos de globalização**, selecione **Recursos**, selecione o bloco **Cálculo de Imposto** e, em seguida, selecione **Adicionar**.
10. Selecione um dos seguintes tipos de recurso:

    - **Novo recurso** – crie uma configuração de recurso com conteúdo em branco.
    - **Com base no recurso existente** – crie um recurso usando um recurso existente e copie o conteúdo da configuração de recurso existente.

11. Insira um nome e uma descrição para o recurso e selecione **Criar recurso**.

    Depois de criar o recurso, será criada uma versão de rascunho dele automaticamente. Você pode selecionar **Obter esta versão** para trocar a base da versão de rascunho em qualquer versão concluída.

12. Selecione a versão de rascunho do recurso e, em seguida, selecione **Editar**. A página **Configuração de Cálculo do Imposto** é preenchida.
13. Selecione **Versão da configuração**. Consulte a versão da configuração importada na etapa 8.

    A Microsoft fornece uma configuração de imposto padrão para o cálculo do imposto. Essa configuração abrange a maioria dos requisitos de comportamentos de cálculo do imposto. Ela será atualizada com base nos feedbacks de mercado. Caso precise estender a configuração para atender a requisitos específicos, consulte [Como criar extensão no serviço de imposto](./tax-service-add-data-fields-tax-integration-by-extension.md) para obter informações sobre como gerar e selecionar sua própria configuração de imposto.

14. Depois de selecionar a **Versão da configuração**, várias guias são exibidas. Siga a ordem mostrada aqui para concluir a configuração de guia obrigatória.

    **Configuração obrigatória**

    - **Códigos do imposto** – mantém os dados mestres de códigos de imposto. Todos os códigos de imposto criados nessa guia são automaticamente sincronizados ao Finance ao habilitar a versão atual.
    - **Grupo de impostos** – define os dados mestres do grupo de impostos e os códigos de imposto no grupo.
    - **Grupo de impostos do item** – define os dados mestres do grupo de impostos e os códigos de imposto no grupo.

    **Configurações opcionais**

    - **Aplicabilidade do grupo de impostos** – define uma matriz que determina o grupo de impostos. Se nenhuma regra de aplicabilidade nessa matriz coincidir com o documento tributável do Dynamics 365, o Cálculo do Imposto usará o valor padrão na linha de documento tributável.
    - **Aplicabilidade do grupo de impostos do item** – define uma matriz que determina o grupo de impostos do item. Se nenhuma regra de aplicabilidade nessa matriz coincidir com o documento tributável do Dynamics 365, o Cálculo do Imposto usará o valor padrão na linha de documento tributável.
    - **Aplicabilidade do número de registro de imposto do cliente** – Se você tiver vários números de registro de imposto para um cliente, o Cálculo de Imposto pode automaticamente determinar o número de registro de imposto correto. Na matriz nessa guia, você define as regras que devem ser usadas para criar a determinação. Caso contrário, o Finance e o Supply Chain Management continuarão usando o número de registro de imposto padrão em documentos tributáveis de transações de vendas.
    - **Aplicabilidade do número de registro de imposto do fornecedor** – Se você tiver vários números de registro de imposto para um fornecedor, o Cálculo de Imposto pode automaticamente determinar o número de registro de imposto correto. Na matriz nessa guia, você define as regras que devem ser usadas para criar a determinação. Caso contrário, o Finance e o Supply Chain Management continuarão usando o número de registro de imposto padrão em documentos tributáveis de transações de compras.
    - **Aplicabilidade de códigos de lista** – determina automaticamente o valor do campo **Código da lista** por meio de regras mais flexíveis e configuráveis. Na matriz nessa guia, você define as regras que devem ser usadas para criar a determinação. Caso contrário, o Finance e o Supply Chain Management continuarão usando o código padrão em documentos tributáveis.

14. Na guia **Códigos de imposto**, selecione **Adicionar** e insira o código de imposto e uma descrição.
15. Selecione **Componente de imposto**. O componente de imposto é um grupo de métodos que foram definidos na versão anterior da configuração de imposto selecionada. Os seguintes componentes de imposto estão disponíveis:

    - Por valor líquido
    - Por valor bruto
    - Por quantidade
    - Por margem
    - Imposto sobre imposto

16. Selecione **Salvar**. Mais campos serão disponibilizados, com base no componente de imposto selecionado.
17. Use as seguintes opções para identificar a natureza do código de imposto:

    - É isento
    - É imposto sobre o uso
    - É encargo revertido
    - Excluir do cálculo de valor base

    Para um cenário de imposto sobre o uso, configure um único código de imposto com taxa de imposto positiva e marque como **É imposto sobre o uso**.

    Para um cenário de encargo revertido, configure até dois códigos de imposto, sendo que um tem uma taxa de imposto positiva e o outro tem uma taxa de imposto negativa, mas o mesmo valor de taxa. Marque o código de imposto negativo como **É encargo revertido**. Para obter mais informações sobre a solução de encargo revertido no Finance, consulte [Mecanismo de encargo revertido do esquema de IVA/GST](emea-reverse-charge.md).

    Para alguns tipos de impostos, que devem ser excluídos do cálculo de valor base do imposto para transações com preço incluído (por exemplo, taxas alfandegárias em alguns países ou regiões), marque a caixa de seleção **Excluir do Cálculo de Valor Base**. Para obter mais informações sobre esse parâmetro, consulte [Calculando o imposto sobre o preço quando a opção Preços incluem impostos está habilitada](global-exclude-from-tax-base-amount-calculation.md).

    Mantenha as taxas de impostos e os limites de valor do imposto para este código de imposto.

18. Repita as etapas 14 a 17 para adicionar outros códigos de imposto necessários.
19. Na guia **Grupo de impostos**, selecione a coluna **Grupo de impostos**, adicione-a à matriz como condição de entrada e, em seguida, adicione linhas para manter os dados mestre do grupo de impostos.

    Veja aqui um exemplo.

    | Grupo de impostos    | Códigos de impostos           |
    | ------------ | ------------------- |
    | DEU_Domestic | DEU_VAT19; DEU_VAT7 |
    | DEU_EU       | DEU_Exempt          |
    | BEL_Domestic | BEL_VAT21; BEL_VAT6 |
    | BEL_EU       | BEL_Exempt          |

20. Na guia **Grupo de impostos**, selecione a coluna **Grupo de impostos**, adicione-a à matriz como condição de entrada e, em seguida, adicione linhas para manter os dados mestre do grupo de impostos.

    Veja aqui um exemplo.

    | Grupo de impostos do item | Códigos de impostos                                    |
    | -------------- | -------------------------------------------- |
    | Completo           | DEU_VAT19; BEL_VAT21; DEU_Exempt; BEL_Exempt |
    | Reduzido        | DEU_VAT7; BEL_VAT6; DEU_Exempt; BEL_Exempt   |

21. Na guia **Aplicabilidade de grupo de impostos**, selecione as colunas necessárias para determinar o grupo de imposto correto e selecione **Adicionar**. Insira ou selecione os valores de cada coluna. O campo **Grupo de impostos** será a saída dessa matriz. Se essa guia não estiver configurada, será usado o grupo de impostos na linha da transação.

    Veja aqui um exemplo.

    | Processo comercial | Remeter de | Remeter para | Grupo de impostos    |
    | ---------------- | --------- | ------- | ------------ |
    | Vendas            | DEU       | DEU     | DEU_Domestic |
    | Vendas            | DEU       | FRA     | DEU_EU       |
    | Vendas            | BEL       | BEL     | BEL_Domestic |
    | Vendas            | BEL       | FRA     | BEL_EU       |

22. Na guia **Aplicabilidade do grupo de impostos do item**, selecione as colunas necessárias para determinar o código do imposto correto e selecione **Adicionar**. Insira ou selecione os valores de cada coluna. O campo **Grupo de impostos** será a saída dessa matriz. Se essa guia não estiver configurada, será usado o grupo de impostos do item na linha da transação.

    Veja aqui um exemplo.

    | Código do item | Grupo de impostos do item |
    | --------- | -------------- |
    | D0001     | Completo           |
    | D0003     | Reduzido        |

    Para obter mais informações sobre como os códigos de impostos são determinados no Cálculo do Imposto, consulte [Grupo de impostos e lógica de determinação do grupo de impostos do item](global-sales-tax-group-determination.md).

23. Configure a aplicabilidade dos números de registro de imposto do cliente, números de registro de imposto do fornecedor e códigos de lista com base nas necessidades de negócios.
24. Selecione **Salvar** e feche a página.
25. Selecione **Alterar status** \> **Concluir**. Depois que o status for alterado para **Concluído**, a versão não poderá mais ser editada.
26. Selecione **Alterar status** \> **Publicar**. Esta versão da configuração do recurso de imposto será enviado para o repositório global e ficará visível para cada entidade legal no Finance.

## <a name="set-up-tax-calculation-in-dynamics-365"></a>Configurar Cálculo de Imposto no Dynamics 365

Depois de concluir a configuração no RCS, você terá uma versão publicada do recurso de imposto. Siga estas etapas para configurar o Cálculo de Imposto no Finance.

A configuração nesta seção é realizada pela entidade legal. É necessário configurá-la para cada entidade legal em que deseja habilitar o Cálculo de Imposto do Finance.

1. No Finance, vá para **Imposto** \> **Configuração** \> **Configuração do imposto** \> **Parâmetros de cálculo do imposto**.
2. Na guia **Geral**, defina os seguintes campos:

    - **Habilitar Serviço de Cálculo de Imposto** – marque esta caixa de seleção para habilitar o Cálculo de Imposto da entidade legal. Se ele não estiver habilitado para a entidade legal atual, a entidade legal continuará usando o mecanismo de imposto existente para determinar e calcular o imposto.
    - **Configuração do recurso** – selecione uma configuração e versão de recurso de imposto publicado da entidade legal. Para obter mais informações sobre como configurar e concluir um recurso de imposto publicado, consulte a versão anterior deste tópico.
    - **Processo Comercial** – Selecione os processos comerciais a serem habilitados.

3. Na guia **Cálculo**, defina a regra de arredondamento esperada para a entidade legal. Para obter mais informações sobre a lógica de arredondamento, consulte [Regras de arredondamento de cálculo de imposto](https://go.microsoft.com/fwlink/?linkid=2166988).
4. Na guia **Tratamento de erros**, defina o método de tratamento de erros esperado para a entidade legal. Três opções estão disponíveis:

    - Não
    - Aviso
    - Erro

    Você pode configurar um método de tratamento de erros para cada código de resultado na seção **Detalhes**. Como alternativa, se alguns códigos de resultado não são sincronizados do serviço de cálculo de imposto, você pode configurar um método padrão na seção **Geral**.

5. Na guia **Vários registros de IVA**, é possível habilitar a declaração de IVA, a lista de Vendas da UE e o Intrastat separadamente para trabalhar em um cenário de registros de IVA múltiplo. Para obter mais informações sobre relatórios de impostos para vários registros de IVA, consulte [Relatórios de vários registros de IVA](emea-reporting-for-multiple-vat-registrations.md).
6. Salve a configuração e repita as etapas anteriores para cada entidade legal adicional. Quando uma nova versão for publicada e você desejar aplicá-la, defina o campo **Configuração do recurso** na guia **Geral** da página **Parâmetros de cálculo de imposto** (consulte a etapa 2).

## <a name="transaction-processing"></a>Processamento de transações

Depois de concluir todos os procedimentos de configuração, é possível usar o Cálculo de Imposto para determinar e calcular impostos no Finance. As etapas para processar transações continuam as mesmas. As seguintes transações são compatíveis com o Finance versão 10.0.21:

- Processo de Vendas

    - Cotação de Venda
    - Ordem de Venda
    - Confirmação
    - Lista de Separação
    - Guia de Remessa
    - Fatura de venda
    - Nota de Crédito
    - Ordem de retorno
    - Encargo de cabeçalho
    - Encargo da linha

- Processo de compra

    - Ordem de Compra
    - Confirmação
    - Lista de Recebimentos
    - Recebimento de produtos
    - Fatura de compra
    - Encargo de cabeçalho
    - Encargo da linha
    - Nota de Crédito
    - Ordem de retorno
    - Requisição de Compra
    - Encargo da linha de requisição de compra
    - Solicitação de cotação
    - Encargo do cabeçalho da solicitação de cotação
    - Encargo da linha da solicitação de cotação

- Processo de estoque

    - Ordem de transferência – enviar
    - Ordem de transferência – receber
