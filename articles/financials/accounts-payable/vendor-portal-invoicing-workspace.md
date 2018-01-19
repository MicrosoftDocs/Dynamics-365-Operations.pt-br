---
title: "Espaço de trabalho de faturamento de colaboração do fornecedor"
description: "Este tópico explica como podem exibir faturas de fornecedor e enviar notas fiscais de colaboração de fornecedor que ao espaço de trabalho."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendInvoiceWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 221534
ms.assetid: c4ed62f3-d351-41d7-a2ad-790576cde4ab
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: ff1818d927f7ab9212c4d5d9109c426be5e0e152
ms.openlocfilehash: 0d11e4fecc4c42636be63c1ce622f0b2f8e58f2c
ms.contentlocale: pt-br
ms.lasthandoff: 11/29/2017

---

# <a name="vendor-collaboration-invoicing-workspace"></a>Espaço de trabalho de faturamento de colaboração do fornecedor

[!include[banner](../includes/banner.md)]


Este tópico explica como podem exibir faturas de fornecedor e enviar notas fiscais de colaboração de fornecedor que ao espaço de trabalho.

O espaço de trabalho **Faturamento da colaboração de fornecedores** pode ser usado para exibir informações de fatura de fornecedor e enviar faturas ao Microsoft Dynamics 365 for Finance and Operations, Enterprise edition usando recursos de fluxo de trabalho.


<a name="vendor-collaboration-invoicing-workspace"></a>Espaço de trabalho de faturamento da colaboração de fornecedores
----------------------------------------

### <a name="summary-tiles"></a>Blocos do resumo

Os blocos **Resumo** darão uma visão geral de notas fiscais do fornecedor selecionado. Você pode exibir faturas pelo estado.
-   Faturas de rascunho não foram enviadas ao fluxo de trabalho.
-   As faturas enviadas não aprovadas são aquelas que o fornecedor enviou, mas que não foram lançadas no Finance and Operations.
-   As faturas aprovadas não pagas são aquelas que foram lançadas no Finance and Operations, mas que ainda não foram totalmente pagas.
-   As faturas pagas são aquelas que foram totalmente pagas no Finance and Operations.

Clique em um quadro abrirá uma exibição filtrada da página **Lista de notas fiscais**.

### <a name="tabular-lists"></a>Listas tabulares

Na seção **Listas Tabular**, o status do faturamento está dividido de formas semelhantes como o resumo organiza lado a lado: Rascunho, e listas enviadas não aprovadas. Quando o estado de rascunho, uma nota fiscal pode ser enviada ao fluxo de trabalho ou ser excluída. A última lista tabular é uma opção para encontrar faturas. Você pode filtrar enquanto pesquisa, para permitir pesquisas mais rápidas.

<a name="all-vendor-invoices-list-page"></a>Página Todas faturas de fornecedor
-----------------------------

É possível exibir todas as faturas de fornecedor lançadas na página de listagem **Faturas de colaboração do fornecedor**. Você pode usar esta página de lista para visualizar o status de pagamento das faturas. Os status de pagamento inclui Não feito, e parcialmente pagas totalmente paga.
Criar uma nova fatura a partir de uma ordem de compra
--------------------------------------------

Você pode criar uma nova nota fiscal do fornecedor selecionando **Novo** a ação **Faturamento de colaboração de fornecedor** no espaço de trabalho. A ordem de compra e o número de nota fiscal devem ser fornecidos pelo fornecedor. Por padrão, todas as linhas de ordem de compra de fornecedores aparecerão em nova nota fiscal. A quantidade e as informações de custo podem ser editadas antes de enviar a nota fiscal de fornecedor para o fluxo de trabalho. Você pode anexar arquivos, notas, imagens e URLs a uma nota fiscal antes enviá-la.



Para obter mais informações, consulte [Colaboração de fornecedores com fornecedores externos](../../supply-chain/procurement/vendor-collaboration-work-external-vendors.md)




