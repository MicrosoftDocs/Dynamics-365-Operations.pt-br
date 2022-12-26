---
title: Otimizar o fechamento do exercício
description: Este artigo descreve o suplemento de serviço Otimizar o fechamento do exercício que está disponível para o processo de fechamento anual da contabilidade.
author: moaamer
ms.date: 12/02/2022
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
ms.openlocfilehash: bc6ab7e36f37707442f8d5d5b6e0d5f5d42e2171
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831520"
---
# <a name="optimize-year-end-close"></a>Otimizar o fechamento do exercício 

O suplemento de serviço Otimizar o fechamento do exercício para o Microsoft Dynamics 365 Finance permite que o processamento de fechamento anual seja executado fora da instância do AOS (Servidor de Objetos de Aplicativo) para recursos do Dynamics 365 Finance. Ele utiliza tecnologia de microsserviços. Os benefícios associados à funcionalidade Otimizar o fechamento do exercício incluem desempenho aprimorado e impacto minimizado no banco de dados SQL durante o processamento de fechamento anual.

>[!NOTE]
> O recurso Otimizar o fechamento do exercício está disponível no Microsoft Dynamics 365 Finance versão 10.0.31. Esse recurso foi devolvido para o Dynamics Finance versões 10.0.30 e 10.0.29 e você precisará usar a atualização de qualidade mais recente.   

Para usar a funcionalidade Otimizar o fechamento do exercício, você deve concluir as seguintes tarefas:

1. Instale o suplemento de serviço Otimizar o fechamento do exercício do seu projeto no Microsoft Dynamics Lifecycle Service.
2. Habilite o recurso **Otimizar o fechamento do exercício** no gerenciamento de recursos.

> [!NOTE]
> Você ainda pode usar a funcionalidade de fechamento do exercício atual para o recurso **Otimizar o fechamento do exercício** no gerenciamento de recursos.

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

[![Colunas de resultados e status na página de fechamento do exercício.](./media/Optimize-year-end-close-Image3.png)](./media/Optimize-year-end-close-Image3.png)

Além disso, quando o recurso **Otimizar o fechamento do exercício** está ativado, uma FastTab **Dimensões financeiras do balanço** fica disponível na página **Modelo de fechamento do exercício**. Você pode usar esta FastTab para especificar as dimensões financeiras do balanço em detalhes ao fechar um ano. Esse recurso é paralelo ao recurso que já está disponível para contas de lucros e perdas.

[![FastTab Dimensões financeiras do balanço](./media/Optimize-year-end-close-Image4.png)](./media/Optimize-year-end-close-Image4.png)

## <a name="architecture-and-data-flow"></a>Arquitetura e fluxo de dados

Para usar o recurso **Otimizar o fechamento do exercício** e executar o fechamento do exercício em um microsserviço, você precisa instalar o **suplemento de serviço Otimizar o fechamento do exercício** do Lifecycle Services e habilitar o recurso **Otimizar o fechamento do exercício** no gerenciamento de recursos.

Como mostra a ilustração a seguir, o processamento de fechamento do exercício verifica se o suplemento está instalado e se o recurso está ativado. Se ambos os pré-requisitos forem atendidos, o fechamento do exercício será executado no microsserviço.

[![Diagrama de fluxo de dados.](./media/Optimize-year-end-close-Image5.png)](./media/Optimize-year-end-close-Image5.png)

## <a name="high-level-flow-for-year-end-close-processing"></a>Fluxo de alto nível para processamento de fechamento do exercício

1. O processo de fechamento do exercício começa no Finance, vá para **Contabilidade \> Fechamento de período \> Fechamento do exercício**. O processo cria trabalhos e tarefas em lote de fechamento para as entidades legais que estão sendo fechadas.
2. O fechamento do exercício determina se o fechamento de fim de ano deve ser executado no microsserviço ou na lógica de fechamento atual.

    - Se o **suplemento de serviço Otimizar o fechamento do exercício** estiver instalado no Lifecycle Services e o recurso **Otimizar o fechamento do exercício** estiver ativado no gerenciamento de recursos, o fechamento anual será executado no microsserviço.

        1. A funcionalidade Otimizar o fechamento do exercício cria um trabalho de serviço de fechamento anual para cada entidade legal que está sendo fechada e, depois, executa a lógica de fechamento anual. O microsserviço realiza o fechamento do exercício.
        2. O Finance analisa o fechamento do ano no microsserviço para determinar quando o microsserviço foi concluído. Os resultados de fechamento do exercício são atualizados na página **Fechamento do exercício** no Finance.

    - Caso contrário, o fechamento do exercício será executado na lógica de fechamento atual.
