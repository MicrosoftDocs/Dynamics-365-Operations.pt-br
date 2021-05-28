---
title: Erro quando o diário Relatar como finalizado é postado
description: Quando posta o diário Relatar como finalizado, você recebe uma mensagem de erro que afirma que a quantidade pedido não pode ser reduzida.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTableListPage, ProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 55db7d0033dd66c1b973abf96671a20ab05d61d8
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026258"
---
# <a name="error-when-the-report-as-finished-journal-is-posted"></a><span data-ttu-id="19c98-103">Erro quando o diário Relatar como finalizado é postado</span><span class="sxs-lookup"><span data-stu-id="19c98-103">Error when the Report as finished journal is posted</span></span>

<span data-ttu-id="19c98-104">Número da base de dados de conhecimento: 4612891</span><span class="sxs-lookup"><span data-stu-id="19c98-104">KB number: 4612891</span></span>

## <a name="symptoms"></a><span data-ttu-id="19c98-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="19c98-105">Symptoms</span></span>

<span data-ttu-id="19c98-106">Quando posta o diário **Relatar como finalizado**, um erro ocorre e você recebe a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="19c98-106">When you post the **Report as finished** journal, an error occurs, and you receive the following error message:</span></span>

> <span data-ttu-id="19c98-107">A quantidade encomendada não pode ser reduzida porque não há transações de estoque em aberto suficientes com status 'Encomendado'.</span><span class="sxs-lookup"><span data-stu-id="19c98-107">Quantity ordered cannot be reduced because there are not enough open inventory transactions with the ordered status.</span></span> <span data-ttu-id="19c98-108">Os itens são Comprados, Recebidos ou Registrados.</span><span class="sxs-lookup"><span data-stu-id="19c98-108">The items are Purchased, Received or Registered.</span></span>

<span data-ttu-id="19c98-109">Este erro ocorre somente quando o campo **Quantidade incorreta** estiver definido na primeira linha do diário **Relatar como finalizado** e o campo **Quantidade correta** estiver definido na última linha.</span><span class="sxs-lookup"><span data-stu-id="19c98-109">This error occurs only when the **Error quantity** field is set on the first line of the **Report as finished** journal, and the **Good quantity** field is set on the last line.</span></span> <span data-ttu-id="19c98-110">Se o campo **Quantidade incorreta** estiver definido na última linha, nenhum erro ocorre.</span><span class="sxs-lookup"><span data-stu-id="19c98-110">If the **Error quantity** field is set on the last line, no error occurs.</span></span>

## <a name="resolution"></a><span data-ttu-id="19c98-111">Resolução</span><span class="sxs-lookup"><span data-stu-id="19c98-111">Resolution</span></span>

<span data-ttu-id="19c98-112">Para evitar esse erro, abra a página **Parâmetros de controle de produção** e, na guia **Geral**, defina a opção **Aumentar qtde restante com qtde incorreta** como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="19c98-112">To prevent this error, open the **Production control parameters** page, and then, on the **General** tab, set the **Increase remain qty with error qty** option to *Yes*.</span></span>
