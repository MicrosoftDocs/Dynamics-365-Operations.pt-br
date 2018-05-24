---
title: "Gerenciamento de serviços"
description: "Use Gerenciamento de serviço para estabelecer contratos de serviço e subscrições de serviço, lidar com ordens de serviço e consultas de cliente e gerenciar e analisar a entrega de serviços a clientes."
author: YuyuScheller
manager: AnnBe
ms.date: 05/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 02cdf4615e2071f2b7de2e86b6f9e6637c6e5d8d
ms.openlocfilehash: 236ab21b2d1c5a4e82270e5381d163e97437cb7f
ms.contentlocale: pt-br
ms.lasthandoff: 05/09/2018

---


# <a name="service-management"></a>Gerenciamento de serviços 

[!include [banner](../includes/banner.md)]


Use **Gerenciamento de serviço** para estabelecer contratos de serviço e subscrições de serviço, lidar com ordens de serviço e consultas de cliente e gerenciar e analisar a entrega de serviços a clientes. É possível usar os contratos de serviço para definir os recursos usados em uma típica visita de serviço. Também é possível usar contratos de serviço para exibir como esses recursos são faturados para o cliente. Um contrato de serviço também pode incluir um contrato de nível de serviço que especifica o tempo de resposta padrão e fornece ferramentas para registrar o tempo real.

Você pode criar ordens de serviço para gerenciar informações sobre visitas programadas e não programadas por um técnico de serviço a um site do cliente. As ordens de serviço incluem informações como:

1.  As horas de trabalho que o técnico de serviço executará

2.  O tipo de serviço ou reparo

3.  O item para reparo, incluindo detalhes sobre os sintomas e o diagnóstico

4.  Algumas despesas e taxas relacionadas ao serviço ou reparo

Os clientes podem enviar solicitações de serviço com a Internet usando Portal Empresarial. É possível receber, processar e para despachar essas solicitações. Depois de criar uma ordem de serviço, você pode usar as fases de serviço para monitorar o andamento e especificar as regras que controlam quais ações estão habilitadas em cada fase. Quando uma ordem de serviço é concluída, você pode se desconectar da ordem para confirmar que está concluída e lançar a ordem para iniciar o processo da fatura.

Use as ferramentas de relatório para monitorar transações de subscrição e margens da ordem de serviço e descrições de trabalho de impressão e recebimentos de trabalho.

## <a name="business-processes"></a>Processos empresariais

O diagrama a seguir ilustra os processos comerciais de alto nível para **Gerenciamento de serviço**, e mostra onde processos de serviço se integram com outros módulos no Microsoft Dynamics 365 for Finance and Operations.

[![Diagrama de processos de negócios do gerenciamento de serviços](./media/sm_home_page.gif)](./media/sm_home_page.gif)

## <a name="service-management-at-a-glance"></a>Visão geral do gerenciamento de serviços

<table>
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Tarefas importantes</p></th>
<th><p>Principais formulários</p></th>
<th><p>Relatórios conhecidos</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Preencher contrato de serviço</a></p></td>
<td><p><a href="https://technet.microsoft.com/en-us/library/aa617823(v=ax.60)">Contratos de serviço (formulário)</a></p></td>
<td><p><strong>Margem de ordem de serviço</strong></p></td>
</tr>
<tr class="even">
<td><p>Tratar consultas de cliente</a></p></td>
<td><p><a href="https://technet.microsoft.com/en-us/library/aa554361(v=ax.60)">Ordens de serviço (formulário)</a></p></td>
<td><p><strong>Descrição do trabalho</strong></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><a href="https://technet.microsoft.com/en-us/library/hh242789(v=ax.60)">Quadro de expedição (formulário)</a></p></td>
<td><p><strong>Transação - Subscrição</strong></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p></p></td>
<td><p><strong>Transações de taxa de subscrição</strong></p></td>
</tr>
</tbody>
</table>


## <a name="integration-of-service-management"></a>Integração do gerenciamento de serviços

O gerenciamento de serviço pode ser integrado aos seguintes módulos no Microsoft Dynamics 365 for Finance and Operations:

  - [Vendas e marketing](../sales-marketing/overview-sales-marketing.md)

  - [Recursos humanos](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/index)

  


