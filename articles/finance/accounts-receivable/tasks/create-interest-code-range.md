---
title: Criar um código de juros com um intervalo
description: Os códigos de juros podem ser configurados para calcular os valores diferentes de juros com base em um intervalo de valores.
author: ShivamPandey-msft
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Interest, CustInterestRange
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b20870ade99dd48e72c8aa63f563bc51dc93bd9601d309c474af93cee6eddedb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6771839"
---
# <a name="create-an-interest-code-with-a-range"></a>Criar um código de juros com um intervalo

[!include [banner](../../includes/banner.md)]
Os códigos de juros podem ser configurados para calcular os valores diferentes de juros com base em um intervalo de valores. Este procedimento mostrará como adicionar um código de juros e adicionar um intervalo a ele.

1. Acesse Crédito e cobranças > Juros > Configurar códigos de juros.
2. Clique em Novo.
3. No campo Código de juros, insira o nome do código de juros.
4. No campo Descrição, insira uma descrição para o código de juros.
5. Selecione Mês.
6. Expandir a seção Ganhos.
7. Expanda a seção Ganhos pela moeda.
8. No campo Conta de lançamento contábil, especifique os valores desejados.
9. No campo Juros por intervalo, selecione 'Meses'.
10. Clique em Adicionar.
11. No campo Descrição, insira uma descrição para esta moeda e intervalo.
12. Clique em Salvar.
13. Clique em Intervalos.
14. Clique em Novo.
15. Insira o valor De como 0 e insira a porcentagem de juros para o mês que será usado para calcular os juros. Para nosso exemplo, será 1,5.
16. Clique em Novo.
17. Insira o próximo valor De como 4, que é o primeiro mês que você estará calculando um novo valor de juros.
18. Insira a porcentagem de juros por mês que será usada para calcular os juros a partir do mês 4. Para este exemplo, será 2,0.
19. Clique em Novo.
20. Insira o próximo valor De como 7, que é o próximo mês que você estará calculando um novo valor de juros.
21. Insira a porcentagem de juros por mês que será usada para calcular os juros a partir do mês 7. Para este exemplo, será 2,5.
22. Clique em Fechar para finalizar a configuração.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]