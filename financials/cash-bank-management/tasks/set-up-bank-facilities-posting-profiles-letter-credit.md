--- 
title: "Configurar recursos bancários e perfis de lançamento para carta de crédito"
description: "Este procedimento apresenta as etapas da criação de um Recurso bancário e perfil de lançamento necessários para processar Cartas de crédito."
author: kweekley
manager: AnnBe
ms.date: 11/14/2016
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
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 4cf5d982fa58df93529f3506beef46f660265530
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letter-of-credit"></a>Configurar recursos bancários e perfis de lançamento para carta de crédito

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento apresenta as etapas da criação de um Recurso bancário e perfil de lançamento necessários para processar Cartas de crédito. 

Essas tarefas usam a empresa de demonstração 'USMF'.






## <a name="general-ledger-parameter"></a>Parâmetro da contabilidade
1. Vá para Gerenciamento de dinheiro e banco > Configuração > Parâmetros do gerenciamento de dinheiro e banco.
2. Expanda a seção Documento bancário.
3. Selecione a opção Habilitar importação de carta de crédito.
4. Selecione a opção Habilitar exportação de carta de crédito.
5. Clique em Salvar.
6. Feche a página.

## <a name="create-bank-facility"></a>Criar Recursos bancários
1. Vá para Gerenciamento de dinheiro e banco > Configuração > Recursos bancários.
2. Clique em Novo.
3. No campo Grupo de recursos, insira o nome do grupo de recursos bancários.
4. No campo Descrição, insira a descrição do grupo de recursos bancários.
5. Clique em Salvar.
6. Clique na aba Tipos de recursos.
7. Clique em Novo.
8. No campo Tipo de recurso, insira um código exclusivo.
9. No campo Descrição, digite um valor.
10. No campo Grupo de recursos, clique no botão suspenso para abrir a pesquisa.
11. Na lista, localize e selecione o registro desejado.
12. Na lista, clique no link na linha selecionada.
13. No campo Natureza dos recursos, selecione a natureza dos recursos bancários.
14. Clique em Salvar.
15. Feche a página.

## <a name="bank-posting-profile"></a>Perfil de lançamento bancário
1. Vá para Gerenciamento de dinheiro e banco > Configuração > Perfil de lançamento de documentos bancários.
2. Clique em Novo.
3. No campo Número de conta/grupo, clique no botão suspenso para abrir a pesquisa.
4. Na lista, localize e selecione o registro desejado.
5. Na lista, clique no link na linha selecionada.
6. Selecione a conta principal para liquidação.
    * Essa conta é usada para calcular a previsão do fluxo de caixa.  
7. No campo Conta de encargos, selecione a conta para transações de despesa.
8. No campo Conta de margem, selecione a conta para transações de margem.
    * Esta conta é debitada quando a margem de abertura é lançada e creditada quando o pagamento é lançado.  
9. Clique em Salvar.


