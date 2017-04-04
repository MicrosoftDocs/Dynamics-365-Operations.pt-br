---
title: "Visão geral de gerenciamento de transporte"
description: "Este tópico fornece uma visão geral da funcionalidade de gerenciamento de transporte no Microsoft Dynamics 365 for Operations."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 30251
ms.assetid: d4e3550c-bca8-469c-82df-56ac0083e4ac
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 3136fd95c4c56495a391668d6c854a6ae1e36479
ms.lasthandoff: 03/31/2017


---

# <a name="transportation-management-overview"></a>Visão geral de gerenciamento de transporte

Este tópico fornece uma visão geral da funcionalidade de gerenciamento de transporte no Microsoft Dynamics 365 for Operations.

O gerenciamento de transporte permite que você gerencie o transporte de sua empresa e também permite que você identifique soluções de fornecedor e de roteiro para ordens de entrada e de saída. Por exemplo, você pode identificar o roteiro mais rápido ou a taxa menos dispendiosa para uma remessa. A tabela a seguir descreve os principais cenários para o uso do Gerenciamento de transporte no Microsoft Dynamics 365 for Operations.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Cenário</th>
<th>Como o Gerenciamento de transporte pode ajudar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Use fornecedores externos de logística para atividades de transporte.</td>
<td>Use o Gerenciamento de transporte para o transporte de entrada e/ou de saída.</td>
</tr>
<tr class="even">
<td>A frota própria da empresa está disponível para entrega/retirada, e as taxas de entrega são passadas para os clientes.</td>
<td>Para os processos de saída, você pode usar o Gerenciamento de transporte para determinar os encargos de transporte e passá-los para os clientes. No entanto, o processo de reconciliação da fatura da transportadora não é necessário.</td>
</tr>
<tr class="odd">
<td>A frota própria da empresa está disponível entrega/retirada, mas as taxas de entrega não são passadas para os clientes, já que os preços dos produtos incluem o transporte.</td>
<td>Grande parte da funcionalidade do Gerenciamento de transporte não é necessária. No entanto, você pode usar o Gerenciamento de transporte para determinar as taxas de transporte e ajustar o preço de venda adequadamente.</td>
</tr>
<tr class="even">
<td>O serviço de logística é fornecido por outra entidade legal na mesma empresa.</td>
<td><ul>
<li>Você pode usar o Gerenciamento de transporte ai tratar a outra entidade legal como qualquer outra transportadora. Não é possível automatizar as transações econômicas entre as entidades legais. Portanto, você deve lidar com essas transações manualmente (por exemplo, criando uma ordem de compra).</li>
<li>Na entidade legal que fornece os serviços de logística, o Gerenciamento de transporte pode ser usado para determinar as taxas de transporte.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="planning-transportation-in-dynamics-365-for-operations"></a>Planejamento de transporte no Dynamics 365 for Operations
No Gerenciamento de transporte, o planejamento de transporte pode se basear em ordens ou nas remessas criadas com base nessas ordens. As remessas sempre existem em algum momento, mas não são obrigatórias para o planejamento de transporte. As ordens de transferência fazem parte do cenário de saída e podem ser planejadas junto com as ordens de venda. 

![Emissão de carga](./media/Load-drawing1-1024x477.jpg)

## <a name="inbound-transportation"></a>Transporte de entrada
Quando você encomendar itens de um fornecedor, e itens devem ser entregues ao depósito, você pode desejar organizar o transporte de itens você. Você pode usar o dynamics 365 para as operações planejem o transporte e o recebimento da carga de entrada. A ilustração a seguir mostra o fluxo de processos de negócios para planejar o transporte de uma carga de entrada. 

![Fluxo de processo comercial para transporte de carga de entrada](./media/Businessprocessflowforinboundloadtransportation.jpg)

## <a name="outbound-transportation"></a>Transporte de saída
É possível planejar e processar uma carga de saída para enviar itens específicos do depósito de uma empresa para um cliente. Você pode usar o Dynamics 365 for Operations para planejar o transporte e a remessa de uma carga de saída. A ilustração a seguir mostra o fluxo de processos de negócios para planejar e processar cargas de saída para remessa. 

![Cargas de saída de planejamento e de processamento](./media/Planningandprocessingoutboundloads.jpg)

## <a name="load-building"></a>Criação de carga
O Dynamics 365 for Operations fornece uma estratégia de criação de carga chamada Estratégia de criação de carga com base no volume. Essa estratégia permite usar os valores máximos especificados para a altura e o peso do modelo de carga ou substituí-los pelas configurações por meio da inserção de novos valores. Para usar essa estratégia, selecione-a no campo **Estratégia de criação de carga** na Guia Rápida **Configuração** da página **Bancada de criação de carga**. Além disso, você pode adicionar suas próprias estratégias de carga criando uma nova classe na Árvore de Objetos de Aplicativo (AOT).


