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
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d6e0833eed3a423938ecc76957d18cccad2ca9b0
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686957"
---
# <a name="loan-item-to-a-worker"></a>Item de empréstimo para um funcionário


[!INCLUDE [PEAP](../includes/peap-1.md)]

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
