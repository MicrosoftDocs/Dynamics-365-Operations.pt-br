---
title: Importar notas fiscais do Brasil
description: Este tópico descreve a funcionalidade para notas fiscais de importação direta disponível da localização brasileira.
author: sndray
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BrazilParameters, FiscalDocument_BR, PurchImportDeclaration_BR, PurchImportDeclarationList_BR, VendEditInvoice
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 270204
ms.assetid: b2389297-1359-498f-b755-c20574248ae1
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d9737430f23f653663e33d638071092d83e579bc
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408447"
---
# <a name="import-fiscal-documents-for-brazil"></a>Importar notas fiscais do Brasil

[!include [banner](../includes/banner.md)]

Este tópico descreve a funcionalidade para notas fiscais de importação direta disponível da localização brasileira.

Você pode emitir uma nota fiscal de importação direta quando cria uma ordem de compra para importar itens de um fornecedor estrangeiro. Uma nota fiscal de importação registra informações de trânsito sobre os itens que você importa. A nota fiscal de importação é usada para liberar os itens das tarifas alfandegárias e validar a entrada dos itens no depósito da entidade legal. É necessário especificar as informações da declaração de importação (o número de adição e o número da declaração de importação) para uma ordem de compra que é emitida para importar itens de um fornecedor estrangeiro antes de lançar a ordem de compra. Um documento fiscal de importação direta inclui as seguintes informações:

-   Cálculo de impostos brasileiros para a nota fiscal de importação direta
-   Informações introdutórias sobre a declaração de importação
-   Geração de NF-e (modelo 55 de documento fiscal eletrônico brasileiro)
-   Um documento DANFE impresso
-   Integração com o módulo **Livros fiscais**

**Observação:** Você também pode emitir uma nota fiscal de importação ao criar uma ordem de compra para importar serviços de um fornecedor estrangeiro. Ao importar um serviço, não é obrigatório especificar o número da declaração de importação e o número de adição da nota fiscal do fornecedor. Antes de gerar uma nota fiscal de importação, selecione a opção **Gerar nota fiscal recebida** para o fornecedor estrangeiro na página **Fornecedores**. Você pode usar a opção **Cancelar** para cancelar uma nota fiscal de importação. É possível usar **Consultar** para carregar todas as notas fiscais, junto com as informações relacionadas para a página **Visualizador de nota fiscal**.

## <a name="prerequisites"></a>Pré-requisitos
Antes de criar e lançar uma nota fiscal de importação direta, você deve definir os seguintes parâmetros no grupo de campos **Declaração de importação** na guia **Nota fiscal** da página **Parâmetros brasileiros**:

-   **O valor da linha baseia-se em** – Selecione um dos seguintes valores:
    -   **FOB** – O valor de linha na nota fiscal é igual ao valor de linha bruta.
    -   **CIF + II** – O **Valor de linha** na nota fiscal é igual ao valor bruto de linha além dos encargos diversos (exceto encargos diversos do SISCOMEX ou cliente) relacionados à instalação do processo de importação para a linha da fatura do fornecedor.
-   **ID do Texto** – selecione o texto usado para imprimir informações de declaração de importação como informações adicionais na nota fiscal impresso ou no DANFE.

## <a name="import-declaration"></a>Declaração da importação
Após criar e confirmar a ordem de compra de um fornecedor estrangeiro e antes da fatura do fornecedor ser lançada, é possível inserir as informações sobre a declaração de importação. Na página **Comércio exterior**, selecione o número da declaração de importação criado anteriormente, ou crie um novo número de declaração de importação.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Campo</th>
<th>descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Número de declaração da importação</td>
<td>O número de identificação da declaração de importação.</td>
</tr>
<tr class="even">
<td>Data</td>
<td>A data em que a declaração de importação foi emitida.</td>
</tr>
<tr class="odd">
<td>Porto</td>
<td>O código de identificação do porto onde o item importado é carregado.</td>
</tr>
<tr class="even">
<td>Descrição (descrição do porto)</td>
<td>O nome e a descrição do porto.</td>
</tr>
<tr class="odd">
<td>Estado do porto</td>
<td>O estado no qual o porto está localizado.</td>
</tr>
<tr class="even">
<td>Tipo de DI</td>
<td>O tipo da declaração de importação:
<ul>
<li><strong>Declaração de importação</strong> – Uma declaração de importação detalhada é gerada.</li>
<li><strong>Declaração de importação simplificada</strong> – Uma declaração de importação resumida é gerada.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Data de nacionalização</td>
<td>A data na qual o item é nacionalizado no Brasil.</td>
</tr>
<tr class="even">
<td>Número do drawback</td>
<td>O código de identificação da operação de drawback.</td>
</tr>
<tr class="odd">
<td>Via de transporte</td>
<td>O tipo de transporte.</td>
</tr>
<tr class="even">
<td>ARFMM</td>
<td>O valor adicional de frete para o tipo de transporte <strong>Marinho</strong>.</td>
</tr>
</tbody>
</table>

