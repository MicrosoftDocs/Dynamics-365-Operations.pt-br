---
title: Cobrança por manutenção sobre ativos de propriedade do cliente
description: Este artigo explica como criar, processar e cobrar o trabalho de manutenção que é feito em ativos que seus clientes possuem.
author: johanhoffmann
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjProjectContractsListPage, ProjInvoiceTable, ProjProjectsListPage, ProjTable, EntAssetWorkOrderType, EntAssetWorkOrderProjectSetup, EntAssetObjectTable, EntAssetWorkOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: c0d067ec4f2110b1c146ef0229b90e309578eaa7
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335065"
---
# <a name="bill-for-maintenance-on-customer-owned-assets"></a>Cobrança por manutenção sobre ativos de propriedade do cliente

[!include [banner](../../includes/banner.md)]

O recurso *Cobrança de ordem de serviço* permite criar, processar e cobrar o trabalho de manutenção realizado em ativos que seus clientes possuem. Este recurso permite executar as seguintes tarefas:

- Conectar os clientes aos ativos que eles possuem.
- Selecionar um cliente e exiba os ativos que o cliente possui ao criar uma ordem de serviço.
- Configurar um projeto pai para cada cliente.
- Registrar horas, itens, despesas e taxas em relação à ordem de serviço e criar uma proposta de fatura para o cliente posteriormente.

Além disso, o recurso fornece as seguintes funcionalidades:

- O contrato de projeto do projeto pai de um cliente é copiado automaticamente para o projeto de ordem de serviço relevante.
- O gerenciamento de ativos agora pode usar o tipo de transação de projeto *taxa* em previsões de ordem de serviço e diários de ordem de serviço.

## <a name="turn-on-the-customer-billing-feature"></a>Ativar o recurso de cobrança de cliente

Para poder usar esse recurso, você deve habilitá-lo para o seu sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *gerenciamento e contabilidade do projeto*
- **Nome do recurso:** *cobrança da ordem de serviço*

## <a name="example-scenario"></a>Cenário de exemplo

Para saber como esse recurso funciona, veja o cenário de exemplo a seguir.

Para trabalhar nesse cenário usando os registros e valores de exemplo especificados aqui, você deve usar um sistema em que os [dados de demonstração](../../../fin-ops-core/fin-ops/get-started/demo-data.md) padrão estejam instalados. Você deve selecionar a entidade legal **USMF** antes de começar.

Você também pode usar este cenário como orientação para usar o recurso ao trabalhar em um sistema de produção. No entanto, nesse caso, você deve substituir seus próprios valores e talvez não tenha alguns tipos de registros necessários fornecidos pelos dados de demonstração padrão.

### <a name="step-1-create-a-new-project-contract-for-the-customer"></a>Etapa 1: criar um novo contrato de projeto para o cliente

1. Acesse **Gerenciamento e contabilidade de projeto \> Projetos \> Contratos do projeto**.
1. No Painel de Ações, selecione **Novo**.
1. Na caixa de diálogo **Novo contrato de projeto**, defina os seguintes valores:

    - **Nome:** *atacados Pelican*
    - **Tipo de financiamento:** *cliente*
    - **Fonte de financiamento:** *EUA-013* (*Atacados Pelican*)

1. Selecione **OK**.

### <a name="step-2-create-a-new-parent-project-for-the-customer"></a>Etapa 2: criar um novo projeto pai para o cliente

O projeto pai que você criar aqui será usado quando as ordens de serviços do cliente forem criadas.

1. Acesse **Gerenciamento e contabilidade de projeto \> Projetos \> Todos os projetos**.
1. No Painel de Ações, selecione **Novo**.
1. Na caixa de diálogo **Novo projeto**, defina os seguintes valores:

    - **Tipo de projeto:** *Tempo e material*
    - **Nome do projeto:** *ordens de serviço da Atacados Pelican*
    - **Grupo de projeto:** *TM*
    - **ID do contrato de projeto:** *Atacados Pelican* (o contrato criado anteriormente)
    - **Data de início**: selecione a data de hoje.

1. Selecione **Criar projeto**.
1. O novo projeto é aberto. Anote o valor de **ID do projeto**. Você terá que digitá-lo posteriormente.

### <a name="step-3-create-a-new-work-order-type-in-asset-management"></a>Etapa 3: criar um novo tipo de ordem de serviço no Gerenciamento de ativos

1. Acesse **Gerenciamento de Ativos \> Configuração \> Ordens de serviço \> Tipos de ordem de serviço**.
1. No Painel de Ações, selecione **Novo**.
1. Um novo registro é adicionada à lista. Defina os seguintes valores para ele:

    - **Tipo de ordem de serviço:** *Serviço*
    - **Nome:** *ordens de serviço de serviço*
    - **Estado do ciclo de vida da ordem de serviço:** *Padrão*

### <a name="step-4-link-the-customer-account-to-the-parent-project"></a>Etapa 4: vincular a conta de cliente ao projeto pai

Agora, você deve vincular a conta de cliente ao projeto pai na configuração do projeto no Gerenciamento de ativos.

