---
title: Introdução ao Cálculo de Imposto
description: Este tópico explica como configurar o Cálculo de Imposto.
author: wangchen
ms.date: 05/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: e72b81d4a109db2dd8b4c6ca2ca0b030220e25f3
ms.sourcegitcommit: 60afcd85b3b5b9e5e8981ebbb57c0161cf05e54b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2021
ms.locfileid: "6216710"
---
# <a name="get-started-with-the-tax-calculation-preview"></a>Introdução ao Cálculo de Imposto (versão preliminar)

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Este tópico fornece informações sobre como começar a usar o Cálculo de Imposto. Primeiro, ele orienta você nas etapas de configuração no Microsoft Dynamics Lifecycle Services (LCS), no Regulatory Configuration Services (RCS) e no Dynamics 365 Finance e Dynamics 365 Supply Chain Management. Depois, ele analisa o processo comum para usar recursos de Cálculo de Imposto em transações do Finance e do Supply Chain Management.

A configuração consiste em quatro etapas principais:

1. No LCS, instale o Cálculo de Imposto.
2. No RCS, configure o recurso de Cálculo de Imposto. Essa configuração não é específica de uma entidade legal. Ela pode ser configurada entre entidades legais no Finance e no Supply Chain Management.
3. No Finance e no Supply Chain Management, configure os parâmetros de Cálculo de Imposto por entidade legal.
4. No Finance e no Supply Chain Management, crie transações, como ordens de venda, e use o Cálculo de Imposto para determinar e calcular impostos.

## <a name="prerequisites"></a>Pré-requisitos

Antes de poder concluir os procedimentos neste tópico, é preciso ter os seguintes pré-requisitos em vigor:

