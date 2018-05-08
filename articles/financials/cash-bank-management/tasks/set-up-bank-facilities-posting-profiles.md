--- 
title: "Configurar recursos bancários e perfis de lançamento para cartas de garantia"
description: "Essa tarefa cria um Recurso bancário e um perfil de lançamento que são necessários para processar uma carta de garantia."
author: kweekley
manager: AnnBe
ms.date: 02/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 022b5d411b8240390c543ba726fe0d6838752944
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letters-of-guarantee"></a>Configurar recursos bancários e perfis de lançamento para cartas de garantia

[!include [task guide banner](../../includes/task-guide-banner.md)]

Essa tarefa cria um Recurso bancário e um perfil de lançamento que são necessários para processar uma carta de garantia.



Esta tarefa usa a empresa de demonstração USMF. 




## <a name="general-ledger-parameter"></a>Parâmetro da contabilidade
1. Vá para Gerenciamento de dinheiro e banco > Configuração > Parâmetros do gerenciamento de dinheiro e banco.
2. Expanda a seção Documento bancário.
3. Selecione a opção Habilitar carta de garantia.
4. No campo Diário de transação, clique no botão suspenso para abrir a pesquisa.
5. Na lista, localize e selecione o registro desejado.
6. Na lista, clique no link na linha selecionada.
7. Clique na aba Sequências numéricas.
    * Definir código de sequência numérica para o número da Carta de garantia e referências de transação da Carta de garantia  
8. Clique em Salvar.
9. Feche a página.

## <a name="create-bank-facility"></a>Criar Recursos bancários
1. Vá para Gerenciamento de dinheiro e banco > Configuração > Recursos bancários.
2. Clique em Novo.
3. No campo Grupo de recursos, insira o nome do grupo de recursos bancários para a transação da carta de garantia.
4. No campo Descrição, digite um valor.
5. Clique em Salvar.
6. Clique na aba Tipos de recursos.
7. Clique em Novo.
8. No campo Tipo de recurso, insira o nome do tipo de recurso bancário que está relacionado ao contrato de recursos bancários.
9. No campo Descrição, digite um valor.
10. No campo Grupo de recursos, clique no botão suspenso para abrir a pesquisa.
11. Na lista, localize e selecione o registro desejado.
12. Na lista, clique no link na linha selecionada.
13. No campo Natureza dos recursos, selecione uma opção.
14. Clique em Salvar.
15. Feche a página.

## <a name="bank-posting-profile"></a>Perfil de lançamento bancário
1. Vá para Gerenciamento de dinheiro e banco > Configuração > Perfil de lançamento de documentos bancários.
2. Clique em Novo.
3. No campo Número de conta/grupo, clique no botão suspenso para abrir a pesquisa.
4. Na lista, localize e selecione o registro desejado.
5. Na lista, clique no link na linha selecionada.
6. No campo Liquidar conta, selecione a conta principal para liquidação.
7. No campo Conta de encargos, selecione a conta para transações de despesa.
8. No campo Conta de margem, selecione a conta para a transação de margem.
9. No campo Conta de liquidação, selecione a conta de liquidação para a transação da carta de garantia. 
10. Clique em Salvar.
11. Feche a página.


