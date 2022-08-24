---
title: Emitir notas fiscais de transferência de crédito de imposto ICMS (Brasil)
description: Este artigo explica como criar e emitir uma nova nota fiscal de transferência e gerar uma nota fiscal eletrônica (NF-e).
author: AdamTrukawka
ms.date: 06/24/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: atrukawk
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.search.industry: Manufacturing;Distribution;Service industries
ms.openlocfilehash: a0941896ddc447471c569ff3a2d62f7f83a8dd9f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279181"
---
# <a name="issue-icms-tax-credit-transfer-fiscal-documents-brazil"></a>Emitir notas fiscais de transferência de crédito de imposto ICMS (Brasil)

[!include [banner](../../includes/banner.md)]

Você pode criar uma nota fiscal de transferência ou apropriação de imposto e gerar uma nota fiscal eletrônica (NF-e). Quando você lança o documento, uma mensagem XML da NF-e é gerada e enviada para a Secretaria da Fazenda (SEFAZ). Esta tarefa usa a empresa de demonstração BRMF.

1. Acesse Contabilidade > Entradas de diário > Todas as notas fiscais de transferência ou apropriação de imposto.
2. Clique em Novo.
3. No campo Tipo de documento fiscal de transferência ou apropriação de imposto, selecione uma opção.
    * Selecione o tipo de nota fiscal de transferência de impostos, a transferência de imposto ICMS entre estabelecimentos fiscais ou prestação de crédito de importo de ICMS.  
4. No campo ID do estabelecimento fiscal, insira ou selecione um valor.
5. No campo Tipo de conta, selecione uma opção.
    * Ao fazer transferência de imposto ICMS, selecione um fornecedor para receber o crédito de impostos de outro estabelecimento fiscal ou selecione um cliente para transferir o crédito de impostos para outro estabelecimento fiscal.  
6. No campo Número de conta, insira ou selecione um valor.
    * O estabelecimento fiscal deve ser um fornecedor ou cliente.  
7. No campo Modelo do documento, insira ou selecione um valor.
8. No campo Chave de acesso, digite um valor.
9. No campo Data, insira uma data.
10. Clique em Salvar.
11. Clique em Adicionar linha.
12. No campo Descrição do item, digite um valor.
13. Na lista, marque a linha selecionada.
14. No campo CFOP, insira ou selecione um valor.
15. No campo Código de impostos sobre vendas, insira ou selecione um valor.
16. No campo Valor, insira um número.
17. Clique em Salvar.
18. Clique em Lançar.
19. Clique em OK.
20. Feche a página.
21. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
