---
title: Configurar mestres de taxa
description: Este procedimento mostra como configurar um mestre de taxa.
author: Weijiesa
ms.date: 10/16/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSBreakMaster,TMSRateMaster,TMSRateMasterBase,TMSRateBaseType, TMSRouteWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: weijiesa
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6e707d226894c3cd647094556bfcc017347cb7f6
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675505"
---
# <a name="set-up-rate-masters"></a>Configurar mestres de taxa

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como configurar um mestre de taxa. O gerente logístico geralmente configura os mestres de taxa, dependendo dos contratos assinados com as transportadoras. Neste cenário você irá configurar um mestre de taxa para um transportador aérea. A empresa de dados demo usada para criar este procedimento é USMF.

## <a name="set-up-break-master"></a>Configurar mestre de interrupção

1. Acesse **Gerenciamento de transporte > Configurar > Classificação > Mestre de quebra**. Mestres de interrupção são usados para definir a estrutura de definição de preços e seus pontos de interrupção. A estrutura de definição de preços usa definição de preços hierarquizada baseada em dimensões físicas.  
1. Selecione **Novo**.
1. No campo **Mestre de quebra**, insira um valor.
1. No campo **Nome**, insira um valor.
1. No campo **Tipo de dados**, selecione o tipo de dados.
1. No campo **Comparação**, insira o tipo de comparação solicitada (usando operadores).
1. No campo **Quebrar unidade**, insira os valores da unidade de interrupção.
1. Na seção **Detalhes**, crie quantas quebras forem necessárias para a estrutura de preços.
1. Selecione **Salvar**.

## <a name="set-up-rate-master"></a>Configurar mestre de taxa

1. Acesse **Gerenciamento de transporte > Configurar > Classificação > Mestre de taxa**.
1. Selecione **Novo**.
1. No campo **Mestre de taxa**, digite um valor.
1. No campo **Nome**, digite um valor.
1. No campo **ID de metadados de classificação**, selecione o botão suspenso para abrir a pesquisa. A ID de metadados de classificação determinará os dados necessários para o mestre de taxa, uma vez que ela define os metadados esperados pelo mecanismo de gerenciamento de transporte usando esse mestre de taxa.  
1. Para este exemplo, selecione a opção P2P. Isso já está definido nos dados de demonstração.
1. Na lista, selecione o link na linha selecionada.
1. Selecione **Salvar**.

## <a name="set-up-rate-base"></a>Configurar base da taxa

1. Selecione **Base de taxa**.
    * A base da taxa determina a taxa da transportadora, e pode ser usada para configurar uma estrutura de tarifa uma vez que ela estrutura as taxas nos pontos de interrupção definidos pelo mestre de interrupção.  
2. Selecione **Novo**.
3. No campo **Base de taxa**, digite um valor.
4. No campo **Nome**, digite um valor.
5. No campo **Mestre de interrupção**, selecione o botão suspenso para abrir a pesquisa.
    * Mestres de interrupção são usados para definir a estrutura de definição de preços e seus pontos de interrupção. A estrutura de definição de preços usa definição de preços hierarquizada baseada em dimensões físicas.  
6. Neste exemplo, use peso. Isso já está definido nos dados de demonstração.
7. Na lista, selecione o link na linha destacada.
8. Expanda a seção **Detalhes**.
9. Selecione **Novo**.
10. No campo **CEP de entrega De**, digite "30301".
11. No campo **CEP de entrega Até**, digite "30318".
12. No campo **Região do país de entrega**, digite "USA".
13. No campo **<1,00 Lbs**, digite "100".
    * Insira a taxa por libras se o peso total da carga for menor que 1 libra.  
14. No campo **<5,00 Lbs**, digite "300".
    * Insira a taxa por libras se o peso total da carga for menor que 5 libras.  
15. No campo **<20,00 Lbs**, digite "500".
    * Insira a taxa por libras se o peso total da carga for menor que 20 libras.  
16. No campo **<100,00 Lbs**, digite "1000".
    * Insira a taxa por libras se o peso total da carga for menor que 100 libras.  
17. No campo **<1.000,00 Lbs**, digite "3000".
    * Insira a taxa por libras se o peso total da carga for menor que 1000 libras.  
18. Selecione **Salvar**.
19. Feche a página.

## <a name="assign-rate-base"></a>Atribua base de taxa

1. Expanda a seção **Atribuições base de taxa**.
2. Selecione **Novo**.
    * Você pode ter diversas atribuições de base da taxa para cada mestre de taxa. Isso possibilita criar vários pontos de preço para cada transportadora de acordo com os destinos, serviços ou diferentes bases da taxa. Neste procedimento você irá criar somente uma atribuição de base da taxa.  
3. No campo **Nome**, digite um valor.
4. No campo **Base da taxa**, selecione o botão suspenso para abrir a pesquisa.
5. Na lista, selecione o link na linha destacada.
6. No campo **Serviço**, selecione o botão suspenso para abrir a pesquisa.
7. Na lista, localize e selecione o registro desejado.
8. Na lista, selecione o link na linha destacada.
9. No campo **CEP de retirada**, digite "98052".
    * Especifique de qual CEP essa atribuição da base da taxa deverá ser válida.
10. No campo **Região do país de retirada**, digite "USA".
11. Selecione **Salvar**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]