---
title: Configurar mestres de taxa
description: Este procedimento mostra como configurar um mestre de taxa.
author: ShylaThompson
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 462bfce89fa77c8830a93a22b0dd6c8c8fb2cde6
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "344906"
---
# <a name="set-up-rate-masters"></a>Configurar mestres de taxa

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como configurar um mestre de taxa. O gerente logístico geralmente configura os mestres de taxa, dependendo dos contratos assinados com as transportadoras. Neste cenário você irá configurar um mestre de taxa para um transportador aérea. A empresa de dados demo usada para criar este procedimento é USMF.


## <a name="set-up-rate-master"></a>Configurar mestre de taxa
1. Vá para Gerenciamento de transporte > Configurar > Classificação > Mestre de taxa.
2. Clique em Novo.
3. No campo Mestre de taxa, digite um valor.
4. No campo Nome, digite um valor.
5. No campo ID de metadados de classificação, clique no botão suspenso para abrir a pesquisa.
    * A ID de metadados de classificação irá determinar os dados necessários para o mestre de taxa, uma vez que ela define os metadados esperados pelo mecanismo TMS usando esse mestre de taxa.  
6. Para este exemplo, selecione a opção P2P.
7. Na lista, clique no link na linha selecionada.
8. Clique em Salvar.

## <a name="set-up-rate-base"></a>Configurar base da taxa
1. Clique em Base de taxa.
    * A base da taxa determina a taxa da transportadora, e pode ser usada para configurar uma estrutura de tarifa uma vez que ela estrutura as taxas nos pontos de interrupção definidos pelo mestre de interrupção.  
2. Clique em Novo.
3. No campo Base de taxa, digite um valor.
4. No campo Nome, digite um valor.
5. No campo Mestre de interrupção, clique no botão suspenso para abrir a pesquisa.
    * Mestres de interrupção são usados para definir a estrutura de definição de preços e seus pontos de interrupção. A estrutura de definição de preços usa definição de preços hierarquizada baseada em dimensões físicas.  
6. Neste exemplo, use peso
7. Na lista, clique no link na linha selecionada.
8. Ative a expansão da seção Detalhes.
9. Clique em Novo.
10. No campo CEP de entrega De, digite '30301'.
11. No campo CEP de entrega Até, digite '30318'.
12. No campo Região do país de entrega, digite 'USA'.
13. No campo <1,00 Lbs, digite '100'.
    * Insira a taxa por libras se o peso total da carga for menor que 1 libra.  
14. No campo <5,00 lbs, digite '300'.
    * Insira a taxa por libras se o peso total da carga for menor que 5 libras.  
15. No campo <20,00 lbs, digite '500'.
    * Insira a taxa por libras se o peso total da carga for menor que 20 libras.  
16. No campo <100,00 lbs, digite '1000'.
    * Insira a taxa por libras se o peso total da carga for menor que 100 libras.  
17. No campo <1.000,00 lbs, digite '3000'.
    * Insira a taxa por libras se o peso total da carga for menor que 1000 libras.  
18. Clique em Salvar.
19. Feche a página.

## <a name="assign-rate-base"></a>Atribua base de taxa
1. Ative a expansão da seção Atribuições da base da taxa.
2. Clique em Novo.
    * Você pode ter diversas atribuições de base da taxa para cada mestre de taxa. Isso possibilita criar vários pontos de preço para cada transportadora de acordo com os destinos, serviços ou diferentes bases da taxa. Neste procedimento você irá criar somente uma atribuição de base da taxa.  
3. No campo Nome, digite um valor.
4. No campo Base da taxa, clique no botão suspenso para abrir a pesquisa.
5. Na lista, clique no link na linha selecionada.
6. No campo Serviço, clique no botão suspenso para abrir a pesquisa.
7. Na lista, localize e selecione o registro desejado.
8. Na lista, clique no link na linha selecionada.
9. No campo CEP de retirada, digite '98052'.
    * Especifique de qual CEP essa atribuição da base da taxa deverá ser válida.    
10. No campo Região do país de retirada, digite 'USA'.
11. Clique em Salvar.

