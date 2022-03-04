---
title: Criar um código de juros com um intervalo
description: Os códigos de juros podem ser configurados para calcular os valores diferentes de juros com base em um intervalo de valores.
author: ShivamPandey-msft
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Interest, CustInterestRange
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d77fc88f606f4e690583fbcda79f628a35f14f6a
ms.sourcegitcommit: 6a269db08e8bb3bb3405c9f4a512091d13c80faa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2022
ms.locfileid: "8119465"
---
# <a name="create-an-interest-code-with-a-range"></a>Criar um código de juros com um intervalo

[!include [banner](../../includes/banner.md)]
Os códigos de juros podem ser configurados para calcular os valores diferentes de juros com base em um intervalo de valores. Este procedimento mostrará como adicionar um código de juros e adicionar um intervalo a ele.

1. Acesse **Crédito e cobranças > Juros > Configurar códigos de juros**.
2. Clique em **Novo**.
3. No campo **Código de juros**, insira o nome do código de juros.
4. No campo **Descrição**, insira uma descrição para o código de juros.
5. Selecione **Mês**.
6. Expanda a seção **Ganhos**.
7. Expanda a seção **Ganhos pela moeda**.
8. No campo **Conta de lançamento contábil**, especifique os valores desejados.
9. No campo **Juros por intervalo**, selecione 'Meses'.
10. Clique em **Adicionar**.
11. No campo **Descrição**, insira uma descrição para essa moeda e o intervalo.
12. Clique em **Salvar**.
13. Clique em **Intervalos**.
14. Clique em **Novo**.
15. Insira o **Valor inicial** como 0 e, depois, a porcentagem de juros por mês que será usada para calcular os juros. Para nosso exemplo, será 1,5.
16. Clique em **Novo**.
17. Insira o próximo valor De como 4, que é o primeiro mês que você estará calculando um novo valor de juros.
18. Insira a porcentagem de juros por mês que será usada para calcular os juros a partir do mês 4. Para este exemplo, será 2,0.
19. Clique em **Novo**.
20. Insira o próximo valor De como 7, que é o próximo mês que você estará calculando um novo valor de juros.
21. Insira a porcentagem de juros por mês que será usada para calcular os juros a partir do mês 7. Para este exemplo, será 2,5.
22. Clique em **Fechar** para finalizar a configuração.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
