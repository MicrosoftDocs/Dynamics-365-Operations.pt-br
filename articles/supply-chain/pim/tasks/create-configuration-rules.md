---
title: Criar regras de configuração
description: Esse procedimento cria regras de configuração que podem ser usadas na configuração baseada em dimensão para forçar ou evitar certas combinações de linhas da Lista de Materiais.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMTable, BOMConfigRule, ConfigItemIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6bc0af4d95e9430d0b5c8b7fc9a4ade076802044
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422187"
---
# <a name="create-configuration-rules"></a>Criar regras de configuração

[!include [banner](../../includes/banner.md)]

Esse procedimento cria regras de configuração que podem ser usadas na configuração baseada em dimensão para forçar ou evitar certas combinações de linhas da Lista de Materiais. A empresa de dados demo usada para criar este procedimento é USMF. Este é o sétimo procedimento dos oito que explicam como criar combinações para configuração baseada em dimensão.

1. Vá para Gerenciamento de informações sobre produtos > Lista de materiais e fórmulas > Lista de materiais.
2. Na lista, localize e selecione o PDV desejado.
    * Localize e selecione a Lista de Materiais para a configuração baseada em dimensão.  
3. No Painel de Ação, clique em Opções.
4. Clique em Alterar exibição.
5. Clique em Exibição do cabeçalho.
    * Abra a exibição do cabeçalho para acessar a aba rápida do Roteiro de configuração.  
6. Expandir ou recolher a seção Rota de configuração.
    * A aba rápida Roteiro de configuração deve estar no modo expandido.  
7. Clique em Regras de configuração.
8. Clique em Novo.
9. Na lista, marque a linha selecionada.
10. No campo Número de item, clique no botão suspenso para abrir a pesquisa.
    * Os itens do grupo de configuração atual estão exibidos. Selecione aquele que representa a condição na regra.  
11. Na lista, clique no link na linha selecionada.
12. No campo Método, selecione uma opção.
    * É possível forçar tanto uma seleção como uma desmarcação de um item de outro grupo de configuração.  
13. No campo Grupo derivado, clique no botão suspenso para abrir a pesquisa.
14. Na lista, localize e selecione o PDV desejado.
15. Na lista, clique no link na linha selecionada.
    * Selecione o grupo de configuração desejado.  
16. No campo Número de item derivado, clique no botão suspenso para abrir a pesquisa.
17. Na lista, clique no link na linha selecionada.
    * Selecione o número de item que será selecionado ou desmarcado de acordo com o método escolhido.  
18. Feche a página.

