---
title: Configurar recursos bancários e perfis de lançamento para cartas de garantia
description: Essa tarefa cria um Recurso bancário e um perfil de lançamento que são necessários para processar uma carta de garantia.
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
ms.openlocfilehash: 0987ae1e9cfbb1e2d2a957a5fd1ad82257292c0a
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/23/2022
ms.locfileid: "9804092"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letters-of-guarantee"></a>Configurar recursos bancários e perfis de lançamento para cartas de garantia

[!include [banner](../../includes/banner.md)]

Essa tarefa cria um Recurso bancário e um perfil de lançamento que são necessários para processar uma carta de garantia.



Esta tarefa usa a empresa de demonstração USMF. 




## <a name="general-ledger-parameter"></a>Parâmetro da contabilidade
1. Vá para **Gerenciamento de caixa e bancos > Configuração > Parâmetros de gerenciamento de caixa e bancos**.
2. Expanda a seção **Documento bancário**.
3. Selecione a opção **Habilitar carta de garantia**.
4. No campo **Diário de transação**, clique no botão suspenso para abrir a pesquisa.
5. Na lista, localize e selecione o registro desejado.
6. Na lista, clique no link na linha selecionada.
7. Clique na aba **Sequências numéricas**.
    * Definir código de sequência numérica para o número da Carta de garantia e referências de transação da Carta de garantia  
8. Clique em **Salvar**.
9. Feche a página.

## <a name="create-bank-facility"></a>Criar Recursos bancários
1. Vá para **Gerenciamento de caixa e bancos > Configuração > Recursos bancários**.
2. Clique em **Novo**.
3. No campo **Grupo de instalações**, insira o nome do grupo de instalações bancárias para a transação da carta de garantia.
4. No campo **Descrição**, digite um valor.
5. Clique em **Salvar**.
6. Clique na guia **Tipos de instalações**.
7. Clique em **Novo**.
8. No campo **Tipo de instalação**, insira o nome do tipo de recurso bancário relacionado ao contrato de instalação bancária.
9. No campo **Descrição**, digite um valor.
10. No campo **Grupo de instalações**, clique no botão suspenso para abrir a pesquisa.
11. Na lista, localize e selecione o registro desejado.
12. Na lista, clique no link na linha selecionada.
13. No campo **Natureza da instalação**, selecione uma opção.
14. Clique em **Salvar**.
15. Feche a página.

## <a name="bank-posting-profile"></a>Perfil de lançamento bancário
1. Vá para **Gerenciamento de caixa e bancos > Configuração > Perfil de lançamento de documentos bancários**.
2. Clique em **Novo**.
3. No campo **Número de conta/grupo**, clique no botão suspenso para abrir a pesquisa.
4. Na lista, localize e selecione o registro desejado.
5. Na lista, clique no link na linha selecionada.
6. No campo **Liquidar conta**, selecione a conta principal para liquidação.
7. No campo **Conta de encargos**, selecione a conta para transações de despesa.
8. No campo **Conta de margem**, selecione a conta para transações de margem.
9. No campo **Conta de liquidação**, selecione a conta de liquidação para a transação da carta de garantia. 
10. Clique em **Salvar**.
11. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
