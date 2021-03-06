---
title: Lançar em diário entradas de diário
description: Este procedimento aborda como lançar em diário entradas de diário postadas.
author: aprilolson
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5028db1db2359a54d565fc299c9a3353a4cf8297
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826145"
---
# <a name="journalize-posted-journal-entries"></a>Lançar em diário entradas de diário

[!include [banner](../../includes/banner.md)]

Este procedimento aborda como lançar em diário entradas de diário postadas. Este procedimento usa a empresa de dados de demonstração USMF.

1. No **painel de Navegação**, vá para **Módulos > Contabilidade > Configuração do razão > parâmetros de Contabilidade**.
2. O campo **Diário-razão estendido** pode ser definido como Sim ou Não. Se Sim, as versões de relatório serão diferentes.
3. Selecione se o período pode ser inserido se o processo se lançando em diário não foi executado. Se esta opção é definida em Sim, o período não poderá ser fechado até o processo se lançando em diário foi preenchido para o período.  
4. Feche a página.
5. No **painel de Navegação**, vá para **Módulos > Contabilidade > Tarefas periódicas > Lançamento em diário**.
6. Clique em **Filtrar**.
7. Realce a linha com os critérios do filtro que você deseja definir.
8. No campo **Critérios**, informe ou selecione os critérios do filtro.
9. Clique em **OK** para fechar a página de filtro.
10. Clique em **OK** para iniciar o processo de lançamento em diário. Um relatório será gerado depois que o processo foi concluído.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]