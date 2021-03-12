---
title: Workspace de entrada de fatura de fornecedor
description: Este tópico explica como configurar o workspace que está relacionado às faturas de fornecedor e que mostra as informações que estão disponíveis pelo Microsoft Power BI.
author: abruer
manager: AnnBe
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2020-09-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 04aca717c3f255799699d63fb74ee0b543f8c8ba
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993254"
---
# <a name="vendor-invoice-entry-workspace"></a>Workspace de entrada de fatura de fornecedor

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tópico explica como configurar o workspace que está relacionado às faturas de fornecedor e que mostra as informações que estão disponíveis pelo Microsoft Power BI. As informações de fatura de fornecedor neste workspace estão filtradas por usuário e são mostradas em um formato gráfico.

## <a name="overview"></a>Visão Geral

O workspace **Entrada de fatura de fornecedor** mostra informações relacionadas ao processamento da fatura de fornecedor. Ele inclui uma exibição **Meu trabalho** e uma página **Análise - Todas as empresas**. A visualização **Meu trabalho** mostra quadros resumidos, grades de transação de fornecedor, e informações relacionadas do fornecedor. A página **Análise - Todas as empresas** usa recursos do Power BI para mostrar as visualizações relacionadas a faturas de fornecedor.

## <a name="set-up-the-workspace-to-show-power-bi-content"></a>Configurar o workspace para mostrar conteúdo do Power BI

Você deve concluir essa configuração antes que os dados possam ser mostrado em visualizações do Power BI no workspace **Entrada de fatura de fornecedor**.

1. No workspace **Gerenciamento de recursos**, filtre a lista para localizar o recurso **Automação de fatura de fornecedor**.
3. Selecione **Habilitar agora**.
4. Para garantir que as faturas possam ser processadas do início ao fim sem exigir intervenção manual, configure um fluxo de trabalho de fatura de fornecedor. Para configurar um fluxo de trabalho, vá **Contas apagar \> Configurar \> Fluxos de trabalho de contas a pagar**.
5. Acesse **Contas a pagar \> Configurar \> Parâmetros de contas a pagar** e selecione a guia **Automação de fatura de fornecedor**. Para obter mais informações, consulte [Configurar opções para automação de fatura de fornecedor](vnd-invoice-set-up-options.md).
6. Configure a opção **Enviar automaticamente faturas importadas para o sistema de fluxo de trabalho** como **Sim**.
7. Caso seja necessário correlacionar os recebimentos de produtos automaticamente, defina a opção **Coincidir automaticamente os recebimentos de produtos para as linhas da fatura** como **Sim**.
8. Examine as configurações opcionais restantes e configure-as de acordo com as necessidades da sua organização.
9. Acesse **Administração do sistema \> Configurar \> Parâmetros do sistema** e defina os campos **Moeda do sistema** e **Taxa de câmbio do sistema**.
10. Acesse **Contabilidade \> Configurar \> Razão** e defina os campos **Moeda da contabilidade** e **Tipo de taxa de câmbio**.
11. Acesse **Contabilidade \> Moedas \> Taxas de câmbio do sistema** e insira as taxas de câmbio entre a moeda da transação e a moeda da contabilidade e também entre moeda da contabilidade e moeda do sistema.
12. Acesse **Administração do sistema \> Configurar \> Repositório de entidades** e procure **Medida de automação de fatura de fornecedor**. Selecione **Atualizar**.

Para exibir as informações mostradas no workspace, você deve ter a função de segurança Gerente de contas a pagar ou Auxiliar de contas a pagar.

## <a name="my-work-view"></a>Visualização Meu trabalho

### <a name="company-selection"></a>Seleção da empresa

Quando o recurso **Automatizar faturas de fornecedor** é ativado, um campo **Empresa** aparece na parte superior do workspace. A seleção no campo **Empresa** afeta todas as informações exibidas no workspace. Por padrão, o modo de exibição mostra informações da empresa na qual você fez login. Ao selecionar uma empresa diferente no campo **Empresa**, você poderá mostrar informações daquela empresa no workspace. Em seguida, você poderá selecionar um bloco no workspace para ir para a página relacionada na empresa selecionada.

### <a name="summary-tiles"></a>Blocos do resumo

Os blocos na seção **Resumo de faturas pendentes** do modo de exibição **Meu trabalho** fornece uma visão geral do estado das faturas de fornecedor. Você pode ver diários que ainda não foram lançados e faturas em espera. Além disso, há quatro blocos que estão associados ao recurso Automação de fatura de fornecedor:

- Conciliação de recebimento manual necessária
- Falha na validação da conciliação
- Faturas não enviadas para o fluxo de trabalho
- Faturas não importadas

(Esses quatro blocos exigem que o recurso Automação de fatura de fornecedor seja ativado no Gerenciamento de recursos.)

Para usar o bloco **Recuperar faturas de fornecedor**, o recurso deve estar ativado nos Parâmetros de contas a pagar. Acesse **Contas a pagar \> Parâmetros de contas a pagar** e na guia **Fatura**, defina a opção **Permitir recuperação de fatura de fornecedor** como **Sim**.

