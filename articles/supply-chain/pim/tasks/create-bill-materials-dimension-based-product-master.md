---
title: Criar uma lista de materiais para um produto mestre baseado na dimensão
description: Para esse procedimento é necessário ter concluído as 4 guias anteriores nesta sequência de oito registros.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventItemIdLookupSimple, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e7961cfb4ad0e20c49d327d83f56c08811598ac1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422189"
---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a>Criar uma lista de materiais para um produto mestre baseado na dimensão

[!include [banner](../../includes/banner.md)]

Para esse procedimento é necessário ter concluído as 4 guias anteriores nesta sequência de oito registros. Os primeiras 4 registros configuram os dados necessários para concluir este procedimento. A empresa de dados demo usada para criar este procedimento é USMF. Esta tarefa é tratada normalmente pelo designer do produto.


## <a name="select-the-product"></a>Selecionar o produto
1. Clique em Manutenção de produto liberado.
2. Clique em Produtos liberados.
3. Na lista, marque a linha selecionada.
    * Localize o produto mestre liberado com tecnologia de configuração baseada em dimensão que você criou no primeiro guia de tarefa nesta sequência.  
4. No Painel de Ação, clique em Engenharia.
5. Clique em Versões BOM.

## <a name="create-new-bom-and-bom-version"></a>Criar uma nova BOM e versão da BOM
1. Clique em Novo.
2. Clique em Nova BOM e versão da BOM.
3. No campo Nome, digite um valor.
    * Configurações do site  
    * Nesse procedimento, não definimos um site específico da BOM.  
4. Clique em OK.
5. Clique em Novo.
    * Nesse procedimento adicionaremos quatro linhas à BOM. Duas linhas representam as opções de aumento e duas linhas representam as opções do gabinete.  
6. Na lista, marque a linha selecionada.
7. No campo Número do item, insira ou selecione um valor.
    * Selecionar número de item Cabos A0001, HDMI 6'.  
8. No campo Grupo de configuração, insira ou selecione um valor.
    * Selecione o Grupo de configuração de cabo criado na guia 4 nesta sequência.  
9. Clique em Novo.
    * Selecionar número de item Cabos A0002, HDMI 12'.  
10. Na lista, marque a linha selecionada.
11. No campo Número do item, insira ou selecione um valor.
12. No campo Grupo de configuração, insira ou selecione um valor.
    * Selecione o grupo de configurações do cabo novamente.  
13. Clique em Novo.
14. Na lista, marque a linha selecionada.
15. No campo Número do item, insira ou selecione um valor.
    * Selecionar número de item Gabinete D0002.  
16. No campo Grupo de configuração, insira ou selecione um valor.
    * Selecione o grupo de configuração do gabinete para esta linha BOM.  
17. Clique em Novo.
18. Na lista, marque a linha selecionada.
19. No campo Número do item, insira ou selecione um valor.
    * Selecione o número do item M0007 StandardCabinet como a linha BOM da última vez.  
20. No campo Grupo de configuração, insira ou selecione um valor.
    * Selecione o grupo de configuração do gabinete para esta última linha BOM.  

## <a name="approve-and-activate"></a>Aprovar e ativar
1. Feche a página.
2. Clique em Aprovar.
3. No campo Aprovado por, insira ou selecione um valor.
4. Selecione Sim em Também deseja aprovar a lista de materiais? .
5. Clique em OK.
6. Clique em Ativar.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]