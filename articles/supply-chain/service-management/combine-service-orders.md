---
title: Combinar ordens de serviço
description: Você pode combinar ordens de serviço.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f89c60561746ac9f1c2e9d611089bfac69089081
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8676765"
---
# <a name="combine-service-orders"></a>Combinar ordens de serviço   

[!include [banner](../includes/banner.md)]


Quando você cria linhas de ordem de serviço automaticamente no formulário de **Contratos de serviço**, é possível escolher uma das seguintes opções para especificar como deseja agrupá-las:

  - **Por contrato de serviço**

  - **Por tarefa de serviço**

  - **Por funcionário**

  - **Por objeto de serviço**

## <a name="example"></a>Exemplo

Você cria um contrato de serviço com uma data inicial em 31-03-2007. No campo **Combinar ordens de serviço**, você especifica **Por objeto de serviço**. Em seguida, será possível criar estas linhas de contrato de serviço:

<table>
<colgroup>
<col />
<col />
<col />
<col />
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>Número da linha do contrato</p></th>
<th><p>Tipo de transação</p></th>
<th><p>descrição</p></th>
<th><p>Intervalo</p></th>
<th><p>Objeto de serviço</p></th>
<th><p>Data de início</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p><strong>Hora</strong></p></td>
<td><p>SAL1</p></td>
<td><p>Semanalmente</p></td>
<td><p>X-1</p></td>
<td><p>04-01-2007</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p><strong>Hora</strong></p></td>
<td><p>SAL2</p></td>
<td><p>Quinzenal</p></td>
<td><p>X-2</p></td>
<td><p>04-01-2007</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p><strong>Hora</strong></p></td>
<td><p>SAL3</p></td>
<td><p>Semanalmente</p></td>
<td><p>X-2</p></td>
<td><p>04-01-2007</p></td>
</tr>
</tbody>
</table>


Você não especifica janelas de tempo para nenhuma das linhas de contrato de serviço. Portanto, as linhas da ordem de serviço não serão movidas a partir do dia calculado em que caem.

Em seguida, gere as linhas de ordem de serviço no formulário **Criar ordens de serviço** de 01-04-2007 até 30-04-2007.

No total, serão criadas 10 ordens de serviço. Como a configuração combinada selecionada era **Por objeto de serviço**, todas as ordens de serviço que forem criadas terão somente linhas de ordem de serviço com um objeto de serviço específico. As linhas de ordem de serviço são geradas a partir do contrato de serviço e que têm a mesma data de serviço e objeto que serão combinados na mesma ordem de serviço.


> [!NOTE]
> <P>Neste exemplo, o calendário especificado no formulário de <STRONG>Parâmetros de gerenciamento de serviços</STRONG> não tem dias fechados.</P>



O agrupamento adicional de linhas de ordem de serviço em ordens de serviço ocorre de acordo com a janela de tempo especificada nas linhas de contrato de serviço.

## <a name="see-also"></a>Consulte também

[Criar ordens de serviço automaticamente](create-service-orders-automatically.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]