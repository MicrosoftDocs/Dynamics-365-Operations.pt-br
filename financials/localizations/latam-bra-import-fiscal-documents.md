---
title: Importar notas fiscais do Brasil
description: "Este tópico descreve a funcionalidade para notas fiscais de importação direta disponível da localização brasileira."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BrazilParameters, FiscalDocument_BR, PurchImportDeclaration_BR, PurchImportDeclarationList_BR, VendEditInvoice
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 270204
ms.assetid: b2389297-1359-498f-b755-c20574248ae1
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: e85f2763bbbab6220c831476e3939a7b1c343e5a
ms.lasthandoff: 03/31/2017


---

# <a name="import-fiscal-documents-for-brazil"></a>Importar notas fiscais do Brasil

Este tópico descreve a funcionalidade para notas fiscais de importação direta disponível da localização brasileira.

Você pode emitir uma nota fiscal de importação direta ao criar uma ordem de compra importar itens de um fornecedor estrangeiro. Uma nota fiscal de importação registra informações de trânsito sobre os itens que você importa. A nota fiscal de importação é usada para itens gratuitos de alfândega e para validar a entrada de itens no depósito de entidade legal. É necessário especificar as informações da declaração de importação (o número de adição e o número da declaração de importação) para uma ordem de compra que é emitida para importar itens de um fornecedor estrangeiro antes de lançar a ordem de compra. Um documento fiscal de importação direta inclui as seguintes informações:

-   Cálculo de impostos brasileiros para a nota fiscal de importação direta
-   Informações introdutória sobre a declaração de importação
-   Geração de NF-e (método fiscal eletrônico brasileiro 55 de documento)
-   Um documento impresso de DANFE
-   ** Integração com livros fiscais ** o módulo

** Observação: ** Você também pode emitir uma nota fiscal de importação quando você cria uma ordem de compra importar serviços do fornecedor estrangeiro. Quando você importa um serviço, se não requer que especificar o número de demonstrativo de importação e o número de acréscimo para a nota fiscal de fornecedor. Antes de gerar uma nota fiscal de importação, marque ** gerar a nota fiscal de entrada ** a opção para o fornecedor estrangeiro ** fornecedores ** na página. Você pode usar ** cancelar ** para cancelar uma nota fiscal de importação incorreta. Você pode usar ** consulte ** para carregar todos os documentos de impostos, com informações relacionadas, ** visualizador de documento fiscal ** na página.

## <a name="prerequisites"></a>Pré-requisitos
Para criar e lançar um documento fiscal de importação direta, você deve definir os seguintes parâmetros ** declaração de importação ** o grupo de campos ** documento fiscal ** na guia ** parâmetros brasileiros ** de página:

-   ** O valor da linha se baseia ** – selecione um destes valores:
    -   ** FOB ** – valor de linha na nota fiscal é igual à linha. valor bruto
    -   ** O CIF + II ** – ** linha em valor ** nota fiscal é igual ao valor bruto de linha além dos encargos diversos (exceto encargos diversos do SISCOMEX ou cliente) relacionadas da instalação do processo de importação para a nota fiscal de fornecedor.
-   ** ID de texto ** – selecione o texto usado para imprimir informações de declaração de importação como informações adicionais no documento ou no DANFE fiscal impressa.

## <a name="import-declaration"></a>Declaração da importação
Após criar e confirmou ordem de compra para um fornecedor estrangeiro e, antes que a nota fiscal de fornecedor foi lançada, você pode inserir informações sobre a declaração de importação. ** Comércio exterior ** na página, selecione o número de demonstrativo de importação criado anteriormente, ou criar um novo número de demonstrativo de importação.

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
<td>A data em que a declaração de importação é emitida.</td>
</tr>
<tr class="odd">
<td>Porto</td>
<td>O código de identificação de porto onde o item importado foi cobrado.</td>
</tr>
<tr class="even">
<td>Descrição (descrição do porto)</td>
<td>A descrição e o nome da porta.</td>
</tr>
<tr class="odd">
<td>Estado do porto</td>
<td>O estado onde o porto é alcançada.</td>
</tr>
<tr class="even">
<td>Tipo de DI</td>
<td>O tipo de demonstrativo de importação:
<ul>
<li><strong>Declaração de importação</strong> – Uma declaração de importação detalhada é gerada.</li>
<li><strong>Declaração de importação simplificada</strong> – Uma declaração de importação resumida é gerada.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Data de nacionalização</td>
<td>A data em que o item é nacionalizado em O Brasil.</td>
</tr>
<tr class="even">
<td>Número do drawback</td>
<td>O código de identificação da operação de inconveniente.</td>
</tr>
<tr class="odd">
<td>Via de transporte</td>
<td>O tipo de transporte.</td>
</tr>
<tr class="even">
<td>ARFMM</td>
<td>O valor adicional de frete para o tipo de transporte <strong>Marinho</strong> .</td>
</tr>
</tbody>
</table>

