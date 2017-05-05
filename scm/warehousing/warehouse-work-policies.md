---
title: "Políticas de trabalho de depósito"
description: "Uma nova política de trabalho de depósito foi introduzida no Microsoft Dynamics AX 7.0.1 (atualização de maio de 2016). Esta política de trabalho controla se o trabalho de depósito é criado para os processos de depósito na fabricação."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: WHSWorkPolicy
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 196561
ms.assetid: cbf48ec6-1836-48d5-ad66-a9b534af1786
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 5660e5c8e3329564fc4262b5ad4f2547347bbb1a
ms.lasthandoff: 03/31/2017


---

# <a name="warehouse-work-policies"></a>Políticas de trabalho de depósito

[!include[banner](../includes/banner.md)]


Uma nova política de trabalho de depósito foi introduzida no Microsoft Dynamics AX 7.0.1 (atualização de maio de 2016). Esta política de trabalho controla se o trabalho de depósito é criado para os processos de depósito na fabricação.

Esta política de trabalho controla se o trabalho de depósito é criado para os processos de depósito na fabricação. Você pode configurar a política de trabalho usando uma combinação de **tipos de ordem de trabalho**, **localização de estoque** e um **produto**. Por exemplo, o produto L0101 é reportado como terminado para o local de saída 001. O bem acabado é posteriormente consumido noutra ordem de produção no local de saída 001. Nesse caso, você pode configurar uma política de trabalho para impedir que o trabalho para produtos terminados colocados de lado seja criado quando você relata o produto L0101 como concluído para o local de saída 001. A política de trabalho é uma entidade individual que pode ser descrita pelas seguintes informações:

-   **Nome da política de trabalho **(o identificador exclusivo da política de trabalho)
-   **Tipos de ordem de trabalho **e** Método de criação de trabalho**
-   **Localizações de estoque**
-   **Produtos**

## <a name="work-order-types"></a>Tipos de ordem de trabalho
Você pode selecionar os seguintes tipos de ordem de trabalho:

-   Armazenamento de mercadorias acabadas
-   Armazenamento de coproduto e subproduto
-   Separação de matéria-prima

O campo **Método de criação de trabalho** tem o valor **Nunca**. Esse valor indica que a política de trabalho impedirá que o trabalho de depósito seja criado para o tipo de ordem de trabalho selecionado.

## <a name="inventory-locations"></a>Localizações de estoque
Você pode selecionar uma localização à qual a política de trabalho seja aplicável. Se nenhuma localização for associada à política de trabalho, a política de trabalho não será aplicável a nenhum processo. Na página **Localizações**, é possível marcar ou cancelar a seleção da política de trabalho para uma localização específica.

## <a name="products"></a>Produtos
Você pode selecionar um produto ao qual a política de trabalho seja aplicável. Você pode aplicar a política de trabalho a todos os produtos ou a produtos selecionados.

## <a name="example"></a>Exemplo
No exemplo a seguir, há duas ordens de produção, PRD-001 e PRD-00*2*. A ordem de produção PRD-001 tem uma operação que é chamada **Montagem**, em que o produto SC1 está sendo relatado como acabado para a localização O1. A ordem de produção PRD-002 tem uma operação que é chamada **Pintura** e consome o produto SC1 da localização O1. A ordem de produção PRD-002 também consome a matéria-prima RM1 da localização O1. A RM1 é armazenada na localização BULK-001 e será separada para a localização O1 pelo trabalho de depósito para a separação de matéria-prima. O trabalho de separação será gerado quando a produção PRD-002 for liberada. 

