---
title: Configurar recursos bancários e perfis de lançamento para carta de crédito
description: Este procedimento apresenta as etapas da criação de um Recurso bancário e perfil de lançamento necessários para processar Cartas de crédito.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankParameters, DefaultDashboard, BankDocumentSetup, BankDocumentPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7fe5b2ba43c4fcb4855c742bdb6f8209ebd92d68
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779423"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letter-of-credit"></a>Configurar recursos bancários e perfis de lançamento para carta de crédito

[!include [banner](../../includes/banner.md)]

Este procedimento apresenta as etapas da criação de um Recurso bancário e perfil de lançamento necessários para processar Cartas de crédito. 

Essas tarefas usam a empresa de demonstração 'USMF'.


## <a name="general-ledger-parameter"></a>Parâmetro da contabilidade
1. Vá para **Gerenciamento de caixa e bancos > Configuração > Parâmetros de gerenciamento de caixa e bancos**.
2. Expanda a seção **Documento bancário**.
3. Selecione a opção **Habilitar importação de carta de crédito**.
4. Selecione a opção **Habilitar exportação de carta de crédito**.
5. Clique em **Salvar**.
6. Feche a página.

## <a name="create-bank-facility"></a>Criar Recursos bancários
1. Vá para **Gerenciamento de caixa e bancos > Configuração > Recursos bancários**.
2. Clique em **Novo**.
3. No campo **Grupo de recursos**, insira o nome do grupo de instalações bancárias.
4. No campo **Descrição**, insira a descrição do grupo de instalações bancárias.
5. Clique em **Salvar**.
6. Clique na guia **Tipos de instalações**.
7. Clique em **Novo**.
8. No campo **Tipo de instalação**, insira um código exclusivo.
9. No campo **Descrição**, digite um valor.
10. No campo **Grupo de instalações**, clique no botão suspenso para abrir a pesquisa.
11. Na lista, localize e selecione o registro desejado.
12. Na lista, clique no link na linha selecionada.
13. No campo **Natureza das instalações**, selecione a natureza das instalações bancárias.
14. Clique em **Salvar**.
15. Feche a página.

## <a name="bank-posting-profile"></a>Perfil de lançamento bancário
1. Vá para **Gerenciamento de caixa e bancos > Configuração > Perfil de lançamento de documentos bancários**.
2. Clique em **Novo**.
3. No campo **Número de conta/grupo**, clique no botão suspenso para abrir a pesquisa.
4. Na lista, localize e selecione o registro desejado.
5. Na lista, clique no link na linha selecionada.
6. Selecione a conta principal para liquidação.
    * Essa conta é usada para calcular a previsão do fluxo de caixa.  
7. No campo **Conta de encargos**, selecione a conta para transações de despesa.
8. No campo **Conta de margem**, selecione a conta para transações de margem.
    * Esta conta é debitada quando a margem de abertura é lançada e creditada quando o pagamento é lançado.  
9. Clique em **Salvar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