Quando o recurso estiver ativado, você também terá três blocos agrupados no workspace em uma seção chamada **Diários**. Os blocos são denominados **Diários**, **Diários - Atribuídos a mim** e **Grupo de faturas**. 

As informações na seção **Resumo de faturas pendentes** é para a empresa definida como a empresa padrão à qual você se conecta.

### <a name="creating-new-records"></a>Criação de novos registros

Para criar um novo registro de fatura, selecione **Novo** e, em seguida, selecione um dos seguintes tipos de registro na lista:

- Fatura de fornecedor
- Diário de faturas
- Diário de faturas globais
- Registro de fatura
- Aprovação da fatura

Observe que o registro criado se baseia no filtro da empresa, não na empresa na qual você está conectado. Por exemplo, você está conectado à empresa **UMSF**, mas o filtro da empresa está definido como **GBSI**. Nesse caso, quando você seleciona **Novo** e seleciona um tipo de registro na lista, o registro é criado na empresa GBSI.

### <a name="documents-not-invoiced-grids"></a>Grades de documentos não faturados

A seção **Documentos não faturados** contém grades que mostram os documentos que estão aguardando as faturas de fornecedor.

A grade **Ordens de compra em aberto** mostra todas as ordens de compra que ainda não foram totalmente faturadas. Você pode usar o botão **Faturar agora** para criar uma fatura de fornecedor para uma ordem de compra. Você pode usar o botão **Pagar antecipadamente fatura agora** para criar uma fatura para pagamento antecipado para uma ordem de compra.

A grade **Recebimentos de produto** mostra transações de recebimento de produto que ainda não foram totalmente faturadas. Você pode usar o botão **Faturar agora** para criar uma fatura de fornecedor para uma ordem de compra.

A grade **Faturas de fornecedores pendentes** mostra todas as faturas de fornecedor que não foram enviadas ao sistema de fluxo de trabalho. Você pode usar o campo **Pesquisar** e/ou o filtro da empresa para procurar uma fatura de fornecedor específica. Você pode usar o botão **Editar** para editar uma transação que apareça na grade.

Na grade **Localizar ordem de compra**, você pode usar o campo **Pesquisar** para procurar uma ordem de compra específica.

### <a name="related-information"></a>Informações Relacionadas

Você pode exibir informações sobre faturas lançadas usando os links no lado direito do workspace. Esses links incluem **Faturas de fornecedor em aberto**, **Diário de faturas** e **Detalhes de histórico e conciliação de faturas**. Na seção **Fornecedores**, você pode acessar uma lista filtrada que mostra todos os fornecedores que estão em espera ou pode usar o link **Todos os fornecedores**. Os links **Todas as ordens de compra** e **Pagamentos antecipados em aberto** também estão disponíveis.

### <a name="analytics--all-companies-page"></a>Página Análise – Todas as empresas

Quando a opção **Enviar automaticamente faturas importadas para o fluxo de trabalho** está definida como **Sim** na página **Parâmetros de contas a pagar**, você pode ver as análises de automação. A página **Análise – Todas as empresas** fornece métricas importantes, como faturas de fornecedor que estão sendo aprovadas por aprovador e por empresa. Essa página contém cinco páginas de relatório. Uma página fornece uma visão geral, e as outras páginas fornecem detalhes sobre métricas de Automação de contas a pagar.

A tabela a seguir mostra as visualizações disponíveis em cada página de relatório.

| Página de relatório                    | Visualizações |
|--------------------------------|----------------|
| Visão geral de faturas de fornecedor        | <ul><li>Faturas de fornecedor pendentes em automação na moeda do sistema</li><li>Faturas com falha de importação</li><li>Faturas no fluxo de trabalho</li><li>Faturas não mexidas nos últimos 30 dias</li><li>Total de faturas automatizadas nos últimos 30 dias</li><li>Saldo de faturas em aberto na moeda do sistema</li><li>Motivos para falhas, últimos 30 dias</li><li>Porcentagem de faturas lançadas que foram processadas automaticamente</li><li>Dias para processar uma fatura</ul></li> |
| Status de automação              | <ul><li>Faturas não mexidas nos últimos 30 dias</li><li>Faturas não mexidas nos últimos 30 dias por empresa</li><li>Faturas não mexidas nos últimos 30 dias por grupo de fornecedores</li><li>Porcentagem de faturas lançadas que foram processadas automaticamente</li><li>Dias para processar uma fatura</li></ul> |
| Faturas com falha de importação | <ul><li>Faturas com falha de importação</li><li>Faturas com falha de importação por empresa</li></ul> |
| Motivos da falha de automação | <ul><li>Faturas com falha</li><li>Faturas com falha por empresa</li><li>Faturas com falha por grupo de fornecedores</li></ul> |
| Status do fluxo de trabalho                | <ul><li>Faturas no fluxo de trabalho</li><li>Instâncias de fluxo de trabalho de fatura de fornecedor</li><li>Atribuição por aprovador</li><li>Fluxo de trabalho de fatura de fornecedor por empresa</li><li>Média de dias no fluxo de trabalho por aprovador</li></ul> |
