---
title: Otimizar o fechamento do exercício
description: Este artigo descreve o suplemento de serviço Otimizar o fechamento do exercício que está disponível para o processo de fechamento anual da contabilidade.
author: moaamer
ms.date: 11/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerClosingSheet
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2022-11-28
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: 41d0c2975341cf3d612cc36be348326e24e94f1b
ms.sourcegitcommit: 707957bb7bcd98faf2600eff1c98067901a0fb73
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2022
ms.locfileid: "9750002"
---
# <a name="optimize-year-end-close"></a>Otimizar o fechamento do exercício

O suplemento de serviço Otimizar o fechamento do exercício para o Microsoft Dynamics 365 Finance permite que o processamento de fechamento anual seja executado fora da instância do AOS (Servidor de Objetos de Aplicativo) para recursos do Dynamics 365 Finance. Ele utiliza tecnologia de microsserviços. Os benefícios associados à funcionalidade Otimizar o fechamento do exercício incluem desempenho aprimorado e impacto minimizado no banco de dados SQL durante o processamento de fechamento anual.

Para usar a funcionalidade Otimizar o fechamento do exercício, você deve concluir as seguintes tarefas:

1. Instale o suplemento de serviço Otimizar o fechamento do exercício do seu projeto no Microsoft Dynamics Lifecycle Service.
2. Habilite o recurso **Otimizar o fechamento do exercício** no gerenciamento de recursos.

> [!NOTE]
> Você ainda pode usar a funcionalidade de fechamento do exercício atual para recursos financeiros desativando o recurso **Otimizar o fechamento do exercício** no gerenciamento de recursos.

## <a name="improved-performance"></a>Desempenho aprimorado

O recurso **Otimizar o fechamento do exercício** foi desenvolvido para acelerar o processamento de fechamento anual, especialmente para clientes que têm grandes volumes de dados. Quando o fechamento do exercício é executado em um serviço, o processamento pesado é descarregado dos recursos do Finance para ajudar a reduzir o tempo de processamento e liberar os recursos que podem afetar as operações diárias de outros usuários.

O recurso **Otimizar o fechamento do exercício** pode ajudar você a atingir as seguintes metas:

- Melhore o desempenho do fechamento do exercício reduzindo o tempo de execução.
- Reduzir o impacto em outros processos durante a execução do fechamento do exercício.
- Melhore a criação de relatórios e ajustes para os resultados de final de exercício, pois a execução de fechamento do exercício leva menos tempo.

## <a name="new-options-and-visibility"></a>Novas opções e visibilidade

Quando o recurso **Otimizar o fechamento do exercício** está ativado, duas novas colunas, **Resultados** e **Status**, são adicionadas nos seguintes locais:

- Na página **Fechamento do exercício**
- Na caixa de diálogo **Resultados do fechamento do exercício**
- Nas opções **Transferência de dimensão financeira do balanço** na página **Modelo de fechamento do exercício**

A ilustração a seguir mostra um exemplo das colunas **Resultados** e **Status** na página **Fechamento do exercício**. Você pode selecionar o link **Exibir resultados** na coluna **Resultados** para abrir os resultados do fechamento do exercício. A coluna **Status** mostra o estado atual do processo de fechamento do exercício. Portanto, as novas colunas fornecem visibilidade sobre o andamento do processo de fechamento do exercício.

[![Colunas de resultados e status na página de fechamento do exercício.](./media/Yearendclose.jpg)](./media/Yearendclose.jpg)

Além disso, quando o recurso **Otimizar o fechamento do exercício** está ativado, uma FastTab **Dimensões financeiras do balanço** fica disponível na página **Modelo de fechamento do exercício**. Você pode usar esta FastTab para especificar as dimensões financeiras do balanço em detalhes ao fechar um ano. Esse recurso é paralelo ao recurso que já está disponível para contas de lucros e perdas.

## <a name="architecture-and-data-flow"></a>Arquitetura e fluxo de dados

Para usar o recurso **Otimizar o fechamento do exercício** e executar o fechamento do exercício em um microsserviço, você deve instalar o suplemento de serviço Otimizar o fechamento do exercício dos Lifecycle Services e habilitar o recurso **Otimizar o fechamento do exercício** no gerenciamento de recursos.

Como mostra a ilustração a seguir, o processamento de fechamento do exercício verifica se o suplemento está instalado e se o recurso está ativado. Se ambos os pré-requisitos forem atendidos, o fechamento do exercício será executado no microsserviço.

[![Diagrama de fluxo de dados.](./media/Lifecycle-services.jpg)](./media/Lifecycle-services.jpg)

## <a name="high-level-flow-for-year-end-close-processing"></a>Fluxo de alto nível para processamento de fechamento do exercício

1. O processo de fechamento do exercício começa no Finance, em **Contabilidade \> Fechamento de período \> Fechamento do exercício**. O processo cria trabalhos e tarefas em lote de fechamento para as entidades legais que estão sendo fechadas.
2. O fechamento do exercício determina se o fechamento de fim de ano deve ser executado no microsserviço ou na lógica de fechamento atual.

    - Se o suplemento de serviço Otimizar o fechamento do exercício estiver instalado no Lifecycle Services e o recurso **Otimizar o fechamento do exercício** estiver ativado no gerenciamento de recursos, o fechamento anual será executado no microsserviço.

        1. A funcionalidade Otimizar o fechamento do exercício cria um trabalho de serviço de fechamento anual para cada entidade legal que está sendo fechada e, depois, executa a lógica de fechamento anual. O microsserviço realiza o fechamento do exercício.
        2. O Finance analisa o fechamento do ano no microsserviço para determinar quando o microsserviço foi concluído. Os resultados de fechamento do exercício são atualizados na página **Fechamento do exercício** no Finance.

    - Caso contrário, o fechamento do exercício será executado na lógica de fechamento atual.
