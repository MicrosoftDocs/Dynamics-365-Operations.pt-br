---
title: Notas fiscais e suas estruturas para o Brasil
description: "Este tópico descreve as notas fiscais do Brasil."
author: sndray
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: FiscalDocument_BR, FiscalDocumentAmounts_BR, FiscalDocumentChargesTotals_BR, FiscalDocumentElectronic_BR
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 269094
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: ed953f52d0e816cd2e8804409672e09141096cd2
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="fiscal-documents-and-fiscal-document-framework-for-brazil"></a>Notas fiscais e suas estruturas para o Brasil

[!include[banner](../includes/banner.md)]


Este tópico descreve as notas fiscais do Brasil.

<a name="overview"></a>Visão Geral
--------

Nota fiscal é um documento legal que registra a transferência de propriedade de um item ou serviço fornecido por um estabelecimento fiscal (emissor) para uma pessoa ou outro estabelecimento fiscal (cliente, fornecedor, subsidiária ou filial). Uma nota fiscal é usada para registrar impostos. Cada estabelecimento fiscal emite e recebe notas fiscais para todas as transações, incluindo vendas, compras, ajustes de impostos e transferências de item ou ativo. As notas fiscais podem ser geradas usando os seguintes formatos:
-   Nota fiscal impressa – a nota fiscal é impressa em papel.
-   Nota fiscal eletrônica – uma nota fiscal digital é emitida e recebida em formato eletrônico. Uma nota fiscal eletrônica pode ser uma NF-e (nota fiscal eletrônica) federal, que é gerada para itens e relatada no nível estadual ou federal pode ser uma NF-e municipal, que é gerada para serviços e relatada no nível municipal.

Todas as notas fiscais emitidas ou recebidas por um estabelecimento fiscal devem ser relatadas no nível de autoridade federal, estadual ou municipal. As notas fiscais devem ser relatadas em formatos específicos, como relatório fiscal do SPED (Sistema Público de Escrituração Digital) ou livros fiscais, PIS/COFINS (Programa de Integração Social/Contribuição para o Financiamento da Seguridade Social) do SPED ou SINTEGRA (Sistema Integrado de Informações sobre Operações Interestaduais com Mercadorias e Serviços). A estrutura da nota fiscal é usada para garantir que todos os documentos fiscais lançados estejam em conformidade com uma estrutura específica, independentemente do processo que é usado para gerar o documento fiscal. Você pode revisar as notas fiscais lançadas na página de listagem **Todas as notas fiscais**. Você pode verificar as transações de nota fiscal, os impostos lançados, os encargos lançados, os documentos fiscais referenciados e o texto da nota fiscal de uma nota fiscal lançada. A estrutura da nota fiscal também garante que todas as informações relacionadas usem o formato correto. As informações relacionadas incluem:
-   Relações entre notas fiscais e seus documentos de origem.
-   Texto da nota fiscal, processos referenciados, referências fiscais, faturas e prestações, imposto lançado e encargos lançados.

## <a name="view-and-print-fiscal-documents"></a>Exibir e imprimir as notas fiscais.
Você pode exibir e imprimir todas as notas fiscais das seguintes páginas:
-   **Contas a receber** &gt; **Notas fiscais** &gt; **Todas as notas fiscais**
-   **Contas a pagar** &gt; **Notas fiscais** &gt; **Todas as notas fiscais**
-   **Contabilidade** &gt; **Consulta e relatórios** &gt; **Notas fiscais** &gt; **Todas as notas fiscais**
-   **Gerenciamento de estoque** &gt; **Ordens de entradas** &gt; **Todas as notas fiscais**
-   **Gerenciamento de estoque** &gt; **Ordens de saída** &gt; **Todas as notas fiscais**
-   **Gerenciamento e contabilidade de projeto** &gt; **Nota fiscal** &gt; **Todas as notas fiscais**
-   **Livros fiscais** &gt; **Período de escrituração**

## <a name="actions"></a>Ações
Depois que uma nota fiscal for lançada, o usuário poderá ver as informações a seguir.

| **Botão de ação**                 | **Descrição**                                                                                                                                                                                                                                                                                                                                                      |
|-----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Nota fiscal complementar** | Na página **Nota fiscal complementar de compra** ou na página **Nota fiscal complementar de venda** você pode criar uma nota fiscal complementar de compra ou de venda. A página **Nota fiscal complementar de compra** ou a página **Nota fiscal complementar de venda** é determinada pelo tipo de nota fiscal (fornecedor ou cliente) selecionada. |
| **Totais**                        | Exibe os totais da nota fiscal.                                                                                                                                                                                                                                                                                                                             |
| **Comprovante**                       | Exibe as transações do comprovante da nota fiscal.                                                                                                                                                                                                                                                                                                               |
| **Encargos**                       | Exibe os encargos da nota fiscal.                                                                                                                                                                                                                                                                                                                            |
| **Imposto sobre vendas**              | Exibe o impostos sobre vendas lançado para a nota fiscal.                                                                                                                                                                                                                                                                                                                   |
| **Documento original**             | Exibe a transação lançada na qual a nota fiscal é gerada.                                                                                                                                                                                                                                                                                               |
| **Textos das notas fiscais**         | Exibe os textos das notas fiscais associados à nota fiscal.                                                                                                                                                                                                                                                                                             |
| **Referência fiscal**              | Exibe as referências fiscais associadas à nota fiscal.                                                                                                                                                                                                                                                                                                 |
| **Declaração de importação**            | Exibe informações de declaração de importação para a nota fiscal.                                                                                                                                                                                                                                                                                                     |






