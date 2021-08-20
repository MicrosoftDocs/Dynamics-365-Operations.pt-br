---
title: Criar regras de configuração
description: Esse procedimento cria regras de configuração que podem ser usadas na configuração baseada em dimensão para forçar ou evitar certas combinações de linhas da Lista de Materiais.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BOMTable, BOMConfigRule, ConfigItemIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4e84370041f0b64b0ae07d7076592b285ed335ac66bd8f1efe8512caecbf1bba
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6776353"
---
# <a name="create-configuration-rules"></a>Criar regras de configuração

[!include [banner](../../includes/banner.md)]

Esse procedimento cria regras de configuração que podem ser usadas na configuração baseada em dimensão para forçar ou evitar certas combinações de linhas da Lista de Materiais. A empresa de dados demo usada para criar este procedimento é USMF. Este é o sétimo procedimento dos oito que explicam como criar combinações para configuração baseada em dimensão.

1. Acesse Gerenciamento de informações sobre produtos > Lista de materiais e fórmulas > Lista de materiais.
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]