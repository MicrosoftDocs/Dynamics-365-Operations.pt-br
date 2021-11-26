---
title: Item de empréstimo para um funcionário
description: Este procedimento mostra como emprestar um item a um funcionário e registrar o funcionário que retorna um item.
author: twheeloc
ms.date: 11/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPersonLoan, HcmPersonLookup, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b60439f5f7bb5509423219606d7b9bb2cf3c28a6
ms.sourcegitcommit: 7e0e2a266d9a9473df72e207554d9bd150e17ce3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2021
ms.locfileid: "7771305"
---
# <a name="loan-item-to-a-worker"></a>Item de empréstimo para um funcionário

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Este procedimento mostra como emprestar um item a um trabalhador e registrar a devolução de um item que um trabalhador pegou emprestado. Os operadores também podem solicitar itens de empréstimo por meio da página **Autoatendimento para funcionários**. A empresa de dados de demonstração **USMF** foi usada para criar este procedimento.


## <a name="loan-an-item-to-a-worker"></a>Emprestar um item a um trabalhador

1. Acesse **Recursos humanos \> Trabalhadores \> Itens de empréstimo \> Equipamento emprestado**.
2. Selecione **Novo**.
3. No campo **Pessoa**, insira ou selecione um valor.
4. No campo **Item de empréstimo**, insira ou selecione um valor.
5. No campo **Devolução planejada**, insira a data em que o funcionário deverá devolver o item emprestado.
6. Selecione **Salvar**.
7. Feche a página.

## <a name="return-a-loan-item"></a>Devolver um item emprestado

1. Acesse **Recursos humanos \> Trabalhadores \> Itens de empréstimo \> Equipamento emprestado**.
2. Selecione **Editar**.
3. No campo **Devolução real**, insira uma data.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
