---
title: Identificar uma hipótese e determinar as métricas para um experimento
description: Este tópico descreve como identificar a hipótese e métricas de sucesso para um experimento que será executado em um site de comércio eletrônico no Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 99642861d69b7545f03c6ed2c2650eadeb377534
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930138"
---
# <a name="identify-a-hypothesis-and-determine-success-metrics-for-an-experiment"></a>Identificar uma hipótese e determinar as métricas de sucesso para um experimento
A primeira fase no ciclo de vida de experimentação inclui a identificação da hipótese de fazer experimentos e determinar as métricas que você rastreará para avaliar o êxito. O diagrama a seguir mostra todas as etapas envolvidas na [configuração e na execução de um experimento](experimentation-overview.md) em um site de comércio eletrônico no Dynamics 365 Commerce. Etapas adicionais são abordadas em tópicos separados. 

[ ![Usuário de teste de experimentação - identificar](./media/experimentation_identify.svg) ](./media/experimentation_identify.svg#lightbox)

Uma hipótese é um instrução na qual você prevê o resultado do experimento. Muitos fatores vão para a definição de uma hipótese, por exemplo, pesquisar sobre comportamento do usuário e dados de sites que você coletou. Com a hipótese, você definirá a suposição ou teoria que deseja validar com seu experimento. Um exemplo de uma hipótese de seu experimento pode ser "*uma imagem de uma camiseta branca na minha página inicial vai impulsionar uma taxa de clickthrough maior do que um suéter azul-marinho durante os meses de verão, pois as pessoas desejam usar algo leve e claro no verão.*" Nesse caso, você criará variações que incluem uma camiseta branca e um suéter azul-marinho e publicará ambas ao mesmo tempo.

Para validar uma hipótese, o êxito ou a falha de um experimento deve estar diretamente ligado às ações do usuário; por exemplo, se o usuário do site clicar em um link ou botão. Essas ações devem corresponder a eventos que serão informados ao serviço de terceiros que rastreia o experimento. Com o tempo, a porcentagem de usuários que executam a ação será registrada como uma métrica que pode ser usada para gerar relatórios e realizar análises. Consulte o tópico [Eventos do componente do Commerce para diagnóstico e solução de problemas](dev-itpro/retail-component-events-diagnostics-troubleshooting.md) para analisar todos os eventos e atributos disponíveis.

## <a name="previous-step"></a>Etapa anterior
[Experimentação no Dynamics 365 Commerce](experimentation-overview.md)


## <a name="next-step"></a>Próxima etapa
[Configurar um experimento](experimentation-setup.md)