## <a name="scenario-overview"></a>Visão geral do cenário
Para esse cenário, você deve criar e lançar um documento fiscal de importação direta.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Plano de fundo</td>
<td>Itens de importações de empresa e devem emitir uma nota fiscal de entrada para os itens importados com corretos os impostos calculados para os itens são liberados customs em. Estes contatos/funções são involvidos:
<ul>
<li>(Alicia agente de compras)</li>
<li>abril (coordenador de contas a pagar)</li>
<li>(Sammy envio e recebimento)</li>
</ul></td>
</tr>
<tr class="even">
<td>Meta de usuário</td>
<td><ul>
<li>Tenha os impostos (IPI, II, PIS, COFINS, ICMS) calculados corretamente para a importação de nota fiscal, de acordo com as regras especificadas pelo governo.</li>
<li>Imprima a nota fiscal de entrada.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Etapas de cenário</td>
<td><ol>
<li>Alicia cria uma ordem de compra para um fornecedor estrangeiro. A ordem de compra usando a moeda estrangeira que o preço de itens foi negociado em.</li>
<li>O agente de aduaneiro alfândega (do despachante) Alicia notifica que os itens chegaram na porta, ou em aeroporto e fornece o valor previsto de imposto a ser pago antes da porta ou o aeroporto pode liberar os itens.</li>
<li>abril gera um pagamento antecipado na moeda da empresa do agente alfândega. Use o valor de imposto como referência.</li>
<li>O customs () Aduana geram um documento da declaração de importação por fornecedor. Este documento declaração de importação for entregue do agente alfândega. Obtém com base em impostos que são apresentados a declaração de importação, e gera e paga os documentos de pagamento de impostos (GARE).</li>
<li>O agente de alfândega enviar uma cópia do documento de importação a declaração de abril. abril ajuste nos valores de encargos diversos relacionados para transportar, seguro, e o SISCOMEX em ordens de compra relacionadas o processo de importação. (Distribuição de encargos diversos é criada manualmente.) daqui até abril</li>
<li>abril prepare a importação de nota fiscal se ordens de compra e os itens da ordem de compra. Insira o número de demonstrativo de importação na ordem de compra. Também insere o número de adição nas linhas de nota fiscal de postagem por item de ordem de compra.</li>
<li>abril verifica o valor de impostos sobre vendas antes de lançar a nota fiscal contra de importação a declaração de importação. Quando os valores de imposto de importação de nota fiscal e de correspondência da declaração de importação, ela postarem a fatura. Se os valores não correspondem, ajuste os valores da nota fiscal a ser lançada. <strong>Observação:</strong> Por que as mercadorias estão não não incluído posse de uma empresa, um depósito diferente pode ser usado em cada linha de ordem de compra relacionada a nota fiscal de importação.</li>
<li>abril envia a nota fiscal de fornecedor do agente impressa alfândega.</li>
<li>O agente de alfândega adiciona os documentos que são necessários para liberar mercadorias: a declaração de importação, o GARE pago (imposto), e a nota fiscal impressa de importação (próprio - nota fiscal). O agente de alfândega solicita em que a versão de porto ou de aeroporto mercadorias.</li>
<li>As mercadorias são transportados para o depósito da empresa.</li>
<li>Sammy recebe quando as mercadorias chegam da empresa e transfere os itens de depósito eficaz temporário ao depósito.</li>
<li>Alicia usam a fatura complementar para adicionar as despesas do agente alfândega, frete nacional positivo ou outro custo relacionadas ao processo de importação após a nacionalização de mercadorias (entrada no território brasil), ocorre ao custo do item de nota fiscal original de importação.</li>
</ol></td>
</tr>
</tbody>
</table>




