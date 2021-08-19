---
title: Criar uma lista de materiais para um produto mestre baseado na dimensão
description: Para esse procedimento é necessário ter concluído as 4 guias anteriores nesta sequência de oito registros.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventItemIdLookupSimple, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 696cb96c6e934eaa44bfe6f51347df4541e5648f75f1ce07139787a1b235d69d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6715762"
---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a>Criar uma lista de materiais para um produto mestre baseado na dimensão

[!include [banner](../../includes/banner.md)]

Para esse procedimento é necessário ter concluído as 4 guias anteriores nesta sequência de oito registros. Os primeiras 4 registros configuram os dados necessários para concluir este procedimento. A empresa de dados demo usada para criar este procedimento é USMF. Esta tarefa é tratada normalmente pelo designer do produto.

## <a name="select-the-product"></a>Selecionar o produto

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Na lista, marque a linha selecionada.
    * Localize o produto mestre liberado com tecnologia de configuração baseada em dimensão que você criou no primeiro guia de tarefa nesta sequência.  
1. No Painel de Ação, selecione **Engenheiro**.
1. Selecione **Versões da BOM**.

## <a name="create-new-bom-and-bom-version"></a>Criar uma nova BOM e versão da BOM

1. Selecione **Novo**.
1. Selecione **BOM e versão da BOM**.
1. No campo **Nome**, digite um valor.
    * Configurações do site  
    * Nesse procedimento, não definimos um site específico da BOM.  
1. Selecione **OK**.
1. Selecione **Novo**.
    * Nesse procedimento adicionaremos quatro linhas à BOM. Duas linhas representam as opções de aumento e duas linhas representam as opções do gabinete.  
1. Na lista, marque a linha selecionada.
1. No campo **Número do item**, insira ou selecione um valor.
    * Selecionar número de item Cabos A0001, HDMI 6'.  
1. No campo **Grupo de configuração**, informe ou selecione um valor.
    * Selecione o grupo de configuração de cabo criado na guia 4 nesta sequência.  
1. Selecione **Novo**.
    * Selecionar número de item Cabos A0002, HDMI 12'.  
1. Na lista, marque a linha selecionada.
1. No campo **Número do item**, insira ou selecione um valor.
1. No campo **Grupo de configuração**, informe ou selecione um valor.
    * Selecione o grupo de configurações do cabo novamente.  
1. Selecione **Novo**.
1. Na lista, marque a linha selecionada.
1. No campo **Número do item**, insira ou selecione um valor.
    * Selecionar número de item Gabinete D0002.  
1. No campo **Grupo de configuração**, informe ou selecione um valor.
    * Selecione o grupo de configuração do gabinete para esta linha da BOM.  
1. Selecione **Novo**.
1. Na lista, marque a linha selecionada.
1. No campo **Número do item**, insira ou selecione um valor.
    * Selecione o número do item M0007 StandardCabinet como a linha BOM da última vez.  
1. No campo **Grupo de configuração**, informe ou selecione um valor.
    * Selecione o grupo de configuração do gabinete para a última linha da BOM.  

## <a name="approve-and-activate"></a>Aprovar e ativar

1. Feche a página.
1. Selecione **Aprovar**.
1. No campo **Aprovado por** insira ou selecione um valor.
1. Selecione *Sim* no campo **Também deseja aprovar a lista de materiais?**.
1. Selecione **OK**.
1. Selecione **Ativar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]