1. Acesse **Gerenciamento de ativos \> Configuração \> Ordens de serviço \> Configuração de projeto**.
1. Na guia **Projeto pai**, selecione **Adicionar** para adicionar uma linha.
1. Na nova linha, defina os valores a seguir:

    - **Conta de cliente:** *US-013* (*Atacados Pelican*)
    - **ID do projeto:** insira o ID de projeto que você anotou anteriormente.

### <a name="step-5-link-the-project-group-and-type-to-the-work-order-project"></a>Etapa 5: vincular o grupo e o tipo de projeto ao projeto da ordem de serviço

Você ainda deve estar na página **Configuração do projeto** (**Gerenciamento de ativos \> Configuração \> Ordens de serviço \> Configuração do projeto**).

1. Na guia **Grupo de projeto**, selecione **Adicionar** para adicionar uma linha.
1. Na nova linha, defina os valores a seguir:

    - **Tipo de ordem de serviço:** *Serviço* (o tipo de ordem de serviço criado anteriormente)
    - **Grupo de projeto:** *TM*

> [!NOTE]
> O contrato de projeto no projeto da ordem de serviço sempre é herdado do projeto pai.

### <a name="step-6-link-an-asset-to-the-customer-id"></a>Etapa 6: vincular um ativo ao ID do cliente

1. Acesse **Gerenciamento de ativos \> Ativos \> Ativos ativos**.
1. No campo **Filtro**, digite *VE-102* e selecione para filtrar por **Ativo**.
1. Selecione o ativo para abrir suas configurações.
1. Na guia rápida **Cliente**, defina o campo **Conta do cliente** como *US-013* (*Atacados Pelican*).

    O campo **Nome** é atualizado automaticamente para *Atacados Pelican*.

### <a name="step-7-create-a-new-work-order-on-the-asset"></a>Etapa 7: criar uma nova ordem de serviço no ativo

1. Acesse **Gerenciamento de Ativos \> Ordens de serviço \> Ordens de serviço ativas**.
1. No Painel de Ações, selecione **Novo**.
1. Na caixa de diálogo **Criar ordem de serviço**, defina os seguintes valores:

    - **Tipo de ordem de serviço:** *Serviço*
    - **Descrição:** *reparar caminhão*
    - **Conta de cliente:** *US-013* (*Atacados Pelican*)
    - **Ativo:** *VE-102*

        > [!NOTE]
        > A pesquisa mostra somente os ativos vinculados à conta de cliente selecionada.

    - **Tipo de trabalho de manutenção:** *Reparo*
    - **Comércio:** *Mecânico*
    - **Nível de serviço:** *4*

1. Selecione **OK**.

### <a name="step-8-review-the-work-order-and-start-to-work-on-it"></a>Etapa 8: revisar a ordem de serviço e comece a trabalhar nela

Nesta seção, você trabalhará na ordem de serviço criada na seção anterior.

1. Siga estas etapas para verificar se o projeto pai é o projeto *Ordem de serviço a Atacados Pelican*:

    1. Na seção **Trabalhos de manutenção da ordem de serviço**, selecione uma linha.
    1. Na guia rápida **Detalhes da linha**, inspecione o valor **ID do projeto**. Ele deve ser um número de hifenização no formulário *\<Parent-Project-ID\>-\<Project-ID\>*. Esse valor é um link.
    1. Selecione o link do ID do projeto para abrir uma página na qual é possível exibir os nomes do projeto e do projeto pai.

1. No Painel de Ação, na guia **Ordem de serviço**, no grupo **Estado de ciclo de vida**, selecione **Atualizar estado da ordem de serviço**.
1. Na caixa de diálogo **Atualizar estado da ordem de serviço**, na coluna **Selecionar**, marque a caixa de seleção da linha na qual o campo **Estado de ciclo de vida** está definido como *Em andamento*.
1. Selecione **OK**.
1. Na caixa de diálogo **Estado do ciclo de vida: Em andamento**, selecione **OK**.

### <a name="step-9-post-the-hours-that-were-spent-on-the-work-order-and-create-a-new-invoice-proposal"></a>Etapa 9: lançar as horas gastas na ordem de serviço e criar uma nova proposta de fatura

Nesta seção, você continuará trabalhando na ordem de serviço em que você trabalhou na seção anterior.

1. No Painel de Ação, na guia **Ordem de serviço**, no grupo **Projeto**, selecione **Diários**.

    A página **Diários de ordem de serviço** será exibida. Aqui, você pode registrar o tempo gasto na ordem de serviço.

1. Na guia rápida **Horas**, selecione **Adicionar linha**.
1. Na linha nova, defina o campo **Horas** como *4*.
1. No Painel de Ação, selecione **Lançar diários**.
1. Feche a página **Diários de ordem de serviço** para retornar à ordem de serviço.
1. No Painel de ações, na guia **Faturamento**, selecione **Nova proposta de fatura**.
1. Na caixa de diálogo **Criar proposta de fatura**, na seção **Transações do projeto**, marque a caixa de seleção **Selecionar** para cada linha que você deseja faturar.
1. Selecione **OK** para fechar a caixa de diálogo e exibir a nova proposta de fatura.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]