---
title: Criar regras avançadas para diários
description: Este procedimento aborda a criação de regras avançadas para diários.
author: aprilolson
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalControl, CompanyLookup, LedgerJournalPostControl
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cd753d521dc4ad4c1e46bf51d9c1e4aa0ba02721
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832793"
---
# <a name="create-advanced-rules-for-journals"></a>Criar regras avançadas para diários

[!include [banner](../../includes/banner.md)]

Este procedimento aborda a criação de regras avançadas para diários. Inclui a configuração de controle de diário e restrições de lançamento de usuário. Este procedimento usa a empresa de dados de demonstração USMF.


## <a name="set-up-journal-control"></a>Configurar controle do diário
1. No **Painel de Navegação**, vá para **Módulos > Contabilidade > Configuração do diário > Nomes de diário**.
2. Na lista, localize e selecione o registro desejado.
3. No **Painel de Ações**, clique em **Controle de diário**.
4. Na Guia Rápida **Que tipos de conta podem ser lançados?**, clique em **Adicionar**.
5. No campo **Contas da empresa**, clique no botão suspenso para abrir a pesquisa.
6. Na lista, localize e selecione o registro desejado.
7. Na lista, clique no link na linha selecionada.
8. Na Guia Rápida **Que valores de segmento são válidos para este diário?**, clique em **Adicionar**.
9. No campo **Estrutura de conta**, clique no botão suspenso para abrir a pesquisa.
10. Na lista, localize e selecione o registro desejado.
11. Na lista, clique no link na linha selecionada.
12. No campo **Segmento**, clique no botão suspenso para abrir a pesquisa.
13. Na lista, clique no link na linha selecionada.
14. No campo **Valor inicial**, clique no botão suspenso para abrir a pesquisa.
15. Na lista, localize e selecione o registro desejado.
16. Na lista, clique no link na linha selecionada.
17. No campo **Valor final**, clique no botão suspenso para abrir a pesquisa.
18. Na lista, localize e selecione o PDV desejado.
19. Na lista, clique no link na linha selecionada.

## <a name="set-up-posting-restrictions"></a>Configurar restrições de lançamento
1. Feche a página.
2. Clique em **Restrições de lançamento**.
3. No campo **Como deseja configurar as restrições de lançamento**, selecione "Por grupo de usuários".
4. Na árvore, verifique 'o grupo do qual deseja permitir o lançamento para o nome desse diário'.
5. Clique em **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]