## <a name="scenario-overview"></a>Visão geral do cenário
Para esse cenário, você deve criar e lançar uma nota fiscal de importação direta.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Plano de fundo</td>
<td>A empresa importa os itens e deve emitir uma nota fiscal de entrada para os itens importados com corretos os impostos corretos calculados para os itens serem liberados nas Alfândegas. As seguintes pessoas/funções estão envolvidas:
<ul>
<li>Alicia (Agente de compras)</li>
<li>April (coordenador de Contas a Pagar)</li>
<li>Sammy (Remessa e recebimento)</li>
</ul></td>
</tr>
<tr class="even">
<td>Metas do usuário</td>
<td><ul>
<li>Ter os impostos (IPI, II, PIS, COFINS, ICMS) calculados corretamente para a nota fiscal de importação, de acordo com as regras especificadas pelo governo.</li>
<li>Imprima a nota fiscal de entrada.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Etapas de cenário</td>
<td><ol>
<li>Alicia cria uma ordem de compra para um fornecedor estrangeiro. A ordem de compra usa a moeda estrangeira pela qual o preço do item foi negociado.</li>
<li>O despachante aduaneiro notifica Alicia de que os itens chegaram no porto ou no aeroporto e fornece o valor previsto de imposto a ser pago, antes de o porto ou aeroporto liberar os itens.</li>
<li>April gera um pagamento antecipado na moeda da empresa do despachante aduaneiro. Ela usa o valor estimado do imposto como referência.</li>
<li>O despachante aduaneiro gera um documento de declaração de importação por fornecedor. Este documento de declaração de importação é entregue ao despachante aduaneiro. É baseado nos impostos que são apresentados na declaração de importação e gera e paga os documentos de pagamento de impostos (GARE).</li>
<li>O despachante aduaneiro envia uma cópia do documento de declaração de importação para April. April ajusta os valores de encargos diversos relacionados a frete, seguro e SISCOMEX em ordens de compra relacionadas ao processo de importação. (A distribuição de encargos diversos é criada manualmente por April).</li>
<li>April prepara a nota fiscal de importação, selecionando as ordens de compra e os itens da ordem de compra. Em seguida, ela insere o número de declaração de importação na ordem de compra. Ela também insere o número de adição nas linhas de nota fiscal de lançamento por item de ordem de compra.</li>
<li>April verifica o valor de impostos sobre vendas antes de lançar a nota fiscal de importação com a declaração de importação. Quando os valores de impostos da nota fiscal de importação e da declaração de importação forem correspondentes, ela lança a fatura. Se os valores não forem correspondentes, ela ajusta os valores da nota fiscal da fatura que deve ser lançada. <strong>Observação:</strong> Como as mercadorias ainda não estão incluídas na posse de uma empresa, um depósito diferente pode ser usado em cada linha de ordem de compra relacionada à nota fiscal de importação.</li>
<li>April envia a nota fiscal de fornecedor impressa ao despachante aduaneiro.</li>
<li>O despachante aduaneiro adiciona os documentos que são necessários para liberar as mercadorias: a declaração de importação, o GARE (impostos pagos) e a nota fiscal impressa de importação (própria nota fiscal). O despachante aduaneiro solicita que o porto ou o aeroporto libere as mercadorias.</li>
<li>As mercadorias são transportadas para o depósito da empresa.</li>
<li>Sammy recebe as mercadorias quando chegam na empresa e transfere os itens de depósito temporário para o depósito efetivo.</li>
<li>Alicia usa a fatura complementar para adicionar as despesas do despachante aduaneiro, mais frete nacional ou outros custos relacionados ao processo de importação, após a nacionalização de mercadorias (entrada no território brasil), aos custos do item da nota fiscal original de importação.</li>
</ol></td>
</tr>
</tbody>
</table>





