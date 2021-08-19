---
title: Completar instalação básica de um produto mestre lançado
description: Este tópico mostra como concluir a configuração mínima necessária antes de o produto mestre ser usado em versões de BOM.
author: ShylaThompson
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventTableInventoryDimensionGroups, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 370afb43d314915958b6e5377028f2ade2b9609cc6e365f0499a9f7c3373f9e3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6734154"
---
# <a name="complete-basic-setup-of-a-released-product-master"></a>Completar instalação básica de um produto mestre lançado

[!include [banner](../../includes/banner.md)]

Este tópico mostra como concluir a configuração mínima necessária antes de o produto mestre ser usado em versões de BOM.

Este é o terceiro procedimento dos oito que explicam como criar combinações para configuração baseada em dimensão. A empresa de dados demo usada para criar este procedimento é USMF.

1. Acesse **Painel de Navegação > Módulos > Gerenciamento de informações do produto > Produtos > Produtos liberados**.
2. Na lista, localize e selecione o PDV desejado. Selecione o produto mestre que você liberou no segundo procedimento. Esse produto mestre foi criado com a tecnologia de configuração baseada em dimensão.  
3. No Painel de Ação, selecione **Produto**.
4. Selecione **Grupos de dimensões** para abrir a caixa de diálogo suspensa.
5. No campo **Grupo de dimensões de armazenamento**, selecione o botão suspenso para abrir a pesquisa.
6. Na lista, localize e selecione o registro desejado. O grupo dimensões de armazenamento determina quais dimensões de armazenamento são usadas na transação do produto. Selecione **Site** para esse procedimento.  
7. No campo **Grupo de dimensões de rastreamento**, selecione o botão suspenso para abrir a pesquisa.
8. Na lista, localize e selecione o registro desejado. O grupo dimensões de rastreamento determina quais dimensões de rastreamento são usadas na transação do produto. Selecione **Nenhum** para esse procedimento.  
9. Clique em **OK**.
10. Clique em **Editar**.
11. No campo **Grupo de modelos do item**, selecione o botão suspenso para abrir a pesquisa.
12. Na lista, localize e selecione o registro desejado. Os grupos de modelo de item contêm configurações que determinam como os itens são controlados e processados em recebimentos e saídas. Eles também determinam como o consumo de itens é calculado. Selecione **FIFO** para esse procedimento.  
13. Expanda a seção **Gerenciar custos**.
14. No campo **Grupo de itens**, selecione o botão suspenso para abrir a pesquisa.
15. Na lista, localize e selecione o registro desejado. Os grupos de itens são usados para gerenciar o estoque, dividindo os itens de estoque em grupos. Selecione **CarAudio** para esse procedimento.  
16. No Painel de Ações, selecione **Plano**.
17. Selecione **Configurações de ordem padrão**.
18. No campo **Tipo de ordem padrão**, selecione uma opção. Selecione **Produção** para especificar que a opção de fornecimento padrão para esse produto mestre é produzi-lo.  
19. Selecione **Salvar**.
20. Feche a página.
21. Feche o formulário **Detalhes do produto liberado**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]