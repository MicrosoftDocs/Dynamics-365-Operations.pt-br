---
title: Propor aquisições de ativo fixo
description: Este tópico descreve como adquirir um ativo fixo usando a proposta de aquisição no Diário de ativos fixos.
author: saraschi2
manager: AnnBe
ms.date: 07/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0997af638c141661afb677e2407a90a883168aed
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440206"
---
# <a name="propose-fixed-asset-acquisitions"></a>Propor aquisições de ativo fixo

[!include [banner](../../includes/banner.md)]

Este tópico descreve como adquirir um ativo fixo usando a proposta de aquisição no Diário de ativos fixos. Ela usa a função de contador e os dados de demonstração da entidade legal de USMF. Para adquirir um ativo fixo por meio de um diário de propostas de ativos fixos, é necessário criar o registro de ativo fixo e definir o preço de aquisição no registro de ativos.

1. No Painel de navegação, vá para **Módulos > Ativos fixos > Entradas de diário > Diário de ativos fixos**.
2. Selecione **Novo**.
3. No campo **Nome**, insira ou selecione um valor.
4. No painel de ações, selecione **Linhas**.
5. Selecione **Propostas**.
6. Selecione **Proposta de aquisição**.
7. Selecione **Filtro**. Selecione **Redefinir** para limpar valores anteriores.
8. Selecione a linha de **Número de ativo fixo**.
9. No campo **Critérios**, insira ou selecione um valor. Defina os critérios restantes para os ativos fixos que você deseja adquirir com esta proposta.  
10. Selecione **OK** duas vezes a sair do painel.
- Verifique as linhas de transação criadas.  
- Somente os ativos fixos com a data de aquisição e o preço de aquisição definidos no registro serão incluídos na proposta de aquisição.  
11. Na página, selecione a guia **Registros**.
12. Selecione **Lançar**.
