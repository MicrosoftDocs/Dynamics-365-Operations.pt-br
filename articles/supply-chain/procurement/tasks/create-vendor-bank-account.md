---
title: Criar uma conta bancária de fornecedor
description: Este procedimento mostra como criar uma conta de banco para um fornecedor.
author: GalynaFedorova
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts, LogisticsPostalAddressSingle
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0b201f5eb2bf8eb496a761b6fc6ca729a46a85ce
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8677832"
---
# <a name="create-a-vendor-bank-account"></a>Criar uma conta bancária de fornecedor

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como criar uma conta de banco para um fornecedor. Você pode usar este procedimento na empresa USMF de dados de demonstração.

1. Acesse **Painel de Navegação > Módulos > Compras e fornecimento > Fornecedores > Todos os fornecedores**.
2. Selecione o fornecedor para o qual você deseja criar uma conta bancária e clique no link no campo **ID da conta do fornecedor**.
3. No **Painel de Ações**, clique em **Fornecedor**.
4. Clique em **Contas bancárias**.
5. No **Painel de Ação**, clique em **Novo**.
6. No campo **Conta bancária**, digite um valor. Esta identificação será usada para identificar a conta bancária no registro do vendedor.  
7. No campo **Nome**, digite um valor.
8. No campo **Grupos de banco**, insira ou selecione um valor.
9. No campo **Tipo de número de roteiro**, selecione uma opção. Este é o tipo do número de roteamento usado para pagamentos internacionais.  
10. No campo **Número da conta bancária**, digite um valor.
11. No campo **Código SWIFT**, digite um valor.
12. No campo **IBAN**, digite um valor.
    - O número de IBAN deve estar no formato correto. Por exemplo, é possível usar o DE89370400440532013000.  
    - O estado da conta bancária é ativo se a data ativa foi alcançada, e a data de validade não esteve excedida. É igualmente ativa se a data ativa e os campos da data de validade estão vazios. Se as datas nos campos Data ativa e Data de vencimento ocorrerem no futuro, os pagamentos eletrônicos não estarão disponíveis. Outros tipos de pagamentos estarão disponíveis e a conta bancária estará ativa.  
13. Expanda a seção **Instalação**.
14. No campo **Código de texto**, digite um valor. Este campo especifica um código que aparece na indicação de banco do receptor.  
15. No campo **Mensagem ao banco**, digite um valor.
16. No campo **Referência de troca**, insira um valor. Este é o número de referência de qualquer taxa de câmbio futuro ou de prazo fixo.
17. No campo **Moeda**, insira ou selecione um valor. Quando as pré-notas são emitidas, esta seção fornece uma visão geral de seu estado (pendente ou aprovado).  
18. Expanda a seção **Endereço**.
19. Expanda a seção **Pré-registros**.
20. Expanda a seção **Informações do contato**.
21. No campo **Telefone**, digite um valor.
22. Feche a página.
23. Clique em **Editar**.
24. Expanda a seção **Pagamento**.
25. No campo **Conta bancária**, selecione a conta que você apenas criou.
26. Clique em **Salvar**. O endereço pode ser herdado do grupo do banco, se for um especificado, ou você pode adicioná-lo aqui.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]