- Você tem acesso à conta do LCS e já implementou um projeto do LCS com um ambiente de Camada 2 (ou superior) que executa o Dynamics 365 versão 10.0.18 com [KB4616360](https://fix.lcs.dynamics.com/Issue/Details?kb=4616360&bugId=568738&dbType=3&qc=1f1c04ff39adad74ef871f539e8d73e14c1893ef7cc4b6e3f7d5c5864ec2781a) ou superior.
- Você tem acesso à sua conta RCS.
- Você entrou em contato com a Microsoft para habilitar a liberação de versões de pré-lançamento no ambiente do Finance ou Supply Chain Management implantado.

## <a name="set-up-tax-calculation-in-lcs"></a>Configure o Cálculo de Imposto em LCS

1. Entre no [LCS](https://lcs.dynamics.com)
2. Calcule a configuração da integração do Microsoft Power Platform. Para obter mais informações, consulte a [Visão geral dos suplementos](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).
3. Selecione um dos ambientes de não produção implantados e depois selecione **Instalar um novo suplemento**.
4. Selecione **Cálculo de Imposto (versão preliminar)**.
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
8. Selecione a versão mais recente e, depois, selecione **Importar**.
9. Retorne ao espaço de trabalho **Recursos de globalização (Versão preliminar)**, selecione **Recursos**, selecione o bloco **Cálculo do Imposto** e **Adicionar**.
10. Selecione um dos seguintes tipos de recurso:

    - **Novo recurso** – crie uma configuração de recurso com conteúdo em branco.
    - **Com base no recurso existente** – crie um recurso usando um recurso existente e copie o conteúdo da configuração de recurso existente.

11. Insira um nome e uma descrição para o recurso e selecione **Criar recurso**.

    Depois de criar o recurso, será criada uma versão de rascunho dele automaticamente.

12. Selecione a versão de rascunho do recurso e, em seguida, selecione **Editar**. A página **Configuração de Cálculo do Imposto** é preenchida.
13. Selecione **Versão da configuração**. Consulte a versão da configuração importada na etapa 8.

    A Microsoft fornece uma configuração de imposto padrão para o suplemento de cálculo do imposto. Essa configuração abrange a maioria dos requisitos de comportamentos de cálculo do imposto. Ela será atualizada com base nos feedbacks de mercado. Caso precise estender a configuração para atender a requisitos específicos, consulte [Como criar extensão no serviço de imposto](./tax-service-add-data-fields-tax-integration-by-extension.md) para obter informações sobre como gerar e selecionar sua própria configuração de imposto.

    Depois de selecionar a **Versão da configuração**, várias guias são exibidas:

    - **Códigos de imposto** – esta guia é obrigatória. É usada para manter os dados mestres de códigos de imposto. Todos os códigos de imposto criados nessa guia são automaticamente sincronizados ao Finance ao habilitar a versão atual da configuração do recurso de imposto na entidade legal.
    - **Aplicabilidade de códigos de imposto** – esta guia é obrigatória. Ele é usado para definir uma matriz que determina o código do imposto, grupo de impostos e o grupo de impostos sobre o item. O código do imposto determinado é usado para calcular o valor do imposto. Os valores dos campos **Código do imposto**, **Grupo de impostos** e **Grupo de impostos sobre o item** são retornados ao Finance.
    - **Aplicabilidade do número de registro de imposto do cliente** – esta guia é opcional. Se você tiver vários números de registro de imposto para um cliente, o Cálculo de Imposto poderá automaticamente determinar o número de registro de imposto correto. Na matriz nessa guia, você define as regras que o suplemento usa para fazer a determinação. Caso contrário, o Finance e o Supply Chain Management continuarão usando o número de registro de imposto padrão em documentos tributáveis de transações de vendas.
    - **Aplicabilidade do número de registro de imposto do fornecedor** – esta guia é opcional. Se você tiver vários números de registro de imposto para um fornecedor, o Cálculo de Imposto poderá automaticamente determinar o número de registro de imposto correto. Na matriz nessa guia, você define as regras que o suplemento usa para fazer a determinação. Caso contrário, o Finance e o Supply Chain Management continuarão usando o número de registro de imposto padrão em documentos tributáveis de transações de compras.
    - **Aplicabilidade de código de lista** – esta guia é opcional. Ela pode ajudar a determinar automaticamente o valor do campo **Código de lista** por meio de regras mais flexíveis e configuráveis. Na matriz nessa guia, você pode definir as regras que o suplemento usa para fazer a determinação. Caso contrário, o Finance e o Supply Chain Management continuarão usando o código padrão em documentos tributáveis.

14. Na guia **Códigos de imposto**, selecione **Adicionar** e insira o código de imposto e uma descrição.
15. Selecione **Componente de imposto**. O componente de imposto é um grupo de métodos que foram definidos na versão anterior da configuração de imposto selecionada. Os seguintes componentes de imposto estão disponíveis:

    - Por valor líquido
    - Por valor bruto
    - Por quantidade
    - Por margem
    - Imposto sobre imposto

16. Selecione **Salvar**. Mais campos serão disponibilizados, com base no componente de imposto selecionado.
17. Use as seguintes opções para identificar a natureza do código de imposto:

    - É Isento
    - É Imposto sobre o uso
    - É Encargo Revertido
    - Excluir do Cálculo de Valor Base

    Para um cenário de imposto sobre o uso, configure um único código de imposto com taxa de imposto positiva e marque como **É Imposto sobre o uso**.

    Para um cenário de encargo revertido, configure até dois códigos de imposto, sendo que um tem uma taxa de imposto positiva e o outro tem uma taxa de imposto negativa, mas o mesmo valor de taxa. Marque o código de imposto negativo como **É encargo revertido**. Para obter mais informações sobre a solução de encargo revertido no Finance, consulte [Mecanismo de encargo revertido do esquema de IVA/GST](emea-reverse-charge.md).
    
    Para alguns tipos de impostos, que devem ser excluídos no cálculo de valor base do imposto para transações com preço incluído, como taxas alfandegárias em alguns países, marque a caixa de seleção **Excluir do Cálculo de Valor Base**.

    Mantenha as taxas de impostos e os limites de valor do imposto para este código de imposto.

18. Repita as etapas 14 a 17 para adicionar outros códigos de imposto necessários.
19. Na guia **Aplicabilidade de códigos de imposto**, selecione as colunas necessárias para determinar o código de imposto correto e selecione **Adicionar**.
20. Insira ou selecione os valores de cada coluna. Os campos **Código do imposto**, **Grupo de impostos** e **Grupo de impostos sobre o item** serão a saída dessa matriz.
21. Repita as etapas 19 a 20 para configurar a aplicabilidade dos números de registro de imposto do cliente, números de registro de imposto do fornecedor e códigos de lista.
22. Selecione **Salvar** e feche a página.
23. Selecione **Alterar status** \> **Concluir**. Depois que o status for alterado para **Concluído**, a versão não poderá mais ser editada.
24. Selecione **Alterar status** \> **Publicar**. Esta versão da configuração do recurso de imposto será enviado para o repositório global e ficará visível para cada entidade legal no Finance.

## <a name="dynamics-365-setup"></a>Configuração do Dynamics 365

Depois de concluir a configuração no RCS, conforme descrito na seção anterior, você terá uma versão publicada do recurso de imposto. Siga estas etapas para configurar o Cálculo de Imposto no Finance.

A configuração nesta seção é realizada pela entidade legal. É necessário configurá-la para cada entidade legal em que deseja habilitar o Cálculo de Imposto do Finance.

1. No Finance, acesse **Imposto** \> **Configuração** \> **Configuração de imposto** \> **Configuração de cálculo de imposto (Versão preliminar)**.
2. Na guia **Geral**, defina os seguintes campos:

    - **Habilitar Cálculo de Imposto** – marque esta caixa de seleção para habilitar o suplemento de Cálculo de Imposto da entidade legal. Se ele não estiver habilitado para a entidade legal atual, a entidade legal continuará usando o mecanismo de imposto existente para determinar e calcular o imposto.
    - **Configuração do recurso** – selecione uma configuração e versão de recurso de imposto publicado da entidade legal. Para obter mais informações sobre como configurar e concluir um recurso de imposto publicado, consulte a versão anterior deste tópico.
    - **Processo Comercial** – Selecione os processos comerciais a serem habilitados.
    - **Habilitar ajuste de código de imposto** – defina esta opção como **Sim** para habilitar os ajustes de código de imposto na página de imposto sobre venda.

3. Na guia **Cálculo**, defina a regra de arredondamento esperada para a entidade legal.
4. Na guia **Tratamento de erros**, defina o método de tratamento de erros esperado para a entidade legal. Três opções estão disponíveis para cada código de resultado:

    - Não
    - Aviso
    - Erro

5. Salve a configuração.
6. Repita as etapas 1 a 5 para cada entidade legal adicional.

## <a name="transaction-processing"></a>Processamento de transações

Depois de concluir todos os procedimentos de configuração, é possível usar o Cálculo de Imposto para determinar e calcular impostos no Finance. As etapas para processar transações continuam as mesmas. As seguintes transações são compatíveis com o Finance versão 10.0.18:

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
