---
title: Gerar documentos fiscais para uma carga
description: "Este tópico explica como gerar gerar documentos fiscais para uma carga do Brasil."
author: ShylaThompson
manager: AnnBe
ms.date: 06/05/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Brazil
ms.author: shylaw
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: 06a66fb4fd0215c4cea63a5e3735f4159ac7fe6c
ms.openlocfilehash: dd7343a08196b45ec0ebb455f779642b7ca26cca
ms.contentlocale: pt-br
ms.lasthandoff: 10/13/2018

---

# <a name="generate-fiscal-documents-for-a-load"></a>Gerar documentos fiscais para uma carga 

[!include [banner](../includes/banner.md)]

Você pode criar uma carga que contém várias linhas de carga. Cada linha de carga é criada para uma quantidade específica de itens de uma linha de ordem de venda. Você pode criar uma ou mais linhas de carga ou cargas para uma ou mais linhas da ordem de venda ou para ordens de venda.

> [!NOTE]
> Este tópico se aplica aos recursos do módulo **Gerenciamento de transporte**. Não se aplica aos recursos do módulo de Gerenciamento de estoque.

Você pode gerar um ou mais documentos fiscais para uma carga, dependendo das ordens de venda na qual a carga foi criada. A quantidade em uma linha de documento fiscal é a quantidade de retirada da linha de carga, não a quantidade da linha de ordem de venda.

O exemplo a seguir mostra como você pode criar linhas de cargas e cargas para linhas da ordem de venda e ordens de venda e como os documentos fiscais são gerados para cada carga.

### <a name="sales-orders-and-sales-order-lines"></a>Ordens de venda e linhas de ordens de venda

1. Ordem de venda 1 para o cliente C1 que contém as seguintes linhas da ordem de venda:

    1. Linha da ordem de venda 1.1 que contém 50 unidades do item. A.
    2. Linha da ordem de venda 1.2 que contém 20 unidades do item B

2. Ordem de venda 2 para o cliente C2 que contém as seguintes linhas da ordem de venda:

    1. Linha da ordem de venda 2.1 que contém 200 unidades do item C
    2. Linha da ordem de venda 2.2 que contém 100 unidades do item D

### <a name="loads-and-load-lines"></a>Cargas e linhas de carga

1. Você cria uma carga 1 que contém as linhas de carga a seguir:

    1. Linha de carga 1.1 para linha de ordem de vendas 1.1. Esta linha de carga tem 30 unidades do item A.
    2. Linha de carga 1.2 para linha de ordem de vendas 1.2. Esta linha de carga tem 10 unidades do item B.
    3. Linha de carga 1.3 para linha de ordem de vendas 2.1. Esta linha de carga tem 100 unidades do item C.

2. Você cria uma carga 2 que contém as linhas de carga a seguir:

    1. Linha de carga 2.1 para linha de ordem de vendas 1.1. Esta linha de carga tem as 20 unidades restantes do item A.
    2. Linha de carga 2.2 para linha de ordem de vendas 2.1. Esta linha de carga tem 50 unidades do item C.

### <a name="fiscal-documents"></a>Notas fiscais

1. Estes documentos fiscais são gerados para a carga 1:

    1. Um documento fiscal é gerado para o cliente C1 que contém uma linha de documento fiscal para 30 unidades do item A e outra para 10 unidades do item B.
    2. Um documento fiscal é gerado para o cliente C2 que contém uma linha de documento fiscal para 100 unidades do item C.

2. Estes documentos fiscais são gerados para a carga 2:

    1. Um documento fiscal é gerado para o cliente C1 que contém uma linha de documento fiscal para 20 unidades do item A.
    2. Um documento fiscal é gerado para o cliente C2 que contém uma linha de documento fiscal para 50 unidades do item C.

Siga as etapas deste tópico para gerar documentos fiscais para uma carga.

## <a name="prerequisites"></a>Pré-requisitos

A tabela a seguir mostra os pré-requisitos que devem estar funcionando antes de começar.

<table>
<thead>
<tr>
<th>Categoria</th>
<th>Pré-requisito</th>
</tr>
</thead>
<tbody>
<tr>
<td>País/região</td>
<td>O público-alvo principal da entidade legal deve estar no Brasil.</td>
</tr>
<tr>
<td>Tarefas de configuração relacionadas</td>
<td>
<ul>
<li>Criar um grupo de estabelecimentos fiscais e um estabelecimento fiscal. </li>
<li>Configurar um tipo de documento fiscal e, em seguida, atribuí-lo a clientes, fornecedores ou itens de estoque.</li>
<li>Configurar uma transportadora de gerenciamento de transporte que contém o mesmo fornecedor que o especificado no campo de <strong>Conta do fornecedor</strong> no formulário de <strong>Transportadora</strong> no módulo <strong>Vendas e marketing</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>Tarefas relacionadas</td>
<td>Criar uma carga de saída para uma remessa.</td>
</tr>
</tbody>
</table>

## <a name="generate-fiscal-documents-for-a-load"></a>Gerar documentos fiscais para uma carga

Use o formulário **Cargas** para exibir as cargas, selecione uma carga com uma remessa confirmada. Em seguida, você pode usar o formulário **Lançando fatura** para lançar ordens de venda e gerar documentos fiscais para uma carga.

Siga essas etapas para concluir essa tarefa.

1. Clique em **Contas a receber** \> **Periódico** \> **Atualização de vendas** \> **Cargas**.
2. No formulário **Cargas**, selecione uma carga que contenha uma remessa confirmada, e verifique o código de identificação, o status, a direção, o local, depósito e a remessa de carga.

    | Campo                                 | descrição |
    |---------------------------------------|-------------|
    | ID da Carga                               | O código de identificação da remessa. |
    | Status da carga                           | O status da carga. O status pode ser **Enviado**. |
    | Direção                             | A direção da carga. A direção pode ser **Saída**. |
    | Site                                  | O local no qual a carga é separada. |
    | Depósito                             | O depósito no qual a carga é separada. |
    | ID da Remessa                           | O código de identificação da remessa da carga. |
    | Data e a hora da remessa de carga agendada | A data e a hora agendadas para remessa de carga. |

3. Clique em **Fatura** para abrir o formulário **Lançamento de fatura**, no qual você pode exibir as linhas da ordem de venda para as quais a carga foi criada. As linhas contêm somente as quantidades de linha da carga.
4. Marque a caixa de seleção **Lançamento** para lançar as ordens de venda para a carga para gerar documentos fiscais.
5. Especifica qualquer linha adicional de detalhes necessária. 
6. Clique em **OK** para lançar ordens de venda para a carga e gerar os documentos fiscais.

## <a name="technical-information-for-system-administrators"></a>Informações técnicas para administradores de sistemas

Se você não tiver acesso às páginas que são usadas para concluir essa tarefa, entre em contato com o administrador do sistema e forneça as informações que são mostradas na tabela a seguir.

| Categoria                      | Pré-requisito |
|-------------------------------|--------------|
| Chaves de configuração            | Clique em **Administração do sistema** &gt; **Configuração** &gt; **Licença** &gt; **Configuração do sistema**. Expanda a chave de licença de **Comércio** e selecione a chave de configuração **gerenciamento de Depósito e Transporte**. |
| Funções de segurança e direitos     | Para executar essa tarefa, você deve ser membro da função de segurança que inclui o direito **Manter transações da fatura de cliente** (CustInvoiceCustomerInvoiceTransMaintain). |
| Funções de segurança e privilégios | Para executar essa tarefa, você deve ser membro de uma função de segurança que inclua o privilégio **Cargas** (WHSLoadTableInvoicePost\_BR). |