[![Políticas de trabalho de depósito](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png) 

Quando você planejar configurar uma política de trabalho de depósito para este cenário, considere as seguintes informações:

-   O trabalho de depósito para o armazenamento de mercadorias acabadas não é necessário quando você relatar o produto SC1 como acabado da ordem de produção PRD-001 para a localização O1. Isso ocorre porque a operação **Pintura** para a ordem de produção PRD-002 consome o produto SC1 na mesma localização.
-   O trabalho de depósito para a separação de matérias-primas é necessário para mover a matéria-prima RM1 da localização de depósito BULK-001 para a localização O1.

Veja um exemplo da política de trabalho que você pode configurar com base nestas considerações.

|                                         |                                                       |
|-----------------------------------------|-------------------------------------------------------|
|**Nome da política de trabalho**<br>                 |**Tipos de ordem de trabalho**<br>                               |
| Nenhum armazenamento de 01                    |- Armazenamento de mercadorias acabadas<br>                           |
|                                         |**Localizações**<br>                                      |
|                                         |- O1   |                                               |
|                                         |**Produtos** <br>                                      |
|                                         |- SC1                                                  |

Os procedimentos a seguir fornecem instruções passo a passo sobre como configurar a política de trabalho de depósito para este cenário. Uma configuração de exemplo mostrando como relatar uma ordem de produção como acabada para uma localização que não seja controlada por placa de licença também é descrita.

## <a name="set-up-a-warehouse-work-policy"></a>Configurar uma política de trabalho de depósito
Os processos de depósito nem sempre incluem o trabalho do depósito. Ao definir uma diretiva de trabalho, você pode impedir a criação de trabalho para a separação de matéria-prima e o separar as mercadorias concluídas para um conjunto de produtos em locais específicos. A empresa de dados de demonstração USMF foi usada para criar este procedimento. 

ETAPAS (21)

|     |                                                                            |
|-----|----------------------------------------------------------------------------|
| 1.  | Vá para Gerenciamento de depósito &gt; Configuração &gt; Trabalho &gt; Políticas de trabalho.        |
| 2.  | Clique em Novo.                                                                 |
| 3.  | No campo Nome de política de trabalho, digite "Sem trabalhos ausentes".                    |
| 4.  | Clique em Salvar.                                                                |
| 5.  | Clique em Adicionar.                                                                 |
| 6.  | Na lista, marque a linha selecionada.                                        |
| 7.  | No campo Tipo de ordem de trabalho, selecione as mercadorias “Concluiu mercadorias dadas”.            |
| 8.  | Clique em Adicionar.                                                                 |
| 9.  | Na lista, marque a linha selecionada.                                        |
| 10. | No campo Tipo de ordem de trabalho, selecione "Coproduto e subproduto cedido". |
| 11. | Expanda a seção Localizações de estoque.                                    |
| 12. | Clique em Adicionar.                                                                 |
| 13. | Na lista, marque a linha selecionada.                                        |
| 14. | Na lista Depósito, insira "51".                                         |
| 15. | No campo Local, insira ou selecione "001".                              |
| 16. | Expanda a seção Produtos.                                               |
| 17. | No campo Seleção do produto, selecione "Selecionado".                         |
| 18. | Clique em Adicionar.                                                                 |
| 19. | Na lista, marque a linha selecionada.                                        |
| 20. | No campo Número do item, insira ou selecione "L0101".                         |
| 21. | Clique em Salvar.                                                                |

## <a name="report-a-production-order-as-finished-to-a-location-that-isnt-license-platecontrolled"></a>Relatar uma ordem de produção como acabada para uma localização que não seja controlada por placa de licença
Este procedimento mostra um exemplo de como relatar uma ordem de produção como acabada para uma localização que não seja controlada por placa de licença. Uma diretiva de trabalho aplicável é o pré-requisito para esta tarefa. O procedimento anterior mostra a configuração da política de trabalho. 

ETAPAS (25)

<table>
<tbody>
<tr>
<td colspan="3"><strong>Subtarefa: Configurar uma localização de saída.</strong></td>
</tr>
<tr>
<td></td>
<td>1.</td>
<td>Vá para Administração da organização &gt; Recursos &gt; Grupos de recursos.</td>
</tr>
<tr>
<td></td>
<td>2.</td>
<td>Na lista, selecione grupo de recurso "5102".</td>
</tr>
<tr>
<td></td>
<td>3.</td>
<td>Clique em Editar.</td>
</tr>
<tr>
<td></td>
<td>4.</td>
<td>No campo Depósito de saída, insira "51".</td>
</tr>
<tr>
<td></td>
<td>5.</td>
<td>No campo Local de saída, insira "001".</td>
</tr>
<tr>
<td></td>
<td>6.</td>
<td>O local 001 não é um local controlado por placa de licença. Você pode configurar um local de saída em branco da licença não aplicável somente se uma diretiva de trabalho existir para o local.</td>
</tr>
<tr>
<td colspan="3"><strong>Subtarefa: Criar uma ordem de produção e relatar como concluída.</strong></td>
</tr>
<tr>
<td></td>
<td>1.</td>
<td>Feche a página.</td>
</tr>
<tr>
<td></td>
<td>2.</td>
<td>Vá para Controle de produção &gt; Ordens de produção &gt; Todas ordens de produção.</td>
</tr>
<tr>
<td></td>
<td>3.</td>
<td>Clique em Nova ordem de produção.</td>
</tr>
<tr>
<td></td>
<td>4.</td>
<td>No campo Número do item, insira "L0101".</td>
</tr>
<tr>
<td></td>
<td>5.</td>
<td>Clique em Criar.</td>
</tr>
<tr>
<td></td>
<td>6.</td>
<td>No Painel de Ação, clique em Ordem de produção.</td>
</tr>
<tr>
<td></td>
<td>7.</td>
<td>Clique em Estimar.</td>
</tr>
<tr>
<td></td>
<td>8.</td>
<td>Clique em OK.</td>
</tr>
<tr>
<td></td>
<td>9.</td>
<td>Clique em Iniciar.</td>
</tr>
<tr>
<td></td>
<td>10.</td>
<td>Clique na guia Geral.</td>
</tr>
<tr>
<td></td>
<td>11.</td>
<td>No campo Consumo automático de BOM, selecione 'Nunca'.</td>
</tr>
<tr>
<td></td>
<td>12.</td>
<td>Clique em OK.</td>
</tr>
<tr>
<td></td>
<td>13.</td>
<td>Clique em Relatório de conclusão.</td>
</tr>
<tr>
<td></td>
<td>14.</td>
<td>Clique na guia Geral.</td>
</tr>
<tr>
<td></td>
<td>15.</td>
<td>Selecione Sim no campo Aceitar erro.</td>
</tr>
<tr>
<td></td>
<td>16.</td>
<td>Clique em OK.</td>
</tr>
<tr>
<td></td>
<td>17.</td>
<td>No Painel de Ação, clique em Depósito.</td>
</tr>
<tr>
<td></td>
<td>18.</td>
<td>Clique em Detalhes do trabalho.</td>
</tr>
<tr>
<td></td>
<td>19.</td>
<td>Quando a ordem de produção foi informada como concluída, nenhum trabalho foi gerado para ser colocado de lado. Isso ocorre porque uma diretiva de trabalho que é definida impede que o trabalho seja gerado quando o produto L0101 é relatado como concluídos no local 001.</td>
</tr>
</tbody>
</table>



